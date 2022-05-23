---
title: Hello World
parent: Getting Started
has_children: false
nav_order: 1
---

# Hello World Example

This is the Hello World tutorial...

DEMO: [https://wallabyway.github.io/tandem-api-hello-world/](https://wallabyway.github.io/tandem-api-hello-world/)

REPO: [https://github.com/wallabyway/tandem-api-hello-world/](https://github.com/wallabyway/tandem-api-hello-world/)

![settings](../img/helloworld.gif)


#### Create an index.html with the following code:

```html
<header>
    <link href="https://tandem.autodesk.com/viewer/style.min.css" rel="stylesheet" type="text/css">
    <link href="https://tandem.autodesk.com/client/index-ELLCBQ7R.css" rel="stylesheet" type="text/css">
    <style>
        .button:hover {background-color:rgb(90,90,90);}
        .nav img:hover {border:2px solid lightgray; transform:translateY(-2px);}
        body { font-family: ArtifaktElement; font-size:14px; font-weight:600; -webkit-font-smoothing: antialiased; margin: 0; padding: 0; overflow: hidden;}
        .nav ul { background-color: rgb(55,55,55); list-style-type: none; margin: 0; padding: 5px; position: fixed; top: 0; width: 100%; z-index: 10}
        .nav li a { color: white; text-decoration: none; }
        .nav li img { height: 38px; border-radius: 50%; line-height:35px }
        .nav li { float: right;  display: block; padding: 5px; height: 40px; line-height: 40px; }
        .nav .left { float: left }
        .button { margin: 4px; padding: 0 10px 0 10px !important; border: 2px solid white; border-radius: 10px;  }
        #viewer { width:100%;  height:calc(100% - 65px); position:fixed; top:65px }
        #combo { margin:1px; height: calc(2.25rem + 2px); border-radius: 10px;padding: 5px;}
    </style>
</header>

<body>
<div class="nav"><ul> 
    <!-- Nav ToolBar -->
    <li class="left"><img title = "Your Logo Here" src="https://thumbs.dreamstime.com/t/hand-drawn-headquarters-doodle-sketch-style-icon-military-decoration-element-isolated-white-background-flat-design-vector-141216432.jpg"/></li>
    <li class="left"><a href="https://intandem.autodesk.com">Hello World </a></li>
    <li class="left"><select id="combo" style="font-family:ArtifaktElement"></select></li>
    <li><a href="https://github.com/wallabyway/tandem-api-hello-world/"><img style="height:25px; padding:10px" src="https://github.githubassets.com/favicons/favicon-dark.png"/></a></li>
    <li><a href="#" id="userprofile"></a></li>
    <li class="button"><a href="#" id="loginout">Login</a></li>
</ul>
</div>
<div id="viewer"></div>
</body>

<script src="https://tandem.autodesk.com/viewer/viewer3D.min.js"></script>

<script type="module">
const $ = (id) => {return document.getElementById(id)};
const show = (id) => { $(id).style.display="block"};
const hide = (id) => { $(id).style.display="none"};


// handle login user interface

class loginUI {
    constructor( forgeClientID ) {
        this.clientID = forgeClientID;
        this.scope = "data:read";
        this.redirect_uri = encodeURIComponent(location.href.split('#')[0]);

        this.facComboBox = $('combo');
        this.facComboBox.addEventListener("change", (e) => {this.onComboBoxChange(e)});
        $('loginout').addEventListener(   "click",  (e) => {this.onLogin(e)});
        $('userprofile').addEventListener("click",  (e) => { location.href="https://accounts.autodesk.com/users/@me/view" });

        this.updateToken();
        this.renderUI();
    }

    updateToken() {
        if (location.hash.length > 2) {
            const params = location.hash.slice(1).split('&').map(i=>{ return i.split('=')  });
            if (params && params[0][0]=="access_token") 
                window.sessionStorage.token = params[0][1];
        }
        this.token = window.sessionStorage.token;
    }

    onLogin() {
        if (!this.token)
            location.href = `https://developer.api.autodesk.com/authentication/v1/authorize?response_type=token&client_id=${this.clientID}&redirect_uri=${this.redirect_uri}&scope=${encodeURIComponent(this.scope)}`;
        else {
            this.logout();
        }
    }

    logout() {
        delete(window.sessionStorage.token);
        location.reload();
    };

    async renderUI() {
        $("loginout").text = (this.token) ? "Logout" : "Login";
        if (this.token) {
            await this.setProfileImage('userprofile');
            location.hash="";
            this.tviewer = await new tandemViewer($("viewer"));
            this.renderFacilitiesList(this.facComboBox);
        } else
            hide("userprofile");
    }

    async renderFacilitiesList(div) {
        this.allFacilities = await this.tviewer.fetchFacilities();
        this.allFacilities.map ( item => {
            const i = document.createElement('option');
            const id = item.settings.props["Identity Data"];
            i.text = `${id["Building Name"]} : ${id["Project Name"]} / ${id.Owner}`
            i.selected = item;
            div.add(i);
        });
        this.facComboBox.selectedIndex = window.sessionStorage.selectedIndex || 0;
        this.onComboBoxChange();
    }

    async onComboBoxChange() {
        window.sessionStorage.selectedIndex = this.facComboBox.selectedIndex;
        const fac = this.allFacilities[this.facComboBox.selectedIndex];
        this.tviewer.openFacility(fac);
    }


    async setProfileImage(div) {
        const res = await fetch( 'https://developer.api.autodesk.com/userprofile/v1/users/@me', {
            headers : { "Authorization":`Bearer ${this.token}`}
        });
        this.user = await res.json();
        $(div).innerHTML=`<li><img src="${this.user.profileImages.sizeX40}" title="${this.user.firstName} ${this.user.lastName}"/></li>`
    }
}



const av = Autodesk.Viewing;


// initialize Tandem Viewer and load different facilities

class tandemViewer {

    constructor(div) {
    return new Promise(resolve=>{

        const options = {
            env: "DtProduction",
            api: 'dt',
            productId: 'Digital Twins',
            corsWorker: true,
            config3d: {
              extensions: ['Autodesk.BoxSelection'],
              screenModeDelegate: av.NullScreenModeDelegate,
            }
        };
        av.Initializer(options, () => {
            this.viewer = new av.GuiViewer3D(div, {
                extensions: ['Autodesk.BoxSelection'],
                screenModeDelegate: av.NullScreenModeDelegate,
                theme: 'light-theme',
            });
            this.viewer.start();
            av.endpoint.HTTP_REQUEST_HEADERS['Authorization'] = 'Bearer ' + window.sessionStorage.token;
            this.app = new av.Private.DtApp({});
            window.DT_APP = this.app;
            resolve(this);
        });
    })}

    async fetchFacilities(URN) {
        const FacilitiesSharedWithMe = await this.app.getCurrentTeamsFacilities();
        const myFacilities = await this.app.getUsersFacilities();
        return [].concat(FacilitiesSharedWithMe, myFacilities);
    }

    async openFacility(facility) {
        this.app.displayFacility(facility, false, this.viewer);
    }    
}

const FORGE_CLIENT_ID = "rZboPCXwdKnmxeByCWbX7Fz1YGmIjGja"
const _login = new loginUI( FORGE_CLIENT_ID );

</script>

```

# Edit the index.html file

Change the `forge_clientID` to your own Forge Key Client ID

```code
        const forge_clientID = "rZboPCXwdKnmxeByCWbX7Fz1YGmIjGja";
```

# Testing it locally


From a command line, type: 

```
python3 -m http.server
```

( make sure you have python installed )

and open your browser to `http://localhost:8000/`

Click the 'Login' button, top right, and login.
