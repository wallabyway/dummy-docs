---
title: Hello World
parent: Getting Started
has_children: false
nav_order: 1
---

# Hello World Example

This is the Hello World tutorial...

```html
<header>
    <link href="https://tandem.autodesk.com/viewer/style.min.css" rel="stylesheet" type="text/css">
    <script src="https://tandem.autodesk.com/viewer/viewer3D.min.js"></script>

    <style>
        body { font-family: helvetica;sans-serif; margin: 0; padding: 0; overflow: hidden;}
        .nav ul { background-color: rgba(20,30,70,0.5); list-style-type: none; margin: 0; padding: 5px; position: fixed; top: 0; width: 100%; }
        .nav li a { color: white; text-decoration: none; }
        .nav li img { height: 38px; border-radius: 50%; padding:2px}
        .nav li { float: right;  display: block; padding: 0 8px 0 5px; height: 40px; line-height: 40px; }
        .nav .nleft { float: left }
    </style>
</header>

<body>
<div class="nav"><ul>
    <li class="nleft"><img src="https://thumbs.dreamstime.com/t/hand-drawn-headquarters-doodle-sketch-style-icon-military-decoration-element-isolated-white-background-flat-design-vector-141216432.jpg"/></li>
    <li class="nleft"><a href="https://intandem.autodesk.com">Hello World Demo</a></li>
    <li><a href="#" id="userprofile">Logout</a></li>
    <li><a href="#" id="autodeskSigninButton">Login</a></li>
    <li><a href="http://github.com/wallabyway"><img style="" src="https://www.iconpacks.net/icons/3/free-github-logo-icon-6531.png"/></a></li>
</ul>
</div>
<div id="viewer" style="height: 99.7%; width: 100%;"></div>
</body>

<script type="module">
const $ = (id) => {return document.getElementById(id)};
const show = (id) => { $(id).style.display="block"};
const hide = (id) => { $(id).style.display="none"};

checkLogin();
$('autodeskSigninButton').addEventListener("click", login);
$('userprofile').addEventListener("click", logout);

    function login() {
        const forge_clientID = "rZboPCXwdKnmxeByCWbX7Fz1YGmIjGja";
        doRedirection(forge_clientID, "data:read");
    }

    function logout() {
        delete(window.sessionStorage.token);
        location.reload();
    };

    function checkLogin() {
        if (!!location.hash) 
            setTokenStorage();

        if (window.sessionStorage.token) {
            hide("autodeskSigninButton");
            show("userprofile");
            loadUserToDIVimage('userprofile');
            location.hash="";
            return;
        }
        hide("userprofile");
    }

    function doRedirection(forge_clientID, scope) {
        const redirect_uri = encodeURIComponent(location.href.split('#')[0]);
        location.href = `https://developer.api.autodesk.com/authentication/v1/authorize?response_type=token&client_id=${forge_clientID}&redirect_uri=${redirect_uri}&scope=${encodeURIComponent(scope)}`;
    }

    function setTokenStorage() {
        const params = location.hash.slice(1).split('&').map(i=>{
            return i.split('=') });
        if (params[0][0]=="access_token") 
            window.sessionStorage.token = params[0][1];
    }

    async function loadUserToDIVimage(div) {
        const res = await fetch( 'https://developer.api.autodesk.com/userprofile/v1/users/@me', {
            headers : { "Authorization":`Bearer ${window.sessionStorage.token}`}
        });
        const user = await res.json();
        $(div).innerHTML=`${user.firstName} ${user.lastName}</li><li><img src="${user.profileImages.sizeX40}"/></li>`
    }


</script>

```

# Edit the index.html file

# Testing it locally


From a command line, type: 

```
python3 -m http.server
```

( make sure you have python installed )
