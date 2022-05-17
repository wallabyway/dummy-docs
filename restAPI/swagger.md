
# Autodesk Tandem Model Service (BETA)

Autodesk Tandem Model Service API (BETA)

This is the REST API for the Tandem model service. It gives you access to the Tandem database for Facilities created through the Tandem product.

*Autodesk Tandem API is currently released under a beta program and subject to Autodesk Tandem API Public Beta Program Terms. To learn more, please go to Tandem API page at Autodesk Feedback Community:* [Tandem Feedback Community](https://feedback.autodesk.com/project/home.html?cap=0951fbaea16047758976fdb0db4d4502)

For notes on how to use this Postman collection interactively, please visit: [https://autodesk-tandem.github.io/API_postman.html](https://autodesk-tandem.github.io/API_postman.html)

For an overview and links to sample source code and detailed notes, please visit: [https://autodesk-tandem.github.io](https://autodesk-tandem.github.io)

Contact Support:  
Name: Tandem development team  
Email: [tandem-support@autodesk.com](mailto:tandem-support@autodesk.com)

Slack (internal Autodesk only): #tandem-api

<!--- If we have only one group/collection, then no need for the "ungrouped" heading -->


## Variables

| Key | Value | Type |
| --- | ------|-------------|
| baseUrl | //tandem-stg.autodesk.com/api/v1 | string |



## Endpoints

* [groups](#groups)
    1. [{group ID}](#1-group-id)
    1. [/groups](#2-groups)
        * [OK](#i-example-request-ok)
* [modeldata/{model ID}](#modeldatamodel-id)
    1. [scan](#1-scan)
    1. [/modeldata/:modelID/aecmodeldata](#2-modeldatamodelidaecmodeldata)
        * [OK](#i-example-request-ok-1)
    1. [/modeldata/:modelID/attrs](#3-modeldatamodelidattrs)
        * [OK](#i-example-request-ok-2)
    1. [/modeldata/:modelID/fragments](#4-modeldatamodelidfragments)
        * [OK](#i-example-request-ok-3)
    1. [/modeldata/:modelID/history](#5-modeldatamodelidhistory)
        * [OK - 30 days, includeChanges=true](#i-example-request-ok---30-days-includechangestrue)
        * [OK - 30 days, includeChanges=false](#ii-example-request-ok---30-days-includechangesfalse)
        * [OK - with specific timestamps](#iii-example-request-ok---with-specific-timestamps)
    1. [/modeldata/:modelID/model](#6-modeldatamodelidmodel)
        * [OK](#i-example-request-ok-4)
    1. [/modeldata/:modelID/mutate](#7-modeldatamodelidmutate)
        * [OK - Update "Common | Name" property to new value](#i-example-request-ok---update-common--name-property-to-new-value)
        * [OK - Update user-defined property to new value](#ii-example-request-ok---update-user-defined-property-to-new-value)
        * [OK - Update single property, multiple elements](#iii-example-request-ok---update-single-property-multiple-elements)
        * [OK - Update different properties, different elements](#iv-example-request-ok---update-different-properties-different-elements)
        * [OK - Delete a property from a given element](#v-example-request-ok---delete-a-property-from-a-given-element)
        * [OK - Add Classification to an element](#vi-example-request-ok---add-classification-to-an-element)
        * [OK - Update multiple properties, same element](#vii-example-request-ok---update-multiple-properties-same-element)
        * [OK - Delete multiple properties, same entity](#viii-example-request-ok---delete-multiple-properties-same-entity)
    1. [/modeldata/:modelID/props/:elementID](#8-modeldatamodelidpropselementid)
        * [OK](#i-example-request-ok-5)
    1. [/modeldata/:modelID/schema](#9-modeldatamodelidschema)
        * [OK](#i-example-request-ok-6)
* [models/{model ID}](#modelsmodel-id)
    1. [streams/{element ID}](#1-streamselement-id)
    1. [/models/:modelID/props](#2-modelsmodelidprops)
        * [OK](#i-example-request-ok-7)
* [twins/{twin ID}](#twinstwin-id)
    1. [classification (DEPRECATED/LEGACY)](#1-classification-deprecatedlegacy)
    1. [documents](#2-documents)
    1. [model](#3-model)
    1. [psets (DEPRECATED/LEGACY)](#4-psets-deprecatedlegacy)
    1. [template](#5-template)
    1. [thumbnail](#6-thumbnail)
    1. [users/{user ID}](#7-usersuser-id)
    1. [/twins/:twinID](#8-twinstwinid)
        * [OK (204 - No Content)](#i-example-request-ok-204---no-content)
    1. [/twins/:twinID](#9-twinstwinid)
        * [OK](#i-example-request-ok-8)
    1. [/twins/:twinID](#10-twinstwinid)
    1. [/twins/:twinID](#11-twinstwinid)
    1. [/twins/:twinID/cleanup](#12-twinstwinidcleanup)
        * [OK](#i-example-request-ok-9)
    1. [/twins/:twinID/confirmupload](#13-twinstwinidconfirmupload)
    1. [/twins/:twinID/documentsbulk](#14-twinstwiniddocumentsbulk)
        * [OK - add PDF file from ACC Docs repository](#i-example-request-ok---add-pdf-file-from-acc-docs-repository)
    1. [/twins/:twinID/import](#15-twinstwinidimport)
    1. [/twins/:twinID/inlinetemplate](#16-twinstwinidinlinetemplate)
        * [OK](#i-example-request-ok-10)
    1. [/twins/:twinID/subjects](#17-twinstwinidsubjects)
        * [OK](#i-example-request-ok-11)
    1. [/twins/:twinID/uploadlink](#18-twinstwiniduploadlink)
* [Ungrouped](#ungrouped)
    1. [/users/:userID/twins](#1-usersuseridtwins)
        * [OK - userID](#i-example-request-ok---userid)
        * [OK - @me](#ii-example-request-ok---me)
    1. [/health](#2-health)
        * [OK - verbose=false](#i-example-request-ok---verbosefalse)
        * [OK - verbose=true](#ii-example-request-ok---verbosetrue)
    1. [/admin/modelscheck](#3-adminmodelscheck)

--------



## groups



### 1. {group ID}



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 2. /groups


Returns the groups (aka "Teams") that this user is a part of (based on the supplied user auth token).


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/groups
```



***More example Requests/Responses:***


#### I. Example Request: OK



***Body: None***



#### I. Example Response: OK
```js
[
    {
        "name": "James Awe's Account",
        "urn": "urn:adsk.dtg:iCGGqdNMS4-9o-iVOs86Tw",
        "owner": "Q7W5J5WV3AEJ",
        "accessLevel": "Owner",
        "twins": {
            "urn:adsk.dtt:39KVUhgmSQKdQjx3JxJFkA": "Owner",
            "urn:adsk.dtt:91XGFtvUR8aHe7e9t3RVmw": "Owner",
            "urn:adsk.dtt:Apj75MFWTweMBB-Gz8NVEw": "Owner",
            "urn:adsk.dtt:DG8d4c62TG203Ec6tKMgsg": "Owner",
            "urn:adsk.dtt:F8O1d_DOTn6C-F0emV-Cvw": "Owner",
            "urn:adsk.dtt:GC93w3XPSTihCVeil1Q3EQ": "Owner",
            "urn:adsk.dtt:JEJ0a1kzTseHJULYDycPdQ": "Owner",
            "urn:adsk.dtt:WtKv1jSXTYGCuZxXo9GCWw": "Owner",
            "urn:adsk.dtt:XnlWAxf2Ty62Ld5FUBnFjg": "Owner",
            "urn:adsk.dtt:b3VjbgWjTYSADxz8qBsS0w": "Owner",
            "urn:adsk.dtt:doSOmNYkRseic4UdNeWbGw": "Owner",
            "urn:adsk.dtt:enBQAJYtQtKCT49tj0vRfQ": "Owner",
            "urn:adsk.dtt:ipUl-oD1TbqehNMwo0_7Rw": "Owner",
            "urn:adsk.dtt:nf2UQERcQymNslcJXAFtTA": "Owner",
            "urn:adsk.dtt:qq1vdCkIS0C01e8dUKHBCg": "Owner",
            "urn:adsk.dtt:vziIqFg7Rva6ihCPkGR9wg": "Owner"
        },
        "accountSettings": {
            "type": "free",
            "assetLimit": 1000,
            "expiryDate": "2022-07-07T00:00:00Z",
            "createDate": "2020-07-27T18:55:21Z"
        }
    },
    {
        "name": "Autodesk - TK",
        "urn": "urn:adsk.dtg:607v8BKfQzWH_LnYYds-_A",
        "owner": "5BNWQTDL8LHM",
        "accessLevel": "ReadWrite",
        "twins": {
            "urn:adsk.dtt:0w6smFaqT8-WrnuZ6examw": "Owner",
            "urn:adsk.dtt:5knfogjuRqigCZtRff-70Q": "Owner",
            "urn:adsk.dtt:7QDiWpDcRBeZ31EDNrv9Cg": "Owner",
            "urn:adsk.dtt:GCoHm526QuGPdEhEo5nQVQ": "Owner",
            "urn:adsk.dtt:QmFHWoa1QwmWMVYhxXjQMA": "Owner",
            "urn:adsk.dtt:Sze-tR7ZRzm-rk4GEAYxGw": "Owner",
            "urn:adsk.dtt:U5kXa69WThe8xKc4p8ZiyA": "Owner",
            "urn:adsk.dtt:XQvgYbRyQdGxSfQp8_yy2g": "Owner",
            "urn:adsk.dtt:akMfz-NASeyfSEaByt_6jQ": "Owner",
            "urn:adsk.dtt:dfRNGbYpT0CPKseZOz8uSg": "Owner",
            "urn:adsk.dtt:keidAg96RYeUqDZTxufW3Q": "Owner",
            "urn:adsk.dtt:mriPHRa-QCu4NtBeigvjiQ": "Owner",
            "urn:adsk.dtt:nzP1Lgw5RneF3FP_o9TN5Q": "Owner",
            "urn:adsk.dtt:o23nAlYZSwC1XQyYTRhxjg": "Owner",
            "urn:adsk.dtt:qHqnudh5SnC3HlA-9aY7Fw": "Owner",
            "urn:adsk.dtt:qJkn5Lb2TCajlxpy850eTQ": "Owner",
            "urn:adsk.dtt:snFhpMynSjuNIl0yXdfbPw": "Owner",
            "urn:adsk.dtt:uc9_GS42ROyFmoWtB8tzCg": "Owner",
            "urn:adsk.dtt:w-yCDeK8SqaZDStMpQBhIA": "Owner",
            "urn:adsk.dtt:y2Q5Ad0uRgGb5L4uF2ffkA": "Owner",
            "urn:adsk.dtt:yMgZLmxbRG6IBVuic-ntEA": "Owner",
            "urn:adsk.dtt:zfOzlU4USNa97JkHMLhW6w": "Owner"
        },
        "accountSettings": {
            "type": "free",
            "assetLimit": 1000,
            "expiryDate": "2022-07-07T00:00:00Z",
            "createDate": "2020-08-06T14:27:29Z"
        }
    }
]
```


***Status Code:*** 200

<br>



## modeldata/{model ID}



### 1. scan



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 2. /modeldata/:modelID/aecmodeldata


Get an additional resource for the model - AECModelData.json. Contains various metadata, related to AEC model, such as levels


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/modeldata/:modelID/aecmodeldata
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model ID |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model ID |



***Body: None***



#### I. Example Response: OK
```js
{
    "documentId": "9b09524f-3ba4-476b-95ad-ed9646f413d6",
    "grids": [
        {
            "boundingBox": [
                -84.73934111132522,
                -70.42225465032544,
                -1,
                -84.73934111132522,
                76.83859074923794,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002453b",
            "label": "A",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002453b",
                    "points": {
                        "end": [
                            -84.73934111132522,
                            -70.42225465032544,
                            0
                        ],
                        "start": [
                            -84.73934111132522,
                            76.83859074923794,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -65.01101938016544,
                -26.29238728241836,
                -1,
                -65.01101938016544,
                76.7966495202354,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024581",
            "label": "B",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024581",
                    "points": {
                        "end": [
                            -65.01101938016544,
                            -26.29238728241836,
                            0
                        ],
                        "start": [
                            -65.01101938016544,
                            76.7966495202354,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -40.528696819833854,
                -71.21248091780433,
                -1,
                -39.25344566163268,
                76.83859074923805,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002458b",
            "label": "B2",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002458b",
                    "points": {
                        "end": [
                            -39.253445661632675,
                            76.83859074923805,
                            0
                        ],
                        "start": [
                            -40.52869681983385,
                            -71.21248091780433,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -3.29998642637338,
                32.647008362714985,
                -1,
                -3.29998642637338,
                76.84364243823597,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000245e5",
            "label": "C1",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000245e5",
                    "points": {
                        "end": [
                            -3.29998642637338,
                            32.647008362714985,
                            0
                        ],
                        "start": [
                            -3.29998642637338,
                            76.84364243823597,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                8.233101759640483,
                -70.42225465032553,
                -1,
                9.501546233151544,
                76.83859074923794,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000245ef",
            "label": "C2",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000245ef",
                    "points": {
                        "end": [
                            9.501546233151544,
                            76.83859074923795,
                            0
                        ],
                        "start": [
                            8.233101759640483,
                            -70.42225465032554,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                29.897370707519826,
                -70.40789920033859,
                -1,
                31.16581518103095,
                76.85294619922473,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000245f9",
            "label": "C3",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000245f9",
                    "points": {
                        "end": [
                            31.16581518103095,
                            76.85294619922473,
                            0
                        ],
                        "start": [
                            29.897370707519826,
                            -70.40789920033859,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36506067661944,
                57.17849561325113,
                -1,
                -66.7039777779917,
                57.17849561325113,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002460d",
            "label": "109",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002460d",
                    "points": {
                        "end": [
                            -66.7039777779917,
                            57.17849561325113,
                            0
                        ],
                        "start": [
                            -114.36506067661944,
                            57.17849561325113,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                54.34021114129837,
                -1,
                -13.814799444659343,
                54.34021114129837,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024617",
            "label": "210",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024617",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            54.34021114129837,
                            0
                        ],
                        "start": [
                            -13.814799444659343,
                            54.34021114129837,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36506067661944,
                44.38682894658439,
                -1,
                -66.7039777779917,
                44.38682894658439,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024642",
            "label": "108",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024642",
                    "points": {
                        "end": [
                            -114.36506067661944,
                            44.38682894658439,
                            0
                        ],
                        "start": [
                            -66.7039777779917,
                            44.38682894658439,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36506067661944,
                41.544961141298586,
                -1,
                -13.814799444659343,
                41.544961141298586,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024657",
            "label": "209",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024657",
                    "points": {
                        "end": [
                            -114.36506067661944,
                            41.544961141298586,
                            0
                        ],
                        "start": [
                            -13.814799444659343,
                            41.544961141298586,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36506067661944,
                32.588286141298454,
                -1,
                -58.97831432176713,
                32.588286141298454,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024661",
            "label": "208",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024661",
                    "points": {
                        "end": [
                            -114.36506067661944,
                            32.588286141298454,
                            0
                        ],
                        "start": [
                            -58.97831432176713,
                            32.588286141298454,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                31.505611141299028,
                -1,
                -66.70397777799167,
                31.505611141299028,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002466b",
            "label": "107",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002466b",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            31.505611141299028,
                            0
                        ],
                        "start": [
                            -66.70397777799167,
                            31.505611141299028,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                30.06204447463176,
                -1,
                -13.814799444659286,
                30.06204447463176,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246a1",
            "label": "207",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246a1",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            30.06204447463176,
                            0
                        ],
                        "start": [
                            -13.814799444659286,
                            30.06204447463176,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36506067661944,
                18.644744474632148,
                -1,
                -66.70397777799167,
                18.644744474632148,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246ab",
            "label": "106",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246ab",
                    "points": {
                        "end": [
                            -114.36506067661944,
                            18.644744474632148,
                            0
                        ],
                        "start": [
                            -66.70397777799167,
                            18.644744474632148,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                18.579127807964994,
                -1,
                -13.8147994446593,
                18.579127807964994,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246c0",
            "label": "206",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246c0",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            18.579127807964994,
                            0
                        ],
                        "start": [
                            -13.8147994446593,
                            18.579127807964994,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                14.31404447463217,
                -1,
                -60.547730651128916,
                14.31404447463217,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246ca",
            "label": "205",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246ca",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            14.31404447463217,
                            0
                        ],
                        "start": [
                            -60.547730651128916,
                            14.31404447463217,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                7.096211141298397,
                -1,
                -13.814799444659286,
                7.096211141298397,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246d4",
            "label": "204",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246d4",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            7.096211141298397,
                            0
                        ],
                        "start": [
                            -13.814799444659286,
                            7.096211141298397,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                5.751069474632345,
                -1,
                -66.7039777779917,
                5.751069474632345,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246de",
            "label": "105",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246de",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            5.751069474632345,
                            0
                        ],
                        "start": [
                            -66.7039777779917,
                            5.751069474632345,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36506067661944,
                -7.142605525367685,
                -1,
                -66.7039777779917,
                -7.142605525367685,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246e8",
            "label": "104",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246e8",
                    "points": {
                        "end": [
                            -114.36506067661944,
                            -7.142605525367685,
                            0
                        ],
                        "start": [
                            -66.7039777779917,
                            -7.142605525367685,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36496304839733,
                -15.858287983234845,
                -1,
                -13.814701816437207,
                -15.858287983234845,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246f2",
            "label": "202",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246f2",
                    "points": {
                        "end": [
                            -114.36496304839733,
                            -15.858287983234845,
                            0
                        ],
                        "start": [
                            -13.814701816437207,
                            -15.858287983234845,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                -20.036280525367715,
                -1,
                -66.7039777779917,
                -20.036280525367715,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000246fc",
            "label": "103",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000246fc",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            -20.036280525367715,
                            0
                        ],
                        "start": [
                            -66.7039777779917,
                            -20.036280525367715,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36456452042347,
                -25.8644584582579,
                -1,
                127.71058640632307,
                -25.8644584582579,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024706",
            "label": "201",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024706",
                    "points": {
                        "end": [
                            -114.36456452042347,
                            -25.8644584582579,
                            0
                        ],
                        "start": [
                            127.71058640632307,
                            -25.8644584582579,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36506067661944,
                -32.89714719203437,
                -1,
                -66.7039777779917,
                -32.89714719203437,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002471a",
            "label": "102",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002471a",
                    "points": {
                        "end": [
                            -66.7039777779917,
                            -32.89714719203437,
                            0
                        ],
                        "start": [
                            -114.36506067661944,
                            -32.89714719203437,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -114.36506067661944,
                -45.29869719203441,
                -1,
                -15.239341111325302,
                -45.29869719203441,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024724",
            "label": "101",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024724",
                    "points": {
                        "end": [
                            -15.239341111325302,
                            -45.29869719203441,
                            0
                        ],
                        "start": [
                            -114.36506067661944,
                            -45.29869719203441,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -84.73934111132522,
                -70.42225465032544,
                -1,
                -84.73934111132522,
                76.83859074923794,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002472e",
            "label": "A1",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002472e",
                    "points": {
                        "end": [
                            -84.73934111132522,
                            -70.42225465032544,
                            0
                        ],
                        "start": [
                            -84.73934111132522,
                            76.83859074923794,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -70.60812104683214,
                -70.42225465032544,
                -1,
                -70.60812104683214,
                76.7966495202354,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024738",
            "label": "A2",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024738",
                    "points": {
                        "end": [
                            -70.60812104683214,
                            -70.42225465032544,
                            0
                        ],
                        "start": [
                            -70.60812104683214,
                            76.7966495202354,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -56.57267444465856,
                -70.42225465032544,
                -1,
                -56.57267444465856,
                76.7966495202354,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024756",
            "label": "A3",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024756",
                    "points": {
                        "end": [
                            -56.57267444465856,
                            -70.42225465032544,
                            0
                        ],
                        "start": [
                            -56.57267444465856,
                            76.7966495202354,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -42.44941271349879,
                -70.42225465032544,
                -1,
                -42.44941271349879,
                76.79664952023542,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024760",
            "label": "A4",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024760",
                    "points": {
                        "end": [
                            -42.44941271349879,
                            -70.42225465032543,
                            0
                        ],
                        "start": [
                            -42.44941271349879,
                            76.79664952023542,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -28.449412713498788,
                -70.42225465032544,
                -1,
                -28.449412713498788,
                76.7966495202354,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002476a",
            "label": "A5",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002476a",
                    "points": {
                        "end": [
                            -28.449412713498788,
                            -70.42225465032544,
                            0
                        ],
                        "start": [
                            -28.449412713498788,
                            76.7966495202354,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -13.387778611325302,
                -70.4222546503255,
                -1,
                -13.387778611325302,
                -26.869216181870343,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002477e",
            "label": "Cx",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002477e",
                    "points": {
                        "end": [
                            -13.387778611325302,
                            -26.869216181870343,
                            0
                        ],
                        "start": [
                            -13.387778611325302,
                            -70.4222546503255,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                1.9385580269588818,
                -70.42225465032544,
                -1,
                1.9385580269588818,
                -45.46372631535294,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024788",
            "label": "C1x",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024788",
                    "points": {
                        "end": [
                            1.9385580269588818,
                            -45.46372631535294,
                            0
                        ],
                        "start": [
                            1.9385580269588818,
                            -70.42225465032544,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                13.798538756130556,
                -70.42225465032544,
                -1,
                13.798538756130556,
                -45.46372631535294,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024792",
            "label": "C2x",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024792",
                    "points": {
                        "end": [
                            13.798538756130556,
                            -45.46372631535294,
                            0
                        ],
                        "start": [
                            13.798538756130556,
                            -70.42225465032544,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                29.897370707519826,
                -70.40789920033859,
                -1,
                31.16581518103095,
                76.85294619922473,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002479c",
            "label": "C2y",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002479c",
                    "points": {
                        "end": [
                            31.16581518103095,
                            76.85294619922473,
                            0
                        ],
                        "start": [
                            29.897370707519826,
                            -70.40789920033859,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -15.544145321502157,
                52.961403946584596,
                -1,
                108.68471996697804,
                52.961403946584596,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000247a6",
            "label": "310",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000247a6",
                    "points": {
                        "end": [
                            -15.544145321502157,
                            52.961403946584596,
                            0
                        ],
                        "start": [
                            108.68471996697804,
                            52.961403946584596,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -15.544145321502157,
                -50.538596053415375,
                -1,
                108.68471996697804,
                -50.538596053415375,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000247b0",
            "label": "301",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000247b0",
                    "points": {
                        "end": [
                            -15.544145321502157,
                            -50.538596053415375,
                            0
                        ],
                        "start": [
                            108.68471996697804,
                            -50.538596053415375,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -15.544145321502157,
                -39.03859605341539,
                -1,
                108.68471996697805,
                -39.03859605341539,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000247ba",
            "label": "302",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000247ba",
                    "points": {
                        "end": [
                            -15.544145321502157,
                            -39.03859605341539,
                            0
                        ],
                        "start": [
                            108.68471996697805,
                            -39.03859605341539,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -13.814799444659343,
                -27.538596053415397,
                -1,
                108.585760968983,
                -27.538596053415397,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000247c4",
            "label": "303",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000247c4",
                    "points": {
                        "end": [
                            -13.814799444659343,
                            -27.538596053415397,
                            0
                        ],
                        "start": [
                            108.585760968983,
                            -27.538596053415397,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -15.544145321502157,
                -16.038596053415404,
                -1,
                108.68471996697804,
                -16.038596053415404,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000247ce",
            "label": "304",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000247ce",
                    "points": {
                        "end": [
                            -15.544145321502157,
                            -16.038596053415404,
                            0
                        ],
                        "start": [
                            108.68471996697804,
                            -16.038596053415404,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -15.544145321502157,
                -4.538596053415404,
                -1,
                108.68471996697804,
                -4.538596053415404,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000247d8",
            "label": "305",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000247d8",
                    "points": {
                        "end": [
                            -15.544145321502157,
                            -4.538596053415404,
                            0
                        ],
                        "start": [
                            108.68471996697804,
                            -4.538596053415404,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -15.544145321502157,
                6.961403946584426,
                -1,
                108.58576096898298,
                6.961403946584426,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000247e2",
            "label": "306",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000247e2",
                    "points": {
                        "end": [
                            -15.544145321502157,
                            6.961403946584426,
                            0
                        ],
                        "start": [
                            108.58576096898298,
                            6.961403946584426,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -12.406720109320588,
                18.461403946584596,
                -1,
                108.58576096898298,
                18.461403946584596,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000247f7",
            "label": "307",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000247f7",
                    "points": {
                        "end": [
                            -12.406720109320588,
                            18.461403946584596,
                            0
                        ],
                        "start": [
                            108.58576096898298,
                            18.461403946584596,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -15.544145321502157,
                29.961403946584596,
                -1,
                108.68471996697804,
                29.961403946584596,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024801",
            "label": "308",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024801",
                    "points": {
                        "end": [
                            -15.544145321502157,
                            29.961403946584596,
                            0
                        ],
                        "start": [
                            108.68471996697804,
                            29.961403946584596,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                -15.544145321502157,
                41.461403946584596,
                -1,
                108.68471996697804,
                41.461403946584596,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002480b",
            "label": "309",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002480b",
                    "points": {
                        "end": [
                            -15.544145321502157,
                            41.461403946584596,
                            0
                        ],
                        "start": [
                            108.68471996697804,
                            41.461403946584596,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                31.648990490268318,
                -49.40761680330678,
                -1,
                108.68471996697804,
                -48.74406265181108,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024815",
            "label": "401",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024815",
                    "points": {
                        "end": [
                            31.648990490268318,
                            -48.74406265181108,
                            0
                        ],
                        "start": [
                            108.68471996697805,
                            -49.40761680330678,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                31.752982518409112,
                -37.33370225601146,
                -1,
                108.68471996697807,
                -36.67104384915882,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002482a",
            "label": "402",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002482a",
                    "points": {
                        "end": [
                            31.752982518409112,
                            -36.67104384915882,
                            0
                        ],
                        "start": [
                            108.68471996697807,
                            -37.33370225601146,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                31.847084000395228,
                -26.40812197272527,
                -1,
                108.6847199669781,
                -25.746274117410962,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024843",
            "label": "403",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024843",
                    "points": {
                        "end": [
                            31.847084000395228,
                            -25.746274117410962,
                            0
                        ],
                        "start": [
                            108.6847199669781,
                            -26.408121972725272,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                31.941750656447198,
                -15.416922588638672,
                -1,
                108.68471996697802,
                -14.75589015304007,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002485c",
            "label": "404",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002485c",
                    "points": {
                        "end": [
                            31.941750656447198,
                            -14.75589015304007,
                            0
                        ],
                        "start": [
                            108.68471996697804,
                            -15.416922588638672,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                32.036417312499225,
                -4.425723204552011,
                -1,
                108.68471996697805,
                -3.7655061886691215,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024875",
            "label": "405",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024875",
                    "points": {
                        "end": [
                            32.036417312499225,
                            -3.7655061886691215,
                            0
                        ],
                        "start": [
                            108.68471996697807,
                            -4.425723204552011,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                32.131366555584236,
                6.598285729934859,
                -1,
                108.68471996697805,
                7.257684892013344,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-0002488e",
            "label": "406",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002488e",
                    "points": {
                        "end": [
                            32.131366555584236,
                            7.257684892013344,
                            0
                        ],
                        "start": [
                            108.68471996697807,
                            6.598285729934859,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                45.69131393126446,
                -56.381207540247175,
                -1,
                46.474550071592546,
                34.549076426313945,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-00024898",
            "label": "D",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024898",
                    "points": {
                        "end": [
                            45.69131393126446,
                            -56.381207540247175,
                            0
                        ],
                        "start": [
                            46.474550071592546,
                            34.549076426313945,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                48.48423084343712,
                -44.47748503237865,
                -1,
                49.164733609139745,
                34.52590428960869,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000248a2",
            "label": "D1",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000248a2",
                    "points": {
                        "end": [
                            49.16473360913975,
                            34.5259042896087,
                            0
                        ],
                        "start": [
                            48.484230843437125,
                            -44.47748503237866,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                59.963468355376904,
                -56.38120754024709,
                -1,
                60.74670449570499,
                34.549076426313945,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000248bb",
            "label": "D2",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000248bb",
                    "points": {
                        "end": [
                            59.963468355376904,
                            -56.38120754024709,
                            0
                        ],
                        "start": [
                            60.74670449570499,
                            34.549076426313945,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                64.76264680309191,
                -43.91105902386133,
                -1,
                65.43919142907242,
                34.6328076198737,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000248c5",
            "label": "D3",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000248c5",
                    "points": {
                        "end": [
                            64.76264680309191,
                            -43.911059023861334,
                            0
                        ],
                        "start": [
                            65.43919142907242,
                            34.63280761987371,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                69.37980932025118,
                -56.38120754024703,
                -1,
                70.16304546057938,
                34.549076426313945,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000248cf",
            "label": "D4",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000248cf",
                    "points": {
                        "end": [
                            69.37980932025118,
                            -56.38120754024703,
                            0
                        ],
                        "start": [
                            70.16304546057938,
                            34.549076426313945,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                81.25593163495864,
                -45.06261372113559,
                -1,
                81.94186634727956,
                34.57140080192022,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000248d9",
            "label": "D5",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000248d9",
                    "points": {
                        "end": [
                            81.94186634727956,
                            34.57140080192023,
                            0
                        ],
                        "start": [
                            81.25593163495864,
                            -45.0626137211356,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        },
        {
            "boundingBox": [
                83.75039239556452,
                -56.38120754024692,
                -1,
                84.53362853589181,
                34.54907642631397,
                82.99999999999964
            ],
            "document": "R21 Mill Building - Arch.rvt",
            "id": "72f55228-44b9-4681-a393-b3df0d8783da-000248e3",
            "label": "D6",
            "segments": [
                {
                    "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000248e3",
                    "points": {
                        "end": [
                            83.75039239556452,
                            -56.38120754024692,
                            0
                        ],
                        "start": [
                            84.53362853589181,
                            34.549076426313974,
                            0
                        ]
                    },
                    "type": 1
                }
            ]
        }
    ],
    "levelOccluderIds": [
        533,
        3376,
        534,
        535,
        366,
        5622,
        5753,
        5812,
        5887,
        5940,
        5623,
        3377,
        5555,
        5640,
        4303,
        4304,
        4305,
        4306,
        4307,
        4308,
        4309,
        4312,
        4313,
        4314,
        4315,
        4316,
        4317,
        4318,
        4319,
        4320,
        4321,
        4324,
        856,
        857,
        866,
        6000,
        4715,
        4716,
        4717,
        4718,
        4719,
        4720,
        4721,
        4722,
        4723,
        4724,
        2471,
        2472,
        1615,
        1616,
        922,
        923,
        5071,
        5072,
        5073,
        5074,
        5075,
        5076,
        5077,
        5078,
        5079,
        5080,
        5081,
        5082,
        5083,
        5084,
        2712,
        2713,
        2714,
        2715,
        2716,
        2717,
        2718,
        2719,
        2720,
        2721,
        2722,
        2723,
        2724,
        2725,
        1928,
        1929,
        1930,
        1931,
        1932,
        1933,
        1934,
        1935,
        1936,
        1937,
        1938,
        1939,
        1940,
        1941,
        1234,
        1235,
        1236,
        1237,
        1238,
        1239,
        1240,
        1241,
        1242,
        1243,
        1244,
        1245,
        1313,
        2153,
        2953,
        4345,
        5212,
        5213,
        5214,
        5215,
        5216,
        5217,
        5218,
        5219,
        5220,
        5221,
        5222,
        5223,
        5224,
        5225,
        5226,
        5227,
        5228,
        5229,
        5230,
        5231,
        5232,
        5233,
        5234,
        5235,
        5236,
        5237,
        5238,
        5239,
        5240,
        5556,
        5557,
        5564,
        718,
        719,
        725,
        1397,
        4350,
        4351,
        4352,
        4353,
        4354,
        4355,
        4356,
        4357,
        4358,
        4359,
        4360,
        4361,
        4362,
        4363,
        4364,
        4365,
        4366,
        4367,
        4368,
        4369,
        4370,
        4371,
        4372,
        4373,
        4374,
        4375,
        4376,
        4377,
        4378,
        4379,
        4380,
        4381,
        4382,
        4383,
        4384,
        4385,
        3102,
        3103,
        3104,
        3105,
        3106,
        3107,
        3108,
        3109,
        3110,
        3111,
        3112,
        3113,
        3114,
        3115,
        3116,
        3117,
        3118,
        3119,
        3120,
        3121,
        3122,
        3123,
        3124,
        3125,
        3126,
        3127,
        3128,
        3129,
        3130,
        3131,
        3132,
        3133,
        3134,
        3135,
        3136,
        3137,
        5565,
        5566,
        5567,
        5568,
        5569,
        5570,
        5571,
        5572,
        5573,
        5574,
        5575,
        5576,
        5577,
        5578,
        5579,
        5580,
        5581,
        5582,
        5583,
        5584,
        5585,
        5586,
        5587,
        5588,
        5589,
        5590,
        5591,
        5592,
        5593,
        5594,
        5595,
        5596,
        5597,
        5598,
        5599,
        5600,
        4481,
        4486,
        4529,
        6002
    ],
    "levels": [
        {
            "elevation": -4,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "3f2a32a1-52d9-455c-9f04-0869eaea0b56-0002508b",
            "height": 4,
            "name": "BLDG 1- BASEMENT FLR. FIN."
        },
        {
            "elevation": 0,
            "extension": {
                "buildingStory": true,
                "computationHeight": 4,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
            "height": 3.5000000000000004,
            "name": "All-Ground Level"
        },
        {
            "elevation": 3.5000000000000004,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": false,
                "structure": false
            },
            "guid": "f0a0636f-f66b-48ee-9b05-60315985620a-000aa609",
            "height": 3.9166666666666674,
            "name": "T.O. Landing01"
        },
        {
            "elevation": 7.416666666666668,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "28479c3b-0010-4600-b8e2-7b45e5e695d5-00025328",
            "height": 0.3854166666695136,
            "name": "BLDG 4- LEVEL 1 FLR. FIN."
        },
        {
            "elevation": 7.802083333336181,
            "extension": {
                "buildingStory": true,
                "computationHeight": 4,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "6341822b-d4f3-11d3-a039-0000863f1523-000026da",
            "height": 1.5312499999971507,
            "name": "BLDG 1,2,3- LEVEL 1 FLR. FIN."
        },
        {
            "elevation": 9.333333333333332,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": false,
                "structure": false
            },
            "guid": "f0a0636f-f66b-48ee-9b05-60315985620a-000aa694",
            "height": 5.833333333333332,
            "name": "T.O. Landing02"
        },
        {
            "elevation": 15.166666666666664,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": false,
                "structure": false
            },
            "guid": "f0a0636f-f66b-48ee-9b05-60315985620a-000aa6b7",
            "height": 3.3333333333333357,
            "name": "T.O. Landing03"
        },
        {
            "elevation": 18.5,
            "extension": {
                "buildingStory": true,
                "computationHeight": 4,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "28479c3b-0010-4600-b8e2-7b45e5e695d5-000253a4",
            "height": 1.981290982828483,
            "name": "BLDG 4- LEVEL 2 FLR. FIN."
        },
        {
            "elevation": 20.481290982828483,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": false,
                "structure": false
            },
            "guid": "f83bf80e-0695-4379-9c02-3bdecd92ddd4-000a98c5",
            "height": 0.518709017171517,
            "name": "T.O. Prapet BLDG. 1,2,8"
        },
        {
            "elevation": 21,
            "extension": {
                "buildingStory": true,
                "computationHeight": 4,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00023e4a",
            "height": 0.5431802342545211,
            "name": "BLDG 1,2,3- LEVEL 2 FLR. FIN."
        },
        {
            "elevation": 21.54318023425452,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": false,
                "structure": false
            },
            "guid": "efc58211-7a47-4361-af7f-d65bfb506ecb-000f95b3",
            "height": 8.206819765745479,
            "name": "Level 1"
        },
        {
            "elevation": 29.75,
            "extension": {
                "buildingStory": true,
                "computationHeight": 4,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "28479c3b-0010-4600-b8e2-7b45e5e695d5-000253ba",
            "height": 1.793180234252958,
            "name": "BLDG 4- LEVEL 3 FLR. FIN."
        },
        {
            "elevation": 31.543180234252958,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": false,
                "structure": false
            },
            "guid": "efc58211-7a47-4361-af7f-d65bfb506ecb-000f95b4",
            "height": 1.7484864324137064,
            "name": "Level 2"
        },
        {
            "elevation": 33.291666666666664,
            "extension": {
                "buildingStory": true,
                "computationHeight": 4,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "72f55228-44b9-4681-a393-b3df0d8783da-00024027",
            "height": 7.208333333333336,
            "name": "BLDG. 1,2,3- LEVEL 3 FLR. FIN."
        },
        {
            "elevation": 40.5,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "28479c3b-0010-4600-b8e2-7b45e5e695d5-000253d0",
            "height": 4.041666666666664,
            "name": "BLDG 4- LEVEL 4 FLR. FIN."
        },
        {
            "elevation": 44.541666666666664,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "72f55228-44b9-4681-a393-b3df0d8783da-000242b1",
            "height": 7.041666666666671,
            "name": "BLDG. 1,2,3- LEVEL 4 FLR. FIN."
        },
        {
            "elevation": 51.583333333333336,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "28479c3b-0010-4600-b8e2-7b45e5e695d5-000253e6",
            "height": 4.208333333333329,
            "name": "T.O. ROOF BLDG 4"
        },
        {
            "elevation": 55.791666666666664,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "72f55228-44b9-4681-a393-b3df0d8783da-0002448e",
            "height": 0.9166666666666643,
            "name": "BLDG. 1,2,3- LEVEL 5 FLR. FIN."
        },
        {
            "elevation": 56.70833333333333,
            "extension": {
                "buildingStory": true,
                "computationHeight": 4,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "631be40e-a72e-4652-a589-e494ec4eaa61-000e3cec",
            "height": 7.3243400228783315,
            "name": "Upper Deck Landing"
        },
        {
            "elevation": 64.03267335621166,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": false,
                "structure": false
            },
            "guid": "5a585ce4-52b3-4215-9561-7eada5937e27-000b6464",
            "height": 3.0506599771216685,
            "name": "T.O. Landing05"
        },
        {
            "elevation": 67.08333333333333,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "c99c4dac-7c6e-47e2-9c2b-bb82c28a1903-00024fa3",
            "height": 11.1875,
            "name": "BLDG. 1,2,3- LEVEL 6 FLR. FIN."
        },
        {
            "elevation": 78.27083333333333,
            "extension": {
                "buildingStory": true,
                "computationHeight": 0,
                "groundPlane": false,
                "hasAssociatedViewPlans": true,
                "structure": false
            },
            "guid": "c99c4dac-7c6e-47e2-9c2b-bb82c28a1903-00024fb9",
            "height": 2147483647,
            "name": "T.O. ROOF BLDG. 1,2,3"
        }
    ],
    "linkedDocuments": [],
    "locationParameters": {
        "placeName": "Boston, MA"
    },
    "phases": [
        {
            "name": "Existing"
        },
        {
            "name": "New Construction"
        }
    ],
    "refPointTransformation": [
        1,
        0,
        0,
        0,
        1,
        0,
        0,
        0,
        1,
        0,
        0,
        0
    ],
    "scopeBoxes": [],
    "version": "1.0.0",
    "viewports": [
        {
            "cameraOrientation": [
                0,
                0,
                -1,
                0,
                1,
                0,
                0,
                0,
                0
            ],
            "extensions": {
                "farClipOffset": 100,
                "farClipOffsetActive": false,
                "hasRegions": false,
                "viewRange": {
                    "bottomClipPlane": {
                        "levelGuid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
                        "offset": 0
                    },
                    "cutPlane": {
                        "levelGuid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
                        "offset": 4
                    },
                    "topClipPlane": {
                        "levelGuid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
                        "offset": 7.5
                    },
                    "viewDepthPlane": {
                        "levelGuid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
                        "offset": 0
                    }
                }
            },
            "geometryViewportRegion": [
                -0.3551596500842269,
                -0.5287034513482315,
                -0.01,
                1.5542781796359304,
                1.122126553373433,
                0.01
            ],
            "hasBreaks": false,
            "isCropBoxActive": true,
            "modelToSheetTransform": [
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0.6549783902773714,
                0.45620200362286123,
                0
            ],
            "scale": 192,
            "sectionBox": {
                "max": {
                    "x": 170.94555955684524,
                    "y": 126.13751355210591,
                    "z": 7.5
                },
                "min": {
                    "x": -191.82650374942492,
                    "y": -186.98184735445372,
                    "z": 0
                },
                "transform": [
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    0
                ]
            },
            "sheetGuid": "99c5f461-5395-42d4-9cd2-5c9cbb2ff2aa-000c224f",
            "viewGuid": "48b0002b-1cda-4645-910e-d332915d32ae-000c6ec0",
            "viewType": "FloorPlan",
            "viewportGuid": "39ed83ab-6d29-42b4-ac3b-55475c1f8da9-000cad91",
            "viewportPosition": [
                -0.3551596500842269,
                -0.5287034513482315,
                -0.10440104166666614,
                1.5542781796359304,
                1.122126553373433,
                0.43979600694444443
            ],
            "viewportRotation": 0
        },
        {
            "cameraOrientation": [
                0,
                0,
                -1,
                0,
                1,
                0,
                0,
                0,
                28.99999999999964
            ],
            "extensions": {
                "farClipOffset": 1000,
                "farClipOffsetActive": false,
                "hasRegions": false,
                "viewRange": {
                    "bottomClipPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-00023e4a",
                        "offset": 0
                    },
                    "cutPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-00023e4a",
                        "offset": 4
                    },
                    "topClipPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-00023e4a",
                        "offset": 7.5
                    },
                    "viewDepthPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-00023e4a",
                        "offset": 0
                    }
                }
            },
            "geometryViewportRegion": [
                -0.7478287173274196,
                -0.35582670833587804,
                -0.18187499999999815,
                2.2379034656035777,
                1.6414943957146915,
                0.39812934027777963
            ],
            "hasBreaks": false,
            "isCropBoxActive": false,
            "modelToSheetTransform": [
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0.7002359630223189,
                0.490648739084253,
                -0.1510416666666648
            ],
            "scale": 192,
            "sectionBox": {
                "max": {
                    "x": 100,
                    "y": 100,
                    "z": 7.5
                },
                "min": {
                    "x": -100,
                    "y": -100,
                    "z": -7.999999999999641
                },
                "transform": [
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    28.99999999999964
                ]
            },
            "sheetGuid": "99c5f461-5395-42d4-9cd2-5c9cbb2ff2aa-000c235e",
            "viewGuid": "0b7e8ca9-0ce5-4f9b-9220-2b95da457ff7-000c67a9",
            "viewType": "FloorPlan",
            "viewportGuid": "39ed83ab-6d29-42b4-ac3b-55475c1f8da9-000cad90",
            "viewportPosition": [
                -0.7478287173274196,
                -0.35582670833587804,
                -0.18187499999999815,
                2.2379034656035777,
                1.6414943957146915,
                0.39812934027777963
            ],
            "viewportRotation": 0
        },
        {
            "cameraOrientation": [
                0,
                0,
                -1,
                0,
                1,
                0,
                0,
                0,
                44.499999999999645
            ],
            "extensions": {
                "farClipOffset": 1000,
                "farClipOffsetActive": false,
                "hasRegions": false,
                "viewRange": {
                    "bottomClipPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-00024027",
                        "offset": 0
                    },
                    "cutPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-00024027",
                        "offset": 4
                    },
                    "topClipPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-00024027",
                        "offset": 7.5
                    },
                    "viewDepthPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-00024027",
                        "offset": 0
                    }
                }
            },
            "geometryViewportRegion": [
                -0.7232057751662945,
                -0.361460738483219,
                -0.2626041666666648,
                2.262526407764703,
                1.6358603655673503,
                0.38141927083333516
            ],
            "hasBreaks": false,
            "isCropBoxActive": false,
            "modelToSheetTransform": [
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0.7248589051834441,
                0.485014708936912,
                -0.23177083333333148
            ],
            "scale": 192,
            "sectionBox": {
                "max": {
                    "x": 100,
                    "y": 100,
                    "z": 7.5
                },
                "min": {
                    "x": -100,
                    "y": -100,
                    "z": -11.20833333333298
                },
                "transform": [
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    44.499999999999645
                ]
            },
            "sheetGuid": "5fd2a88d-9011-40e5-8e87-0a9d23d4aecd-000c301f",
            "viewGuid": "f1cef323-54cc-4a78-875d-f7d8e244e02f-000c6316",
            "viewType": "FloorPlan",
            "viewportGuid": "39ed83ab-6d29-42b4-ac3b-55475c1f8da9-000cad92",
            "viewportPosition": [
                -0.7232057751662945,
                -0.361460738483219,
                -0.2626041666666648,
                2.262526407764703,
                1.6358603655673503,
                0.38141927083333516
            ],
            "viewportRotation": 0
        },
        {
            "cameraOrientation": [
                0,
                0,
                -1,
                0,
                1,
                0,
                0,
                0,
                57.999999999999645
            ],
            "extensions": {
                "farClipOffset": 1000,
                "farClipOffsetActive": false,
                "hasRegions": false,
                "viewRange": {
                    "bottomClipPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-000242b1",
                        "offset": 0
                    },
                    "cutPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-000242b1",
                        "offset": 4
                    },
                    "topClipPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-000242b1",
                        "offset": 7.5
                    },
                    "viewDepthPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-000242b1",
                        "offset": 0
                    }
                }
            },
            "geometryViewportRegion": [
                -0.7521283458350726,
                -0.37682406082371334,
                -0.3329166666666648,
                2.233603837095925,
                1.6204970432268562,
                0.36970052083333516
            ],
            "hasBreaks": false,
            "isCropBoxActive": false,
            "modelToSheetTransform": [
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0.695936334514666,
                0.4696513865964177,
                -0.3020833333333315
            ],
            "scale": 192,
            "sectionBox": {
                "max": {
                    "x": 100,
                    "y": 100,
                    "z": 7.5
                },
                "min": {
                    "x": -100,
                    "y": -100,
                    "z": -13.45833333333298
                },
                "transform": [
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    57.999999999999645
                ]
            },
            "sheetGuid": "5fd2a88d-9011-40e5-8e87-0a9d23d4aecd-000c3026",
            "viewGuid": "37635a43-7c9f-44d1-872e-2fefd5263528-000c4ce5",
            "viewType": "FloorPlan",
            "viewportGuid": "39ed83ab-6d29-42b4-ac3b-55475c1f8da9-000cad93",
            "viewportPosition": [
                -0.7521283458350726,
                -0.37682406082371334,
                -0.3329166666666648,
                2.233603837095925,
                1.6204970432268562,
                0.36970052083333516
            ],
            "viewportRotation": 0
        },
        {
            "cameraOrientation": [
                0,
                0,
                -1,
                0,
                1,
                0,
                0,
                0,
                74.99999999999964
            ],
            "extensions": {
                "farClipOffset": 1000,
                "farClipOffsetActive": false,
                "hasRegions": false,
                "viewRange": {
                    "bottomClipPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-0002448e",
                        "offset": 0
                    },
                    "cutPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-0002448e",
                        "offset": 4
                    },
                    "topClipPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-0002448e",
                        "offset": 7.5
                    },
                    "viewDepthPlane": {
                        "levelGuid": "72f55228-44b9-4681-a393-b3df0d8783da-0002448e",
                        "offset": 0
                    }
                }
            },
            "geometryViewportRegion": [
                0.0999231761889814,
                0.09424911748292282,
                -0.8120833333333295,
                1.453185536887547,
                1.1503432478558042,
                -0.7920833333333295
            ],
            "hasBreaks": false,
            "isCropBoxActive": true,
            "modelToSheetTransform": [
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0,
                0,
                0,
                0.005208333333333333,
                0.6972811079679251,
                0.4705197016855706,
                -0.8020833333333295
            ],
            "scale": 192,
            "sectionBox": {
                "max": {
                    "x": 143.41365035256936,
                    "y": 128.80612086468096,
                    "z": 7.5
                },
                "min": {
                    "x": -112.57272290155524,
                    "y": -70.12395216691229,
                    "z": -19.20833333333298
                },
                "transform": [
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    74.99999999999964
                ]
            },
            "sheetGuid": "5fd2a88d-9011-40e5-8e87-0a9d23d4aecd-000c302d",
            "viewGuid": "5fd2a88d-9011-40e5-8e87-0a9d23d4aecd-000c2fe8",
            "viewType": "FloorPlan",
            "viewportGuid": "5fd2a88d-9011-40e5-8e87-0a9d23d4aecd-000c3034",
            "viewportPosition": [
                0.0999231761889814,
                -0.05840841008438107,
                -0.8329166666666629,
                1.453185536887547,
                1.1503432478558042,
                -0.07170572916666292
            ],
            "viewportRotation": 0
        },
        {
            "cameraOrientation": [
                0,
                0,
                -1,
                0,
                1,
                0,
                0,
                0,
                0
            ],
            "extensions": {
                "farClipOffset": 100,
                "farClipOffsetActive": false,
                "hasRegions": false,
                "viewRange": {
                    "bottomClipPlane": {
                        "levelGuid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
                        "offset": -4
                    },
                    "cutPlane": {
                        "levelGuid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
                        "offset": 2
                    },
                    "topClipPlane": {
                        "levelGuid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
                        "offset": 3
                    },
                    "viewDepthPlane": {
                        "levelGuid": "933c4a06-93b8-11d3-80f8-00c04f8efc32-0000001e",
                        "offset": -4
                    }
                }
            },
            "geometryViewportRegion": [
                0.013132019171180129,
                0.1161927705210022,
                -1.127708333333327,
                1.4018811440373702,
                0.9037581220466072,
                -1.107708333333327
            ],
            "hasBreaks": false,
            "isCropBoxActive": true,
            "modelToSheetTransform": [
                0.0008333333333333334,
                0,
                0,
                0,
                0.0008333333333333334,
                0,
                0,
                0,
                0.0008333333333333334,
                0.8450071985165895,
                0.5173457494702037,
                -1.117708333333327
            ],
            "scale": 1200,
            "sectionBox": {
                "max": {
                    "x": 657.4987346249491,
                    "y": 452.94484709165965,
                    "z": 3
                },
                "min": {
                    "x": -985.0002152144789,
                    "y": -468.13357473906626,
                    "z": 0
                },
                "transform": [
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    0,
                    1,
                    0,
                    0,
                    0
                ]
            },
            "sheetGuid": "8efad024-0768-4dc7-bc58-6c6fa207fb5b-000c8640",
            "viewGuid": "8efad024-0768-4dc7-bc58-6c6fa207fb5b-000c8655",
            "viewType": "FloorPlan",
            "viewportGuid": "8efad024-0768-4dc7-bc58-6c6fa207fb5b-000c867b",
            "viewportPosition": [
                0.013132019171180129,
                0.1161927705210022,
                -1.127708333333327,
                1.4018811440373702,
                0.9037581220466072,
                -1.107708333333327
            ],
            "viewportRotation": 0
        },
        {
            "cameraOrientation": [
                -1.3031211604772973e-15,
                1,
                0,
                0,
                0,
                1,
                4.845878836533089,
                -122.93182609268557,
                0
            ],
            "extensions": {
                "elevationMarker": [
                    4.845878836533089,
                    -122.93182609268557,
                    0
                ],
                "farClipOffset": 10,
                "farClipOffsetActive": false,
                "farClipping": 0,
                "isSplitSection": false
            },
            "geometryViewportRegion": [
                -0.4720606501148472,
                0.10150283866712363,
                -2.2120330267992125,
                2.3173834881529767,
                0.7713086587312706,
                -1.181752556988696
            ],
            "hasBreaks": false,
            "isCropBoxActive": false,
            "modelToSheetTransform": [
                0.005208333333333333,
                0,
                0,
                0,
                0,
                -0.005208333333333333,
                0,
                0.005208333333333333,
                0,
                0.7281031473076502,
                0.25326626901218496,
                -1.8320224845547668
            ],
            "scale": 192,
            "sectionBox": {
                "max": {
                    "x": 79.80399997917318,
                    "y": 6,
                    "z": 0
                },
                "min": {
                    "x": -83.77466576051476,
                    "y": -6,
                    "z": -10
                },
                "transform": [
                    1,
                    1.3031211604772973e-15,
                    0,
                    0,
                    0,
                    1,
                    1.3031211604772973e-15,
                    -1,
                    0,
                    4.845878836533089,
                    -122.93182609268557,
                    0
                ]
            },
            "sheetGuid": "badad818-4f44-4a28-b861-7b2fa0c1aeba-000cada3",
            "viewGuid": "5f835dbc-9347-11d5-93d5-0000863f27ad-00007211",
            "viewType": "Elevation",
            "viewportGuid": "ad94e58a-9b49-4269-8544-9259603642a1-000cb4b3",
            "viewportPosition": [
                -0.4720606501148472,
                0.10150283866712363,
                -2.2120330267992125,
                2.3173834881529767,
                0.7713086587312706,
                -1.181752556988696
            ],
            "viewportRotation": 0
        }
    ]
}
```


***Status Code:*** 200

<br>



### 3. /modeldata/:modelID/attrs


The /attrs and /schema endpoints are used to retrieve information about the properties that are available within Tandem. Some properties are read-only and come from the design source files (e.g. Revit, IFC). Other properties are defined in Tandem by the user and are read/write.  
When reading property values via /scan or writing property values via /mutate, it is necessary to know information about the property definition. For instance, both endpoints expect properties to be referenced by their internal "fully qualified" names (e.g., "z:zAc" instead of the human-readable display name "Concrete | Param A").

The /schema endpoint returns the list of properties in an easy to read JSON format, but is not the most efficient way to retrieve these names. The Tandem client application calls /attrs and builds a mapping table to go back and forth between DisplayName and internal "fully qualified" names.

See these notes for more information: [https://autodesk-tandem.github.io/API_attrs.html](https://autodesk-tandem.github.io/API_attrs.html)


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/modeldata/:modelID/attrs
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN |



***Body: None***



#### I. Example Response: OK
```js
["pdb version dt 1",
"-AE",["Horizontal Void/Chase Area Threshold","Energy Analytical Model",3,"autodesk.unit.unit:squareFeet-1.0.1","","Horizontal Void/Chase Area Threshold",0,0,"squareFeet"],
"-AI",["Type Name","Identity Data",20,"","","Type Name",8,0,""],
"-AM",["name","__name__",20,"","","",0,0,""],
"-AQ",["Top Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Top Offset",8,0,"feetFractionalInches"],
"-AU",["K1","Materials and Finishes",20,"","","",0,0,""],
"-AY",["Bending","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Bending",0,0,"kipsPerSquareInch"],
"-QE",["Frame","Materials and Finishes",20,"","","",0,0,""],
"-QI",["Shear modulus","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Shear modulus",0,0,"kipsPerSquareInch"],
"-QM",["Guide Grid","Other",20,"","","Guide Grid",0,0,""],
"-QQ",["Length","Analytical Properties",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Length",8,0,"feetFractionalInches"],
"-QU",["glass inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"-QY",["Assembly Description","Identity Data",20,"","","Assembly Description",8,0,""],
"-gE",["Base Material","Materials and Finishes",20,"","","",0,0,""],
"-gI",["Organization Name","Identity Data",20,"","","Organization Name",0,0,""],
"-gM",["Work Plane-Based","Other",1,"","","Work Plane-Based",0,0,""],
"-gQ",["Elevation Tag","Graphics",20,"","","Elevation Tag",0,0,""],
"-gU",["Building Name","Identity Data",20,"","","Building Name",0,0,""],
"-gY",["SmartBIM Object Version","Identity Data",3,"","","",8,0,""],
"-wE",["Zone Name","IFC Parameters",20,"","","",0,0,""],
"-wI",["Gross Volume","Dimensions",3,"autodesk.unit.unit:cubicFeet-1.0.1","","Gross Volume",8,0,"cubicFeet"],
"-wM",["Alternate Units Format","Text",20,"","","Alternate Units Format",0,0,""],
"-wQ",["Default Sill Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"-wU",["Member","__internalref__",11,"","","",1,0,""],
"-wY",["Area","Analytical Properties",3,"autodesk.unit.unit:squareFeet-1.0.1","","Area",8,0,"squareFeet"],
"0AE",["Alternate Units","Text",20,"","","Alternate Units",0,0,""],
"0AI",["Geometry Hint","Phasing",20,"","","",8,0,""],
"0AM",["CWFU","Mechanical",3,"","","CWFU",0,0,""],
"0AQ",["Inlet Spud Size","Constraints",3,"autodesk.unit.unit:fractionalInches-1.0.0","","",0,0,"fractionalInches"],
"0AU",["Lat","Geolocation",3,"autodesk.unit.unit:degrees-1.0.1","","Lat",8,0,"degrees"],
"0AY",["Area","Dimensions",3,"autodesk.unit.unit:squareFeet-1.0.1","","Area",8,0,"squareFeet"],
"0QE",["Top Overhang","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"0QI",["window_inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"0QM",["Zone ObjectType Submeter","Constraints",20,"","","",0,0,""],
"0QQ",["Angled Joins","Construction",20,"","","Angled Joins",0,0,""],
"0QU",["Wall Finish","Identity Data",20,"","","Wall Finish",0,0,""],
"0QY",["Section Tag","Graphics",20,"","","Section Tag",0,0,""],
"0gE",["Monolithic Stairs","Construction",1,"","","Monolithic Stairs",0,0,""],
"0gI",["OmniClass","Identity Data",20,"","","",0,0,""],
"0gM",["Perimeter Zone Division","Energy Analytical Model",1,"","","Perimeter Zone Division",8,0,""],
"0gQ",["Sun Path","Graphics",1,"","","Sun Path",0,0,""],
"0gU",["Calculated Area per Heating Load","Energy Analysis",3,"autodesk.unit.unit:squareFeetPer1000BritishThermalUnitsPerHour-1.0.1","","Calculated Area per Heating Load",8,0,"squareFeetPer1000BritishThermalUnitsPerHour"],
"0gY",["Start Extension","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"0wE",["Tread Material","Materials and Finishes",20,"","","Tread Material",0,0,""],
"0wI",["Caster Material","Materials and Finishes",20,"","","",0,0,""],
"0wM",["Photographic Exposure","Graphics",20,"","","Photographic Exposure",0,0,""],
"0wQ",["Hide at scales coarser than","Graphics",20,"","","Hide at scales coarser than",0,0,""],
"0wU",["CenterK_tophalfwidth","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"0wY",["Parent Name","Constraints",20,"","","",0,0,""],
"1AE",["Analytical Space Resolution","Energy Analytical Model",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Analytical Space Resolution",0,0,"feetFractionalInches"],
"1AI",["Projection Mode","Camera",20,"","","Projection Mode",0,0,""],
"1AM",["door_glass inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"1AQ",["Plan View Symbols End 2 (Default)","Graphics",1,"","","Plan View Symbols End 2 (Default)",0,0,""],
"1AU",["Flushometer","Identity Data",20,"","","",0,0,""],
"1AY",["Riser Type","Risers",20,"","","Riser Type",0,0,""],
"1QE",["Start y Projection","Analytical Alignment",20,"","","Start y Projection",8,0,""],
"1QI",["Shear parallel to grain","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Shear parallel to grain",0,0,"kipsPerSquareInch"],
"1QM",["header","Materials and Finishes",20,"","","",0,0,""],
"1QQ",["Ordinate Dimension Settings","Graphics",20,"","","Ordinate Dimension Settings",8,0,""],
"1QU",["Humidification Set Point","Energy Analysis",3,"autodesk.unit.unit:percentage-1.0.1","","Humidification Set Point",8,0,"percentage"],
"1QY",["End Mz","Releases / Member Forces",1,"","","End Mz",8,0,""],
"1gE",["Heating Set Point","Energy Analysis",3,"autodesk.unit.unit:fahrenheit-1.0.1","","Heating Set Point",8,0,"fahrenheit"],
"1gI",["Height","Top Rail",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Height",8,0,"feetFractionalInches"],
"1gM",["Top Connection","Structural",20,"","","Top Connection",0,0,""],
"1gQ",["depth","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"1gU",["Surface Type","Energy Analysis",20,"","","Surface Type",8,0,""],
"1gY",["Cut with Voids When Loaded","Other",1,"","","Cut with Voids When Loaded",0,0,""],
"1wE",["Revision Date","Other",20,"","","Revision Date",8,0,""],
"1wI",["Panel","Electrical - Loads",20,"","","Panel",8,0,""],
"1wM",["Categorize as","Identity Data",20,"","","Categorize as",0,0,""],
"1wQ",["Join Condition","Construction",20,"","","Join Condition",0,0,""],
"1wU",["Equality Witness Display","Other",20,"","","Equality Witness Display",0,0,""],
"1wY",["Text Background","Text",20,"","","Text Background",0,0,""],
"2AE",["Occupied Area","Dimensions",3,"autodesk.unit.unit:squareFeet-1.0.1","","Occupied Area",8,0,"squareFeet"],
"2AI",["Voltage","Electrical",3,"autodesk.unit.unit:volts-1.0.1","","",0,0,"volts"],
"2AM",["Break Symbol in Plan","Graphics",1,"","","Break Symbol in Plan",0,0,""],
"2AQ",["Parent ObjectType","Constraints",20,"","","",0,0,""],
"2AU",["Issued to","Identity Data",20,"","","Issued to",8,0,""],
"2AY",["Outlet Air Flow","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinute-1.0.1","","",8,0,"cubicFeetPerMinute"],
"2QE",["Leader Line","Graphics",1,"","","Leader Line",0,0,""],
"2QI",["Mass Glazing","Other",20,"","","Mass Glazing",0,0,""],
"2QM",["Level Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"2QQ",["Resistance calculation strength","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Resistance calculation strength",0,0,"kipsPerSquareInch"],
"2QU",["Length Handrail Hold","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"2QY",["Cross-Section Rotation","Analytical Properties",3,"autodesk.unit.unit:degrees-1.0.1","","Cross-Section Rotation",8,0,"degrees"],
"2gE",["Slope","Dimensions",3,"autodesk.unit.unit:riseDividedBy12Inches-1.0.1","","Slope",8,0,"riseDividedBy12Inches"],
"2gI",["Far Clip Offset","Extents",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Far Clip Offset",8,0,"feetFractionalInches"],
"2gM",["Font","Title Text",20,"","","Font",0,0,""],
"2gQ",["View Template","Identity Data",20,"","","View Template",0,0,""],
"2gU",["Box Material","Materials and Finishes",20,"","","",0,0,""],
"2gY",["Component","__internalref__",11,"","","",1,0,""],
"2wE",["Layout","Horizontal Grid",20,"","","Layout",0,0,""],
"2wI",["Sensible Heat Gain per person","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Sensible Heat Gain per person",0,0,"britishThermalUnitsPerHour"],
"2wM",["Base z Projection","Analytical Alignment",20,"","","Base z Projection",8,0,""],
"2wQ",["Issued","Other",1,"","","Issued",8,0,""],
"2wU",["Start Mz","Releases / Member Forces",1,"","","Start Mz",0,0,""],
"2wY",["Top Constraint","Constraints",20,"","","Top Constraint",0,0,""],
"3AE",["Text Font","Graphics",20,"","","Text Font",0,0,""],
"3AI",["Show family pre-cut in plan views","Other",1,"","","Show family pre-cut in plan views",0,0,""],
"3AM",["Checked By","Identity Data",20,"","","Checked By",0,0,""],
"3AQ",["Non-Plan View Symbols (Default)","Graphics",20,"","","Non-Plan View Symbols (Default)",0,0,""],
"3AU",["Orientation","Constraints",20,"","","Orientation",8,0,""],
"3AY",["Witness Line Tick Mark","Graphics",20,"","","Witness Line Tick Mark",0,0,""],
"3QE",["Physical Material Asset","Analytical Properties",20,"","","Physical Material Asset",8,0,""],
"3QI",["Iy","Structural",3,"","","",0,0,""],
"3QM",["Bold","Text",1,"","","Bold",0,0,""],
"3QQ",["Shear modulus Z","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Shear modulus Z",8,0,"kipsPerSquareInch"],
"3QU",["Critical Path","Mechanical - Flow",1,"","","Critical Path",8,0,""],
"3QY",["schema_version","__document__",20,"","","",1,0,""],
"3gE",["Unit weight","Materials and Finishes",3,"autodesk.unit.unit:poundsForcePerCubicFoot-1.0.1","","Unit weight",0,0,"poundsForcePerCubicFoot"],
"3gI",["Calculated Supply Airflow","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinute-1.0.1","","Calculated Supply Airflow",8,0,"cubicFeetPerMinute"],
"3gM",["d","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"3gQ",["Number of Elements","Mechanical",20,"","","Number of Elements",8,0,""],
"3gU",["Revision Sequence","Other",20,"","","Revision Sequence",0,0,""],
"3gY",["Right Attachment","Graphics",20,"","","Right Attachment",0,0,""],
"3wE",["Compression perpendicular to grain","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Compression perpendicular to grain",0,0,"kipsPerSquareInch"],
"3wI",["Cross-Section","Constraints",20,"","","Cross-Section",8,0,""],
"3wM",["Revision Number","Other",20,"","","Revision Number",8,0,""],
"3wQ",["System Name","Mechanical",20,"","","System Name",8,0,""],
"3wU",["y Justification","Geometric Position",20,"","","y Justification",0,0,""],
"3wY",["Lon","Geolocation",3,"autodesk.unit.unit:degrees-1.0.1","","Lon",8,0,"degrees"],
"4AE",["Operation","IFC Parameters",20,"","","Operation",0,0,""],
"4AI",["NK1","Materials and Finishes",20,"","","",0,0,""],
"4AM",["Section Name Key","Identity Data",20,"","","Section Name Key",8,0,""],
"4AQ",["Slope Angle","Dimensions",3,"autodesk.unit.unit:degrees-1.0.1","","Slope Angle",0,0,"degrees"],
"4AU",["Angle","Horizontal Grid",3,"autodesk.unit.unit:degrees-1.0.1","","Angle",0,0,"degrees"],
"4AY",["Coarse Poche Material","Graphics",20,"","","Coarse Poche Material",0,0,""],
"4QE",["Manually Adjusted","Analytical Alignment",1,"","","Manually Adjusted",8,0,""],
"4QI",["Position","Handrail 2",20,"","","Position",8,0,""],
"4QM",["Circuit Number","Electrical - Loads",20,"","","Circuit Number",8,0,""],
"4QQ",["Offset From Roof Base","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset From Roof Base",0,0,"feetFractionalInches"],
"4QU",["Vertical Align","Graphics",20,"","","Vertical Align",0,0,""],
"4QY",["Poisson ratio X","Materials and Finishes",3,"","","Poisson ratio X",0,0,""],
"4gE",["Start Extension","Geometric Position",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Start Extension",8,0,"feetFractionalInches"],
"4gI",["Volume","Dimensions",3,"autodesk.unit.unit:cubicFeet-1.0.1","","Volume",8,0,"cubicFeet"],
"4gM",["End with Riser","Risers",1,"","","End with Riser",0,0,""],
"4gQ",["Far Clip Active","Extents",1,"","","Far Clip Active",0,0,""],
"4gU",["Sticking","Materials and Finishes",20,"","","",0,0,""],
"4gY",["Minimum tensile strength","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Minimum tensile strength",0,0,"kipsPerSquareInch"],
"4wE",["ceilingHeight","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"4wI",["A","Structural",3,"autodesk.unit.unit:squareFeet-1.0.1","","",0,0,"squareFeet"],
"4wM",["Stringer Height","Stringers",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Stringer Height",8,0,"feetFractionalInches"],
"4wQ",["Door Width","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"4wU",["Section Box","Extents",1,"","","Section Box",0,0,""],
"4wY",["Compression parallel to grain","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Compression parallel to grain",0,0,"kipsPerSquareInch"],
"5AE",["Stringer Carriage Height","Stringers",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Stringer Carriage Height",8,0,"feetFractionalInches"],
"5AI",["Reference Label","Graphics",20,"","","Reference Label",8,0,""],
"5AM",["Background","Graphics",20,"","","Background",0,0,""],
"5AQ",["Mass Opening","Other",20,"","","Mass Opening",0,0,""],
"5AU",["Calculated Heating Load per area","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHourSquareFoot-1.0.1","","Calculated Heating Load per area",8,0,"britishThermalUnitsPerHourSquareFoot"],
"5AY",["Tread Thickness","Treads",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Tread Thickness",0,0,"feetFractionalInches"],
"5QE",["Post Material","Materials and Finishes",20,"","","",0,0,""],
"5QI",["Construction Type","Construction",20,"","","Construction Type",8,0,""],
"5QM",["Justification","Horizontal Grid",20,"","","Justification",8,0,""],
"5QQ",["Border 2 Type","Vertical Mullions",20,"","","Border 2 Type",0,0,""],
"5QU",["Sx","Structural",3,"","","",0,0,""],
"5QY",["Thermal Resistance (R)","Analytical Properties",3,"autodesk.unit.unit:hourSquareFootDegreesFahrenheitPerBritishThermalUnit-1.0.1","","Thermal Resistance (R)",8,0,"hourSquareFootDegreesFahrenheitPerBritishThermalUnit"],
"5gE",["Drawn By","Identity Data",20,"","","Drawn By",0,0,""],
"5gI",["Location Line Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Location Line Offset",8,0,"feetFractionalInches"],
"5gM",["Trim Width","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"5gQ",["Panel","Construction",20,"","","",0,0,""],
"5gU",["lintel","Materials and Finishes",20,"","","",0,0,""],
"5gY",["z Offset Value","Geometric Position",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","z Offset Value",0,0,"feetFractionalInches"],
"5wE",["Host","Constraints",20,"","","Host",8,0,""],
"5wI",["Base x Projection","Analytical Alignment",20,"","","Base x Projection",8,0,""],
"5wM",["Subcategory","Identity Data",20,"","","",8,0,""],
"5wQ",["Text Size","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Text Size",0,0,"fractionalInches"],
"5wU",["End Mx","Releases / Member Forces",1,"","","End Mx",8,0,""],
"5wY",["Room Calculation Point","Other",1,"","","Room Calculation Point",0,0,""],
"6AE",["End Fx","Releases / Member Forces",1,"","","End Fx",8,0,""],
"6AI",["Parts Visibility","Graphics",20,"","","Parts Visibility",0,0,""],
"6AM",["Poisson ratio","Materials and Finishes",3,"","","Poisson ratio",0,0,""],
"6AQ",["Coil Bypass","Energy Analysis",3,"autodesk.unit.unit:percentage-1.0.1","","Coil Bypass",0,0,"percentage"],
"6AU",["Property Set Name","Materials and Finishes",20,"","","Property Set Name",0,0,""],
"6AY",["Head Height","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Head Height",0,0,"feetFractionalInches"],
"6QE",["Assembly Code","Identity Data",20,"","","Assembly Code",8,0,""],
"6QI",["sash","Materials and Finishes",20,"","","",0,0,""],
"6QM",["Analytic Construction","Analytical Properties",20,"","","Analytic Construction",8,0,""],
"6QQ",["Glass","Materials and Finishes",20,"","","",0,0,""],
"6QU",["Closing Time","Energy Analysis",20,"","","Closing Time",0,0,""],
"6QY",["V/G Overrides Model","Graphics",20,"","","V/G Overrides Model",0,0,""],
"6gE",["Base Offset From Level","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Base Offset From Level",0,0,"feetFractionalInches"],
"6gI",["glass_thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"6gM",["Apply Nosing Profile","Treads",20,"","","Apply Nosing Profile",8,0,""],
"6gQ",["Show Area","Graphics",1,"","","",0,0,""],
"6gU",["Start Level Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Start Level Offset",0,0,"feetFractionalInches"],
"6gY",["Default Elevation","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Default Elevation",0,0,"feetFractionalInches"],
"6wE",["Series","Identity Data",20,"","","",8,0,""],
"6wI",["Detail Line","Graphics",1,"","","Detail Line",8,0,""],
"6wM",["Width","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"6wQ",["Far Clipping","Extents",2,"","","Far Clipping",0,0,""],
"6wU",["Schedule/Type","Mechanical",20,"","","Schedule/Type",0,0,""],
"6wY",["Minimum Tread Depth","Calculation Rules",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Minimum Tread Depth",0,0,"feetFractionalInches"],
"7AE",["Shininess","Materials and Finishes",20,"","","Shininess",0,0,""],
"7AI",["Railing Height","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Railing Height",8,0,"feetFractionalInches"],
"7AM",["Specified Power Load per area","Energy Analysis",3,"autodesk.unit.unit:wattsPerSquareFoot-1.0.1","","Specified Power Load per area",0,0,"wattsPerSquareFoot"],
"7AQ",["Shear modulus X","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Shear modulus X",0,0,"kipsPerSquareInch"],
"7AU",["End Join Cutback","Geometric Position",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","End Join Cutback",0,0,"feetFractionalInches"],
"7AY",["Height","Identity Data",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Height",8,0,"feetFractionalInches"],
"7QE",["Width","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Width",8,0,"feetFractionalInches"],
"7QI",["Project Number","Other",20,"","","Project Number",0,0,""],
"7QM",["Concrete Cantilever","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Concrete Cantilever",0,0,"feetFractionalInches"],
"7QQ",["Frame Material","Materials and Finishes",20,"","","",0,0,""],
"7QU",["Supply Horizontal Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"7QY",["Inlet Spud Size","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"7gE",["Top Material","Materials and Finishes",20,"","","",0,0,""],
"7gI",["Lightweight","Materials and Finishes",1,"","","Lightweight",0,0,""],
"7gM",["Column Style","Constraints",20,"","","Column Style",0,0,""],
"7gQ",["Border 1 Type","Vertical Mullions",20,"","","Border 1 Type",0,0,""],
"7gU",["Default Analysis Display Style","Graphics",20,"","","Default Analysis Display Style",0,0,""],
"7gY",["Base Fx","Releases / Member Forces",1,"","","Base Fx",8,0,""],
"7wE",["Revision","Identity Data",20,"","","Revision",0,0,""],
"7wI",["child","__child__",11,"","","",1,0,""],
"7wM",["Structural Usage","Structural",20,"","","Structural Usage",8,0,""],
"7wQ",["Position","Construction",20,"","","Position",0,0,""],
"7wU",["Referencing Detail","Identity Data",20,"","","Referencing Detail",8,0,""],
"7wY",["Number","Horizontal Grid",20,"","","Number",8,0,""],
"8AE",["Wall Join Display","Graphics",20,"","","Wall Join Display",8,0,""],
"8AI",["Defines Roof Slope","Constraints",1,"","","Defines Roof Slope",0,0,""],
"8AM",["Dimension Line Extension","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Dimension Line Extension",0,0,"fractionalInches"],
"8AQ",["Glow","Materials and Finishes",1,"","","Glow",0,0,""],
"8AU",["End Segment Color","Graphics",2,"","","End Segment Color",0,0,""],
"8AY",["Level","__internalref__",11,"","","",1,0,""],
"8QE",["Support Plate Offset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"8QI",["Outdoor Airflow","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinute-1.0.1","","Outdoor Airflow",8,0,"cubicFeetPerMinute"],
"8QM",["Power Load","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Power Load",8,0,"britishThermalUnitsPerHour"],
"8QQ",["Base Constraint","Constraints",20,"","","Base Constraint",8,0,""],
"8QU",["Interior Tick Mark","Graphics",20,"","","Interior Tick Mark",8,0,""],
"8QY",["Current Revision Issued","Identity Data",1,"","","Current Revision Issued",8,0,""],
"8gE",["Member Forces","Releases / Member Forces",20,"","","Member Forces",0,0,""],
"8gI",["Phase Created","Phasing",20,"","","Phase Created",8,0,""],
"8gM",["Head R2","Materials and Finishes",20,"","","",0,0,""],
"8gQ",["W","Structural",3,"","","",0,0,""],
"8gU",["Category","__category__",20,"","","",1,0,""],
"8gY",["Transparency","Materials and Finishes",20,"","","Transparency",0,0,""],
"8wE",["Room Number","Other",20,"","","Room Number",9,0,""],
"8wI",["Number of studs","Structural",20,"","","Number of studs",0,0,""],
"8wM",["Extend into wall (to core)","Constraints",1,"","","Extend into wall (to core)",0,0,""],
"8wQ",["Gross Floor Area","Dimensions",3,"autodesk.unit.unit:squareFeet-1.0.1","","Gross Floor Area",8,0,"squareFeet"],
"8wU",["Model","Identity Data",20,"","","Model",8,0,""],
"8wY",["Formatting","Other",20,"","","Formatting",0,0,""],
"9AE",["brick columns","Materials and Finishes",20,"","","",0,0,""],
"9AI",["ADA Compliant","Identity Data",1,"","","",0,0,""],
"9AM",["Apparent Load","Electrical - Loads",3,"autodesk.unit.unit:voltAmperes-1.0.1","","",0,0,"voltAmperes"],
"9AQ",["wood","Materials and Finishes",20,"","","",0,0,""],
"9AU",["Always vertical","Other",1,"","","Always vertical",0,0,""],
"9AY",["Architectural Design Manual","Identity Data",20,"","","",0,0,""],
"9QE",["Base Extension Method","Analytical Alignment",20,"","","Base Extension Method",0,0,""],
"9QI",["Finish","Materials and Finishes",20,"","","Finish",8,0,""],
"9QM",["Mass Roof","Other",20,"","","Mass Roof",0,0,""],
"9QQ",["Post","Construction",1,"","","Post",0,0,""],
"9QU",["Rail Connections","Construction",20,"","","Rail Connections",0,0,""],
"9QY",["Text Offset","Text",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Text Offset",0,0,"fractionalInches"],
"9gE",["Approved By","Identity Data",20,"","","Approved By",0,0,""],
"9gI",["Pilaster Thickness","Identity Data",20,"","","",0,0,""],
"9gM",["Heating Information","Energy Analysis",20,"","","Heating Information",0,0,""],
"9gQ",["Alternate Units Suffix","Text",20,"","","Alternate Units Suffix",0,0,""],
"9gU",["Default Setback","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Default Setback",0,0,"feetFractionalInches"],
"9gY",["Type","Handrail 1",20,"","","Type",0,0,""],
"9wE",["Symbolic Representation","Other",20,"","","Symbolic Representation",0,0,""],
"9wI",["Underlay Orientation","Underlay",20,"","","Underlay Orientation",8,0,""],
"9wM",["Nominal Length","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"9wQ",["Horizontal Scale","Dimensions",3,"","","Horizontal Scale",0,0,""],
"9wU",["Up arrow","Graphics",1,"","","Up arrow",0,0,""],
"9wY",["Heat Transfer Coefficient (U)","Analytical Properties",3,"autodesk.unit.unit:britishThermalUnitsPerHourSquareFootDegreeFahrenheit-1.0.1","","Heat Transfer Coefficient (U)",8,0,"britishThermalUnitsPerHourSquareFootDegreeFahrenheit"],
"AQ",["Spacing_of_Bars","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Ag",["Code Name","Identity Data",20,"","","Code Name",8,0,""],
"Aw",["Tick Mark Line Weight","Graphics",20,"","","Tick Mark Line Weight",0,0,""],
"BA",["Centerline Pattern","Graphics",20,"","","Centerline Pattern",0,0,""],
"BQ",["Trim","Materials and Finishes",20,"","","",0,0,""],
"Bg",["MasterFormat 2004","Identity Data",20,"","","",8,0,""],
"Bw",["Floor Finish","Identity Data",20,"","","Floor Finish",0,0,""],
"CA",["Border 2 Type","Horizontal Mullions",20,"","","Border 2 Type",0,0,""],
"CQ",["D1","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Cg",["Round Connector Dimension","Dimensions",20,"","","Round Connector Dimension",0,0,""],
"Cw",["glass_inset2","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"DA",["Mass Interior Wall","Other",20,"","","Mass Interior Wall",0,0,""],
"DQ",["Computation Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Computation Height",8,0,"feetFractionalInches"],
"Dg",["Text Size","Text",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Text Size",0,0,"fractionalInches"],
"Dw",["glass","Materials and Finishes",20,"","","",0,0,""],
"EA",["Sill","Materials and Finishes",20,"","","",0,0,""],
"EQ",["doorframe thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Eg",["Landing Height Adjustment","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Landing Height Adjustment",8,0,"feetFractionalInches"],
"Ew",["Occupancy","Identity Data",20,"","","Occupancy",0,0,""],
"FA",["Down label","Graphics",1,"","","Down label",8,0,""],
"FQ",["V/G Overrides Analytical Model","Graphics",20,"","","V/G Overrides Analytical Model",0,0,""],
"Fg",["Outdoor Air per Person","Energy Analysis",3,"autodesk.unit.unit:cubicFeetPerMinute-1.0.1","","Outdoor Air per Person",0,0,"cubicFeetPerMinute"],
"Fw",["Schedule Level","Constraints",20,"","","Schedule Level",0,0,""],
"GA",["Wall Closure","Construction",20,"","","Wall Closure",0,0,""],
"GQ",["Primary Air Inlet Diameter","Dimensions",3,"autodesk.unit.unit:fractionalInches-1.0.0","","",8,0,"fractionalInches"],
"Gg",["Member Number","Identity Data",20,"","","Member Number",0,0,""],
"Gw",["schema_name","__document__",20,"","","",1,0,""],
"HA",["Referencing Sheet","Identity Data",20,"","","Referencing Sheet",8,0,""],
"HQ",["Suppress Spaces","Text",1,"","","Suppress Spaces",0,0,""],
"Hg",["Roughness","Mechanical",3,"autodesk.unit.unit:feet-1.0.1","","Roughness",0,0,"feet"],
"Hw",["Calculated Cooling Load per area","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHourSquareFoot-1.0.1","","Calculated Cooling Load per area",8,0,"britishThermalUnitsPerHourSquareFoot"],
"IA",["Limit Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Limit Offset",0,0,"feetFractionalInches"],
"IQ",["End z Projection","Analytical Alignment",20,"","","End z Projection",8,0,""],
"Ig",["Witness Line Extension","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Witness Line Extension",0,0,"fractionalInches"],
"Iw",["Trim Projection - Int.","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"JA",["tf","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"JQ",["Work Plane Grid Spacing","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Work Plane Grid Spacing",0,0,"feetFractionalInches"],
"Jg",["Bottom Rail Height","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Jw",["Riser to Tread Connection","Risers",20,"","","Riser to Tread Connection",8,0,""],
"KA",["Sy","Structural",3,"","","",0,0,""],
"KQ",["Base Fy","Releases / Member Forces",1,"","","Base Fy",8,0,""],
"Kg",["Bending reinforcement","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Bending reinforcement",0,0,"kipsPerSquareInch"],
"Kw",["Phase","Phasing",20,"","","Phase",8,0,""],
"LA",["Dehumidification Set Point","Energy Analysis",3,"autodesk.unit.unit:percentage-1.0.1","","Dehumidification Set Point",8,0,"percentage"],
"LQ",["Mark","Identity Data",20,"","","Mark",8,0,""],
"Lg",["Station","Constraints",20,"","","",0,0,""],
"Lw",["Baluster Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Baluster Height",0,0,"feetFractionalInches"],
"MA",["Plenum Air Inlet Length","Dimensions",3,"autodesk.unit.unit:fractionalInches-1.0.0","","",0,0,"fractionalInches"],
"MQ",["Structural","Identity Data",1,"","","Structural",0,0,""],
"Mg",["Keynote","Identity Data",20,"","","Keynote",8,0,""],
"Mw",["Level","Constraints",20,"","","Level",8,0,""],
"NA",["Plate Offset From Base","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Plate Offset From Base",0,0,"feetFractionalInches"],
"NQ",["Material for Model Behavior","Structural",20,"","","Material for Model Behavior",0,0,""],
"Ng",["Coarse Scale Fill Color","Graphics",2,"","","Coarse Scale Fill Color",0,0,""],
"Nw",["Frame Width","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"OA",["Absorptance","Analytical Properties",3,"","","Absorptance",0,0,""],
"OQ",["Trim Stringers at Top","Stringers",20,"","","Trim Stringers at Top",0,0,""],
"Og",["Plate Thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"Ow",["Position","Handrail 1",20,"","","Position",8,0,""],
"PA",["Power Schedule","Energy Analysis",20,"","","Power Schedule",0,0,""],
"PQ",["Always export as geometry","Structural",1,"","","Always export as geometry",0,0,""],
"Pg",["End Extension","Geometric Position",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","End Extension",8,0,"feetFractionalInches"],
"Pw",["Trim Exterior Material","Materials and Finishes",20,"","","",0,0,""],
"QA",["Moves With Grids","Constraints",1,"","","Moves With Grids",0,0,""],
"QQ",["Cold Water Connection Diameter","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Qg",["Classification","Mechanical",20,"","","Classification",8,0,""],
"Qw",["Primary Air Flow","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinute-1.0.1","","",8,0,"cubicFeetPerMinute"],
"RA",["Sheet Issue Date","Identity Data",20,"","","Sheet Issue Date",0,0,""],
"RQ",["Cooling Set Point","Energy Analysis",3,"autodesk.unit.unit:fahrenheit-1.0.1","","Cooling Set Point",8,0,"fahrenheit"],
"Rg",["Image","Identity Data",20,"","","Image",8,0,""],
"Rw",["Calculations","Mechanical",20,"","","Calculations",0,0,""],
"SA",["System Equipment","Mechanical",20,"","","System Equipment",8,0,""],
"SQ",["Show Extension Line","Graphics",1,"","","Show Extension Line",0,0,""],
"Sg",["height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Sw",["Wall offset","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Wall offset",0,0,"feetFractionalInches"],
"TA",["Revisions Date","Identity Data",20,"","","",8,0,""],
"TQ",["Bold","Title Text",1,"","","Bold",0,0,""],
"Tg",["Leader/Border Offset","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Leader/Border Offset",0,0,"fractionalInches"],
"Tw",["Poisson ratio Y","Materials and Finishes",3,"","","Poisson ratio Y",8,0,""],
"UA",["Plenum Lighting Contribution","Energy Analysis",3,"autodesk.unit.unit:percentage-1.0.1","","Plenum Lighting Contribution",0,0,"percentage"],
"UQ",["Type Comments","Identity Data",20,"","","Type Comments",8,0,""],
"Ug",["Middle Stringers","Stringers",20,"","","Middle Stringers",0,0,""],
"Uw",["Landing Carriage Height","Stringers",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Landing Carriage Height",8,0,"feetFractionalInches"],
"VA",["Base Radius","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"VQ",["Shape","Construction",20,"","","Shape",0,0,""],
"Vg",["frame_thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Vw",["Corner Mullion","Construction",1,"","","Corner Mullion",8,0,""],
"WA",["Height","Handrail 2",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Height",8,0,"feetFractionalInches"],
"WQ",["inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Wg",["yz Justification","Geometric Position",20,"","","yz Justification",0,0,""],
"Ww",["Line Pattern","Graphics",20,"","","Line Pattern",0,0,""],
"XA",["Node Number","Identity Data",20,"","","Node Number",0,0,""],
"XQ",["Calculated Heating Load","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Calculated Heating Load",8,0,"britishThermalUnitsPerHour"],
"Xg",["Alignment Method","Analytical Alignment",20,"","","Alignment Method",0,0,""],
"Xw",["Show Title","Graphics",20,"","","Show Title",0,0,""],
"YA",["Description","Identity Data",20,"","","Description",8,0,""],
"YQ",["Column Location Mark","Constraints",20,"","","Column Location Mark",8,0,""],
"Yg",["topCut","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"Yw",["Primary Air Pressure Drop","Mechanical",3,"autodesk.unit.unit:inchesOfWater60DegreesFahrenheit-1.0.1","","",0,0,"inchesOfWater60DegreesFahrenheit"],
"ZA",["Calculated Supply Airflow per area","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinuteSquareFoot-1.0.1","","Calculated Supply Airflow per area",8,0,"cubicFeetPerMinuteSquareFoot"],
"ZQ",["Base is Attached","Constraints",1,"","","Base is Attached",8,0,""],
"Zg",["Interior Tick Mark Display","Graphics",20,"","","Interior Tick Mark Display",0,0,""],
"Zw",["95 CSI","Identity Data",20,"","","",8,0,""],
"_AE",["Perimeter Zone Depth","Energy Analytical Model",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Perimeter Zone Depth",8,0,"feetFractionalInches"],
"_AI",["Underline","Text",1,"","","Underline",0,0,""],
"_AM",["Nosing Length","Treads",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Nosing Length",0,0,"feetFractionalInches"],
"_AQ",["View Name","Identity Data",20,"","","View Name",8,0,""],
"_AU",["Gross Surface Area","Dimensions",3,"autodesk.unit.unit:squareFeet-1.0.1","","Gross Surface Area",8,0,"squareFeet"],
"_AY",["Trim Projection - Ext.","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"_QE",["Subclass","Materials and Finishes",20,"","","Subclass",0,0,""],
"_QI",["Fields","Other",20,"","","Fields",0,0,""],
"_QM",["Air Outlet Half Width","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"_QQ",["Date/Time Stamp","Identity Data",20,"","","Date/Time Stamp",8,0,""],
"_QU",["Minimum yield stress","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Minimum yield stress",0,0,"kipsPerSquareInch"],
"_QY",["thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"_gE",["Top is Attached","Constraints",1,"","","Top is Attached",8,0,""],
"_gI",["Young modulus Z","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Young modulus Z",8,0,"kipsPerSquareInch"],
"_gM",["Average Vertical Void Height Threshold","Energy Analytical Model",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Average Vertical Void Height Threshold",0,0,"feetFractionalInches"],
"_gQ",["Analyze As","Analytical Model",20,"","","Analyze As",0,0,""],
"_gU",["Young modulus","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Young modulus",0,0,"kipsPerSquareInch"],
"_gY",["Border 1 Type","Horizontal Mullions",20,"","","Border 1 Type",0,0,""],
"_wE",["Door Material","Materials and Finishes",20,"","","",0,0,""],
"_wI",["Leader Arrowhead","Graphics",20,"","","Leader Arrowhead",0,0,""],
"_wM",["Top Extension Method","Analytical Alignment",20,"","","Top Extension Method",0,0,""],
"_wQ",["parent","__parent__",11,"","","",1,0,""],
"_wU",["Cut Length","Structural",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Cut Length",8,0,"feetFractionalInches"],
"_wY",["Baluster Material","Materials and Finishes",20,"","","",0,0,""],
"aA",["Horizontal Align","Graphics",20,"","","Horizontal Align",0,0,""],
"aQ",["Peak Cooling Load","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Peak Cooling Load",8,0,"britishThermalUnitsPerHour"],
"ag",["Depth Cueing","Graphics",20,"","","Depth Cueing",0,0,""],
"aw",["Defines Constant Height","Constraints",1,"","","Defines Constant Height",8,0,""],
"bA",["Swing Angle 2D","Graphics",3,"autodesk.unit.unit:degrees-1.0.1","","",0,0,"degrees"],
"bQ",["Sorting/Grouping","Other",20,"","","Sorting/Grouping",0,0,""],
"bg",["Origin Level Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Origin Level Offset",8,0,"feetFractionalInches"],
"bw",["Cutoff Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Cutoff Offset",8,0,"feetFractionalInches"],
"cA",["Toilet Partition","Materials and Finishes",20,"","","",0,0,""],
"cQ",["Size","Text",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Size",0,0,"fractionalInches"],
"cg",["z Projection","Analytical Alignment",20,"","","z Projection",8,0,""],
"cw",["Airflow per area","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinuteSquareFoot-1.0.1","","Airflow per area",8,0,"cubicFeetPerMinuteSquareFoot"],
"dA",["Sheet","__internalref__",11,"","","",1,0,""],
"dQ",["Start Extension Calculation","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"dg",["Use Top Rail","Top Rail",1,"","","Use Top Rail",0,0,""],
"dw",["frame thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"eA",["Calculation Rules","Calculation Rules",20,"","","Calculation Rules",0,0,""],
"eQ",["Start Fz","Releases / Member Forces",1,"","","Start Fz",0,0,""],
"eg",["Infiltration Airflow per area","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinuteSquareFoot-1.0.1","","Infiltration Airflow per area",8,0,"cubicFeetPerMinuteSquareFoot"],
"ew",["Leader Tick Mark","Graphics",20,"","","Leader Tick Mark",0,0,""],
"fA",["Centerline Symbol","Graphics",20,"","","Centerline Symbol",0,0,""],
"fQ",["Baseline Offset","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Baseline Offset",8,0,"fractionalInches"],
"fg",["Material Type","Materials and Finishes",20,"","","Material Type",8,0,""],
"fw",["Leader","Graphics",1,"","","Leader",0,0,""],
"gAE",["K4","Materials and Finishes",20,"","","",0,0,""],
"gAI",["Associated Level","Extents",20,"","","Associated Level",8,0,""],
"gAM",["Actual Riser Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Actual Riser Height",8,0,"feetFractionalInches"],
"gAQ",["Detail Level","Graphics",20,"","","Detail Level",0,0,""],
"gAU",["Headrail Material","Identity Data",20,"","","",0,0,""],
"gAY",["Actual Tread Depth","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Actual Tread Depth",0,0,"feetFractionalInches"],
"gAc",["w1","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"gQE",["frame_depth","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"gQI",["Top Release","Releases / Member Forces",20,"","","Top Release",0,0,""],
"gQM",["Mass Exterior Wall","Other",20,"","","Mass Exterior Wall",0,0,""],
"gQQ",["Structural Material","Materials and Finishes",20,"","","Structural Material",8,0,""],
"gQU",["Project Phase","Energy Analytical Model",20,"","","Project Phase",0,0,""],
"gQY",["Start Release","Releases / Member Forces",20,"","","Start Release",0,0,""],
"gQc",["Other Options","Advanced",20,"","","Other Options",0,0,""],
"ggE",["Shear strength modification","Materials and Finishes",3,"","","Shear strength modification",8,0,""],
"ggI",["Occupant","Identity Data",20,"","","",0,0,""],
"ggM",["Riser Material","Materials and Finishes",20,"","","Riser Material",8,0,""],
"ggQ",["Rail Structure (Non-Continuous)","Construction",20,"","","Rail Structure (Non-Continuous)",0,0,""],
"ggU",["Base Mx","Releases / Member Forces",1,"","","Base Mx",8,0,""],
"ggY",["Text Font","Text",20,"","","Text Font",0,0,""],
"ggc",["Peak Latent Cooling Load","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Peak Latent Cooling Load",8,0,"britishThermalUnitsPerHour"],
"gwE",["Visibility/Graphics Overrides","Graphics",20,"","","Visibility/Graphics Overrides",0,0,""],
"gwI",["Embedded Schedule","Other",20,"","","Embedded Schedule",0,0,""],
"gwM",["Alternate Units Prefix","Text",20,"","","Alternate Units Prefix",0,0,""],
"gwQ",["Baluster Offset","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Baluster Offset",0,0,"feetFractionalInches"],
"gwU",["Start Mx","Releases / Member Forces",1,"","","Start Mx",0,0,""],
"gwY",["Solar Heat Gain Coefficient","Analytical Properties",3,"","","Solar Heat Gain Coefficient",8,0,""],
"gwc",["Scale Value    1:","Graphics",20,"","","Scale Value    1:",8,0,""],
"hAE",["Dependency","Identity Data",20,"","","Dependency",8,0,""],
"hAI",["Host Family","__internalref__",11,"","","",1,0,""],
"hAM",["Elevation from Level","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Elevation from Level",8,0,"feetFractionalInches"],
"hAQ",["Area","Energy Analysis",3,"autodesk.unit.unit:squareFeet-1.0.1","","Area",8,0,"squareFeet"],
"hAU",["Offset From Level","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset From Level",0,0,"feetFractionalInches"],
"hAY",["Latches","Identity Data",20,"","","",0,0,""],
"hAc",["Equality Text","Other",20,"","","Equality Text",0,0,""],
"hQE",["V/G Overrides Annotation","Graphics",20,"","","V/G Overrides Annotation",0,0,""],
"hQI",["Associated Datum","Extents",20,"","","Associated Datum",0,0,""],
"hQM",["Offset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"hQQ",["Callout Tag","Graphics",20,"","","Callout Tag",0,0,""],
"hQU",["Range: Base Level","Underlay",20,"","","Range: Base Level",0,0,""],
"hQY",["Bottom_offset","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"hQc",["Rebar Cover - Bottom Face","Structural",20,"","","Rebar Cover - Bottom Face",0,0,""],
"hgE",["Air Changes per Hour","Mechanical - Flow",3,"","","Air Changes per Hour",8,0,""],
"hgI",["Outside Diameter","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"hgM",["Appearance","Other",20,"","","Appearance",0,0,""],
"hgQ",["URL","Identity Data",20,"","","URL",8,0,""],
"hgU",["Shadows","Graphics",20,"","","Shadows",0,0,""],
"hgY",["Size","Title Text",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Size",0,0,"fractionalInches"],
"hgc",["Class","Materials and Finishes",20,"","","Class",8,0,""],
"hwE",["Nosing Profile","Treads",20,"","","Nosing Profile",0,0,""],
"hwI",["Spud Radius","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"hwM",["Story Above","Constraints",20,"","","Story Above",0,0,""],
"hwQ",["b","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"hwU",["Lighting Schedule","Energy Analysis",20,"","","Lighting Schedule",0,0,""],
"hwY",["bf","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"hwc",["Thermal expansion coefficient X","Materials and Finishes",3,"autodesk.unit.unit:inverseDegreesFahrenheit-1.0.1","","Thermal expansion coefficient X",0,0,"inverseDegreesFahrenheit"],
"iAE",["Brace","Materials and Finishes",20,"","","",0,0,""],
"iAI",["Can host rebar","Structural",1,"","","Can host rebar",0,0,""],
"iAM",["Color Scheme Location","Graphics",20,"","","Color Scheme Location",0,0,""],
"iAQ",["door_frame_thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"iAU",["Base My","Releases / Member Forces",1,"","","Base My",8,0,""],
"iAY",["Values Displayed","Graphics",20,"","","Values Displayed",0,0,""],
"iAc",["Width Handrail Hold","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"iQE",["Up label","Graphics",1,"","","Up label",0,0,""],
"iQI",["Behavior","Materials and Finishes",20,"","","Behavior",0,0,""],
"iQM",["Detail Number","Graphics",20,"","","Detail Number",0,0,""],
"iQQ",["Label","Identity Data",20,"","","",0,0,""],
"iQU",["Room Name","Identity Data",20,"","","Room Name",8,0,""],
"iQY",["Depth Clipping","Extents",2,"","","Depth Clipping",0,0,""],
"iQc",["Space Type","Energy Analysis",20,"","","Space Type",8,0,""],
"igE",["Ceiling Finish","Identity Data",20,"","","Ceiling Finish",0,0,""],
"igI",["Width Factor","Text",3,"","","Width Factor",0,0,""],
"igM",["Seat","Identity Data",20,"","","",0,0,""],
"igQ",["Rotation on Sheet","Graphics",20,"","","Rotation on Sheet",0,0,""],
"igU",["Frame Projection Ext.","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"igY",["Show Hidden Lines","Graphics",20,"","","Show Hidden Lines",0,0,""],
"igc",["Species","Materials and Finishes",20,"","","Species",0,0,""],
"iwE",["Scope Box","Extents",20,"","","Scope Box",0,0,""],
"iwI",["Glass Pane Material","Materials and Finishes",20,"","","",0,0,""],
"iwM",["Actual Number of Risers","Dimensions",20,"","","Actual Number of Risers",8,0,""],
"iwQ",["Revision Description","Other",20,"","","Revision Description",8,0,""],
"iwU",["Bottom Rail","Materials and Finishes",20,"","","",0,0,""],
"iwY",["Sill Height","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Sill Height",0,0,"feetFractionalInches"],
"iwc",["K2","Materials and Finishes",20,"","","",0,0,""],
"jAE",["Rendering Settings","Camera",20,"","","Rendering Settings",0,0,""],
"jAI",["Mass Floors","Dimensions",20,"","","Mass Floors",0,0,""],
"jAM",["Outdoor Airflow per person","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinute-1.0.1","","Outdoor Airflow per person",8,0,"cubicFeetPerMinute"],
"jAQ",["End Segment Weight","Graphics",20,"","","End Segment Weight",0,0,""],
"jAU",["Waste Connection Radius","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"jAY",["Frame Projection Int.","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"jAc",["Layout","Vertical Grid",20,"","","Layout",0,0,""],
"jQE",["_RFN","__category__",20,"","","",1,0,""],
"jQI",["Underside of Winder","Construction",20,"","","Underside of Winder",8,0,""],
"jQM",["Base Extension Distance","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Base Extension Distance",8,0,"feetFractionalInches"],
"jQQ",["Open Stringer Offset","Stringers",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Open Stringer Offset",8,0,"feetFractionalInches"],
"jQU",["Material","Materials and Finishes",20,"","","Material",8,0,""],
"jQY",["kr","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"jQc",["Elevation Mark Use","Other",20,"","","Elevation Mark Use",0,0,""],
"jgE",["Supply Verticall Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"jgI",["instanceof_objid","__instanceof__",11,"","","",1,0,""],
"jgM",["Height (pixels)","Identity Data",20,"","","Height (pixels)",8,0,""],
"jgQ",["Revision Date","Identity Data",20,"","","Revision Date",8,0,""],
"jgU",["Trim Projection Int","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"jgY",["Angle","Constraints",3,"autodesk.unit.unit:degrees-1.0.1","","Angle",0,0,"degrees"],
"jgc",["System Color Schemes","Graphics",20,"","","System Color Schemes",0,0,""],
"jwE",["Related to Mass","Constraints",1,"","","Related to Mass",8,0,""],
"jwI",["Display Model","Graphics",20,"","","Display Model",0,0,""],
"jwM",["Tick Mark","Graphics",20,"","","Tick Mark",0,0,""],
"jwQ",["Top Fy","Releases / Member Forces",1,"","","Top Fy",8,0,""],
"jwU",["Number","Identity Data",20,"","","Number",0,0,""],
"jwY",["Door Panel","Materials and Finishes",20,"","","",0,0,""],
"jwc",["File Path","Other",20,"","","File Path",8,0,""],
"kAE",["Define Thermal Properties by","Analytical Properties",20,"","","Define Thermal Properties by",8,0,""],
"kAI",["Spacing","Horizontal Grid",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Spacing",8,0,"feetFractionalInches"],
"kAM",["SmartBIM Object Created By","Identity Data",20,"","","",8,0,""],
"kAQ",["Calculated Area per Cooling Load","Energy Analysis",3,"autodesk.unit.unit:squareFeetPerTonOfRefrigeration-1.0.1","","Calculated Area per Cooling Load",8,0,"squareFeetPerTonOfRefrigeration"],
"kAU",["Revisions on Sheet","Identity Data",20,"","","Revisions on Sheet",0,0,""],
"kAY",["Name","Materials and Finishes",20,"","","Name",8,0,""],
"kAc",["Service Type","Energy Analysis",20,"","","Service Type",0,0,""],
"kQE",["Base Connection","Structural",20,"","","Base Connection",0,0,""],
"kQI",["Down arrow","Graphics",1,"","","Down arrow",8,0,""],
"kQM",["Base Level","Constraints",20,"","","Base Level",8,0,""],
"kQQ",["Roughness","Analytical Properties",20,"","","Roughness",0,0,""],
"kQU",["OmniClass Title","Identity Data",20,"","","OmniClass Title",8,0,""],
"kQY",["Gross Area","Dimensions",3,"autodesk.unit.unit:squareFeet-1.0.1","","Gross Area",8,0,"squareFeet"],
"kQc",["Plenum Air Flow","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinute-1.0.1","","",8,0,"cubicFeetPerMinute"],
"kgE",["k2","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"kgI",["Graphic Overrides","Graphics",20,"","","Graphic Overrides",0,0,""],
"kgM",["Cross-Section Rotation","Constraints",3,"autodesk.unit.unit:degrees-1.0.1","","Cross-Section Rotation",0,0,"degrees"],
"kgQ",["Equality Display","Other",20,"","","Equality Display",0,0,""],
"kgU",["Default Sill Height","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"kgY",["Witness Line Gap to Element","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Witness Line Gap to Element",0,0,"fractionalInches"],
"kgc",["Project Issue Date","Other",20,"","","Project Issue Date",0,0,""],
"kwE",["Number","Vertical Grid",20,"","","Number",8,0,""],
"kwI",["ElementId","__revit__",20,"","","",1,0,""],
"kwM",["Tab Size","Text",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Tab Size",0,0,"fractionalInches"],
"kwQ",["Top Rail","Materials and Finishes",20,"","","",0,0,""],
"kwU",["End Level Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","End Level Offset",0,0,"feetFractionalInches"],
"kwY",["Show Up arrow in all views","Graphics",1,"","","Show Up arrow in all views",0,0,""],
"kwc",["Client Name","Other",20,"","","Client Name",0,0,""],
"lAE",["Grade","Materials and Finishes",20,"","","Grade",0,0,""],
"lAI",["Rough Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Rough Height",0,0,"feetFractionalInches"],
"lAM",["Height","Handrail 1",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Height",8,0,"feetFractionalInches"],
"lAQ",["Visable","Graphics",1,"","","",0,0,""],
"lAU",["WFU","Mechanical",3,"","","WFU",0,0,""],
"lAY",["Department","Identity Data",20,"","","Department",0,0,""],
"lAc",["Left Attachment","Graphics",20,"","","Left Attachment",0,0,""],
"lQE",["Air Changes per Hour","Energy Analysis",3,"","","Air Changes per Hour",0,0,""],
"lQI",["Defines Slope","Constraints",1,"","","Defines Slope",8,0,""],
"lQM",["Perimeter","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Perimeter",8,0,"feetFractionalInches"],
"lQQ",["Head L1","Materials and Finishes",20,"","","",0,0,""],
"lQU",["View Range","Extents",20,"","","View Range",0,0,""],
"lQY",["Top Fz","Releases / Member Forces",1,"","","Top Fz",8,0,""],
"lQc",["Keep Readable","Graphics",1,"","","Keep Readable",0,0,""],
"lgE",["Unconnected Height","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Unconnected Height",8,0,"feetFractionalInches"],
"lgI",["Symbol","Graphics",20,"","","Symbol",0,0,""],
"lgM",["sidestone","Materials and Finishes",20,"","","",0,0,""],
"lgQ",["Stringer Material","Materials and Finishes",20,"","","Stringer Material",8,0,""],
"lgU",["N/S","Identity Data",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","N/S",8,0,"feetFractionalInches"],
"lgY",["Sheet Name","Identity Data",20,"","","Sheet Name",8,0,""],
"lgc",["Function","Construction",20,"","","Function",0,0,""],
"lwE",["Middle Rail","Materials and Finishes",20,"","","",0,0,""],
"lwI",["Casing","Text",20,"","","",0,0,""],
"lwM",["Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset",8,0,"feetFractionalInches"],
"lwQ",["Base Alignment Method","Analytical Alignment",20,"","","Base Alignment Method",0,0,""],
"lwU",["glass_inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"lwY",["Top Extension Distance","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Top Extension Distance",8,0,"feetFractionalInches"],
"lwc",["door","Materials and Finishes",20,"","","",0,0,""],
"mAE",["Width","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"mAI",["End Attachment Type","Structural",20,"","","End Attachment Type",0,0,""],
"mAM",["Trim Width - Interior","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"mAQ",["Current Revision","Identity Data",20,"","","Current Revision",8,0,""],
"mAU",["Latent Heat Gain per person","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Latent Heat Gain per person",0,0,"britishThermalUnitsPerHour"],
"mAY",["Loaded from file","Identity Data",20,"","","Loaded from file",8,0,""],
"mAc",["Radius","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"mQE",["Occupancy Schedule","Energy Analysis",20,"","","Occupancy Schedule",0,0,""],
"mQI",["OmniClass Number","Identity Data",20,"","","OmniClass Number",8,0,""],
"mQM",["Overhang","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Overhang",0,0,"feetFractionalInches"],
"mQQ",["Keystone Spacing","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"mQU",["Adjust for Mullion Size","Horizontal Grid",1,"","","Adjust for Mullion Size",8,0,""],
"mQY",["Analytical Surface Resolution","Energy Analytical Model",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Analytical Surface Resolution",0,0,"feetFractionalInches"],
"mQc",["Material","Mechanical",20,"","","Material",0,0,""],
"mgE",["Location Line","Constraints",20,"","","Location Line",8,0,""],
"mgI",["In-Plane Projection","Analytical Alignment",20,"","","In-Plane Projection",0,0,""],
"mgM",["Waste Outlet Connection Radius","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"mgQ",["Top Fx","Releases / Member Forces",1,"","","Top Fx",8,0,""],
"mgU",["Current Revision Description","Identity Data",20,"","","Current Revision Description",8,0,""],
"mgY",["Smoothness","Materials and Finishes",20,"","","Smoothness",0,0,""],
"mgc",["Fire Rating","Identity Data",20,"","","Fire Rating",0,0,""],
"mwE",["Base Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Base Offset",8,0,"feetFractionalInches"],
"mwI",["Ix","Structural",3,"","","",0,0,""],
"mwM",["Top Cut Angle","Dimensions",3,"autodesk.unit.unit:degrees-1.0.1","","Top Cut Angle",0,0,"degrees"],
"mwQ",["Sun path size (%)","Display",20,"","","Sun path size (%)",0,0,""],
"mwU",["Panel and Door Thickness","Identity Data",20,"","","",0,0,""],
"mwY",["Manufacturer","Identity Data",20,"","","Manufacturer",8,0,""],
"mwc",["SideK-top","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"nAE",["Center_Keystone_Base","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"nAI",["Reference Level","Constraints",20,"","","Reference Level",8,0,""],
"nAM",["Ramp Max Slope (1/x)","Dimensions",3,"","","Ramp Max Slope (1/x)",0,0,""],
"nAQ",["Young modulus X","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Young modulus X",0,0,"kipsPerSquareInch"],
"nAU",["End Release","Releases / Member Forces",20,"","","End Release",0,0,""],
"nAY",["Justification","Vertical Grid",20,"","","Justification",8,0,""],
"nAc",["Flow Pressure","Plumbing",3,"autodesk.unit.unit:poundsForcePerSquareInch-1.0.1","","",0,0,"poundsForcePerSquareInch"],
"nQE",["Top Level","Constraints",20,"","","Top Level",0,0,""],
"nQI",["Surface Number","Identity Data",20,"","","Surface Number",0,0,""],
"nQM",["Ground Plane","Energy Analytical Model",20,"","","Ground Plane",0,0,""],
"nQQ",["Width on side 2","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Width on side 2",0,0,"feetFractionalInches"],
"nQU",["Base Release","Releases / Member Forces",20,"","","Base Release",0,0,""],
"nQY",["Dimension String Type","Graphics",20,"","","Dimension String Type",0,0,""],
"nQc",["Angle to True North","Identity Data",3,"autodesk.unit.unit:degrees-1.0.1","","Angle to True North",0,0,"degrees"],
"ngE",["Ramp Material","Materials and Finishes",20,"","","Ramp Material",0,0,""],
"ngI",["Analytical Links","Analytical Model",1,"","","Analytical Links",0,0,""],
"ngM",["Filter","Other",20,"","","Filter",0,0,""],
"ngQ",["Thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Thickness",8,0,"feetFractionalInches"],
"ngU",["Thermal Mass","Analytical Properties",3,"autodesk.unit.unit:britishThermalUnitsPerDegreeFahrenheit-1.0.1","","Thermal Mass",8,0,"britishThermalUnitsPerDegreeFahrenheit"],
"ngY",["Air Outlet Half Height","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"ngc",["Line Weight","Graphics",20,"","","Line Weight",0,0,""],
"nwE",["Overall Length","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"nwI",["Scale","Graphics",20,"","","Scale",8,0,""],
"nwM",["Numbering","Other",20,"","","Numbering",8,0,""],
"nwQ",["Inside Diameter","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"nwU",["Base y Projection","Analytical Alignment",20,"","","Base y Projection",8,0,""],
"nwY",["Rough Width","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Rough Width",0,0,"feetFractionalInches"],
"nwc",["Equality Formula","Other",20,"","","Equality Formula",0,0,""],
"oAE",["Arc Leaders","Graphics",1,"","","Arc Leaders",0,0,""],
"oAI",["New views are dependent on template","Identity Data",1,"","","New views are dependent on template",8,0,""],
"oAM",["Structural Framing Length Roundoff","Structural",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Structural Framing Length Roundoff",0,0,"feetFractionalInches"],
"oAQ",["Spacing","Vertical Grid",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Spacing",8,0,"feetFractionalInches"],
"oAU",["Designed By","Identity Data",20,"","","Designed By",0,0,""],
"oAY",["frame_inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"oAc",["voidWidth","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"oQE",["node_flags","__node_flags__",2,"","","",1,0,""],
"oQI",["Graphic Display Options","Graphics",20,"","","Graphic Display Options",0,0,""],
"oQM",["Trim Width - Exterior","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"oQQ",["Level Offset","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Level Offset",0,0,"feetFractionalInches"],
"oQU",["Half_Base_Width","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"oQY",["Frame Type","Construction",20,"","","Frame Type",0,0,""],
"oQc",["Color","Materials and Finishes",2,"","","Color",0,0,""],
"ogE",["Elevation","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Elevation",0,0,"feetFractionalInches"],
"ogI",["k","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"ogM",["length","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"ogQ",["Author","Identity Data",20,"","","Author",0,0,""],
"ogU",["Zone Name Submeter","Constraints",20,"","","",0,0,""],
"ogY",["Width on side 1","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Width on side 1",0,0,"feetFractionalInches"],
"ogc",["Area per Person","Energy Analysis",3,"autodesk.unit.unit:squareFeet-1.0.1","","Area per Person",0,0,"squareFeet"],
"owE",["Outdoor Air Information","Energy Analysis",20,"","","Outdoor Air Information",0,0,""],
"owI",["Camber Size","Structural",20,"","","Camber Size",0,0,""],
"owM",["Lock Proportions","Dimensions",1,"","","Lock Proportions",0,0,""],
"owQ",["Wrapping at Ends","Construction",20,"","","Wrapping at Ends",0,0,""],
"owU",["Offset from Host","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset from Host",0,0,"feetFractionalInches"],
"owY",["wallHeight","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"owc",["Stick Symbol Location","Structural",20,"","","Stick Symbol Location",0,0,""],
"pAE",["Rebar Cover - Other Faces","Structural",20,"","","Rebar Cover - Other Faces",0,0,""],
"pAI",["Rotate text with component","Other",1,"","","Rotate text with component",0,0,""],
"pAM",["Color","Graphics",2,"","","Color",0,0,""],
"pAQ",["Witness Line Length","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Witness Line Length",8,0,"fractionalInches"],
"pAU",["Family Type","Analytical Properties",20,"","","Family Type",8,0,""],
"pAY",["End My","Releases / Member Forces",1,"","","End My",8,0,""],
"pAc",["Extend Below Base","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Extend Below Base",0,0,"feetFractionalInches"],
"pQE",["Side_Keystone_Tops","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"pQI",["Name","Identity Data",20,"","","Name",8,0,""],
"pQM",["Sill Left-Right Overhang","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"pQQ",["Segment Description","Mechanical",20,"","","Segment Description",0,0,""],
"pQU",["Profile Usage","Other",20,"","","Profile Usage",0,0,""],
"pQY",["Column Symbolic Offset","Extents",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Column Symbolic Offset",0,0,"feetFractionalInches"],
"pQc",["Show Border","Graphics",1,"","","Show Border",0,0,""],
"pgE",["System Classification","Mechanical",20,"","","System Classification",8,0,""],
"pgI",["Title","Graphics",20,"","","Title",0,0,""],
"pgM",["Poisson ratio Z","Materials and Finishes",3,"","","Poisson ratio Z",8,0,""],
"pgQ",["Moves With Nearby Elements","Constraints",1,"","","Moves With Nearby Elements",8,0,""],
"pgU",["Enable Analytical Model","Structural",1,"","","Enable Analytical Model",8,0,""],
"pgY",["Rotate with component","Other",1,"","","Rotate with component",0,0,""],
"pgc",["Route Analysis Settings","Route Analysis",20,"","","Route Analysis Settings",0,0,""],
"pwE",["Start z Projection","Analytical Alignment",20,"","","Start z Projection",8,0,""],
"pwI",["Swatch Height","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Swatch Height",0,0,"fractionalInches"],
"pwM",["Group","__internalref__",11,"","","",1,0,""],
"pwQ",["Rise / Drop Symbol","Rise / Drop",20,"","","Rise / Drop Symbol",0,0,""],
"pwU",["Rebar Cover - Exterior Face","Structural",20,"","","Rebar Cover - Exterior Face",0,0,""],
"pwY",["End Connection","Structural",20,"","","End Connection",0,0,""],
"pwc",["frame","Materials and Finishes",20,"","","",0,0,""],
"qAE",["Model Display","Graphics",20,"","","Model Display",0,0,""],
"qAI",["Connection Status","Structural",20,"","","Connection Status",8,0,""],
"qAM",["Opening Time","Energy Analysis",20,"","","Opening Time",0,0,""],
"qAQ",["Show Room Number","Graphics",1,"","","",0,0,""],
"qAU",["top_protrusion","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"qAY",["Mass Exterior Wall - Underground","Other",20,"","","Mass Exterior Wall - Underground",0,0,""],
"qAc",["tw","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"qQE",["Visual Light Transmittance","Analytical Properties",3,"","","Visual Light Transmittance",8,0,""],
"qQI",["Section Shape","Structural",20,"","","Section Shape",8,0,""],
"qQM",["End Segment Pattern","Graphics",20,"","","End Segment Pattern",0,0,""],
"qQQ",["Lighting Load","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Lighting Load",8,0,"britishThermalUnitsPerHour"],
"qQU",["Lateral Offset","Handrail 1",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Lateral Offset",8,0,"feetFractionalInches"],
"qQY",["Energy Settings","Energy Analysis",20,"","","Energy Settings",0,0,""],
"qQc",["Offset","Horizontal Grid",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset",0,0,"feetFractionalInches"],
"qgE",["Air Outlet Height","Dimensions",3,"autodesk.unit.unit:fractionalInches-1.0.0","","",0,0,"fractionalInches"],
"qgI",["Units Format","Text",20,"","","Units Format",0,0,""],
"qgM",["Start Fx","Releases / Member Forces",1,"","","Start Fx",0,0,""],
"qgQ",["Wrapping at Inserts","Construction",20,"","","Wrapping at Inserts",0,0,""],
"qgU",["Issued to","Other",20,"","","Issued to",8,0,""],
"qgY",["Offset","Vertical Grid",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset",0,0,"feetFractionalInches"],
"qgc",["Seat/Back Material","Materials and Finishes",20,"","","",0,0,""],
"qwE",["Nominal Width","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"qwI",["Issued by","Identity Data",20,"","","Issued by",8,0,""],
"qwM",["Show Leader When Text Moves","Graphics",20,"","","Show Leader When Text Moves",0,0,""],
"qwQ",["Fascia Depth","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Fascia Depth",8,0,"feetFractionalInches"],
"qwU",["Head R1","Materials and Finishes",20,"","","",0,0,""],
"qwY",["Description","Materials and Finishes",20,"","","Description",0,0,""],
"qwc",["Beam cutback in plan","Structural",20,"","","Beam cutback in plan",0,0,""],
"rAE",["Unbounded Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Unbounded Height",8,0,"feetFractionalInches"],
"rAI",["Maximum Ridge Height","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Maximum Ridge Height",8,0,"feetFractionalInches"],
"rAM",["Trim Interior Material","Materials and Finishes",20,"","","",0,0,""],
"rAQ",["post","Materials and Finishes",20,"","","",0,0,""],
"rAU",["HWFU","Mechanical",3,"","","HWFU",0,0,""],
"rAY",["Orientation","Graphics",20,"","","Orientation",0,0,""],
"rAc",["Profile","Construction",20,"","","Profile",0,0,""],
"rQE",["Top Mz","Releases / Member Forces",1,"","","Top Mz",8,0,""],
"rQI",["Annotation Crop","Extents",1,"","","Annotation Crop",0,0,""],
"rQM",["halfwidth","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"rQQ",["Appears In Sheet List","Identity Data",1,"","","Appears In Sheet List",0,0,""],
"rQU",["Top Mx","Releases / Member Forces",1,"","","Top Mx",8,0,""],
"rQY",["Glazing Material","Materials and Finishes",20,"","","",0,0,""],
"rQc",["End y Projection","Analytical Alignment",20,"","","End y Projection",8,0,""],
"rgE",["Crop Region Visible","Extents",1,"","","Crop Region Visible",0,0,""],
"rgI",["Comments","Identity Data",20,"","","Comments",8,0,""],
"rgM",["door_thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"rgQ",["Show Opening Height","Text",1,"","","Show Opening Height",0,0,""],
"rgU",["Crop View","Extents",1,"","","Crop View",0,0,""],
"rgY",["Plenum Air Inlet Height","Dimensions",3,"autodesk.unit.unit:fractionalInches-1.0.0","","",0,0,"fractionalInches"],
"rgc",["View","__internalref__",11,"","","",1,0,""],
"rwE",["Camera Position","Camera",20,"","","Camera Position",8,0,""],
"rwI",["Read Convention","Text",20,"","","Read Convention",0,0,""],
"rwM",["Desired Number of Risers","Dimensions",20,"","","Desired Number of Risers",0,0,""],
"rwQ",["Stile","Materials and Finishes",20,"","","",0,0,""],
"rwU",["Color Scheme","Graphics",20,"","","Color Scheme",0,0,""],
"rwY",["Inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"rwc",["Rebar Cover - Interior Face","Structural",20,"","","Rebar Cover - Interior Face",0,0,""],
"sAE",["width","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"sAI",["Width (pixels)","Identity Data",20,"","","Width (pixels)",8,0,""],
"sAM",["Shear modulus Y","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Shear modulus Y",8,0,"kipsPerSquareInch"],
"sAQ",["Start Alignment Method","Analytical Alignment",20,"","","Start Alignment Method",0,0,""],
"sAU",["Project Status","Other",20,"","","Project Status",0,0,""],
"sAY",["Swatch Width","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Swatch Width",0,0,"fractionalInches"],
"sAc",["frame_width","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"sQE",["Head Material","Materials and Finishes",20,"","","",0,0,""],
"sQI",["Offset From Base","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset From Base",8,0,"feetFractionalInches"],
"sQM",["Opening Type","Energy Analysis",20,"","","Opening Type",8,0,""],
"sQQ",["Target Elevation","Camera",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Target Elevation",0,0,"feetFractionalInches"],
"sQU",["Water Closet Material","Materials and Finishes",20,"","","",0,0,""],
"sQY",["Tension perpendicular to grain","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Tension perpendicular to grain",0,0,"kipsPerSquareInch"],
"sQc",["Rafter or Truss","Construction",20,"","","Rafter or Truss",0,0,""],
"sgE",["K3","Materials and Finishes",20,"","","",0,0,""],
"sgI",["viewable_in","__viewable_in__",20,"","","",1,0,""],
"sgM",["Eye Elevation","Camera",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Eye Elevation",0,0,"feetFractionalInches"],
"sgQ",["Width","Identity Data",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Width",8,0,"feetFractionalInches"],
"sgU",["Base Fz","Releases / Member Forces",1,"","","Base Fz",8,0,""],
"sgY",["depth2","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"sgc",["Top Rail Height","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"swE",["Product URL","Identity Data",20,"","","",0,0,""],
"swI",["Room Name","Other",20,"","","Room Name",9,0,""],
"swM",["Outdoor Air Method","Energy Analysis",20,"","","Outdoor Air Method",0,0,""],
"swQ",["Start Connection","Structural",20,"","","Start Connection",0,0,""],
"swU",["is_doc_property","__document__",1,"","","",1,0,""],
"swY",["Trim Projection Ext","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"swc",["Monolithic Material","Materials and Finishes",20,"","","Monolithic Material",8,0,""],
"tAE",["Cooling Information","Energy Analysis",20,"","","Cooling Information",0,0,""],
"tAI",["04 CSI","Identity Data",20,"","","",8,0,""],
"tAM",["Structure","Construction",20,"","","Structure",0,0,""],
"tAQ",["Elevation at Bottom","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Elevation at Bottom",8,0,"feetFractionalInches"],
"tAU",["Start Join Cutback","Geometric Position",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Start Join Cutback",0,0,"feetFractionalInches"],
"tAY",["Abbreviation","Identity Data",20,"","","Abbreviation",0,0,""],
"tAc",["Flow","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinute-1.0.1","","Flow",8,0,"cubicFeetPerMinute"],
"tQE",["Type Mark","Identity Data",20,"","","Type Mark",8,0,""],
"tQI",["Waste Outlet Connection Diameter","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"tQM",["Window Inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"tQQ",["Occupied Volume","Dimensions",3,"autodesk.unit.unit:cubicFeet-1.0.1","","Occupied Volume",8,0,"cubicFeet"],
"tQU",["Revision Number","Identity Data",20,"","","Revision Number",8,0,""],
"tQY",["Side Brace","Other",1,"","","",0,0,""],
"tQc",["Work Plane","Constraints",20,"","","Work Plane",8,0,""],
"tgE",["Air Outlet Width","Dimensions",3,"autodesk.unit.unit:fractionalInches-1.0.0","","",0,0,"fractionalInches"],
"tgI",["Italic","Text",1,"","","Italic",0,0,""],
"tgM",["Phase Demolished","Phasing",20,"","","Phase Demolished",8,0,""],
"tgQ",["Sash Material","Materials and Finishes",20,"","","",0,0,""],
"tgU",["Interior Type","Horizontal Mullions",20,"","","Interior Type",0,0,""],
"tgY",["Nominal Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"tgc",["Maximum Riser Height","Calculation Rules",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Maximum Riser Height",0,0,"feetFractionalInches"],
"twE",["Thermal expansion coefficient Z","Materials and Finishes",3,"autodesk.unit.unit:inverseDegreesFahrenheit-1.0.1","","Thermal expansion coefficient Z",8,0,"inverseDegreesFahrenheit"],
"twI",["Centerline Tick Mark","Graphics",20,"","","Centerline Tick Mark",0,0,""],
"twM",["Detail Door Thickness","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"twQ",["Sill Material","Materials and Finishes",20,"","","",0,0,""],
"twU",["Offset from Path","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset from Path",0,0,"feetFractionalInches"],
"twY",["frame inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"twc",["operable_glazing_inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"uAE",["View Scale","Graphics",20,"","","View Scale",0,0,""],
"uAI",["CenterK_halfwidth","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"uAM",["Down text","Graphics",20,"","","Down text",8,0,""],
"uAQ",["Thermal expansion coefficient","Materials and Finishes",3,"autodesk.unit.unit:inverseDegreesFahrenheit-1.0.1","","Thermal expansion coefficient",0,0,"inverseDegreesFahrenheit"],
"uAU",["Show Volume","Graphics",1,"","","",0,0,""],
"uAY",["Label","Other",20,"","","Label",0,0,""],
"uAc",["Rafter Cut","Construction",20,"","","Rafter Cut",0,0,""],
"uQE",["Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Height",8,0,"feetFractionalInches"],
"uQI",["Range: Top Level","Underlay",20,"","","Range: Top Level",8,0,""],
"uQM",["Bottom Cut Angle","Dimensions",3,"autodesk.unit.unit:degrees-1.0.1","","Bottom Cut Angle",0,0,"degrees"],
"uQQ",["Left Stringer","Stringers",20,"","","Left Stringer",0,0,""],
"uQU",["Infiltration Airflow per area","Energy Analysis",3,"autodesk.unit.unit:cubicFeetPerMinuteSquareFoot-1.0.1","","Infiltration Airflow per area",0,0,"cubicFeetPerMinuteSquareFoot"],
"uQY",["Mass Skylight","Other",20,"","","Mass Skylight",0,0,""],
"uQc",["End Alignment Method","Analytical Alignment",20,"","","End Alignment Method",0,0,""],
"ugE",["frame_width_2","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"ugI",["Up text","Graphics",20,"","","Up text",0,0,""],
"ugM",["Discipline","Graphics",20,"","","Discipline",0,0,""],
"ugQ",["Base Mz","Releases / Member Forces",1,"","","Base Mz",8,0,""],
"ugU",["Height Offset From Level","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Height Offset From Level",0,0,"feetFractionalInches"],
"ugY",["Cold Water Connection Radius","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"ugc",["Type","Top Rail",20,"","","Type",8,0,""],
"uwE",["Cutoff Level","Constraints",20,"","","Cutoff Level",0,0,""],
"uwI",["Mullion Family General Shape","Other",20,"","","Mullion Family General Shape",0,0,""],
"uwM",["Locked Orientation","Camera",1,"","","Locked Orientation",8,0,""],
"uwQ",["Start Attachment Type","Structural",20,"","","Start Attachment Type",0,0,""],
"uwU",["End Extension Calculation","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",8,0,"feetFractionalInches"],
"uwY",["Outdoor Airflow per area","Mechanical - Flow",3,"autodesk.unit.unit:cubicFeetPerMinuteSquareFoot-1.0.1","","Outdoor Airflow per area",8,0,"cubicFeetPerMinuteSquareFoot"],
"uwc",["Mass Slab","Other",20,"","","Mass Slab",0,0,""],
"vAE",["Stringer Thickness","Stringers",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Stringer Thickness",8,0,"feetFractionalInches"],
"vAI",["Waste Connection Diameter","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"vAM",["E/W","Identity Data",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","E/W",8,0,"feetFractionalInches"],
"vAQ",["Static Pressure","Mechanical",3,"autodesk.unit.unit:inchesOfWater60DegreesFahrenheit-1.0.1","","Static Pressure",8,0,"inchesOfWater60DegreesFahrenheit"],
"vAU",["Line Style","Graphics",20,"","","Line Style",0,0,""],
"vAY",["Right Stringer","Stringers",20,"","","Right Stringer",0,0,""],
"vAc",["Title on Sheet","Identity Data",20,"","","Title on Sheet",0,0,""],
"vQE",["Rebar Cover - Top Face","Structural",20,"","","Rebar Cover - Top Face",0,0,""],
"vQI",["Peak Heating Load","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Peak Heating Load",8,0,"britishThermalUnitsPerHour"],
"vQM",["End Fy","Releases / Member Forces",1,"","","End Fy",8,0,""],
"vQQ",["Plenum Air Pressure Drop","Mechanical",3,"autodesk.unit.unit:inchesOfWater60DegreesFahrenheit-1.0.1","","",0,0,"inchesOfWater60DegreesFahrenheit"],
"vQU",["System Type","Mechanical",20,"","","System Type",8,0,""],
"vQY",["End Extension","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"vQc",["Coarse Scale Fill Pattern","Graphics",20,"","","Coarse Scale Fill Pattern",0,0,""],
"vgE",["Tangent Joins","Construction",20,"","","Tangent Joins",0,0,""],
"vgI",["Begin with Riser","Risers",1,"","","Begin with Riser",0,0,""],
"vgM",["Perimeter","Analytical Properties",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Perimeter",8,0,"feetFractionalInches"],
"vgQ",["Base Finish","Identity Data",20,"","","Base Finish",0,0,""],
"vgU",["View Template applied to new views","Identity Data",20,"","","View Template applied to new views",0,0,""],
"vgY",["OmniClass 23","Identity Data",20,"","","",8,0,""],
"vgc",["Sub Family","__internalref__",11,"","","",1,0,""],
"vwE",["Start My","Releases / Member Forces",1,"","","Start My",0,0,""],
"vwI",["Sheet Number","Identity Data",20,"","","Sheet Number",8,0,""],
"vwM",["CategoryId","__categoryId__",2,"","","",1,0,""],
"vwQ",["Underline","Title Text",1,"","","Underline",0,0,""],
"vwU",["Sketchy Lines","Graphics",20,"","","Sketchy Lines",0,0,""],
"vwY",["Type","Handrail 2",20,"","","Type",0,0,""],
"vwc",["Current Revision Issued To","Identity Data",20,"","","Current Revision Issued To",8,0,""],
"wAE",["Occupancy Load","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Occupancy Load",8,0,"britishThermalUnitsPerHour"],
"wAI",["Length","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Length",8,0,"feetFractionalInches"],
"wAM",["glazing_inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"wAQ",["Shear reinforcement yield stress","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Shear reinforcement yield stress",0,0,"kipsPerSquareInch"],
"wAU",["Lighting","Graphics",20,"","","Lighting",0,0,""],
"wAY",["Use Landing Height Adjustment","Construction",1,"","","Use Landing Height Adjustment",0,0,""],
"wAc",["Specified Lighting Load per area","Energy Analysis",3,"autodesk.unit.unit:wattsPerSquareFoot-1.0.1","","Specified Lighting Load per area",0,0,"wattsPerSquareFoot"],
"wQE",["hyperlink","__hyperlink__",20,"","","",1,0,""],
"wQI",["sill","Materials and Finishes",20,"","","",0,0,""],
"wQM",["SideK_base","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"wQQ",["oprable_frame_thickness","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"wQU",["Leader Type","Graphics",20,"","","Leader Type",8,0,""],
"wQY",["Project Address","Other",20,"","","Project Address",0,0,""],
"wQc",["Mode","Energy Analytical Model",20,"","","Mode",0,0,""],
"wgE",["V/G Overrides Import","Graphics",20,"","","V/G Overrides Import",0,0,""],
"wgI",["Offset From Wall","Constraints",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Offset From Wall",0,0,"feetFractionalInches"],
"wgM",["Center Mark Visible","Graphics",1,"","","Center Mark Visible",0,0,""],
"wgQ",["Elevation at Top","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Elevation at Top",8,0,"feetFractionalInches"],
"wgU",["Top x Projection","Analytical Alignment",20,"","","Top x Projection",8,0,""],
"wgY",["Building Story","Identity Data",1,"","","Building Story",0,0,""],
"wgc",["Top Alignment Method","Analytical Alignment",20,"","","Top Alignment Method",0,0,""],
"wwE",["Type Image","Identity Data",20,"","","Type Image",8,0,""],
"wwI",["Maximum Incline Length","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Maximum Incline Length",0,0,"feetFractionalInches"],
"wwM",["Font","Text",20,"","","Font",0,0,""],
"wwQ",["Steel Cantilever","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Steel Cantilever",8,0,"feetFractionalInches"],
"wwU",["Start Fy","Releases / Member Forces",1,"","","Start Fy",0,0,""],
"wwY",["V/G Overrides Filters","Graphics",20,"","","V/G Overrides Filters",0,0,""],
"wwc",["Top z Projection","Analytical Alignment",20,"","","Top z Projection",8,0,""],
"xAE",["angles","Materials and Finishes",20,"","","",0,0,""],
"xAI",["Italic","Title Text",1,"","","Italic",0,0,""],
"xAM",["Thermally Treated","Materials and Finishes",1,"","","Thermally Treated",0,0,""],
"xAQ",["Riser Thickness","Risers",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Riser Thickness",8,0,"feetFractionalInches"],
"xAU",["Multistory Top Level","Constraints",20,"","","Multistory Top Level",0,0,""],
"xAY",["Landing Overlap","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Landing Overlap",8,0,"feetFractionalInches"],
"xAc",["End Fz","Releases / Member Forces",1,"","","End Fz",8,0,""],
"xQE",["Scope","Constraints",20,"","","",0,0,""],
"xQI",["Sheet Width","Identity Data",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Sheet Width",8,0,"feetFractionalInches"],
"xQM",["z Justification","Geometric Position",20,"","","z Justification",0,0,""],
"xQQ",["Curved Edge Condition","Slab Shape Edit",2,"","","Curved Edge Condition",8,0,""],
"xQU",["Sheet Height","Identity Data",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Sheet Height",8,0,"feetFractionalInches"],
"xQY",["Primary Air Inlet Radius","Dimensions",3,"autodesk.unit.unit:fractionalInches-1.0.0","","",0,0,"fractionalInches"],
"xQc",["Dimension Line Snap Distance","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Dimension Line Snap Distance",0,0,"fractionalInches"],
"xgE",["outlet_Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"xgI",["Top y Projection","Analytical Alignment",20,"","","Top y Projection",8,0,""],
"xgM",["Urinal Material","Materials and Finishes",20,"","","",0,0,""],
"xgQ",["Lateral Offset","Handrail 2",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Lateral Offset",8,0,"feetFractionalInches"],
"xgU",["Baluster Placement","Construction",20,"","","Baluster Placement",0,0,""],
"xgY",["Upper Limit","Constraints",20,"","","Upper Limit",0,0,""],
"xgc",["SideK_offset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"xwE",["Phase Filter","Phasing",20,"","","Phase Filter",0,0,""],
"xwI",["Project Name","Other",20,"","","Project Name",0,0,""],
"xwM",["Vertical Scale","Dimensions",3,"","","Vertical Scale",0,0,""],
"xwQ",["Room Bounding","Constraints",1,"","","Room Bounding",0,0,""],
"xwU",["Part Type","Mechanical",20,"","","Part Type",0,0,""],
"xwY",["CenterK_height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"yAE",["Unoccupied Cooling Set Point","Energy Analysis",3,"autodesk.unit.unit:fahrenheit-1.0.1","","Unoccupied Cooling Set Point",0,0,"fahrenheit"],
"yAI",["Outdoor Air per Area","Energy Analysis",3,"autodesk.unit.unit:cubicFeetPerMinuteSquareFoot-1.0.1","","Outdoor Air per Area",0,0,"cubicFeetPerMinuteSquareFoot"],
"yAM",["Head-L2a","Materials and Finishes",20,"","","",0,0,""],
"yAQ",["Thickness","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Thickness",8,0,"feetFractionalInches"],
"yAU",["Draw Layer","Other",20,"","","Draw Layer",0,0,""],
"yAY",["Adjust for Mullion Size","Vertical Grid",1,"","","Adjust for Mullion Size",8,0,""],
"yQE",["Angle","Vertical Grid",3,"autodesk.unit.unit:degrees-1.0.1","","Angle",0,0,"degrees"],
"yQI",["Resolution (dpi)","Identity Data",3,"","","Resolution (dpi)",8,0,""],
"yQM",["Side_Keystone_Bases","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"yQQ",["Thermal expansion coefficient Y","Materials and Finishes",3,"autodesk.unit.unit:inverseDegreesFahrenheit-1.0.1","","Thermal expansion coefficient Y",8,0,"inverseDegreesFahrenheit"],
"yQU",["Interior Type","Vertical Mullions",20,"","","Interior Type",0,0,""],
"yQY",["Mass Floor","Other",20,"","","Mass Floor",0,0,""],
"ygE",["Young modulus Y","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Young modulus Y",8,0,"kipsPerSquareInch"],
"ygI",["Elev","Identity Data",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Elev",8,0,"feetFractionalInches"],
"ygM",["base_protrusion","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"ygQ",["Flipped Dimension Line Extension","Graphics",3,"autodesk.unit.unit:fractionalInches-1.0.0","","Flipped Dimension Line Extension",8,0,"fractionalInches"],
"ygU",["Zone ObjectType","IFC Parameters",20,"","","",0,0,""],
"ygY",["Concrete compression","Materials and Finishes",3,"autodesk.unit.unit:kipsPerSquareInch-1.0.1","","Concrete compression",0,0,"kipsPerSquareInch"],
"ywE",["Issued by","Other",20,"","","Issued by",8,0,""],
"ywI",["y Offset Value","Geometric Position",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","y Offset Value",0,0,"feetFractionalInches"],
"ywM",["Handle Material","Materials and Finishes",20,"","","",0,0,""],
"ywQ",["Default Thickness","Construction",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Default Thickness",8,0,"feetFractionalInches"],
"ywU",["Calculated Cooling Load","Energy Analysis",3,"autodesk.unit.unit:britishThermalUnitsPerHour-1.0.1","","Calculated Cooling Load",8,0,"britishThermalUnitsPerHour"],
"ywY",["Void Height","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"zAE",["Reduction factor for shear","Materials and Finishes",3,"","","Reduction factor for shear",0,0,""],
"zAI",["Current Revision Date","Identity Data",20,"","","Current Revision Date",8,0,""],
"zAM",["Current Revision Issued By","Identity Data",20,"","","Current Revision Issued By",8,0,""],
"zAQ",["System Abbreviation","Mechanical",20,"","","System Abbreviation",8,0,""],
"zAU",["door_glass_inset","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"zAY",["Witness Line Control","Graphics",20,"","","Witness Line Control",0,0,""],
"zQE",["Curtain Panel","Construction",20,"","","Curtain Panel",0,0,""],
"zQI",["Cost","Identity Data",3,"autodesk.unit.unit:currency-1.0.0","","Cost",8,0,"currency"],
"zQM",["_RFT","__category__",20,"","","",1,0,""],
"zQQ",["Value","Text",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","Value",8,0,"feetFractionalInches"],
"zQU",["Organization Description","Identity Data",20,"","","Organization Description",0,0,""],
"zQY",["Stile Width","Other",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"zgE",["Mass Shade","Other",20,"","","Mass Shade",0,0,""],
"zgI",["Shared","Other",1,"","","Shared",0,0,""],
"zgM",["Structural","Structural",1,"","","Structural",8,0,""],
"zgQ",["h2","Dimensions",3,"autodesk.unit.unit:feetFractionalInches-1.0.0","","",0,0,"feetFractionalInches"],
"zgU",["Thickness Note","Dimensions",20,"","","",8,0,""],
"zgY",["Center Segment","Graphics",20,"","","Center Segment",0,0,""],
"zwE",["Top My","Releases / Member Forces",1,"","","Top My",8,0,""],
"zwI",["Connection Type","Mechanical",20,"","","Connection Type",0,0,""],
"zwM",["Number of Poles","Electrical",20,"","","",0,0,""],
"zwQ",["Automatically Embed","Construction",1,"","","Automatically Embed",0,0,""],
"zwU",["_RC","__category__",20,"","","",1,0,""],
"zwY",["Plan View Symbols End 1 (Default)","Graphics",1,"","","Plan View Symbols End 1 (Default)",0,0,""],
"xwc",["WO Id","CW Connection",20,"","","",16,0,"","","","BPqW2OR7Svm4xE1LBmSm1A","U2qVqS3RSO-GYITwQfzSGg",{"masterFormat":["01 00 00"]},null,"e"],
"yAc",["Param 1","Test 1",20,"","","",16,0,"","","","PEBAO6knS3GWXEhy-UURlA","tyFDfH8PRAGPNHoGbwlGng",{"masterFormat":["01 00 00"]},null,"e"],
"yQc",["Param 2","Test 1",1,"","","",16,0,"","","","PAB7Z9zGQQOahYHV8TPeKw","tyFDfH8PRAGPNHoGbwlGng",{"masterFormat":["01 00 00"]},null,"e"],
"ygc",["Param 3","Test 1",2,"","","",16,0,"","","","MpUIVz8SRc6wWabyiBlXdw","tyFDfH8PRAGPNHoGbwlGng",{"masterFormat":["01 00 00"]},null,"e"],
"ywc",["Param 4","Test 1 - General",20,"","","",16,0,"","","","3v1qfB7eT8uakZIYEuJr2Q","tyFDfH8PRAGPNHoGbwlGng",{"masterFormat":["01 00 00"]},null,"e"],
"zAc",["Param A","Test 2 - Concrete",20,"","","",16,0,"","","","JmLGjkWFRBaaRShzUNIbhw","nGs9n4WISzCjDeDVUWTmqA",{"masterFormat":["03 00 00"]},null,"e"],
"zQc",["Param B","Test 2 - Concrete",3,"","","",16,0,"","","","oy2z2U15T0evrZ4BZPEmMw","nGs9n4WISzCjDeDVUWTmqA",{"masterFormat":["03 00 00"]},null,"e"],
"zgc",["Param Alpha","Test 3 - Masonry",20,"","","",16,0,"","","","tLs8mp1DSiOHZtmKgCA73w","IApO4oiHTt-Z39RH9ynniw",{"masterFormat":["04 00 00"]},null,"e"],
"zwc",["Param Beta","Test 3 - Masonry",3,"","","",16,0,"","","","pwyDtcIlRyiTE_XvOt5qiQ","IApO4oiHTt-Z39RH9ynniw",{"masterFormat":["04 00 00"]},null,"e"],
"0Ac",["Param C","Test 2 - Concrete",25,"","","",16,0,"","","","ln1WHcXVR56wsddxF4R8tA","nGs9n4WISzCjDeDVUWTmqA",{"masterFormat":["03 00 00"]},null,"e"],
"0Qc",["Param D","Test 2 - Concrete",25,"","","",16,0,"","","","HHfcQS0hTRC2CWnv2cZeOg","nGs9n4WISzCjDeDVUWTmqA",{"masterFormat":["03 00 00"]},null,"e"]
]

```


***Status Code:*** 200

<br>



### 4. /modeldata/:modelID/fragments


The response contains binary "fragments" needed for 3D rendering for a given model. This data is used by the viewer to render model geometry to the screen and is not of much use in the REST context.


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/modeldata/:modelID/fragments
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model ID |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model ID |



***Body: None***



#### I. Example Response: OK
```js
�                                                                                                                                   ��(3�M̳l�j��� �yFIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   ҰA6�����A        �o��  �?	�?��*> �\B4�A������V�(A�J�� PB    ��(3�M̳l�j��� �z>��R�N�,@�~�z�儩{[�=`O�L ����tIj����   ӤA�_����A�o�7^��7 5?�5?=�*>.K�?�\BP�A�
�����V�(A6��� PBP    ��(3�M̳l�j��� �|���f07L6���	���{[�=`O�L ����tIj����   l'A������A              �?��*>��? �\B�&A6������V�(A��� PB    ��(3�M̳l�j��� ���.CXP�0�IV�V5�/n��{[�=`O�L ����tIj����   ��A�;��W�?�5?� 5�����B��:��*>&��?�ǈBm3Aݐ«:T*A3�� PB    ��(3�M̳l�j��� ���4�}�Rg˙y��
O�E���{[�=`O�L ����tIj����   ��A����W�?�5?� 5�+2����: +>��?�ǈB�A3F«:T*A��� PB    ��(3�M̳l�j��� ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   9�(A3��JU�?              �?��*>��?UňB�'A��«:T*Aݐ� PB    ��(3�M̳l�j��� ��rG��j#�@�����ʈS�{[�=`O�L ����tIj����   {�Am��HU�?i��7~ �7	5?� 5?�*>�f�?bňB@�A�?��:·=)A� � PB@    ��(3�M̳l�j��� ���]�gk9Lժ4_y�6؟��{[�=`O�L ����tIj����   LSA¿�JU�?        �z����? ;�?s+>UňB\�A��:�<�&Amj� PB    ��(3�M̳l�j��� ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   �*AU�JU�?              �?��*>XUM?UňB�=)A¿��:�b�+A���� PB    ��(3�M̳l�j��� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   �m"AMfV@JU�?        ^l��  �?	�?]�*>UňB�\A�Q@�:�~-A��[@ PB    ��(3�M̳l�j��� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   �a"A�+@JU�?        �T��  �?0ȱ?W�*>UňBEA��%@�:�~-ANf0@ PB    ��(3�M̳l�j��� �����f07L6���	���{[�=`O�L ����tIj����   �(,A��@@JU�?              �?��*>��?UňBs�*ANf0@�:�~-A�Q@ PB    ��(3�M̳l�j��� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   �$A�nAJU�?        �l��  �?	�?��*>UňB%�A=�lA�:�G/A�joA PB    ��(3�M̳l�j��� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   ��#A>@cAJU�?        :��  �?0ȱ?
�AJU�?        �l��  �?	�?��*>UňB�A`�A�:��0Au��A PB    ��(3�M̳l�j��� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   ��%A��AJU�?        :��  �?0ȱ?
>m�X>��A�A�Bk$�A������B�y�A�j�   ���Ef�j��,	� g7���eA.��V�%�����&2�Q��3�ޒ�8�����ġ���   ��AqO�@�7�c�A�c�A>�h.��h.? V�=�GA��~A�AƄ��~�+�B�[���   ���Ef�j��,	� g7�����1����N�>�an�}��}$uJ�q�NeȊq�`�1��   "��Aq��Y��F��F>.�.? �*=sc!A͋A�AƤ��+�Bz®j�(   ���Ef�j��,	� g7*�0�%_T���a^�-8uԣ}$uJ�q�NeȊq�`�1��   ���A�\���� �2��?P��D�7����=Q)?��d@V\�A�#¤���A�$���|��   ���Ef�j��,	� g7�T�u `�'����n:���}$uJ�q�NeȊq�`�1��   ��B�vM
B�r
?  �?�4>�6�����A�d�A�����A   kk��=M%�����Ё ���H :5��<�#�(� S�'{[�=`O�L ����tIj����   ��A��+���A        {Np�  �?AZ+B��?  �?d�=�p-���AU��A��*���A   kk��=M%�����Ё ���ܝ@��=&�NҲ��{[�=`O�L ����tIj����   �`�@7����A        ��5  �?�	Bs
?  �?��>������A��A������A   �6<��B�T}�཰� ��E�xO0��:�EB~�C|E�y9j{[�=`O�L ����tIj����   ]�L�P$�Uu�A        �6�;d�?�>�>=O*A���?z�N�Dv����A@�J�PL0@���A   �6<��B�T}�཰� ��E�xO0��:�EB~�C|E�y9j{[�=`O�L ����tIj����   %K��AUu�A        
7�;d�?�3�>;*A���?,+M�PLf@��A	I��cA���A   �6<��B�T}�཰� �-E�xO0��:�EB~�C|E�y9j{[�=`O�L ����tIj����   �I�5�AUu�A        7�;d�?�3�>;*A���?
�K�MqA��A�sG����A���A   �6<��B�T}�཰� �DE�xO0��:�EB~�C|E�y9j{[�=`O�L ����tIj����   ��G��AUu�A        �6�;d�?�3�>;*A���?� J����A��A��E�J�B���A   �6<��B�T}�཰� �W�ȷ��'�_Ws�N��Ы{[�=`O�L ����tIj����   �BF��/0BUu�A        �(�;d�?O+�>��?A���?�kH�J0B��A�D��/HB���A   $�}]K��L���P!� ��a���ƹ���h���C�!�{[�=`O�L ����tIj����   b$³� �              �?  APU�>��A"7�	p��*���¼���JU6@   $�}]K��L���P!� ��a���ƹ���h���C�!�{[�=`O�L ����tIj����   )p³� �              �? �@PU�>��AY�|�	p��*���c¼���JU6@   $�}]K��L���P!� ��!�B�ɫ5���� Z�XyY{[�=`O�L ����tIj����   �L6�z�1� ��#�=        v�~? U�>��@��-A"7��8_��*��Zw5�	p�JU6@$   $�}]K��L���P!� ��!�B�ɫ5���� Z�XyY{[�=`O�L ����tIj����   N�c�z�1� ��#�=        v�~?�U�>��@��-A��d��8_��*���c�	p�JU6@$   $�}]K��L���P!� ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   Yw�$.� �              �?�U�>n<�@��A�L�@�X��*����	p�JU6@   $�}]K��L���P!� ���	i<����y���%���8{[�=`O�L ����tIj����   
��        �9?�U�>7�A�QBA_C��u����*��	���SW��JU6@D   $�}]K��L���P!� ��7A�]'		jK���#�� {[�=`O�L ����tIj����   FV�� G�� �        5M�  �?�/�A�c�>��A	�������*��}I�u���JU6@   $�}]K��L���P!� ��a���ƹ���h���C�!�{[�=`O�L ����tIj����   _C����� �              �?��J@@U�>��A	��������*������SW��JU6@   $�}]K��L���P!� ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   _C��:A� �              �?�U�>H�A��A
���SW���*����������JU6@   $�}]K��L���P!� �꼫�b���8 .��e�\0�{[�=`O�L ����tIj����   �b��FEB� �        ���  �?�tA�f�>��A������E��*��PYH���>�JU6@   $�}]K��L���P!� �됤�f07L6���	���{[�=`O�L ����tIj����   `����� �              �?XU=@PU�>��A����	p��*��
�������JU6@   $�}]K��L���P!� �����2�T��[��Y�x{[�=`O�L ����tIj����   v������� �              �?���@@U�>��A	���u����*���B�� G��JU6@   $�}]K��L���P!� ���_DY�N��5����㛌8Y������n��\w&e�mO�[   oA��Rۖ���/�1p2�j7?�:��p��<��A�m�?n�A���®����*������ T�����??   $�}]K��L���P!� ��L�a
A����Q%���*���́�ie�����?
   $�}]K��L���P!� ����Qwb��N�E�z
A����Q%���*���S�
�� /�"��'�i�=U�~?�ً?�5<5��
A�"��^ ���*��m��4$|����?   $�}]K��L���P!� ���,V߷K����	�>��$�kś{[�=`O�L ����tIj����   ���ߜ�� /�����0(�R�=;�~?ڋ?���>UHA�"��Q%���*���S�4$|����?   $�}]K��L���P!� ��µz�R�����N�j�8�/��/��N����E��b   1^������1�        ��K=��?��?��?TU	A���jQ���*���ȗ�������?   $�}]K��L���P!� ���b8
   $�}]K��L���P!� ��=KG���hA�+AvW��YZ�/��/��N����E��b   ����\����1�        �c�<��?�a?=B@TU	A����a���*������������?   $�}]K��L���P!� ��R�s�7�=\���6��[nU�����n��\w&e�mO�[   ����)����1�              �?  �?��@TU	A����a���*������������?   $�}]K��L���P!� ��I��JL��2�\L!�Ui�{[�=`O�L ����tIj����   Q����)����1�              �? U�>��@TU	A����a���*������������?   $�}]K��L���P!� ���A��2A���9��Na�Z<p{[�=`O�L ����tIj����   /���u�����1��5?�5?�#��#��U�>��Y@�m	A��� G���*���S���������?   $�}]K��L���P!� ���F�����\\)5�u'�ҟ�����n��\w&e�mO�[   /��� G����1�R�3?R�3?�i���i��  �?�z�@�A��� G���*���S�� G�����?   $�}]K��L���P!� ��2R:�&��uA���*\͈�/��/��N����E��b   /���������1�R�3?R�3?�i���i��  �?�z�@�A��������*���S���������?   $�}]K��L���P!� �����f07L6���	���{[�=`O�L ����tIj����   
E�����]6�X
.?�d�wN�f�(i�mk�UR�2��   	�g?�+����f����;0 ���2��P?�+@Fѹ@��@�J�u����*���L6�|G��k���0   $�}]K��L���P!� � �� ؖ����
��.>ݳ�}$uJ�q�NeȊq�`�1��   	��9��ˠ�^�*��IJ?�?
���SW�������������X�   $�}]K��L���P!� �Z����ĄK�B)���k�
�������X�   $�}]K��L���P!� �\���2�T��[��Y�x{[�=`O�L ����tIj����   v��������jf�              �?���@@U�>��A	���u�������B�� G��X�   $�}]K��L���P!� �]�_DY�N��5����㛌8Y������n��\w&e�mO�[   oA��Rۖ��p�1p2�j7?�:��m��<��A�m�?p�A���®���������� T��X+�?   $�}]K��L���P!� �]L�a
A����Q%������́�ie��X+�
   $�}]K��L���P!� �a��3��A^�6��M(d�N[{�/��/��N����E��b   Ӏ�X/���jp��
�'�h�=U�~?ڋ?�
A����Q%������S�
���jp��	�'�i�=U�~?�ً?�5<5��
A�"��^ �����m��4$|�X+�   $�}]K��L���P!� �a�,V߷K����	�>��$�kś{[�=`O�L ����tIj����   ���ߜ���jp�����0(�R�=;�~?ڋ?���>WHA�"��Q%������S�4$|�X+�   $�}]K��L���P!� �bµz�R�����N�j�8�/��/��N����E��b   1^����Wq�        ��K=��?��?��?VU	A���jQ������ȗ�����j,�   $�}]K��L���P!� �b�b8
   $�}]K��L���P!� �e=KG���hA�+AvW��YZ�/��/��N����E��b   ����\��Vq�        �c�<��?�a?=B@VU	A����a�������������j,�   $�}]K��L���P!� �eR�s�7�=\���6��[nU�����n��\w&e�mO�[   ����)��Vq�              �?  �?��@VU	A����a�������������j,�   $�}]K��L���P!� �eI��JL��2�\L!�Ui�{[�=`O�L ����tIj����   Q����)��Vq�              �? U�>��@VU	A����a�������������j,�   $�}]K��L���P!� �f�6��B�>{��:���0��w){[�=`O�L ����tIj����   _���u����!n���3?��3?�ݥ��ݥ��U�>h�P@5�A��� G�������������j,�   $�}]K��L���P!� �f��L[�cb��`�x� ��]1��/��/��N����E��b   �d������Vg��/?�/?�q1��q1�  �?�_�@N�A������������������j,�   $�}]K��L���P!� �f�o�k��v����
S`��������n��\w&e�mO�[   �d�� G��Vg��/?�/?�q1��q1�  �?�_�@N�A��� G�������� G���j,�   $�}]K��L���P!� �g���f07L6���	���{[�=`O�L ����tIj����   
E�����]6�X
.?�d�wN�f�(i�mk�UR�2��   	�g?�+��(]~����;0 ���2��P?�+@Fѹ@��@�J�u�������L6�|G���E�0   $�}]K��L���P!� �p�� ؖ����
��.>ݳ�}$uJ�q�NeȊq�`�1��   	��9��ˠ��Mo��IJ?�?
R
   T��QG�	��.R� 	3���h��a�Q/	���N͏�{[�=`O�L ����tIj����   �:YB���A p�              �?N��A  �?  PA�5B�|�A p!�$c}Bk> B���
   T��QG�	��.R� 	3���'�z�����:RYEи�}Eא�� �s�gtQ�#�e;$,�   $#{B���A p�              �?  �?��
�
��Rn
:�}$uJ�q�NeȊq�`�1��   熀Bp.�A��&�*?&�*?�p>�p>��@�V�?[X@y�{BiuA p1�B,ұA�n�t   T��QG�	��.R� 	3А��f07L6���	���sO�|P���=�����4�   ��@B,ҸA��              �?  @@��*>  �@��:B�'�A����FB�|�AV��   T��QG�	��.R� 	3� t��������6f�̳=�4^*������5/���&9����   ��@B���A�� �              �?  `@  �?  �@��9B�|�A����GB�|�AV��   T��QG�	��.R� 	3�\qj�'+�����X��D���z���(L��X�?��'�l���   ��@B���A�� �              �?  `@UU�?  �@��9B,үA����GB�'�AV��8   T��QG�	��.R� 	54���2�T��[��Y�x�a�"�x�����D�<�wc�Q�   ��VB�|�A���              �?N��A��A   ?��0B�|�A���$c}Bk> B���   �Qi�dG��{q��a �3.�gO�pڵJ[uH�Ѿ�N&KQ�!��(�!D����;�   �{Bh ��SU���;��?��=�.9\U?���BV�B��A�̃� p!�;(BL�JBVE Bz  �Qi�dG��{q��a �3.J]/d�{B6��9�X�疵�&{[�=`O�L ����tIj����   �{Bj ��U��m�;p�~?��ʽ/�߹�UU?Cߟ�B��A�̃� p!�;(BL�JBVE B�   �Զ�Ky���� ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ���A�̃�VUN��J	�N��5?�5?d�)?a�O?���B9��A�v�� p1���A#��V�Bh5   ���GY���~^� �,[� |�i�5f� �Hxڰ`א�� �s�gtQ�#�e;$,�   ��� G�� �vA2B�2B<p�4�p�4?���?:�UB��:B�S��u����*����[�����V�B4    ���GY���~^� �,�L_�ihi`�ï���6`hq��{[�=`O�L ����tIj����   ��� G�� �vA�5?�5?�FJ��FJ����?F9QB �5B�S��u����*����[�����V�B(    ���GY���~^� ��\&�HL.M:
�M)א�� �s�gtQ�#�e;$,�   b>���M�AU�rA<�        ��?���?�3�B�T6B�S������[���)��^c�BV�BE   ���GY���~^� �����*����~}G�&n-xh{[�=`O�L ����tIj����   b>���M�AT�rA�$�;        |�?���?O��B�9B�S������[���)��^c�BV�B	  [��	
�t�]� �}>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W����S«jW��X,����Q5��5?� @�^�?��<A%���S�����ϥ��S«*��Z  [��	
�t�]� ��>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W����Ŀ��jW��X,����Q5��5?� @�^�?��<A%����������ϥ��ķ��*��Z  [��	
�t�]� �>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W���=1��jW��X,����Q5��5?� @�^�?��<A%��=A�����ϥ�=!��*��Z  [��	
�t�]� �>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W���{�?�jW��X,����Q5��5?� @�^�?��<A%���P?����ϥ=4@�*��Z  [��	
�t�]� �3>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W����[kA�jW��X,����Q5��5?� @�^�?��<A%���[[A����ϥ��[{A�*��Z  [��	
�t�]� �H>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W������A�jW��X,����Q5��5?� @�^�?��<A%�����A����ϥ����A�*��Z  [��	
�t�]� �e>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W�����!B�jW��X,����Q5��5?� @�^�?��<A%����B����ϥ���%B�*��Z  [��	
�t�]� ��>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W���TB�jW��X,����Q5��5?� @�^�?��<A%��PB����ϥ�XB�*��Z  [��	
�t�]� ��>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   (����D«jW�$��-E[���X��  �?� @�^�?��<A(���sDG����(���șB«*��Z  [��	
�t�]� ��>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   J]��D«jW�$��-E[���X��  �?� @�^�?��<AJa�sDG����JY�șB«*��Z  [��	
�t�]� ��>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   ��$��D«jW�$��-E[���X��  �?� @�^�?��<A��(�sDG������ �șB«*��Z  [��	
�t�]� �>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   �����D«jW�$��-E[���X��  �?� @�^�?��<A����sDG��������șB«*��Z  ݏv�2K���7�| `��8,<��ҕXpI��K�~א�� �s�gtQ�#�e;$,�   �[?��)A������;m�?�ݼ�<�� @?V��B��B��J�N��� p!�1�3��rGBV�B�   ݏv�2K���7�| `�F����Y;�$�<q��[��{[�=`O�L ����tIj����   �[?��)A������:�]�>�qm?��; @?��B��B��J�N��� p!�1�3��rGBV�B�   ͬR�<L��,w�r&�� 	��f"F'�)L%�j��
d��kg'gF�u�b;W����}$uJ�q�NeȊq�`�1��    ����N���B�V�#�Y<!�?M��&���@n�?��@�d�¬v���,�A�t{��̃��B�   ͬR�<L��,w�r&�� 
dǮ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    ����ଅ��m
d�8M������S�f��y2�3Ha���u	���B1������    ������ª:B          �?���&��r@���>���@CZ��5b����Aۉ}���U�B`  ͬR�<L��,w�r&�� 
e��kg'gF�u�b;W����}$uJ�q�NeȊq�`�1��    �ώ�N���B�V�#�Y<!�?M��&���@n�?��@���¬v���,�AC����̃��B�   ͬR�<L��,w�r&�� 
eǮ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    �ώ�ଅ��m
e�8M������S�f��y2�3Ha���u	���B1������    �ώ���ª:B          �?���&��r@���>���@C���5b����A�����U�B`  ͬR�<L��,w�r&�� 
l�f"F'�)L%�j��
lǮ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    b�`�ଅ��m
l�8M������S�f��y2�3Ha���u	���B1������    b�`���ª:B              �?��r@���>���@�sh�5b����AIY���U�B`  ͬR�<L��,w�r&�� 
m�f"F'�)L%�j��
mǮ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    b^H�ଅ��m
m�8M������S�f��y2�3Ha���u	���B1������    b^H���ª:B              �?��r@���>���@��O�5b����A�@���U�B`  ͬR�<L��,w�r&�� 
s��kg'gF�u�b;W����}$uJ�q�NeȊq�`�1��    ���N���B�V�#�Y<!�?M��&���@n�?��@X@¬v���,�A���̃��B�   ͬR�<L��,w�r&�� 
sǮ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    ���ଅ��m
s�8M������S�f��y2�3Ha���u	���B1������    �����ª:B          �?���&��r@���>���@+�5b����AX ���U�B`  ͬR�<L��,w�r&�� 
t��kg'gF�u�b;W����}$uJ�q�NeȊq�`�1��    �$�N���B�V�#�Y<!�?M��&���@n�?��@X�-¬v���,�Ak��̃��B�   ͬR�<L��,w�r&�� 
tǮ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    �$�ଅ��m
t�8M������S�f��y2�3Ha���u	���B1������    �$���ª:B          �?���&��r@���>���@�+�5b����AX����U�B`  ͬR�<L��,w�r&�� 
z�f"F'�)L%�j��
zǮ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    j���ଅ��m
z�8M������S�f��y2�3Ha���u	���B1������    j�����ª:B              �?��r@���>���@���5b����A�[������U�B`  
?��J�:*� P�~vB\lGB�:�;   
+a�d��n�Kn:��e7   AY��@�:�        �'�=8]~?:�{B	n�B  �?��J�:*«:�~vB�4GB�:�   
?��J��̃�V�#�KMB�?� p!�;   
+a�d��n�Kn:��e7   *�A�*� p!�        @�Y>�'z?|�kB~�tB  �?��J��̃� p!�KMB�?� p!�   
+a�d��n�Kn:��e7   @q����� p1�        fz3��	|?�r�B[}C  �?=����̃� p1�s�	n�B p1�   ��m*JK����N֥� �o���J�rf����.�VjTg1{[�=`O�L ����tIj����   fi���@���2�̼��?�ŋ2�RS��U�>�NGATUA�k�k�?�*����f�bA��@   ��m*JK����N֥� �p���J�rf����.�VjTg1{[�=`O�L ����tIj����   ��G;@����{9? q0��յ1ni�1eU�>   BTUA"g���?�*���G���B�@��@   ��m*JK����N֥� �q%
	E���D?�kA�-����{[�=`O�L ����tIj����   S����)"A���(�̼��?F�/���˱nU�>��@ATUA+���%��@�*��{r���C�A��@   ��m*JK����N֥� �r˃�{ ��b� ���"��{[�=`O�L ����tIj����   �A�H1
A���        +�̼��?s��?7X@ATUA�$C��M'@�*���?��jA��@   ��m*JK����N֥� �t���f07L6���	����0����$P�����L��m�   �c�����A�*��        ��?&�̼+��@��*>  �>B���>}A�*��Å�����A�*��   ��m*JK����N֥� �v���2�T��[��Y�x�}�9�H
1ћfb��   R���9a|A��i�        ��?&�̼ �?���=���@N���~P{A�*��V����q}AU p�   ��m*JK����N֥� �x���2�T��[��Y�x�}�9�H
1ћfb��   ����%{A��i�        '��<��?��:@��*=���@ �T�yA�*�����f�|AU p�   ��m*JK����N֥� �x&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   w���87zA�*��        '��<��?���=  �>  @?�A���/wA�*��q���>}A[Ut�   ��m*JK����N֥� �z���2�T��[��Y�x�0����$P�����L��m�   �`�;�sA�*��        ��?&�̼VUMA��*>  �>{4��CmA�*��� ±.zA�*��   ��m*JK����N֥� �|���2�T��[��Y�x�}�9�H
1ћfb��   �;��	G~A��i�        ��?&�̼��:@��*=���@����q}A�*�������8�AU p�   ��m*JK����N֥� �|Vz��������A�����2��0����$P�����L��m�   p����5A�*��        ��?&�̼���= �>  @?�Q��.|A�*��	�����A[Ut�   ��m*JK����N֥� �~���2�T��[��Y�x�}�9�H
1ћfb��   VB�%flA��i�        ��?&�̼ �?���=���@�WD�jUkA�*���T@��vmAU p�   ��m*JK����N֥� �����2�T��[��Y�x�}�9�H
1ћfb��   *J��*kA��i�        '��<��?��:@��*=���@��O�@�iA�*��xUD�R�lAU p�   ��m*JK����N֥� ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   .�N�$<jA�*��        '��<��?���=  �>  @?�	O��gA�*���N�(�mA[Ut�   ��m*JK����N֥� �����f07L6���	����0����$P�����L��m�   ��]�KfA�*��        ��?&�̼,f�@��*>  �>�mj�nbbA�*��x�P3jA�*��   ��m*JK����N֥� �����2�T��[��Y�x�}�9�H
1ћfb��   W�:��KnA��i�        ��?&�̼��:@��*=���@[@��vmA�*���4��upAU p�   ��m*JK����N֥� ��Vz��������A�����2��0����$P�����L��m�   *�5:oA�*��        ��?&�̼���= �>  @?^6�	3lA�*����5�+BrA[Ut�   ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �a���i�Au���        ��?&�̼+��@���=��@�;���}AX���䇔��	�A�c��  ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �_�dsAu���        ��?&�̼VUMA���=��@I4���mAX���� �/yA�c��  ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �]���eAu���        ��?&�̼,f�@���=��@Sjj¨�bAX�����P��3iA�c��  ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �a���i�AE���        ��?&�̼+��@���=9�@�;���}A?��䇔��	�A^ p�  ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �_�dsAE���        ��?&�̼VUMA���=9�@I4���mA?��� �/yA^ p�  ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �]���eAE���        ��?&�̼,f�@���=9�@Sjj¨�bA?����P��3iA^ p�  ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �a���i�A��Y�        ��?&�̼+��@���=�8@�;���}A�c��䇔��	�A>��  ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �_�dsA��Y�        ��?&�̼VUMA���=�8@I4���mA�c��� �/yA>��  ��m*JK����N֥� �����f07L6���	��䬕��u	���B1������   �]���eA��Y�        ��?&�̼,f�@���=�8@Sjj¨�bA�c����P��3iA>��  ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   ��]�gA?��į�<~�4�ǯ�<~�4?���=  �<,f�@?lj�ubdA�8�ަP½�iA���   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   Qc�N�tA?��į�<~�4�ǯ�<~�4?���=  �<VUMA54��CoA�8�l� ���yA���   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   i����A?��į�<~�4�ǯ�<~�4?���=  �<+��@�?���>A�8������V�A���   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   ��]�gA�c��į�<~�4�ǯ�<~�4?���=  �<,f�@?lj�ubdA縑�ަP½�iA<��   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   i����A�c��į�<~�4�ǯ�<~�4?���=  �<+��@�?���>A縑������V�A<��   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   Qc�N�tA�c��į�<~�4�ǯ�<~�4?���=  �<VUMA54��CoA縑�l� ���yA<��   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   ��]�KfA	��į�<~�4�ǯ�<~�4?��*>��*>,f�@�mj�nbbAa p�x�P3jAc���   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �SB±�kA��į�<~�4�ǯ�<~�4?��*>��*> �?�WD jAa p�ZP@��vmAi���
�+�(������ְ�P��M�   f5��ZG}A��į�<~�4�ǯ�<~�4?��*>��*>��:@����#�zAa p������Ag���
   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   �c�����A	��į�<~�4�ǯ�<~�4?��*>��*>+��@B���>}Aa p�Å�����Ac���   ��m*JK����N֥� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   %�:�FLmA��į�<~�4�ǯ�<~�4?��*>��*>��:@�X@��jAa p�j�4�}�oAg���
   ��m*JK����N֥� ����6�l���c�r��f��r��+�(������ְ�P��M�   ����/&zA��į�<~�4�ǯ�<~�4?��*>��*>��:@ ���wAa p�B���f�|Ag���
   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   �`�;�sA��į�<~�4�ǯ�<~�4?��*>��*>VUMA{4��CmA��� ±.zA��<   ��m*JK����N֥� ����6�l���c�r��f��r��+�(������ְ�P��M�   �&J�+jA��į�<~�4�ǯ�<~�4?��*>��*>��:@��O��gAa p�OD�R�lAg���
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����A���        '��<��?��*>��*>�8@Z��W=�A���f���K��A�c��
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����A��Y�        '��<��?��*>��*>�8@f���?��A�c��r���3��A?��
�+�(������ְ�P��M�   �����AX���        '��<��?��*>��*>���>Ζ���4�A�*���0��Ś�A���
   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   �c�����A���į�<~�4�ǯ�<~�4?��*>��*>+��@B���>}A�*��Å�����AX���   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   �`�;�sA���į�<~�4�ǯ�<~�4?��*>��*>VUMA{4��CmA�*��� ±.zAX���   ��m*JK����N֥� �����f07L6���	����+�(������ְ�P��M�   ��]�KfA���į�<~�4�ǯ�<~�4?��*>��*>,f�@�mj�nbbAX���x�P3jA���   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����~A��Y�$�̼��?       ���*>��*>�8@������A�c�������Q�A=��
�+�(������ְ�P��M�   �����~A�㖿%�̼��?ǈ^-�#N���*>��*>�8@�����A?��B��=I�A����
   ��m*JK����N֥� ����6�l���c�r��f��r��+�(������ְ�P��M�   �����~AX���$�̼��?�#��̯��*>��*>���>�����-}A�*��������A���
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����~A���$�̼��?       ���*>��*>�8@������A��������Q�A�c��
�+�(������ְ�P��M�   rX4¡�nA�㖿$�̼��?       ���*>��*>�8@�\4¹2mA?����3¡�oA<���
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   rX4¡�nA��Y�$�̼��?       ���*>��*>�8@;e4�oA�c��A�3�r�rA=��
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   rX4¡�nA���$�̼��?       ���*>��*>�8@;e4�oA���A�3�r�rA�c��
�+�(������ְ�P��M�   �OP���hA�㖿$�̼��?       ���*>��*>�8@�SP�ؚgA?��ʠO��fjA<���
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �OP���hA��Y�$�̼��?       ���*>��*>�8@J\P©DjA�c��P�OmA=��
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   i ���xA��Y�$�̼��?       ���*>��*>�8@�u ½?zA�c�������}A=��
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   i ���xA���$�̼��?       ���*>��*>�8@�u ½?zA��������}A�c��
�+�(������ְ�P��M�   i ���xA�㖿$�̼��?       ���*>��*>�8@Rm ��wA?���t���azA<���
   ��m*JK����N֥� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   }�j�K�cA�㖿$�̼��?       ���*>��*>�8@�k�W@bA?�� ej�?eA<���
   ��m*JK����N֥� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   }�j�K�cA���$�̼��?       ���*>��*>�8@ k�'�dA����mj��gA�c��
   	
BLO�K϶�+�i, 
����{���n�����J`�Q��3�ޒ�8�����ġ���   Ձ��.�D�V��ޗ�>ޗ���1 ��1 ? �>G�D@��NAu���.�E«���h@..D� ���   	
BLO�K϶�+�i, 
��m����N,?fY�������ޞ�2��r`<\�{�E   ����=�E�a��k���� ?�ڭ�头>($B?Y-?R	@A K���#G�V5��5
�@..D¬���  	
BLO�K϶�+�i, 
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   ����<F¹����?;j�w�P�Z�5�����3�?j؁@ K���G�V5��u���/.E������   	
BLO�K϶�+�i, 
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   S�~�<F¹����?;j�w�P�Z�5�����3�?j؁@�����G�V5���T�/.E������   	
BLO�K϶�+�i, 
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   �@�<F�c�����?;j�w�P�Z�5�����3�?j؁@����G����@��/.E¤k���   	
BLO�K϶�+�i, 
��8غVE��n`u�sT-i�գ}$uJ�q�NeȊq�`�1��   �iU@aF�z��ҍ*,\�?)�B��_/����G�	?�b@�R@�G�V5��kX@/.E�	����   	
BLO�K϶�+�i,  �P|!����	Eۭ�v	W*��Q��3�ޒ�8�����ġ���   H_�?�>�EÝ�30?�v�>��M�H�wP�@ ��@��Au���..D�\��pZA�#-¬�|�  	
BLO�K϶�+�i,  ��u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   @�
�!YB�X��;j���?Z�5�w�P�����3�?j؁@�@
BLO�K϶�+�i,  ��u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   T��!YB¹��;j���?Z�5�w�P�����3�?j؁@�\��/.C�V5������tOA������   	
BLO�K϶�+�i,  ��u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   �iU@!YB�X��;j���?Z�5�w�P�����3�?j؁@�R@/.C«���kX@tOA,~��   	
BLO�K϶�+�i,  �8غVE��n`u�sT-i�գ}$uJ�q�NeȊq�`�1��   �����EB��j��\�?ҍ*,�_/)�B�����G�	?�b@ K��/.C«���u���tOA�^T���   	
BLO�K϶�+�i,  �������R�����:~���|��}$uJ�q�NeȊq�`�1��   ���@�xA«���h??6Q*?Ġ ��R������|�>�T`@��@_�B�����A�@����   	
BLO�K϶�+�i,  �������R�����:~���|��}$uJ�q�NeȊq�`�1��   (�A�C.«���h??6Q*?Ġ ��R������|�>�T`@���@��/����Q�AV�-����   	
BLO�K϶�+�i,  �������R�����:~���|��}$uJ�q�NeȊq�`�1��   �D A��1«���h??6Q*?Ġ ��R������|�>�T`@��@^�2����PA�0����   	
BLO�K϶�+�i,  �������R�����:~���|��}$uJ�q�NeȊq�`�1��   <�AF-«���p�?�',l	^/SA������|�>�T`@�A��2����<�A��'����   	
BLO�K϶�+�i,  �������R�����:~���|��}$uJ�q�NeȊq�`�1��   5
�@�B«���p�?�',l	^/SA������|�>�T`@��@��H����5
�@��=����   	H��AA�y@4x�@ 
������X8#�KșQ�RG��i�}$uJ�q�NeȊq�`�1��   	K���wB�^�A�?c;�>b#���C?&W�@�r�@5�!A�
��*w�_���߸��>����u�JT`}��������]܄���}   	����ȂBU��A(�~?�S�2����MŽ���?S��?q@�Ƨ�H|B�jyA�V�¹^�BU��A0   	H��AA�y@4x�@ 
��V����Eo2O{/�M%b�`9���Ѐ&�A ���l�o�O�   	�����~B�*xA���9ɪl�f��2��?SU�?�V�?�� >\���s]|B��vA|��P�B�jyA  	H��AA�y@4x�@ 
��
��,Z�/
�L��˦���T�0��	�������Hd�xw
��1ʆ�\g[��f���pr�a�����!���ё�BH   	�^����tB~$�A�+a�(��>�h=�aK? X@$o@Z�?"�­(pB�ʄA�Ϡ��xB�ʒA  	H��AA�y@4x�@ 
��������/�E�qx�
o�\-�aN�1
�@�۬��Z���ʲA�߫¿*g���A   	���NA��y��+�&� M���f07L6���	����+�(������ְ�P��M�   �|��M/ªʲA�N?6�>�N?6����*>��*>�(�@0��=�%©ʲAg��^����A   	���NA��y��+�&� N���f07L6���	����+�(������ְ�P��M�   ��´rl��ʲA�N?6�>�N?6����*>��*>���@�t������ʲA�^��L�����A   	���NA��y��+�&� O���f07L6���	����+�(������ְ�P��M�   3$���v|ªʲA�N?6�>�N?6����*>��*>��@S���!l����A��r�Uu�A   	���NA��y��+�&� P$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t���ʲA�N?6�>�N?6����*>��*>���@����`K����A����ʝ��Uu�A   	���NA��y��+�&� [��6�l���c�r��f��r��+�(������ְ�P��M�   %Y��3AT�yA#�9?80?        ��*>��*>���>�����\2A��vAN,��D*5A�?|A
   	���NA��y��+�&� \-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A��A#�9?80?        ��*>��*>�8@�0��92A�?|Aר5A�A
�+�(������ְ�P��M�   �k����T�yA        #�9�80?��*>��*>���>ʘ��X��©�vA?�©g���?|A
   	���NA��y��+�&� a��6�l���c�r��f��r��+�(������ְ�P��M�   �k����Ƒ�A        #�9�80?��*>��*>�8@ʘ��X���8��A?�©g��Uu�A
   	���NA��y��+�&� e���f07L6���	����+�(������ְ�P��M�   �|��M/��?|A�N?6�>�N?6����*>��*>�(�@0��=�%¨�zAg��^��T�}A   	���NA��y��+�&� f���f07L6���	����+�(������ְ�P��M�   3$���v|��?|A�N?6�>�N?6����*>��*>��@S���!l�¨�zA��r�T�}A   	���NA��y��+�&� g���f07L6���	����+�(������ְ�P��M�   ��´rl��?|A�N?6�>�N?6����*>��*>���@�t�������zA�^��L���T�}A   	���NA��y��+�&� h$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3��?|A�N?6�>�N?6����*>��*>��@����?�S�yAo��½B&��?|A   	���NA��y��+�&� i���f07L6���	����+�(������ְ�P��M�   $��	j@�?|A�N?6�>�N?6����*>��*>x��@E���\W�=��zA���µ��@T�}A   	���NA��y��+�&� j���f07L6���	����+�(������ְ�P��M�   ����.�f��?|A�N?6�>�N?6����*>��*>���@���tq¨�zAY"��?\\�T�}A   	���NA��y��+�&� k$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t���?|A�N?6�>�N?6����*>��*>���@����`K��S�yA����ʝ���?|A   	���NA��y��+�&� l���f07L6���	����+�(������ְ�P��M�   �]��x���?|A�N?6�>�N?6����*>��*>
�@�۬��Z����zA�߫¿*g�T�}A   	���NA��y��+�&� w��6�l���c�r��f��r��+�(������ְ�P��M�   sܰ���q�8��A#�9?80?        ��*>��*>9�@K	�r©�zA����-kq��A
   	���NA��y��+�&� }-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �J��\�A#�9? 80?gv�%��ޥ��*>��*>�8@Y"��n\��?|A�ȯ¿�[��A
   	���NA��y��+�&� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   &���R@�A#�9?80?        ��*>��*>�8@i��&�@��?|AS���@��A
   	���NA��y��+�&� ���6�l���c�r��f��r��+�(������ְ�P��M�   �߮���%�8��A#�9?80?        ��*>��*>9�@��¬K&©�zA����N�%��A
   	���NA��y��+�&� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ��l�A#�9? 80?gvS���^%��*>��*>�8@g��;���?|A�������A
   	���NA��y��+�&� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   5^��������A#�9?80?        ��*>��*>�8@8�\���?|Abެ������A
   	���NA��y��+�&� ���6�l���c�r��f��r��+�(������ְ�P��M�   Y���J���8��A#�9?80?        ��*>��*>9�@1�§�����zA�����H���A
   	���NA��y��+�&� ���6�l���c�r��f��r��+�(������ְ�P��M�   .�¿�e�T�yA#�9?80?        ��*>��*>���>�߫�4rg���vA��¾�d��?|A
   	���NA��y��+�&� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   .�¿�e���A#�9? 80?gvӥ���%��*>��*>�8@�߫�4rg��?|A��¾�d��A
   	���NA��y��+�&� ���6�l���c�r��f��r��+�(������ְ�P��M�   冪��H)�8��A#�9?80?        ��*>��*>9�@����}�Ƚ��zAZ��J4�=�A
   	���NA��y��+�&� ���6�l���c�r��f��r��+�(������ְ�P��M�   ©¶]�@T�yA#�9?80?        ��*>��*>���>+���@��vA}���p��@�?|A
   	���NA��y��+�&� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ©¶]�@��A#�9?80?        ��*>��*>�8@�����H�@�?|A
@�·��@�A
x>�Pr$   }��A�����z B        ��t���?|�%Ai?��,A�~�A������A7B�O�� B   	��VNȋY=��?�v ���=-/k�$����֎�t�3��?^��ɬ�@MQ��
x>�Pr$   �v�AZB-��z B�>�2A#2�H2���7?�K�@���>��,A���A�=^����AJ]�AxF�� B   	��VNȋY=��?�v ��b8
x>�Pr$   &��Az˟��z BףS��Z�0�G2���7?~��@d��>��,AޱA����A<p�A��� B$   	��VNȋY=��?�v �j�ܖ�Ū��]|j4��caN�1
x>�Pr$   ��As����z Bt�s9�4�7?KI2?��@���>��,A_�AK�«��A��A6t�� B   	��VNȋY=��?�v �j�ܖ�Ū��]|j4��caN�1
��aN�1
x>�Pr$   �v�AZB-��?A�>�fA#2�H2���7?�K�@���>��,A���A�=^�UՅ@J]�AxF��R�oA   	��VNȋY=��?�v �'�b8
x>�Pr$   &��Az˟��?A�S�cZ�0�G2���7?~��@d��>��,AޱA�UՅ@<p�A���R�oA$   	��VNȋY=��?�v �(j�ܖ�Ū��]|j4��caN�1
x>�Pr$   ^��A���IU����f���l9��?Csu�᎕>���@�-B_�A���������A6t����vA0   	��VNȋY=��?�v �)j�ܖ�Ū��]|j4��caN�1
��aN�1
x>�Pr$   Ѵ�A�����]�w�!��&�ӯ7?eF2?�]�>�$WA�B�~�A�����\
B 0����nA.   	��VNȋY=��?�v �7��=-/k�$����֎�t�3��?^��ɬ�@MQ��
x>�Pr$   �v�AZB-�
x>�Pr$   &��Az˟� ֿ�S��Z�0�G2���7?~��@d��>��,AޱA��*��<p�A���JUn@$   	��VNȋY=��?�v �8j�ܖ�Ū��]|j4��caN�1
��aN�1
x>�Pr$   y
��RF͌�f�u�u �x���eA.��V�%�����&2�Q��3�ޒ�8�����ġ���   ��Aq�(�@�7�c�A�c�A>�h.��h.? V�=�GA��~A�A�)��~�+�B�(�[���   
��RF͌�f�u�u �x�����1����N�>�an�}��}$uJ�q�NeȊq�`�1��   "��Aq�(�Y��F��F>.�.? �*=sc!A͋A�AƤ(��+�Bz(®j�(   
��RF͌�f�u�u �x*�0�%_T���a^�-8uԣ}$uJ�q�NeȊq�`�1��   ���A��'�\�����?H��+D�7/P������Q)?��d@V\�A�(¤���Aa�&���|��   
��RF͌�f�u�u �x�T�u `�'����n:���}$uJ�q�NeȊq�`�1��   ��B��'�wM
��RF͌�f�u�u �x�D&����A���a;#�z��}$uJ�q�NeȊq�`�1��   V\�Aw(��
��RF͌�f�u�u �x�}d7�A�\֢.�K5��o�}$uJ�q�NeȊq�`�1��   ��A��'�0�0���?OR�+Y�5/rv�����-�
��RF͌�f�u�u �x�}d7�A�\֢.�K5��o�}$uJ�q�NeȊq�`�1��   �A��'�0�S���?OR�+Y�5/rv�����-�
��RF͌�f�u�u �x�}d7�A�\֢.�K5��o�}$uJ�q�NeȊq�`�1��   ��A��'�0�v���?OR�+Y�5/rv�����-�
��RF͌�f�u�u ف��}*�{��p<���t��ޞ�2��r`<\�{�E   ��A�$'�+@�c0��b0�>���?�  >7��?6=�AXc{A�d'�����=dB��&����  
��RF͌�f�u�u ٙ�θ�Kt�D{V����m���}$uJ�q�NeȊq�`�1��    <žAq�(�d@�5?�5?m��m�� ��<2ВA��3BlA�(�n���>�BƄ(����AP   $�NK�I��|{}��» �za���ƹ���h���C�!�{[�=`O�L ����tIj����   b$³�Uu�A              �?  APU�>��A"7�	p����A�¼��� �B   $�NK�I��|{}��» �{a���ƹ���h���C�!�{[�=`O�L ����tIj����   )p³�Uu�A              �? �@PU�>��AY�|�	p����A�c¼��� �B   $�NK�I��|{}��» �|!�B�ɫ5���� Z�XyY{[�=`O�L ����tIj����   �L6�z�1�Uu�A�#�=        v�~? U�>��@��-A"7��8_����AZw5�	p� �B$   $�NK�I��|{}��» �}!�B�ɫ5���� Z�XyY{[�=`O�L ����tIj����   N�c�z�1�Uu�A�#�=        v�~?�U�>��@��-A��d��8_����A�c�	p� �B$   $�NK�I��|{}��» �~�Cj΅���l�lq��f���{[�=`O�L ����tIj����   Yw�$.�Uu�A              �?�U�>n<�@��A�L�@�X����A��	p� �B   $�NK�I��|{}��» ��	i<����y���%���8{[�=`O�L ����tIj����   
@�� A��$��8_����A��@�X� �B$   $�NK�I��|{}��» ����B�^�c�
��        �9?�U�>7�A�QBA_C��u������A	���SW�� �BD   $�NK�I��|{}��» ���7A�]'		jK���#�� {[�=`O�L ����tIj����   FV�� G��Uu�A        5M�  �?�/�A�c�>��A	���������A}I�u��� �B   $�NK�I��|{}��» ��a���ƹ���h���C�!�{[�=`O�L ����tIj����   _C�����Uu�A              �?��J@@U�>��A	����������A����SW�� �B   $�NK�I��|{}��» ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   _C��:A�Uu�A              �?�U�>H�A��A
���SW�����A�������� �B   $�NK�I��|{}��» �����b���8 .��e�\0�{[�=`O�L ����tIj����   �b��FEB�Uu�A        ���  �?�tA�f�>��A������E����APYH���>� �B   $�NK�I��|{}��» �����f07L6���	���{[�=`O�L ����tIj����   `�����Uu�A              �?XU=@PU�>��A����	p����A
������� �B   $�NK�I��|{}��» �����2�T��[��Y�x{[�=`O�L ����tIj����   v����������A              �?���@@U�>  A	���u������A�B�� G��V�B   $�NK�I��|{}��» ���_DY�N��5����㛌8Y������n��\w&e�mO�[   oA��Rۖ��b�A1p2�j7?�:��p��<��A�m�?n�A���®������A���� T�� �
A����Q%�����A�́�ie�� �
   $�NK�I��|{}��» ��!/�_���gA���T��������n��\w&e�mO�[   ����e
��Uu�A"��'�i�=U�~?�ً?�5<5��
A�"��^ �����Am��4$|� �
A����Q%�����A�S�
   $�NK�I��|{}��» ��" "E4�`���y�V���y������n��\w&e�mO�[   /4��g�����A        �.���?�e?���?PU	A���3������A�ȗ�jQ���:
   $�NK�I��|{}��» ��=KG���hA�+AvW��YZ�/��/��N����E��b   ����\����A        �c�<��?�a?=B@PU	A����a�����A��������:
E�����]6�X
.?�d�wN�f�(i�mk�UR�2��   	�g?�+��|�A���;0 ���2��P?�+@Fѹ@��@�J�u������A�L6�|G��U�B0   $�NK�I��|{}��» ���� ؖ����
��.>ݳ�}$uJ�q�NeȊq�`�1��   	��9��ˠ���A�IJ?�?
?ȂU>��?Ǫ4AahA*�I����A��A �� BH   $�NK�I��|{}��» �Ă#���Q]���N����g�#�{[�=`O�L ����tIj����   #As#��zB        �$Y>�-z?�:�?J��?��4A1� A*�I����A��A!� B"   $�NK�I��|{}��» ��4��Q�����d�,�Rm��r��/��/��N����E��b   1)A�t��zBQ��.�4-�t?
&����<��@��4A��A�˗����AN�2A�9� B
   $�NK�I��|{}��» �ł]c��x�~�=H� ��5�g������n��\w&e�mO�[   �#A�����zBD�4���-�t?&��ۗ�<4*@��4A��A�������A�L-A*�I� B
   $�NK�I��|{}��» ��Dp)�K�h_y��X���=!{[�=`O�L ����tIj����   �T&A;D|��zB        &��-�t?>�
�4��zB        d��>��l?ߴJ>�v;��4A���x�5����A"B���`3� B   $�NK�I��|{}��» ��x���
yG1���{[�=`O�L ����tIj����   6R��qy:��zB        ���>�~w?��?0�_?��4A&=��ɈB����A����0� B   $�NK�I��|{}��» ��*�.ُ
   $�NK�I��|{}��» �Ȃ��������b>��yYi۝<{[�=`O�L ����tIj����   ���3�I��zB        2�>~�}?��k?C1�?��4A���Q�R����A�[����@� B   $�NK�I��|{}��» ���ƩsC,�hgPL�ZB(n9�����n��\w&e�mO�[   �u��`O��zB        �U<m�?��m@�v?��4A=�Q�R����A����
L� B   $�NK�I��|{}��» ��j�ܖ�Ū��]|j4��c�/��/��N����E��b   ���
L��zB              �?�pt@  �?��4A=��
L����A� ��
L� B   $�NK�I��|{}��» �ɘ��'{{�0�j�Ia���B�l{[�=`O�L ����tIj����   ���_O��zB�/5?$�4�������4���>}t@��4A=�Q�R����A� ��
L� B   $�NK�I��|{}��» ��'+]@DV:�0������O�����n��\w&e�mO�[   �
#Դ���>�4?@��4A�9=��������A�o
��U�6F�u?.����O>��@Ȫ4A]���������A&������� B6   $�NK�I��|{}��» ��xIÃ*1�n4�Q�YHw�ë�/��/��N����E��b   �&��9V���zB:��p�u?�Om�h7�3S/>D�?��4A�P��������Ap���)�� BJ   $�NK�I��|{}��» ���B��e�C$N�_q��ٯ��{[�=`O�L ����tIj����   Ƒ������zB        .��F�u?���?v��?��4A]���������Ap���)�� B   $�NK�I��|{}��» �Φ��<��|{
H���������n��\w&e�mO�[   ��x� �«zBv�7k��-�U��?HR�>���@¬4A&���a«��A������ B&   $�NK�I��|{}��» ��U��Y��Z+J���;��s�P�/��/��N����E��b   XOn�L «zBI6�n�.�U��?c��>\O�@�4Ap��3�«��A������� B&   $�NK�I��|{}��» �����F�{�X;N��L-)��{[�=`O�L ����tIj����   WZo��y «zB        �VO>��z?>?�@ p�@��4A&���a«��A������� B    $�NK�I��|{}��» �ϐY]}��ͪ�ZK�Y��W�I�������n��\w&e�mO�[   ��X?�«zBg8�3���3S�D?$?�F>8��?��4A��R�«��A��?t�� B6   $�NK�I��|{}��» ���
��شw��?&H(>��4A�����«��A���?�� B9   $�NK�I��|{}��» ���N��*p��w�s��W�ri{[�=`O�L ����tIj����   �[?Y«zB        j)���~?f�?�c�?��4A��R�«��A��?�� B   $�NK�I��|{}��» ���%ݯ�7~�`�����u^J�{[�=`O�L ����tIj����   �@wK«zB        LL���yu?.=?�y?��4A���?t�«��A˅#@X�� B   $�NK�I��|{}��» ��O�z��ԆH���#ᮏ`������n��\w&e�mO�[   ��@�«zB_A6�1b5KL�>�yu?P`b?S(;��4A��?t�«��A˅#@�� B   $�NK�I��|{}��» ����֭.aR��ؠe�҉���/��/��N����E��b   ��?0�«zB�4�
�S�RL�>�yu?��_?��%;��4A���?�«��A�@X�� B   $�NK�I��|{}��» ��R�s�7�=\���6��[nU�/��/��N����E��b   ut6������zB              �?  �?�w�@��4Aut6��������Aut6�Q�R� B   $�NK�I��|{}��» ����4{T�jG���F,�1Ȍ�������n��\w&e�mO�[   =������zB              �?  �?�w�@��4A=��������A=�Q�R� B   $�NK�I��|{}��» ���V�E�1�-ԝkЌ��4�{[�=`O�L ����tIj����   ��9������zB              �?@U�>�w�@��4A=��������Aut6�Q�R� B   $�NK�I��|{}��» ��R�s�7�=\���6��[nU�/��/��N����E��b   �6�E����zB              �?  �?;�@��4A�6��Z�����A�6���� B   $�NK�I��|{}��» ����4{T�jG���F,�1Ȍ�������n��\w&e�mO�[   �9=�E����zB              �?  �?;�@��4A�9=��Z�����A�9=���� B   $�NK�I��|{}��» ���V�E�1�-ԝkЌ��4�{[�=`O�L ����tIj����   i�9�E����zB              �?@U�>;�@��4A�9=��Z�����A�6���� B   $�NK�I��|{}��» �ӘZ*yǭ� ��$w��oބ�r�/��/��N����E��b   ut6���+��zB��:        ��?  �?]�@��4Aut6��
L����Aut6�m�� B   $�NK�I��|{}��» ��m�l:b�����nMj��������n��\w&e�mO�[   =���+��zB��:        ��?  �?]�@��4A=��
L����A=�m�� B   $�NK�I��|{}��» �Ӟђ	@ ���٫��28*��m�{[�=`O�L ����tIj����   ��9���+��zB
L����Aut6�m�� B   $�NK�I��|{}��» ��-��Ά�9
Kݾ_Uo��$ȳoe���n[��]��0�    Hr[A1}��  �A4�>ni?�� :���9L�?�ʰ@T��@�F:AS
B  $�NK�I��|{}��» ��G|.�Riw����}��(^*������5/���&9����    �O[A/m�����A        �[m?�̿����@���>  �?þ3A[
B$  $�NK�I��|{}��» ��-��Ά�9
Kݾ_Uo��$ȳoe���n[��]��0�    �LA ���  �A��<�?6:9:�=�8L�?�ʰ@T��@ƎEA9���Uu�A��OA
B  $�NK�I��|{}��» ��G|.�Riw����}��(^*������5/���&9����    ��KA�������A        ��5�J%4?���@���>  �?S3@A隞����AEA��d����A   $�NK�I��|{}��» ��pI�!���-^ݯ�]�E
B$  $�NK�I��|{}��» ��-��Ά�9
Kݾ_Uo��$ȳoe���n[��]��0�    fA����  �Ap&.?�;?�_�9M:J�?�ʰ@T��@�ʾ@m���Uu�A�a7A�M��U�
B  $�NK�I��|{}��» ��G|.�Riw����}��(^*������5/���&9����    WOA�������A        \�?Gq����@���>  �?�L�@<������A�"6A�������A   $�NK�I��|{}��» ��pI�!���-^ݯ�]�E
Q5A���U�
B$  $�NK�I��|{}��» �׻�8"�%�A�m���p�|�$ȳoe���n[��]��0�    ��@�2��  �A�Ц��r?��(�C��9K�?�ʰ@T��@^Q�@�V�Uu�A�}A����U�
B  $�NK�I��|{}��» ��S�IG�ّ��#�r
����^*������5/���&9����    ���@�3�����A        ��c?�;�>���@���>  �?W�@�Vª��A�(A�������A   $�NK�I��|{}��» ��pI�!���-^ݯ�]�E
B$  $�NK�I��|{}��» �ػ�8"�%�A�m���p�|�$ȳoe���n[��]��0�    �GdA�٣�  �A�0���9?6i�Z:J�?�ʰ@T��@�*7AT	��Uu�A��Aί��U�
B  $�NK�I��|{}��» ��S�IG�ّ��#�r
����^*������5/���&9����    c1dA������A        �?��F=���@���>  �?98Ao	�����A:)�AnǠ����A   $�NK�I��|{}��» ��pI�!���-^ݯ�]�E
���?��
B$  $�NK�I��|{}��» �ٻ�8"�%�A�m���p�|�$ȳoe���n[��]��0�    ��GA��6�  �A#c��)_?��7��S	9L�?�ʰ@T��@Q�7A��c�Uu�AW�DAk��U�
B  $�NK�I��|{}��» ��S�IG�ّ��#�r
����^*������5/���&9����    �GA��6����A        ,�=?,?���@���>  �?|�AA��b����A�NAh�
����A   $�NK�I��|{}��» ��pI�!���-^ݯ�]�E
,?���@Ņ�=UU�@��CA�
b�Uu�A�.LAΡ�U�
B$  $�NK�I��|{}��» ��v� TW�߂G��'�/
��{[�=`O�L ����tIj����   .9��r�L�Uu�Aq�<��?^ �2� ���EA�U�>��A=����N«��A��e�J� �B   $�NK�I��|{}��» ��Բ����	X0D�ٽ�(�
�{{[�=`O�L ����tIj����   0���$�Uu�A<60�ѳ9?[�2P�첪��>y�MA��A=���L�&«��A�ٮ��a"� �B   $�NK�I��|{}��» ��^I�_���L�;��X�<���{[�=`O�L ����tIj����   F&������Uu�Aڸ�<|�?c�A1���0J�VA���>��A=����x�����A$��¶��� �B   $�NK�I��|{}��» ��I;E�� ۏ��[�%���D�{[�=`O�L ����tIj����   ����Uu�Aͳ�<}�?�#�xT��h<_A���>��A=���V������A}��¸e�� �B   $�NK�I��|{}��» ���_����^j�o�C.Bb j{[�=`O�L ����tIj����   w����'�Uu�A:��<~�?�1�1�/�gA���>��A=����#1����A���§]� �B   $�NK�I��|{}��» ���X�ZF38��P8�ܵ1���{[�=`O�L ����tIj����   ܋��U7�>Uu�Aª�<�?I&���]��pA���>��A=����_����AP���|? �B   $�NK�I��|{}��» �����2�T��[��Y�x�0����$P�����L��m�   V۰�@�qª��A        80?"�9?�*A��*>  �>R���!l�ª��AY"��?\\ª��A   $�NK�I��|{}��» ����2�T��[��Y�x�0����$P�����L��m�   wԮ��@$ª��A        80?"�9?\F\A��*>  �>����?ª��Ag��^�ª��A   $�NK�I��|{}��» ����2�T��[��Y�x�0����$P�����L��m�   1���`�����A        80?"�9? �IA��*>  �>����aK�����A�߫¿*g����A   $�NK�I��|{}��» ����2�T��[��Y�x�0����$P�����L��m�   Z���.-༪��A        80?"�9?��hA��*>  �>�t��������A���¶��@���A   $�NK�I��|{}��» ����f07L6���	��䬕��u	���B1������   �.���u|�8��A        80?"�9?��@���=��@����tj����A԰ºr�q<�A  $�NK�I��|{}��» ����f07L6���	��䬕��u	���B1������   "B�3�8��A        80?"�9?��@���=��@߬��8�?���Ad׮��C&�q<�A  $�NK�I��|{}��» ����f07L6���	��䬕��u	���B1������   r���0.�8��A        80?"�9?�(�@���=��@�����%���A\��|��q<�A  $�NK�I��|{}��» ����f07L6���	��䬕��u	���B1������   n��Zr��8��A        80?"�9?���@���=��@�{�®D����A����q<�A  $�NK�I��|{}��» ����f07L6���	��䬕��u	���B1������   kh���u��8��A        80?"�9?�@���=��@Ѭ�T����A����6/g�q<�A  $�NK�I��|{}��» ����f07L6���	��䬕��u	���B1������   g����`l�8��A        80?"�9?���@���=��@Uj��E}����Az~���丽q<�A  $�NK�I��|{}��» ����f07L6���	��䬕��u	���B1������   &/���j@8��A        80?"�9?z��@���=��@�����	�=��A�������@q<�A  $�NK�I��|{}��» �"���f07L6���	��䬕��u	���B1������   =����f�8��A        80?"�9?���@���=��@,����pq���AMB��]]\�q<�A  $�NK�I��|{}��» �#���f07L6���	����+�(������ְ�P��M�   ���hN���B�N?6�>�N?6����*>��*>���@s�¿�[ª:B�f��f@�U�B   $�NK�I��|{}��» �$���f07L6���	����+�(������ְ�P��M�   $��	j@��B�N?6�>�N?6����*>��*>x��@E���\W�=�:B���µ��@U�B   $�NK�I��|{}��» �%���f07L6���	����+�(������ְ�P��M�   ����.�f� �B�N?6�>�N?6����*>��*>���@���tqª:BY"��?\\�U�B   $�NK�I��|{}��» �&���f07L6���	����+�(������ְ�P��M�   ���������B�N?6�>�N?6����*>��*>���@'B���ª:B�5��a���U�B   $�NK�I��|{}��» �'$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3���B�N?6�>�N?6����*>��*>��@����?ª:Bo��½B&�U�B   $�NK�I��|{}��» �(���f07L6���	����+�(������ְ�P��M�   ����2yA �B�N?6�>�N?6����*>��*>��o@y�·��@�:B�0��2AU�B   $�NK�I��|{}��» �)���f07L6���	����+�(������ְ�P��M�   e���c�-���B�N?6�>�N?6����*>��*>���@�0�½�d��:B;$�����U�B   $�NK�I��|{}��» �*���f07L6���	����+�(������ְ�P��M�   �]��x����B�N?6�>�N?6����*>��*>
�@�۬��Z����B�߫¿*g��:B   $�NK�I��|{}��» �+���f07L6���	����+�(������ְ�P��M�   �|��M/���B�N?6�>�N?6����*>��*>�(�@0��=�%���Bg��^�ª:B   $�NK�I��|{}��» �,���f07L6���	����+�(������ְ�P��M�   ��´rl���B�N?6�>�N?6����*>��*>���@�t�������B�^��L����:B   $�NK�I��|{}��» �-���f07L6���	����+�(������ְ�P��M�   3$���v|� �B�N?6�>�N?6����*>��*>��@S���!l�ª:B��r�U�B   $�NK�I��|{}��» �.$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t����B�N?6�>�N?6����*>��*>���@����`K���:B����ʝ��U�B   $�NK�I��|{}��» �/��6�l���c�r��f��r��+�(������ְ�P��M�   %Y��3A��A#�9?80?        ��*>��*>���>�����\2A���AN,��D*5AUu�A
   $�NK�I��|{}��» �0-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A�X�A#�9?80?        ��*>��*>�8@�����\2AUu�AN,��D*5Aq<�A
�+�(������ְ�P��M�   �k������A        #�9�80?��*>��*>���>ʘ��X��ª��A?�©g��Uu�A
   $�NK�I��|{}��» �2��6�l���c�r��f��r��+�(������ְ�P��M�   �k���sB        #�9�80?��*>��*>�8@ʘ��X���A?�©g��U�B
   $�NK�I��|{}��» �3���f07L6���	����+�(������ְ�P��M�   �|��M/�Tu�A�N?6�>�N?6����*>��*>�(�@0��=�%©��Ag��^����A   $�NK�I��|{}��» �4���f07L6���	����+�(������ְ�P��M�   3$���v|�Tu�A�N?6�>�N?6����*>��*>��@S���!l����A��r�Uu�A   $�NK�I��|{}��» �5���f07L6���	����+�(������ְ�P��M�   ��´rl�Tu�A�N?6�>�N?6����*>��*>���@�t��������A�^��L�����A   $�NK�I��|{}��» �6$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3�Tu�A�N?6�>�N?6����*>��*>��@����?©��Ao��½B&���A   $�NK�I��|{}��» �7���f07L6���	����+�(������ְ�P��M�   $��	j@Tu�A�N?6�>�N?6����*>��*>x��@E���\W�=���A���µ��@��A   $�NK�I��|{}��» �8���f07L6���	����+�(������ְ�P��M�   ����.�f�Tu�A�N?6�>�N?6����*>��*>���@���tq���AY"��?\\�Uu�A   $�NK�I��|{}��» �9$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t��Tu�A�N?6�>�N?6����*>��*>���@����`K�����A����ʝ����A   $�NK�I��|{}��» �:���f07L6���	����+�(������ְ�P��M�   �]��x��Tu�A�N?6�>�N?6����*>��*>
�@�۬��Z�����A�߫¿*g���A   $�NK�I��|{}��» �;��6�l���c�r��f��r��+�(������ְ�P��M�   sܰ���q�A#�9?80?        ��*>��*>9�@K	�rª��A����-kq�q<�A
   $�NK�I��|{}��» �<-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �J��\��X�A#�9?80?        ��*>��*>�8@�w��.e\�Uu�A���ѱ[�q<�A
   $�NK�I��|{}��» �>-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   &���R@��X�A#�9? 80?,��08�e���*>��*>�8@�f���w@�Uu�A
   $�NK�I��|{}��» �@��6�l���c�r��f��r��+�(������ְ�P��M�   �߮���%�A#�9?80?        ��*>��*>9�@��¬K&ª��A����N�%�q<�A
   $�NK�I��|{}��» �A-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ��l��X�A#�9?80?        ��*>��*>�8@�F��M��Uu�A�����q<�A
   $�NK�I��|{}��» �C-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   5^�������X�A#�9?80?        ��*>��*>�8@���>���Uu�A]1�9��q<�A
   $�NK�I��|{}��» �E��6�l���c�r��f��r��+�(������ְ�P��M�   Y���J�����A#�9?80?        ��*>��*>9�@1�§������A�����H��q<�A
   $�NK�I��|{}��» �F��6�l���c�r��f��r��+�(������ְ�P��M�   .�¿�e���A#�9?80?        ��*>��*>���>A7��W�h����A�ݫ���e�Uu�A
   $�NK�I��|{}��» �G-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   .�¿�e��X�A#�9?80?        ��*>��*>�8@5��yNg�Uu�AW۫��d�q<�A
   $�NK�I��|{}��» �J��6�l���c�r��f��r��+�(������ְ�P��M�   冪��H)���A#�9?80?        ��*>��*>9�@����}�Ƚ���AZ��J4�=q<�A
   $�NK�I��|{}��» �K��6�l���c�r��f��r��+�(������ְ�P��M�   ©¶]�@��A#�9?80?        ��*>��*>���>+���@���A}���p��@Uu�A
   $�NK�I��|{}��» �L-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ©¶]�@�X�A#�9?80?        ��*>��*>�8@���@��@Uu�AA���,+�@q<�A
�+�(������ְ�P��M�   %Y��3A�sB#�9?80?        ��*>��*>�8@�����\2A��AN,��D*5AU�B
   $�NK�I��|{}��» �[-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �k������A        #�9�80?��*>��*>�8@ʘ��X���q<�A?�©g��A
�+�(������ְ�P��M�   sܰ���qsB#�9?80?        ��*>��*>�8@����sr�Aر��e�q�U�B
   $�NK�I��|{}��» �]0]�����!E�U�=7O(
�+�(������ְ�P��M�   �J��\sB#�9? 80?,��08�e���*>��*>�8@Y"��n\�A�ȯ¿�[�U�B
   $�NK�I��|{}��» �^0]�����!E�U�=7O(
�+�(������ְ�P��M�   &���R@sB#�9?80?        ��*>��*>�8@9���8�@�A�d���@�U�B
   $�NK�I��|{}��» �_0]�����!E�U�=7O(
�+�(������ְ�P��M�   �߮���%sB#�9?80?        ��*>��*>�8@����&�A4���%�U�B
   $�NK�I��|{}��» �`0]�����!E�U�=7O(
�+�(������ְ�P��M�   ��lsB#�9? 80?�}������*>��*>�8@g��;��A������U�B
   $�NK�I��|{}��» �a0]�����!E�U�=7O(
�+�(������ְ�P��M�   5^�������sB#�9?80?        ��*>��*>�8@H��­J����A�3������U�B
   $�NK�I��|{}��» �b0]�����!E�U�=7O(
�+�(������ְ�P��M�   Y���J����sB#�9?80?        ��*>��*>�8@l��Z����A����[��U�B
   $�NK�I��|{}��» �c0]�����!E�U�=7O(
�+�(������ְ�P��M�   .�¿�e��sB#�9?80?        ��*>��*>�8@A7��W�h���A�ݫ���e�U�B
   $�NK�I��|{}��» �d0]�����!E�U�=7O(
�+�(������ְ�P��M�   �L�����sB#�9? 80?,��08�e���*>��*>�8@;$���2����A�ʪ����U�B
   $�NK�I��|{}��» �e0]�����!E�U�=7O(
�+�(������ְ�P��M�   冪��H)��sB#�9?80?        ��*>��*>�8@���¤z9���AI\���ûU�B
   $�NK�I��|{}��» �f0]�����!E�U�=7O(
�+�(������ְ�P��M�   ©¶]�@�sB#�9?80?        ��*>��*>�8@+���@��A}���p��@U�B
   $�NK�I��|{}��» �h���f07L6���	��䬕��u	���B1������   �.���u|���A        80?"�9?��@���=�8@����tj��q<�A԰ºr�A  $�NK�I��|{}��» �i���f07L6���	��䬕��u	���B1������   =����f���A        80?"�9?���@���=�8@,����pq�q<�AMB��]]\�A  $�NK�I��|{}��» �k���f07L6���	��䬕��u	���B1������   "B�3���A        80?"�9?��@���=�8@߬��8�?�q<�Ad׮��C&�A  $�NK�I��|{}��» �l���f07L6���	��䬕��u	���B1������   r���0.���A        80?"�9?�(�@���=�8@�����%�q<�A\��|��A  $�NK�I��|{}��» �n���f07L6���	��䬕��u	���B1������   n��Zr����A        80?"�9?���@���=�8@�{�®D��q<�A������A  $�NK�I��|{}��» �o���f07L6���	��䬕��u	���B1������   kh���u����A        80?"�9?�@���=�8@Ѭ�T��q<�A����6/g���A  $�NK�I��|{}��» �q���f07L6���	��䬕��u	���B1������   g����`l���A        80?"�9?���@���=�8@Uj��E}��q<�Az~���丽��A  $�NK�I��|{}��» �r���f07L6���	��䬕��u	���B1������   &/���j@��A        80?"�9?z��@���=�8@�����	�=q<�A�������@��A  $�NK�I��|{}��» �t-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A��A#�9?80?        ��*>��*>�8@���¬�3Aq<�A*��"6A��A
�@����X��8��A��Eg��X�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   *c���1�A�N?6�>�N?6�����=���<�(�@1Ȯ��%�8��A#������X�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   �
�y|�A�N?6�>�N?6�����=���<��@TT��vk��8��A����Qr��X�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   �y����f�A�N?6�>�N?6�����=���<���@�İ��rq�8��A/���b\��X�A   $�NK�I��|{}��» ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y����A�N?6�>�N?6�����=���<���@�F�µH��8��A����4����X�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   �
���i@��A�N?6�>�N?6�����=���<x��@Fo����=8��At�����@�X�A   $�NK�I��|{}��» ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3�A�N?6�>�N?6�����=���<��@�w��<�?�8��A+Į�rI&��X�A   $�NK�I��|{}��» ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l���A�N?6�>�N?6�����=���<���@�4��a���8��A@k�§Ľ�X�A   $�NK�I��|{}��» ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y��q<�A�N?6�>�N?6�����=���<���@�F�µH����A����4���Ƒ�A   $�NK�I��|{}��» ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3�q<�A�N?6�>�N?6�����=���<��@�w��<�?���A+Į�rI&�Ƒ�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   �
���i@q<�A�N?6�>�N?6�����=���<x��@Fo����=��At�����@Ƒ�A   $�NK�I��|{}��» ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l�q<�A�N?6�>�N?6�����=���<���@�4��a�����A@k�§ĽƑ�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   �y����f�q<�A�N?6�>�N?6�����=���<���@�İ��rq���A/���b\�Ƒ�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   "D��t}��q<�A�N?6�>�N?6�����=���<
�@����X����A��Eg�Ƒ�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   *c���1�q<�A�N?6�>�N?6�����=���<�(�@1Ȯ��%���A#�����Ƒ�A   $�NK�I��|{}��» �����f07L6���	����+�(������ְ�P��M�   �
�y|�q<�A�N?6�>�N?6�����=���<��@TT��vk����A����Qr�Ƒ�A   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   꾫�!SM���A        80?"�9?��:@��*=���@��¿�d����A/��6��:B   $�NK�I��|{}��» ��Vz��������A�����2��0����$P�����L��m�   -ޫ�@�_����A        80?"�9?���= �>  @?)?����`����A1}�$_����A   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   �U��r����A        #�9�80?��:@��*=���@����&����A;$�¨����:B   $�NK�I��|{}��» ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   �6�¦4�����A        #�9�80?���= �>  @?�����������A�ժ�e������A   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   ���S.���A        80?"�9? �?���=���@˷��s
6����Acr��3�%��:B   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   t��X�U���A        80?"�9?��:@��*=���@�����[ª��Al���,Pª:B   $�NK�I��|{}��» ��Vz��������A�����2��0����$P�����L��m�   � ��`�Zª��A        80?"�9?���= �>  @?�����Zª��A���·ZZª��A   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   �Э�wG���A        80?"�9?��:@��*=���@���ª��Az������:B   $�NK�I��|{}��» ��Vz��������A�����2��0����$P�����L��m�   ���~�ª��A        80?"�9?���= �>  @?�P��&%ª��Aʎ��ֻª��A   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   �g�D����A        #�9�80?��:@��*=���@J���d������A�5��Ǜ���:B   $�NK�I��|{}��» ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   LH�������A        #�9�80?���= �>  @?����N`�����AҬ­������A   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   ��������A        80?"�9? �?���=���@dɭ������A����u����:B   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   ����,AF���A        #�9�80?��:@��*=���@��Lª��AxQ�� o@ª:B   $�NK�I��|{}��» ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   >y��$�Aª��A        #�9�80?���= �>  @?�į��Aª��A��¸eAª��A   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   �ׯ¤N���A        80?"�9? �?���=���@U���,Pª��A�Lª:B   $�NK�I��|{}��» �����2�T��[��Y�x�}�9�H
1ћfb��   �x��x�
1ћfb��   =Q��i�+A��A        80?"�9?VUU?���=���@�q��'%A���A�0�¬n2A�:B   %�+�JƢo��Y�' �i�߱�����1��,,kr<���e���C�'�a�8�~.�    �5�¿h+��ψA{��z�&�5��5?��@���> �B���>0� ����j�&� �B   %�+�JƢo��Y�' �s���L��p5|4�N���nא�� �s�gtQ�#�e;$,�    6��¾h+��ІA9��:�κ�5��5?���@�ª?��(B�`��j�3�������>#� �Bv  %�+�JƢo��Y�' "�i�߱�����1��,,kr<���e���C�'�a�8�~.�    �5��pm���ψA{��z�&�5��5?��@���> �B����� �������� �B   %�+�JƢo��Y�' "�s���L��p5|4�N���nא�� �s�gtQ�#�e;$,�    6���om���ІA9��:�κ�5��5?���@�ª?��(B�`�������������� �Bv  %�+�JƢo��Y�' I�i�߱�����1��,,kr<���e���C�'�a�8�~.�    �5���rE��ψA{��z�&�5��5?��@���> �B���1�X� ���2� �B   %�+�JƢo��Y�' I�s���L��p5|4�N���nא�� �s�gtQ�#�e;$,�    6����rE��ІA9��:�κ�5��5?���@�ª?��(B�`�f�������1�$� �Bv  %�+�JƢo��Y�' Q�i�߱�����1��,,kr<���e���C�'�a�8�~.�    �5��|E@�ψA{��z�&�5��5?��@���> �B���N~�? �����4�@ �B   %�+�JƢo��Y�' Q�s���L��p5|4�N���nא�� �s�gtQ�#�e;$,�    6��E@�ІA9��:�κ�5��5?���@�ª?��(B�`�¤ӄ?�����ߣ@ �Bv  %�+�JƢo��Y�' Y�i�߱�����1��,,kr<���e���C�'�a�8�~.�    �5���4�A�ψA{��z�&�5��5?��@���> �B���O��A ���¤ߜA �B   %�+�JƢo��Y�' Y�s���L��p5|4�N���nא�� �s�gtQ�#�e;$,�    6����4�A�ІA9��:�κ�5��5?���@�ª?��(B�`�¤߂A������O��A �Bv  %�+�JƢo��Y�' l�i�߱�����1��,,kr<���e���C�'�a�8�~.�    �5��HYB�ψA{��z�&�5��5?��@���> �B����B ���.B �B   %�+�JƢo��Y�' l�s���L��p5|4�N���nא�� �s�gtQ�#�e;$,�    6���IYB�ІA9��:�κ�5��5?���@�ª?��(B�`��:]�A�������B �Bv  %�+�JƢo��Y�' ��i�߱�����1��,,kr<���e���C�'�a�8�~.�    �5��z�DB�ψA{��z�&�5��5?��@���> �B���%!@B ������IB �B   %�+�JƢo��Y�' ��s���L��p5|4�N���nא�� �s�gtQ�#�e;$,�    6���{�DB�ІA9��:�κ�5��5?���@�ª?��(B�`����<B������%!MB �Bv  %�+�JƢo��Y�' ��i�߱�����1��,,kr<���e���C�'�a�8�~.�    �5��Eo�B�ψA{��z�&�5��5?��@���> �B���4	|B �����قB �B   %�+�JƢo��Y�' ��s���L��p5|4�N���nא�� �s�gtQ�#�e;$,�    6���Eo�B�ІA9��:�κ�5��5?���@�ª?��(B�`��߳xB�������B �Bv  ��xr�N���ä�� "���fQU_�gl���`��屣ƣ}$uJ�q�NeȊq�`�1��    �t/��������e5?�4��6ӻ���;��P@��+A�[�A�d��5B�� p!³�@�����4  ��xr�N���ä�� "����f07L6���	��䬕��u	���B1������    �t/�଄�����              �?  "A��*=�b�AQ������¦��]�@5��¬���  
?*AwU�?�o�RL^@��B��l� �aAU�B�  
y15          �?U��A�j
?[U�?A}�K�HB��Ba���JBU�B@  
?+Y�A�U�?���K�HB��B��D���JBU�B  
 < �?�/@�3�>  �@�HPA���«��A�|A����V�	B   b�<ݔD�cQ�Y0�x ��������2���P�k\DA{[�=`O�L ����tIj����   �j
�u�dª��A   *L�ŔI�*����� �I��$
H �J��b1���m�ã}$uJ�q�NeȊq�`�1��   �)jAz����As�4?s�4?�{2��{2�����O��>��c@�gAƤª��A�:lAqO�U5�A   *L�ŔI�*����� �I��$
H �J��b1���m�ã}$uJ�q�NeȊq�`�1��   �)jA�d(����As�4?s�4?�{2��{2�����O��>��c@�gAq�(ª��A�:lA:(�U5�A   *L�ŔI�*����� �� ���b%���ֲIoŮ%�Q��3�ޒ�8�����ġ���   �kAq�©��A��Ǫ          �?�U�=���@ T�=ɺjA:(��_�AtelAƤ�S5�A   *L�ŔI�*����� �
�B��A����V���n'?�!?��*=\A@���@�ֶArv����A0~�A��S��A(   *L�ŔI�*����� ��>��rTl.	ɮ�"�!GQ��3�ޒ�8�����ġ���   r{�A�1©��A        P����?eAu>+? T�=G-lA����_�AA�A�k�S5�A   *L�ŔI�*����� ���T�u `�'����n:���}$uJ�q�NeȊq�`�1��   ,mkA~����A��?���<T^2�������{?m�c@B�jA*�ª��A�:lA���U5�A�   *L�ŔI�*����� ���}d7�A�\֢.�K5��o�}$uJ�q�NeȊq�`�1��   @�A&R��A��?���<��0�Ep�����.�
� �f���2�T��[��Y�xr��(;�{p9DC}�\ə�   Z%�B�#«J��              �?UUu?UUu?VUA0�B�z%�����Bk�!¬j?�   bSF3N1�9��;
� �g���2�T��[��Y�xr��(;�{p9DC}�\ə�   ]&�B�!$«J��              �?UUu?UUu?VUA1�BN&�����B�6"¬j?�   bSF3N1�9��;
� �h���2�T��[��Y�xr��(;�{p9DC}�\ə�   �3GB� #«J��              �?UUu?UUu?VUA+IEB9�$����IB�!¬j?�   bSF3N1�9��;
� �i���2�T��[��Y�xr��(;�{p9DC}�\ə�   �<B�3S«J��              �?UUu?UUu?VUA�:BDU���D�=B�HQ¬j?�   bSF3N1�9��;
� �j���2�T��[��Y�xr��(;�{p9DC}�\ə�   4uBz�S«J��              �?UUu?UUu?VUA�1sB$�U����wB��Q¬j?�   bSF3N1�9��;
� �k���2�T��[��Y�xr��(;�{p9DC}�\ə�   �b�B�T«J��              �?UUu?UUu?VUA�m�B1�U���>X�B�R¬j?�   bSF3N1�9��;
� �l���2�T��[��Y�xr��(;�{p9DC}�\ə�    �BE�T«J��              �?UUu?UUu?VUA�*�B�mV���p�B��R¬j?�   bSF3N1�9��;
� �m���2�T��[��Y�xr��(;�{p9DC}�\ə�   2�GB/����J��              �?UUu?UUu?VUA��EB�p�����~IB�����j?�   bSF3N1�9��;
� �n���2�T��[��Y�xr��(;�{p9DC}�\ə�   �U�B=����J��              �?UUu?UUu?VUA3`�B�������J�B�����j?�   bSF3N1�9��;
� �o���2�T��[��Y�xr��(;�{p9DC}�\ə�   �V�BX����J��              �?UUu?UUu?VUA6a�B�������K�B���j?�   bSF3N1�9��;
� �p���2�T��[��Y�xr��(;�{p9DC}�\ə�   ��B
���J��              �?UUu?UUu?VUA���B_Ɯ���Y|�B����j?�   bSF3N1�9��;
� �q���2�T��[��Y�xr��(;�{p9DC}�\ə�    ��B�͗��J��              �?UUu?UUu?VUA���BD�����U{�B�����j?�   bSF3N1�9��;
� �r���2�T��[��Y�xr��(;�{p9DC}�\ə�   "�GBᮖ��J��              �?UUu?UUu?VUAx
FB6�������IB�ْ��j?�   bSF3N1�9��;
� �s���2�T��[��Y�xr��(;�{p9DC}�\ə�   VHBJ
���J��              �?UUu?UUu?VUAhkFB�/����@JB�����j?�   bSF3N1�9��;
� �t���2�T��[��Y�xr��(;�{p9DC}�\ə�   x��B�����J��              �?UUu?UUu?VUA#��B�m���ͫ�B,1���j?�   bSF3N1�9��;
� �u���2�T��[��Y�xr��(;�{p9DC}�\ə�   |��Bv	��J��              �?UUu?UUu?VUA&¤B!�	���Ѭ�B�����j?�   bSF3N1�9��;
� �v���2�T��[��Y�xr��(;�{p9DC}�\ə�   �BV9@�J��              �?UUu?UUu?VUA��Br�@��nݦB� X@�j?�   bSF3N1�9��;
� �w���2�T��[��Y�xr��(;�{p9DC}�\ə�   �B�nB@�J��              �?UUu?UUu?VUA��BJ�#@��k܅B�a@�j?�   bSF3N1�9��;
� �x���2�T��[��Y�xr��(;�{p9DC}�\ə�   M�HBcgK@�J��              �?UUu?UUu?VUA��FB��,@����JBj@�j?�    ����E����5G��� ���bj>�Zt #�h�����={[�=`O�L ����tIj����   �Ď��_�?Uu�AP���]?�J�19�1��9A���>��A�S��m.�>���A�S����@ �B    ����E����5G��� ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   
�����F�{[�=`O�L ����tIj����   #���/B'j B�%>         �}? U�>UZ�@!A͇�&B���Ax��·�:B �B    ����E����5G��� ���l�Xn>��
1ћfb��   
1ћfb��   b>�����A��A        �5��5?��?���=���@�S�����A���A
    ����E����5G��� �Ð��f07L6���	����+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� �Ʋ�6�l���c�r��f��r��+�(������ְ�P��M�   
    ����E����5G��� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   
    ����E����5G��� �ʲ�6�l���c�r��f��r��+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�����F�{[�=`O�L ����tIj����   #���/B��A�%>         �}? U�>UZ�@!A͇�&BUՅ@x��·�:BR�aA    ����E����5G��� ���l�Xn>��
1ћfb��   
1ћfb��   b>��|�A�*�@        �5��5?��?���=���@�S��|�ARՅ@
1ћfb��   
    ����E����5G��� ����f07L6���	����+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� �"-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� �$0]�����!E�U�=7O(
�+�(������ְ�P��M�   
    ����E����5G��� �%-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� �(-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� �*-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� �,-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� �.-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� �0-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� �2-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�����F�{[�=`O�L ����tIj����   #���/B~ؿ�%>         �}? U�>UZ�@!A͇�&B�*��x��·�:BJU6@    ����E����5G��� �Y�l�Xn>��
1ћfb��   
1ћfb��   b>��|�A��i�        �5��5?��?���=���@�S��|�A�*��
1ћfb��   
    ����E����5G��� �|���f07L6���	����+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�����F�{[�=`O�L ����tIj����   #���/B��_��%>         �}? U�>VZ�@!A͇�&B���x��·�:BX�    ����E����5G��� �ga��'�SHh�hT}�:A�w�א�� �s�gtQ�#�e;$,�   ���M�cB�j_��=�=        �l?  @?��A%OA�Ș���AB����H��^��BX	�     ����E����5G��� �h��
1ћfb��   
1ћfb��   b>��|�AW�        �5��5?��?���=���@�S��|�A���
1ћfb��   
    ����E����5G��� �����f07L6���	����+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
1ћfb��   ������V���A        �5��5?��?���=���@	ۻ���Xª��A^0����Tª:B    ����E����5G��� �����2�T��[��Y�x�}�9�H
1ћfb��   ^����^���A        �5?�5?��:@��*=���@	ۻ�q�dª��A������Xª:B    ����E����5G��� ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   ^����dcª��A        �5?�5?���=���>  @?^0��q�cª��A^0��:cª��A    ����E����5G��� � ���f07L6���	����0����$P�����L��m�   ^0���mª��A        �5��5?�~�@��*>  �>	ۻ���uª��A����:eª��A    ����E����5G��� ����2�T��[��Y�x�}�9�H
1ћfb��   ^���qO���A        �5��5?��:@��*=���@^0����Tª��A	ۻ�:Iª:B    ����E����5G��� �Vz��������A�����2��0����$P�����L��m�   ^����dJª��A        �5��5?���=���>  @?����q�Jª��A����:Jª��A    ����E����5G��� ����f07L6���	����0����$P�����L��m�   ^0����~ª��A        �5��5?�ӂ@��*>  �>	ۻ��w�ª��A������vª��A    ����E����5G��� ����f07L6���	����0����$P�����L��m�   ^0���?ª��A        �5��5?,�@��*>  �>	ۻ�p�Hª��A�����5ª��A    ����E����5G��� ����f07L6���	��䬕��u	���B1������   ���,�+�8��A        �5��5?m��@���=��@	[��C�4���A^���o"�q<�A   ����E����5G��� ����f07L6���	��䬕��u	���B1������   ����?�8��A        �5��5?,�@���=��@	[��p�H���A^����5�q<�A   ����E����5G��� ����f07L6���	��䬕��u	���B1������   ����m�8��A        �5��5?�~�@���=��@	[����u���A^���:e�q<�A   ����E����5G��� ����f07L6���	��䬕��u	���B1������   �����~�8��A        �5��5?�ӂ@���=��@	[���w����A^�����v�q<�A   ����E����5G��� ����f07L6���	��䬕��u	���B1������   ���,�+�9B        �5��5?m��@���=9�@	[��C�4�A^���o"ª:B   ����E����5G��� ����f07L6���	��䬕��u	���B1������   ����?�9B        �5��5?,�@���=9�@	[��p�H�A^����5ª:B   ����E����5G��� ����f07L6���	��䬕��u	���B1������   ����m�9B        �5��5?�~�@���=9�@	[����u�A^���:eª:B   ����E����5G��� ����f07L6���	��䬕��u	���B1������   �����~�9B        �5��5?�ӂ@���=9�@	[���w��A^�����vª:B   ����E����5G��� ����f07L6���	��䬕��u	���B1������   ���,�+���A        �5��5?m��@���=�8@	[��C�4�q<�A^���o"�A   ����E����5G��� ����f07L6���	��䬕��u	���B1������   ����?���A        �5��5?,�@���=�8@	[��p�H�q<�A^����5�A   ����E����5G��� �#���f07L6���	��䬕��u	���B1������   ����m���A        �5��5?�~�@���=�8@	[����u�q<�A^���:e�A   ����E����5G��� �$���f07L6���	��䬕��u	���B1������   �����~���A        �5��5?�ӂ@���=�8@	[���w��q<�A^�����v�A   ����E����5G��� �%���f07L6���	����+�(������ְ�P��M�   	���,�+�A   ?   �   ?   ?���=  �<n��@	���C�4�8��A	���o"��X�A    ����E����5G��� �&���f07L6���	����+�(������ְ�P��M�   	�����~�A   ?   �   ?   ?���=  �<�ӂ@	����w��8��A	�����v��X�A    ����E����5G��� �'���f07L6���	����+�(������ְ�P��M�   	����?�A   ?   �   ?   ?���=  �<,�@	���q�H�8��A	����5��X�A    ����E����5G��� �(���f07L6���	����+�(������ְ�P��M�   	����m�A   ?   �   ?   ?���=  �<�~�@	�����u�8��A	���:e��X�A    ����E����5G��� �)���f07L6���	����+�(������ְ�P��M�   	����?�q<�A   ?   �   ?   ?���=  �<,�@	���q�H���A	����5�Ƒ�A    ����E����5G��� �*���f07L6���	����+�(������ְ�P��M�   	�����~�q<�A   ?   �   ?   ?���=  �<�ӂ@	����w����A	�����v�Ƒ�A    ����E����5G��� �+���f07L6���	����+�(������ְ�P��M�   	����m�q<�A   ?   �   ?   ?���=  �<�~�@	�����u���A	���:e�Ƒ�A    ����E����5G��� �,���f07L6���	����+�(������ְ�P��M�   	���,�+�q<�A   ?   �   ?   ?���=  �<n��@	���C�4���A	���o"�Ƒ�A    ����E����5G��� �-���f07L6���	����+�(������ְ�P��M�   ^0����~� �B   ?   �   ?   ?��*>��*>�ӂ@	ۻ��w�� �B������vª:B    ����E����5G��� �.���f07L6���	����+�(������ְ�P��M�   ^0��,�+� �B   ?   �   ?   ?��*>��*>n��@	ۻ�C�4� �B����o"ª:B    ����E����5G��� �/��6�l���c�r��f��r��+�(������ְ�P��M�   ^0���^� �B   ?   �   ?   ?��*>��*>��:@	ۻ�q�dª:B������X�U�B
    ����E����5G��� �00]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0��qO� �B   ?   �   ?   ?��*>��*>��:@	ۻ���Tª:B����:I�U�B
    ����E����5G��� �1���f07L6���	����+�(������ְ�P��M�   ^0���m� �B   ?   �   ?   ?��*>��*>�~�@	ۻ���uª:B����:e�U�B    ����E����5G��� �2���f07L6���	����+�(������ְ�P��M�   ^0���?� �B   ?   �   ?   ?��*>��*>,�@	ۻ�q�H� �B�����5ª:B    ����E����5G��� �3-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����V� �B   ?   �   ?   ?��*>��*>  �?	ۻ���Xª:B������T�U�B
    ����E����5G��� �6-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0���"���A        �5?�5?��*>��*>�8@	ۻ��"�q<�A����o!�A
�+�(������ְ�P��M�   ^0���"���A        �5?�5?��*>��*>���>	ۻ�o"ª��A����j�!�Uu�A
    ����E����5G��� �8���f07L6���	����+�(������ְ�P��M�   ^0��,�+�Uu�A   ?   �   ?   ?��*>��*>n��@	ۻ�C�4ª��A����o"���A    ����E����5G��� �9���f07L6���	����+�(������ְ�P��M�   ^0���m�Uu�A   ?   �   ?   ?��*>��*>�~�@	ۻ���u���A����:e�Uu�A    ����E����5G��� �:���f07L6���	����+�(������ְ�P��M�   ^0���?�Uu�A   ?   �   ?   ?��*>��*>,�@	ۻ�q�Hª��A�����5���A    ����E����5G��� �;���f07L6���	����+�(������ְ�P��M�   ^0����~�Uu�A   ?   �   ?   ?��*>��*>�ӂ@	ۻ��w�ª��A������v���A    ����E����5G��� �<0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0����HsB�5��5?        ��*>��*>�8@^0��:I�A	ۻ�q�H�U�B
    ����E����5G��� �=-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����H��X�A�5��5?        ��*>��*>�8@^0��:I�Uu�A	ۻ�q�H�q<�A
    ����E����5G��� �?-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����H���A�5��5?        ��*>��*>�8@^0��:I�q<�A	ۻ�q�H�A
�+�(������ְ�P��M�   ^0���T5sB�5��5?        ��*>��*>�8@^0����5�A	ۻ�C�4�U�B
    ����E����5G��� �B��6�l���c�r��f��r��+�(������ְ�P��M�   ^0���T5���A�5��5?        ��*>��*>���>	ۻ��T5ª��A������4�Uu�A
    ����E����5G��� �C-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0���T5��X�A�5��5?        ��*>��*>�8@^0����5�Uu�A	ۻ�C�4�q<�A
�+�(������ְ�P��M�   ^0����dsB�5��5?        ��*>��*>�8@^0��:e�A	ۻ�q�d�U�B
    ����E����5G��� �E-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����d��X�A�5��5?        ��*>��*>�8@^0��:e�Uu�A	ۻ�q�d�q<�A
    ����E����5G��� �H��6�l���c�r��f��r��+�(������ְ�P��M�   ^0��C?v���A�5��5?        ��*>��*>���>	ۻ�C?vª��A������u�Uu�A
    ����E����5G��� �I0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0��C?vsB�5��5?        ��*>��*>�8@^0����v�A	ۻ���u�U�B
    ����E����5G��� �J-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��C?v��X�A�5��5?        ��*>��*>�8@^0����v�Uu�A	ۻ���u�q<�A
    ����E����5G��� �M-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��5����X�A�5��5?        ��*>��*>�8@^0������Uu�A	ۻ�5���q<�A
�+�(������ְ�P��M�   ^0��5��sB�5��5?        ��*>��*>�8@^0������A	ۻ�5���U�B
    ����E����5G��� �O-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��5�����A�5��5?        ��*>��*>�8@^0������q<�A	ۻ�5���A
 L�{[�=`O�L ����tIj����   �����$�U�A        T�<��?Ba)A�^�?TUA��J���&�UՅ@���"��?VA    ����E����5G��� ���'�Aø�������O�����{[�=`O�L ����tIj����   ���3���?A        -�<�?<GdA�L�?��A�r%��!�UՅ@J���S��R�aA    ����E����5G��� �ӖB�,�42��LT[����{[�=`O�L ����tIj����   _g[�|���?A        U��<�?ҫ{A&��?��Ao�z�UՅ@P�;�gf�R�aA    ����E����5G��� �Ծ��xU�gm�u�AW�Z��{[�=`O�L ����tIj����   #���v���?A        S��<�?���A��?��Aŧ� 
1ћfb��   ������V°�i�        �5��5?��?���=���@	ۻ���X®*��^0����T�U p�    ����E����5G��� �����2�T��[��Y�x�}�9�H
1ћfb��   ^����^°�i�        �5?�5?��:@��*=���@	ۻ�q�d®*��������X�U p�    ����E����5G��� ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   ^����dc®*��        �5?�5?���=���>  @?^0��q�c®*��^0��:c�[Ut�    ����E����5G��� �����f07L6���	����0����$P�����L��m�   ^0���m®*��        �5��5?�~�@��*>  �>	ۻ���u®*������:e®*��    ����E����5G��� �����2�T��[��Y�x�}�9�H
1ћfb��   ^���qO°�i�        �5��5?��:@��*=���@^0����T®*��	ۻ�:I�U p�    ����E����5G��� ��Vz��������A�����2��0����$P�����L��m�   ^����dJ®*��        �5��5?���=���>  @?����q�J®*������:J�[Ut�    ����E����5G��� �����f07L6���	����0����$P�����L��m�   ^0����~®*��        �5��5?�ӂ@��*>  �>	ۻ��w�®*��������v®*��    ����E����5G��� ���f07L6���	����0����$P�����L��m�   ^0���?®*��        �5��5?,�@��*>  �>	ۻ�p�H®*�������5®*��    ����E����5G��� �ʐ��f07L6���	��䬕��u	���B1������   ���,�+�u���        �5��5?m��@���=��@	[��C�4�X���^���o"c��   ����E����5G��� �ː��f07L6���	��䬕��u	���B1������   ����?�u���        �5��5?,�@���=��@	[��p�H�X���^����5c��   ����E����5G��� �ϐ��f07L6���	��䬕��u	���B1������   ����m�u���        �5��5?�~�@���=��@	[����u�X���^���:ec��   ����E����5G��� �А��f07L6���	��䬕��u	���B1������   �����~�u���        �5��5?�ӂ@���=��@	[���w��X���^�����vc��   ����E����5G��� �Ґ��f07L6���	��䬕��u	���B1������   ���,�+�E���        �5��5?m��@���=9�@	[��C�4�?��^���o"�^ p�   ����E����5G��� �Ӑ��f07L6���	��䬕��u	���B1������   ����?�E���        �5��5?,�@���=9�@	[��p�H�?��^����5�^ p�   ����E����5G��� �א��f07L6���	��䬕��u	���B1������   ����m�E���        �5��5?�~�@���=9�@	[����u�?��^���:e�^ p�   ����E����5G��� �ؐ��f07L6���	��䬕��u	���B1������   �����~�E���        �5��5?�ӂ@���=9�@	[���w��?��^�����v�^ p�   ����E����5G��� �ڐ��f07L6���	��䬕��u	���B1������   ���,�+°�Y�        �5��5?m��@���=�8@	[��C�4c��^���o"�>��   ����E����5G��� �ې��f07L6���	��䬕��u	���B1������   ����?°�Y�        �5��5?,�@���=�8@	[��p�Hc��^����5�>��   ����E����5G��� �ߐ��f07L6���	��䬕��u	���B1������   ����m°�Y�        �5��5?�~�@���=�8@	[����uc��^���:e�>��   ����E����5G��� �����f07L6���	��䬕��u	���B1������   �����~°�Y�        �5��5?�ӂ@���=�8@	[���w�c��^�����v�>��   ����E����5G��� �ᐤ�f07L6���	����+�(������ְ�P��M�   	���,�+�?��   ?   �   ?   ?���=  �<n��@	���C�4��8�	���o"��    ����E����5G��� �␤�f07L6���	����+�(������ְ�P��M�   	�����~�?��   ?   �   ?   ?���=  �<�ӂ@	����w���8�	�����v��    ����E����5G��� �㐤�f07L6���	����+�(������ְ�P��M�   	����?�?��   ?   �   ?   ?���=  �<,�@	���q�H��8�	����5��    ����E����5G��� �䐤�f07L6���	����+�(������ְ�P��M�   	����m�?��   ?   �   ?   ?���=  �<�~�@	�����u��8�	���:e��    ����E����5G��� �吤�f07L6���	����+�(������ְ�P��M�   	����?c��   ?   �   ?   ?���=  �<,�@	���q�H�縑�	����5�<��    ����E����5G��� �搤�f07L6���	����+�(������ְ�P��M�   	�����~c��   ?   �   ?   ?���=  �<�ӂ@	����w��縑�	�����v�<��    ����E����5G��� �琤�f07L6���	����+�(������ְ�P��M�   	����mc��   ?   �   ?   ?���=  �<�~�@	�����u�縑�	���:e�<��    ����E����5G��� �萤�f07L6���	����+�(������ְ�P��M�   	���,�+c��   ?   �   ?   ?���=  �<n��@	���C�4�縑�	���o"�<��    ����E����5G��� �鐤�f07L6���	����+�(������ְ�P��M�   ^0����~���   ?   �   ?   ?��*>��*>�ӂ@	ۻ��w����������v��<    ����E����5G��� �ꐤ�f07L6���	����+�(������ְ�P��M�   ^0��,�+���   ?   �   ?   ?��*>��*>n��@	ۻ�C�4�������o"��<    ����E����5G��� ���6�l���c�r��f��r��+�(������ְ�P��M�   ^0���^���   ?   �   ?   ?��*>��*>��:@	ۻ�q�d�` p�������X�k���
    ����E����5G��� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0��qO���   ?   �   ?   ?��*>��*>��:@	ۻ���T�` p�����:I�k���
    ����E����5G��� �퐤�f07L6���	����+�(������ְ�P��M�   ^0���m���   ?   �   ?   ?��*>��*>�~�@	ۻ���u�` p�����:e�k���    ����E����5G��� ��f07L6���	����+�(������ְ�P��M�   ^0���?���   ?   �   ?   ?��*>��*>,�@	ۻ�q�H�` p������5�k���    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����V���   ?   �   ?   ?��*>��*>  �?	ۻ���X�` p�������T�k���
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0���"±�Y�        �5?�5?��*>��*>�8@	ۻ�o"c������j�!�?��
�+�(������ְ�P��M�   ^0���"�X���        �5?�5?��*>��*>���>	ۻ�o"®*������j�!����
    ����E����5G��� �����f07L6���	����+�(������ְ�P��M�   ^0��,�+����   ?   �   ?   ?��*>��*>n��@	ۻ�C�4®*������o"�X���    ����E����5G��� �����f07L6���	����+�(������ְ�P��M�   ^0���m����   ?   �   ?   ?��*>��*>�~�@	ۻ���u�X�������:e����    ����E����5G��� �����f07L6���	����+�(������ְ�P��M�   ^0���?����   ?   �   ?   ?��*>��*>,�@	ۻ�q�H®*�������5�X���    ����E����5G��� �����f07L6���	����+�(������ְ�P��M�   ^0����~����   ?   �   ?   ?��*>��*>�ӂ@	ۻ��w�®*��������v�X���    ����E����5G��� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0����H㖿�5��5?        ��*>��*>�8@^0��:I�?��	ۻ�q�H�|���
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����H�����5��5?        ��*>��*>�8@^0��:I����	ۻ�q�Hc��
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����H±�Y��5��5?        ��*>��*>�8@^0��:Ic��	ۻ�q�H�?��
�+�(������ְ�P��M�   ^0���T5㖿�5��5?        ��*>��*>�8@^0����5�?��	ۻ�C�4�|���
    ����E����5G��� ����6�l���c�r��f��r��+�(������ְ�P��M�   ^0���T5�X����5��5?        ��*>��*>���>	ۻ��T5®*��������4����
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0���T5�����5��5?        ��*>��*>�8@^0����5����	ۻ�C�4c��
�+�(������ְ�P��M�   ^0����d㖿�5��5?        ��*>��*>�8@^0��:e�?��	ۻ�q�d�|���
    ����E����5G��� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����d�����5��5?        ��*>��*>�8@^0��:e����	ۻ�q�dc��
    ����E����5G��� ���6�l���c�r��f��r��+�(������ְ�P��M�   ^0��C?v�X����5��5?        ��*>��*>���>	ۻ�C?v®*��������u����
    ����E����5G��� �0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0��C?v㖿�5��5?        ��*>��*>�8@^0����v�?��	ۻ���u�|���
    ����E����5G��� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��C?v�����5��5?        ��*>��*>�8@^0����v����	ۻ���uc��
    ����E����5G��� �	-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��5�������5��5?        ��*>��*>�8@^0���������	ۻ�5��c��
0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0��5��㖿�5��5?        ��*>��*>�8@^0������?��	ۻ�5���|���
    ����E����5G��� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��5��±�Y��5��5?        ��*>��*>�8@^0�����c��	ۻ�5���?��
1ћfb��   ������V�W�        �5��5?��?���=���@	ۻ���X����^0����T¬jH�    ����E����5G��� �����2�T��[��Y�x�}�9�H
1ћfb��   ^����^�W�        �5?�5?��:@��*=���@	ۻ�q�d����������X¬jH�    ����E����5G��� ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   ^����dc����        �5?�5?���=���>  @?^0��q�c����^0��:c����    ����E����5G��� �����f07L6���	����0����$P�����L��m�   ^0���m����        �5��5?�~�@��*>  �>	ۻ���u��������:e����    ����E����5G��� �����2�T��[��Y�x�}�9�H
1ћfb��   ^���qO�W�        �5��5?��:@��*=���@^0����T����	ۻ�:I¬jH�    ����E����5G��� ��Vz��������A�����2��0����$P�����L��m�   ^����dJ����        �5��5?���=���>  @?����q�J��������:J����    ����E����5G��� �����f07L6���	����0����$P�����L��m�   ^0����~����        �5��5?�ӂ@��*>  �>	ۻ��w�����������v����    ����E����5G��� �����f07L6���	����0����$P�����L��m�   ^0���?����        �5��5?,�@��*>  �>	ۻ�p�H���������5����    ����E����5G��� �����f07L6���	��䬕��u	���B1������   ���,�+�s���        �5��5?m��@���=��@	[��C�4«���^���o"�:n��   ����E����5G��� �����f07L6���	��䬕��u	���B1������   ����?�s���        �5��5?,�@���=��@	[��p�H«���^����5�:n��   ����E����5G��� �����f07L6���	��䬕��u	���B1������   ����m�s���        �5��5?�~�@���=��@	[����u«���^���:e�:n��   ����E����5G��� �����f07L6���	��䬕��u	���B1������   �����~�s���        �5��5?�ӂ@���=��@	[���w�«���^�����v�:n��   ����E����5G��� �����f07L6���	��䬕��u	���B1������   ���,�+�s�X�        �5��5?m��@���=9�@	[��C�4�:Ni�^���o"¬jH�   ����E����5G��� �����f07L6���	��䬕��u	���B1������   ����?�s�X�        �5��5?,�@���=9�@	[��p�H�:Ni�^����5¬jH�   ����E����5G��� �����f07L6���	��䬕��u	���B1������   ����m�s�X�        �5��5?�~�@���=9�@	[����u�:Ni�^���:e¬jH�   ����E����5G��� �����f07L6���	��䬕��u	���B1������   �����~�s�X�        �5��5?�ӂ@���=9�@	[���w��:Ni�^�����v¬jH�   ����E����5G��� �����f07L6���	��䬕��u	���B1������   ���,�+�W{�        �5��5?m��@���=�8@	[��C�4�:n��^���o"�:Ni�   ����E����5G��� �����f07L6���	��䬕��u	���B1������   ����?�W{�        �5��5?,�@���=�8@	[��p�H�:n��^����5�:Ni�   ����E����5G��� �����f07L6���	��䬕��u	���B1������   ����m�W{�        �5��5?�~�@���=�8@	[����u�:n��^���:e�:Ni�   ����E����5G��� �����f07L6���	��䬕��u	���B1������   �����~�W{�        �5��5?�ӂ@���=�8@	[���w��:n��^�����v�:Ni�   ����E����5G��� �����f07L6���	����+�(������ְ�P��M�   	���,�+�:Ni�   ?   �   ?   ?���=  �<n��@	���C�4���i�	���o"�h�    ����E����5G��� �����f07L6���	����+�(������ְ�P��M�   	�����~�:Ni�   ?   �   ?   ?���=  �<�ӂ@	����w����i�	�����v�h�    ����E����5G��� �����f07L6���	����+�(������ְ�P��M�   	����?�:Ni�   ?   �   ?   ?���=  �<,�@	���q�H���i�	����5�h�    ����E����5G��� ���f07L6���	����+�(������ְ�P��M�   	����m�:Ni�   ?   �   ?   ?���=  �<�~�@	�����u���i�	���:e�h�    ����E����5G��� �Ð��f07L6���	����+�(������ְ�P��M�   	����?�:n��   ?   �   ?   ?���=  �<,�@	���q�HÆ�	����5����    ����E����5G��� �Đ��f07L6���	����+�(������ְ�P��M�   	�����~�:n��   ?   �   ?   ?���=  �<�ӂ@	����w�Æ�	�����v����    ����E����5G��� �Ő��f07L6���	����+�(������ְ�P��M�   	����m�:n��   ?   �   ?   ?���=  �<�~�@	�����uÆ�	���:e����    ����E����5G��� �Ɛ��f07L6���	����+�(������ְ�P��M�   	���,�+�:n��   ?   �   ?   ?���=  �<n��@	���C�4Æ�	���o"����    ����E����5G��� �ǐ��f07L6���	����+�(������ְ�P��M�   ^0����~�WG�   ?   �   ?   ?��*>��*>�ӂ@	ۻ��w��WG�������v¬jD�    ����E����5G��� �Ȑ��f07L6���	����+�(������ְ�P��M�   ^0��,�+�WG�   ?   �   ?   ?��*>��*>n��@	ۻ�C�4¬jH�����o"��E�    ����E����5G��� �ɲ�6�l���c�r��f��r��+�(������ְ�P��M�   ^0���^�WG�   ?   �   ?   ?��*>��*>��:@	ۻ�q�d¬jH�������X��E�
    ����E����5G��� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0��qO�WG�   ?   �   ?   ?��*>��*>��:@	ۻ���T¬jH�����:I��E�
    ����E����5G��� �ː��f07L6���	����+�(������ְ�P��M�   ^0���m�WG�   ?   �   ?   ?��*>��*>�~�@	ۻ���u¬jH�����:e��E�    ����E����5G��� �̐��f07L6���	����+�(������ְ�P��M�   ^0���?�WG�   ?   �   ?   ?��*>��*>,�@	ۻ�q�H�WG������5¬jD�    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����V�WG�   ?   �   ?   ?��*>��*>  �?	ۻ���X¬jH�������T��E�
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0���"�W{�        �5?�5?��*>��*>�8@	ۻ�o"�:n������j�!�:Ni�
�+�(������ְ�P��M�   ^0���"«���        �5?�5?��*>��*>���>	ۻ�o"��������j�!�V5��
    ����E����5G��� �Ґ��f07L6���	����+�(������ְ�P��M�   ^0��,�+�V5��   ?   �   ?   ?��*>��*>n��@	ۻ�C�4��������o"«���    ����E����5G��� �Ӑ��f07L6���	����+�(������ְ�P��M�   ^0���m�V5��   ?   �   ?   ?��*>��*>�~�@	ۻ���u��������:e«���    ����E����5G��� �Ԑ��f07L6���	����+�(������ְ�P��M�   ^0���?�V5��   ?   �   ?   ?��*>��*>,�@	ۻ�q�H���������5«���    ����E����5G��� �Ր��f07L6���	����+�(������ְ�P��M�   ^0����~�V5��   ?   �   ?   ?��*>��*>�ӂ@	ۻ��w�����������v«���    ����E����5G��� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0����H��W��5��5?        ��*>��*>�8@^0��:I�:Ni�	ۻ�q�H��E�
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����H��Q���5��5?        ��*>��*>�8@^0��:I�V5��	ۻ�q�H�:n��
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����H�W{��5��5?        ��*>��*>�8@^0��:I�:n��	ۻ�q�H�;Ni�
�+�(������ְ�P��M�   ^0���T5��W��5��5?        ��*>��*>�8@^0����5�:Ni�	ۻ�C�4��E�
    ����E����5G��� �ܲ�6�l���c�r��f��r��+�(������ְ�P��M�   ^0���T5«����5��5?        ��*>��*>���>	ۻ��T5����������4�V5��
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0���T5��Q���5��5?        ��*>��*>�8@^0����5�V5��	ۻ�C�4�:n��
�+�(������ְ�P��M�   ^0����d��W��5��5?        ��*>��*>�8@^0��:e�:Ni�	ۻ�q�d��E�
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0����d��Q���5��5?        ��*>��*>�8@^0��:e�V5��	ۻ�q�d�:n��
    ����E����5G��� ���6�l���c�r��f��r��+�(������ְ�P��M�   ^0��C?v«����5��5?        ��*>��*>���>	ۻ�C?v����������u�V5��
    ����E����5G��� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ^0��C?v��W��5��5?        ��*>��*>�8@^0����v�:Ni�	ۻ���u��E�
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��C?v��Q���5��5?        ��*>��*>�8@^0����v�V5��	ۻ���u�:n��
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��5����Q���5��5?        ��*>��*>�8@^0������V5��	ۻ�5���:n��
�+�(������ְ�P��M�   ^0��5����W��5��5?        ��*>��*>�8@^0������:Ni�	ۻ�5����E�
    ����E����5G��� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ^0��5���W{��5��5?        ��*>��*>�8@^0������:n��	ۻ�5���;Ni�
��.zkp��_���O�t����JR� ��}��G    ���BTu�A        F���y?�!B�cB��A=��5A��vA�S��^c�BSu�AL   ��G"�F�!��� �J<�1���f`��Kv��ޒ��Iא�� �s�gtQ�#�e;$,�   QK���y�������>��l?�y��)<+���WA�I@���A�u���«:�a#��	�b«*��Q  ��G"�F�!��� �J�C|(��5�)ʂcN���M{[�=`O�L ����tIj����   �J�� y°������8�N:��þ@�l?>�WA
��A�u���«:�a#��	�b«*���   �s'�@߮�۹=��� :Bh��:�<jE��G��b�f>�}$uJ�q�NeȊq�`�1��    ���@L
IBƪF�;V/=�r;�
IB�E�jT�=9��Y�3��i4?�c�>��5AC�A��>�4HB�����%A��IB��|   �s'�@߮�۹=��� :Py9�e@�[0�l���'v�ܕ��u	���B1������    ���@��HB=�D�<%�<���<(W5?_|4?8U>p�"AӻA2'?�tHB����#A�4IB�j�   �s'�@߮�۹=��� :Q�wYg���mW�@rj�Z��-�}$uJ�q�NeȊq�`�1��    �JqA��HB�E���2�M3?��=�۽S��>0ALgA�J5A��GB���r��AL�IB��|   �s'�@߮�۹=��� :Q٫�����b��@���6"
��;�^��`�?πY>�A!��@�[B���A�*�@@B�oBT�PA   ����!Aә���N�\� 0qw2� xb�c
��;�^��`�?πY>�A!��@�[B���AXՎ�@B�oB���?   ����!Aә���N�\� 0~�(^N9Sg�!�VH���O�/�}$uJ�q�NeȊq�`�1��    ��B;C�A�U����=��7'>�w�~?�c�>��5AD�A,�B�?�A����BC#B��|   ����!Aә���N�\� 0~y9�e@�[0�l���'v�ܕ��u	���B1������    *�BlL�A=�T�e���J�
=��?w��::U>r�"AԻANWB��A����@B"wB�j�   �L�0DB=��E��6� �#�[c;|�8�K6����9�	�ޞ�2��r`<\�{�E   ց����3�V����A��A�>��{�?� >Bsp?4-JA K���#4¬���5
�@��3�����  �L�0DB=��E��6� '�k��|sj�q��tr0��ޞ�2��r`<\�{�E   ���
B��ř�9�>xV`>y�H?��>'�&?��s?a/EA K��..D¬���5
�@�8A�����  �kT}aBX�H�č�� �k9��?���Q��AB�Z�{[�=`O�L ����tIj����   
]B�
 L�{[�=`O�L ����tIj����   �����$®��        T�<��?Ba)A�^�?TUA��J���&«*�����"���@   ��`�BʁR��dW�F �	���f07L6���	���{[�=`O�L ����tIj����   i�����V�\Uٿ              �?��3A�U�>T�+A��J��W«*���Ʒ�pV���j@   ��`�BʁR��dW�F �
���2�T��[��Y�x�0����$P�����L��m�   ЂY���u®*��        o�9?&-0?  A��*>  �>I ��*|�®*���
�u�d®*��   ��`�BʁR��dW�F ����2�T��[��Y�x�}�9�H
1ћfb��   �\��~�V°�i�        o�9?&-0?��?���=���@ ���X®*��a�����T�U p�   ��`�BʁR��dW�F ����2�T��[��Y�x�}�9�H
1ћfb��   ���N°�i�        &-0�o�9?��:@��*=���@4s��5�T®*��Cj��tI�U p�   ��`�BʁR��dW�F �&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   �Ю��0J®*��        &-0�o�9?���=  �>  @?sǿ�eJ®*��m����I�[Ut�   ��`�BʁR��dW�F ����2�T��[��Y�x�0����$P�����L��m�   �zֿ�z7®*��        o�9?&-0?UUA��*>  �>µ��	dH®*��@��ő&®*��   ��`�BʁR��dW�F ����2�T��[��Y�x�}�9�H
1ћfb��   Xw���~^°�i�        o�9?&-0?��:@��*=���@b���Qd®*���>u�F�X�U p�   ��`�BʁR��dW�F �Vz��������A�����2��0����$P�����L��m�   $����'c®*��        o�9?&-0?���=���>  @?9���eZc®*��hN���b�[Ut�   ��`�BʁR��dW�F ����f07L6���	��䬕��u	���B1������   >�^��u�u���        o�9?&-0?  A���=��@�v���{��X���X����dc��  ��`�BʁR��dW�F ����f07L6���	��䬕��u	���B1������   �$ٿ|7�u���        o�9?&-0?UUA���=��@���bH�X���9=��&�&c��  ��`�BʁR��dW�F ����f07L6���	��䬕��u	���B1������   >�^��u�E���        o�9?&-0?  A���=9�@�v���{��?��X����d�^ p�  ��`�BʁR��dW�F � ���f07L6���	��䬕��u	���B1������   >�^��u°�Y�        o�9?&-0?  A���=�8@�v���{�c��X����d�>��  ��`�BʁR��dW�F �$���f07L6���	��䬕��u	���B1������   �$ٿ|7°�Y�        o�9?&-0?UUA���=�8@���bHc��9=��&�&�>��  ��`�BʁR��dW�F �*���f07L6���	��䬕��u	���B1������   �$ٿ|7�E���        o�9?&-0?UUA���=9�@���bH�?��9=��&�&�^ p�  ��`�BʁR��dW�F �-��6�l���c�r��f��r��+�(������ְ�P��M�   �	����d�X���&-0?o�9?        ��*>��*>���>p����Ye®*��Є|�>�d����
   ��`�BʁR��dW�F �.-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �	����d����&-0?o�9?        ��*>��*>�8@p����Ye����Є|�>�dc��
�+�(������ְ�P��M�   �	����d㖿&-0?o�9?        ��*>��*>�8@�@��xe�?��!�}�Qd�|���
   ��`�BʁR��dW�F �1-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �V����H����&-0?o�9?        ��*>��*>�8@��ÿ�cI��������=�Hc��
   ��`�BʁR��dW�F �40]�����!E�U�=7O(
�+�(������ְ�P��M�   �V����H㖿&-0?o�9?        ��*>��*>�8@͍ĿwI�?�����[H�|���
   ��`�BʁR��dW�F �5-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   .�����V�	���&���U��&���U?��*>��*>  �?������X�` p�a�����T�e���
�+�(������ְ�P��M�   }t��H�^����&���U��&���U?��*>��*>��:@���
Zd�` p������X�[���
   ��`�BʁR��dW�F �7��6�l���c�r��f��r��+�(������ְ�P��M�   �뮿6�N����&���U��&���U?��*>��*>��:@|mÿ��T�` p�Dj��tI�[���
   ��`�BʁR��dW�F �8���f07L6���	����+�(������ְ�P��M�   ςY���u�����&���U��&���U?��*>��*>  AH ��*|����
�u�d�s�<   ��`�BʁR��dW�F �9���f07L6���	����+�(������ְ�P��M�   �zֿ�z7�����&���U��&���U?��*>��*>UUA����	dH�` p�@��ő&�=���   ��`�BʁR��dW�F �:���f07L6���	����+�(������ְ�P��M�   ςY���u�����&���U��&���U?��*>��*>  AH ��*|�®*��
�u�d�X���   ��`�BʁR��dW�F �;���f07L6���	����+�(������ְ�P��M�   �zֿ�z7�����&���U��&���U?��*>��*>UUA����	dH®*��@��ő&�X���   ��`�BʁR��dW�F �<���f07L6���	����+�(������ְ�P��M�   �L�/�uc���&���U��&���U?���=  �<  A� ���x��縑��"���d�;��   ��`�BʁR��dW�F �=���f07L6���	����+�(������ְ�P��M�   �п1x7c���&���U��&���U?���=  �<UUA$���E]H�縑��n���&�;��   ��`�BʁR��dW�F �@-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
   ��`�BʁR��dW�F �B-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
   ��`�BʁR��dW�F �D-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   w���������        &-0�o�9?��*>��*>�8@�
��̃�����ѻ�(s�c��
��̃c���ѻ�(s��?��
   ��`�BʁR��dW�F �G0]�����!E�U�=7O(
�+�(������ְ�P��M�   w������X���        &-0�o�9?��*>��*>���>�`5�aу®*��o���w�����
   ��`�BʁR��dW�F �H&��	m���W��nqIѕ�{[�=`O�L ����tIj����   ��Ä́-�
�+�(������ְ�P��M�   f5��ZG}A�ʲAį�<~�4�ǯ�<~�4?��*>��*>��:@����#�zA��A�����AUu�A
   �uAM����N(� �Z���f07L6���	����+�(������ְ�P��M�   �c�����A�ʲAį�<~�4�ǯ�<~�4?��*>��*>+��@B���>}A�ʲAÅ�����A��A   �uAM����N(� �[0]�����!E�U�=7O(
�+�(������ְ�P��M�   %�:�FLmA�ʲAį�<~�4�ǯ�<~�4?��*>��*>��:@�X@��jA��Aj�4�}�oAUu�A
   �uAM����N(� �\��6�l���c�r��f��r��+�(������ְ�P��M�   ����/&zA�ʲAį�<~�4�ǯ�<~�4?��*>��*>��:@ ���wA��AB���f�|AUu�A
   �uAM����N(� �]���f07L6���	����+�(������ְ�P��M�   �`�;�sA�ʲAį�<~�4�ǯ�<~�4?��*>��*>VUMA{4��CmA�ʲA� ±.zA��A   �uAM����N(� �^��6�l���c�r��f��r��+�(������ְ�P��M�   �&J�+jA�ʲAį�<~�4�ǯ�<~�4?��*>��*>��:@��O��gA��AOD�R�lAUu�A
   �uAM����N(� �i-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����A��A        '��<��?��*>��*>�8@Ζ���4�A�?|A�0��Ś�A�A
   �uAM����N(� �k-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����A�ʘA        '��<��?��*>��*>�8@Ζ���4�A�A�0��Ś�A8��A
�+�(������ְ�P��M�   �����AT�yA        '��<��?��*>��*>���>Ζ���4�A��vA�0��Ś�A�?|A
   �uAM����N(� �t���f07L6���	����+�(������ְ�P��M�   �c�����A�?|Aį�<~�4�ǯ�<~�4?��*>��*>+��@B���>}A��zAÅ�����AT�}A   �uAM����N(� �u���f07L6���	����+�(������ְ�P��M�   �`�;�sA�?|Aį�<~�4�ǯ�<~�4?��*>��*>VUMA{4��CmA��zA� ±.zAT�}A   �uAM����N(� �v���f07L6���	����+�(������ְ�P��M�   ��]�KfA�?|Aį�<~�4�ǯ�<~�4?��*>��*>,f�@�mj�nbbAT�yAx�P3jA�?|A   �uAM����N(� ـ-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����~A�ʘA$�̼��?       ���*>��*>�8@�����-}A�A������A8��A
�+�(������ְ�P��M�   �����~AƑ�A%�̼��?ǈ^-�#N���*>��*>�8@�����A8��AB��=I�ATu�A
   �uAM����N(� ق��6�l���c�r��f��r��+�(������ְ�P��M�   �����~AT�yA$�̼��?�#��̯��*>��*>���>�����}A��vA1����A�?|A
   �uAM����N(� ك-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����~A��A$�̼��?       ���*>��*>�8@�����-}A�?|A������A�A
�+�(������ְ�P��M�   rX4¡�nAƑ�A$�̼��?       ���*>��*>�8@�4­!mA8��A��3�oAUu�A
   �uAM����N(� َ-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   rX4¡�nA�ʘA$�̼��?       ���*>��*>�8@;e4�oA�AA�3�r�rA8��A
   �uAM����N(� ِ-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   rX4¡�nA��A$�̼��?       ���*>��*>�8@�4­!mA�?|A��3�oA�A
�+�(������ְ�P��M�   �OP���hAƑ�A$�̼��?       ���*>��*>�8@��P�̉gA8��A�O´UjAUu�A
   �uAM����N(� ٚ-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �OP���hA�ʘA$�̼��?       ���*>��*>�8@�SP�ؚgA�AʠO��fjA8��A
   �uAM����N(� ٤-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   i ���xA�ʘA$�̼��?       ���*>��*>�8@Rm ��wA�A�t���azA8��A
   �uAM����N(� ٦-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   i ���xA��A$�̼��?       ���*>��*>�8@Rm ��wA�?|A�t���azA�A
�+�(������ְ�P��M�   i ���xAƑ�A$�̼��?       ���*>��*>�8@�� ���wA8��A� ��PzAUu�A
   �uAM����N(� ٯ0]�����!E�U�=7O(
�+�(������ְ�P��M�   }�j�K�cAƑ�A$�̼��?       ���*>��*>�8@�k�W@bA8��A ej�?eAUu�A
   �uAM����N(� ٰ-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   }�j�K�cA��A$�̼��?       ���*>��*>�8@4mk�K/bA�?|A:�j�3�dA�A
   ���D���W�j�.y ��c��߼�z�.�g`����K�~�AƈP��%ULڝ.�N   �յ½;�@UE	B�:�5[���>3?��6?�V+A`�CA:F@>�����uJ>V�B5b���[.AV�	B
   ���D���W�j�.y ��,�H�J%�'���s�fJ���S��C\��/��Ȧ��'���R   [���ﳱ@V�	B        �f!<��?/GA��.A  �?�����uJ>V�	B5b���[.AV�	B   ���D���W�j�.y ���2�L�&�l��V1�������AƈP��%ULڝ.�N   ��v��VE	B��H5z3嶣�~?���=��OA=�=A`(@>���§{*�V�Bz���m,�>V�	B
   ���D���W�j�.y �Ԍ'8�e�ʥ���nT~Y��S��C\��/��Ȧ��'���R   �<������V�	B        FC�=��~?�tTAn|NA  �?���§{*�V�	Bz���m,�>V�	B   ���D���W�j�.y ��^�%ٱ���A�N�ȉ�+��AƈP��%ULڝ.�N   �E����w�VE	Bʟ)5aa��e?%��=)�=A�i%AR+@>����,=��V�B����4�'�V�	B
   ���D���W�j�.y ���wɠ��L#@��-��<�S��C\��/��Ȧ��'���R   J˶�w�V�	B        �n�=Fl?� CA��5A  �?����,=��V�	B����4�'�V�	B   ���D���W�j�.y ��>;�ɋuk���,R��~����AƈP��%ULڝ.�N   4ȷ���VE	B��l5�*	���~?�پ=�7<A�+A�+@>���°$��V�B�����!��V�	B
   ���D���W�j�.y ��VYL��."�^�t �aݳS��C\��/��Ȧ��'���R   �Q������V�	B        ]<�=x�~?K@A�:A  �?���°$��V�	B�����!��V�	B   ���D���W�j�.y ��"=�y+����	�%�'J�AƈP��%ULڝ.�N   f)���1]�TE	B�*6"`z7��7��2?+&�@��A�Y@>����jDl�V�BH��]�L�V�	B
   ���D���W�j�.y ��FeK��o-,1�C���S��C\��/��Ȧ��'���R   o��¿�\�V�	B        ��<_�? 0AˇA  �?����jDl�V�	BH��]�L�V�	B   ���D���W�j�.y ��_����9� ���i������AƈP��%ULڝ.�N   "m��¹8�VE	BH�P�s����}?uG�`x8A�kAAW+@>����j2M�V�B#����$�V�	B
   ���D���W�j�.y ���vL]G\�T�s��w�fuS��C\��/��Ȧ��'���R   iݸ�b�8�V�	B        U��}?8�3A��3A  �?����j2M�V�	B#����$�V�	B   ���D���W�j�.y ��*�9R����{*TmUN�K��AƈP��%ULڝ.�N   gշ�l��VE	B�^���㶆;?w����7A�+EAi(@>����7%�V�BO����@��V�	B
   ���D���W�j�.y ����! �����(�!���w�S��C\��/��Ȧ��'���R   A[�����V�	B        P����I?��0A��5A  �?����7%�V�	BO����@��V�	B   ���D���W�j�.y ���D{Y[����rW8�Ħc4�AƈP��%ULڝ.�N   ����k�@TE	B�w�6z7JpC?�X%?�p
   ���D���W�j�.y ��_tgp ㍲!);����S��C\��/��Ȧ��'���R   ;��DӨ@V�	B        �ե��(?09A�]$A  �?i����i?V�	B�S��'�AV�	B   ���D���W�j�.y �0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   bލ��?^AVE	B              �?��(A  �@  @>i���? AV�B�S����AV�	B
   ���D���W�j�.y �Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   bލ��?^AV�	B              �?��(A  �@  �?i���? AV�	B�S����AV�	B   ���D���W�j�.y ��Wd�O�&#�;�ɦG���AƈP��%ULڝ.�N   :D��[<�VE	BmȠ���6 b2��7?��QA�A%@>.r��pV�V�B��[�P�"�V�	B
   ���D���W�j�.y ���kS��NL�YT�8yPޙ̓S��C\��/��Ȧ��'���R   �>���<�V�	B        _c���?ԑA9�MA  �?.r��pV�V�	B��[�P�"�V�	B   ���D���W�j�.y �0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   O7���o�VE	B              �?}�A�~?A  @>.r���̃�V�B��[��W�V�	B
   ���D���W�j�.y �Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   O7���o�V�	B              �?}�A�~?A  �?.r���̃�V�	B��[��W�V�	B   ���D���W�j�.y ��9=����k���X>�ٞ�AƈP��%ULڝ.�N   ������>�VE	BL�8E�`���?8�<��bJA�7`Ag�B>��J���X�V�B�0��Ȟ$�V�	B   ���D���W�j�.y �_h�0kA�e.H���h�}��L�S��C\��/��Ȧ��'���R   ����;�?�V�	B        D��?�PDAU6PA  �?��J���X�V�	B�0��Ȟ$�V�	B   ���D���W�j�.y �'�4�w�s��*z	�~�s�-H��AƈP��%ULڝ.�N   �'���Tj�VE	B��e4�?�6�a3���6?;�Aic;A�+@>��J�jDz�V�B�0��.NZ�V�	B   ���D���W�j�.y �'�	u��=.h�e)<�) ]��S��C\��/��Ȧ��'���R   [
��_Ij�V�	B        ��-�?�U;A:CA  �?��J�jDz�V�	B�0��.NZ�V�	B   ���D���W�j�.y �0���ͳ�˪	^h��Fb�a3�_����_�7h�=�P9Q   ���Cb��IE	B���7�.���<�%�,?KU�Ay#YA�hA>4����a��V�B�S��G̥�V�	B]   ���D���W�j�.y �0���Ֆy�A�wJl�9���ZhS��C\��/��Ȧ��'���R   �"�����V�	B        �:2=��?�*aAV��A  �?4����a��V�	B�S��G̥�V�	B   ���D���W�j�.y ��c��߼�z�.�g`����K�~�AƈP��%ULڝ.�N   �յ½;�@�j<A�:�5[���>3?��6?�V+A`�CA:F@>�����uJ>��:A5b���[.A��=A
   ���D���W�j�.y ��,�H�J%�'���s�fJ���S��C\��/��Ȧ��'���R   [���ﳱ@��=A        �f!<��?/GA��.A  �?�����uJ>��=A5b���[.A��=A   ���D���W�j�.y ���2�L�&�l��V1�������AƈP��%ULڝ.�N   ��v���j<A��H5z3嶣�~?���=��OA=�=A`(@>���§{*���:Az���m,�>��=A
   ���D���W�j�.y ���'8�e�ʥ���nT~Y��S��C\��/��Ȧ��'���R   �<��������=A        FC�=��~?�tTAn|NA  �?���§{*���=Az���m,�>��=A   ���D���W�j�.y ��^�%ٱ���A�N�ȉ�+��AƈP��%ULڝ.�N   �E����w��j<Aʟ)5aa��e?%��=)�=A�i%AR+@>����,=����:A����4�'���=A
   ���D���W�j�.y ���wɠ��L#@��-��<�S��C\��/��Ȧ��'���R   J˶�w���=A        �n�=Fl?� CA��5A  �?����,=����=A����4�'���=A   ���D���W�j�.y ��>;�ɋuk���,R��~����AƈP��%ULڝ.�N   4ȷ����j<A��l5�*	���~?�پ=�7<A�+A�+@>���°$����:A�����!����=A
   ���D���W�j�.y ���VYL��."�^�t �aݳS��C\��/��Ȧ��'���R   �Q��������=A        ]<�=x�~?K@A�:A  �?���°$����=A�����!����=A   ���D���W�j�.y ��"=�y+����	�%�'J�AƈP��%ULڝ.�N   f)���1]¦j<A�*6"`z7��7��2?*&�@��A�Y@>����jDlª�:AH��]�Lª�=A
   ���D���W�j�.y ���FeK��o-,1�C���S��C\��/��Ȧ��'���R   o��¿�\ª�=A        ��<_�? 0AˇA  �?����jDlª�=AH��]�Lª�=A   ���D���W�j�.y ��_����9� ���i������AƈP��%ULڝ.�N   "m��¹8«j<AF�P�s����}?uG�`x8A�kAAW+@>����j2Mª�:A#����$ª�=A
   ���D���W�j�.y ���vL]G\�T�s��w�fuS��C\��/��Ȧ��'���R   iݸ�b�8ª�=A        U��}?8�3A��3A  �?����j2Mª�=A#����$ª�=A   ���D���W�j�.y ��*�9R����{*TmUN�K��AƈP��%ULڝ.�N   gշ�l�«j<A�^���㶆;?w����7A�+EAi(@>����7%ª�:AO����@����=A
   ���D���W�j�.y �ͱ�! �����(�!���w�S��C\��/��Ȧ��'���R   A[����ª�=A        P����I?��0A��5A  �?����7%ª�=AO����@����=A   ���D���W�j�.y �ԶD{Y[����rW8�Ħc4�AƈP��%ULڝ.�N   ����k�@�j<A�w�6�z7JpC?�X%?�p
   ���D���W�j�.y ��_tgp ㍲!);����S��C\��/��Ȧ��'���R   ;��DӨ@��=A        �ե��(?09A�]$A  �?i����i?��=A�S��'�A��=A   ���D���W�j�.y ��0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   bލ��?^A�j<A              �?��(A  �@  @>i���? A��:A�S����A��=A
   ���D���W�j�.y ��Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   bލ��?^A��=A              �?��(A  �@  �?i���? A��=A�S����A��=A   ���D���W�j�.y ���Wd�O�&#�;�ɦG���AƈP��%ULڝ.�N   :D��[<«j<AmȠ���6 b2��7?��QA�A%@>.r��pVª�:A��[�P�"ª�=A
   ���D���W�j�.y �⮕kS��NL�YT�8yPޙ̓S��C\��/��Ȧ��'���R   �>���<ª�=A        _c���?ԑA9�MA  �?.r��pVª�=A��[�P�"ª�=A   ���D���W�j�.y ��0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   O7���oªj<A              �?}�A�~?A  @>.r���̃ª�:A��[��Wª�=A
   ���D���W�j�.y ��Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   O7���oª�=A              �?}�A�~?A  �?.r���̃ª�=A��[��Wª�=A   ���D���W�j�.y ���9=����k���X>�ٞ�AƈP��%ULڝ.�N   ������>¬j<AL�8E�`���?8�<��bJA�7`Ag�B>��J���Xª�:A�0��Ȟ$ª�=A   ���D���W�j�.y ��_h�0kA�e.H���h�}��L�S��C\��/��Ȧ��'���R   ����;�?ª�=A        D��?�PDAU6PA  �?��J���Xª�=A�0��Ȟ$ª�=A   ���D���W�j�.y ���4�w�s��*z	�~�s�-H��AƈP��%ULڝ.�N   �'���Tj¬j<A��e4�?�6�a3���6?;�Aic;A�+@>��J�jDzª�:A�0��.NZª�=A   ���D���W�j�.y ���	u��=.h�e)<�) ]��S��C\��/��Ȧ��'���R   [
��_Ijª�=A        ��-�?�U;A:CA  �?��J�jDzª�=A�0��.NZª�=A   ���D���W�j�.y ����ͳ�˪	^h��Fb�a3�_����_�7h�=�P9Q   ���Cb��yj<A���7�.���<�%�,?KU�Ay#YA�hA>4����a����:A�S��G̥���=A]   ���D���W�j�.y ����Ֆy�A�wJl�9���ZhS��C\��/��Ȧ��'���R   �"�������=A        �:2=��?�*aAV��A  �?4����a����=A�S��G̥���=A   ���D���W�j�.y �tc��߼�z�.�g`����K�~�AƈP��%ULڝ.�N   �յ½;�@k�?�:�5\���>3?��6?�V+A_�CA:F@>�����uJ>PU�>5b���[.A��?
   ���D���W�j�.y �t,�H�J%�'���s�fJ���S��C\��/��Ȧ��'���R   [���ﳱ@��?        �f!<��?/GA��.A  �?�����uJ>��?5b���[.A��?   ���D���W�j�.y �{�2�L�&�l��V1�������AƈP��%ULڝ.�N   ��v����?��H5z3嶣�~?���=��OA=�=A`(@>���§{*�PU�>z���m,�>��?
   ���D���W�j�.y �{�'8�e�ʥ���nT~Y��S��C\��/��Ȧ��'���R   �<��������?        FC�=��~?�tTAn|NA  �?���§{*���?z���m,�>��?   ���D���W�j�.y ��^�%ٱ���A�N�ȉ�+��AƈP��%ULڝ.�N   �E����w���?̟)5aa��e?%��=)�=A�i%AR+@>����,=��PU�>����4�'���?
   ���D���W�j�.y ���wɠ��L#@��-��<�S��C\��/��Ȧ��'���R   J˶�w���?        �n�=Fl?� CA��5A  �?����,=����?����4�'���?   ���D���W�j�.y ��>;�ɋuk���,R��~����AƈP��%ULڝ.�N   4ȷ�����?��l5�*	���~?�پ=�7<A�+A�+@>���°$��PU�>�����!����?
   ���D���W�j�.y ���VYL��."�^�t �aݳS��C\��/��Ȧ��'���R   �Q��������?        ]<�=x�~?K@A�:A  �?���°$����?�����!����?   ���D���W�j�.y ��"=�y+����	�%�'J�AƈP��%ULڝ.�N   f)���1]�Y�?�*6"`z7��7��2?*&�@��A�Y@>����jDl�PU�>H��]�L¨�?
   ���D���W�j�.y ���FeK��o-,1�C���S��C\��/��Ȧ��'���R   o��¿�\¨�?        ��<_�? 0AˇA  �?����jDl¨�?H��]�L¨�?   ���D���W�j�.y ��_����9� ���i������AƈP��%ULڝ.�N   "m��¹8¶�?D�P�s����}?uG�`x8A�kAAW+@>����j2M�PU�>#����$¨�?
   ���D���W�j�.y ���vL]G\�T�s��w�fuS��C\��/��Ȧ��'���R   iݸ�b�8¨�?        U��}?8�3A��3A  �?����j2M¨�?#����$¨�?   ���D���W�j�.y ��*�9R����{*TmUN�K��AƈP��%ULڝ.�N   gշ�l�¯�?�^���㶆;?w����7A�+EAi(@>����7%�PU�>O����@����?
   ���D���W�j�.y ����! �����(�!���w�S��C\��/��Ȧ��'���R   A[����¨�?        P����I?��0A��5A  �?����7%¨�?O����@����?   ���D���W�j�.y ���D{Y[����rW8�Ħc4�AƈP��%ULڝ.�N   ����k�@I�?�w�6z7JpC?�X%?�p
   ���D���W�j�.y ��_tgp ㍲!);����S��C\��/��Ȧ��'���R   ;��DӨ@��?        �ե��(?09A�]$A  �?i����i?��?�S��'�A��?   ���D���W�j�.y ��0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   bލ��?^A��?              �?��(A  �@  @>i���? APU�>�S����A��?
   ���D���W�j�.y ��Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   bލ��?^A��?              �?��(A  �@  �?i���? A��?�S����A��?   ���D���W�j�.y ���Wd�O�&#�;�ɦG���AƈP��%ULڝ.�N   :D��[<ª�?mȠ���6 b2��7?��QA�A%@>.r��pV�PU�>��[�P�"¨�?
   ���D���W�j�.y ����kS��NL�YT�8yPޙ̓S��C\��/��Ȧ��'���R   �>���<¨�?        _c���?ԑA9�MA  �?.r��pV¨�?��[�P�"¨�?   ���D���W�j�.y ��0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   O7���o¨�?              �?}�A�~?A  @>.r���̃�PU�>��[��W¨�?
   ���D���W�j�.y ��Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   O7���o¨�?              �?}�A�~?A  �?.r���̃¨�?��[��W¨�?   ���D���W�j�.y ���9=����k���X>�ٞ�AƈP��%ULڝ.�N   ������>�Ȫ?L�8E�`���?8�<��bJA�7`Ag�B>��J���X�PU�>�0��Ȟ$¨�?   ���D���W�j�.y ��_h�0kA�e.H���h�}��L�S��C\��/��Ȧ��'���R   ����;�?¨�?        D��?�PDAU6PA  �?��J���X¨�?�0��Ȟ$¨�?   ���D���W�j�.y ���4�w�s��*z	�~�s�-H��AƈP��%ULڝ.�N   �'���Tj�Ū?��e4�?�6�a3���6?;�Aic;A�+@>��J�jDz�PU�>�0��.NZ¨�?   ���D���W�j�.y ���	u��=.h�e)<�) ]��S��C\��/��Ȧ��'���R   [
��_Ij¨�?        ��-�?�U;A:CA  �?��J�jDz¨�?�0��.NZ¨�?   ���D���W�j�.y �׃��ͳ�˪	^h��Fb�a3�_����_�7h�=�P9Q   ���Cb����?���7�.���<�%�,?KU�Ay#YA�hA>4����a��PU�>�S��G̥���?]   ���D���W�j�.y �י��Ֆy�A�wJl�9���ZhS��C\��/��Ȧ��'���R   �"�������?        �:2=��?�*aAV��A  �?4����a����?�S��G̥���?   ���D���W�j�.y �Ec��߼�z�.�g`����K�~�AƈP��%ULڝ.�N   �յ½;�@@<��:�5[���>3?��6?�V+A_�CA:F@>�����uJ>�=�5b���[.A�:�
   ���D���W�j�.y �E,�H�J%�'���s�fJ���S��C\��/��Ȧ��'���R   [���ﳱ@�:�        �f!<��?/GA��.A  �?�����uJ>�:�5b���[.A�:�   ���D���W�j�.y �L�2�L�&�l��V1�������AƈP��%ULڝ.�N   ��v��@<���H5z3嶣�~?���=��OA=�=A`(@>���§{*��=�z���m,�>�:�
   ���D���W�j�.y �L�'8�e�ʥ���nT~Y��S��C\��/��Ȧ��'���R   �<�������:�        FC�=��~?�tTAn|NA  �?���§{*��:�z���m,�>�:�   ���D���W�j�.y �S^�%ٱ���A�N�ȉ�+��AƈP��%ULڝ.�N   �E����w�@<�͟)5aa��e?%��=)�=A�i%AR+@>����,=���=�����4�'��:�
   ���D���W�j�.y �S�wɠ��L#@��-��<�S��C\��/��Ȧ��'���R   J˶�w��:�        �n�=Fl?� CA��5A  �?����,=���:�����4�'��:�   ���D���W�j�.y �Z>;�ɋuk���,R��~����AƈP��%ULڝ.�N   4ȷ���@<���l5�*	���~?�پ=�7<A�+A�+@>���°$���=������!���:�
   ���D���W�j�.y �Z�VYL��."�^�t �aݳS��C\��/��Ȧ��'���R   �Q�������:�        ]<�=x�~?K@A�:A  �?���°$���:������!���:�   ���D���W�j�.y �a"=�y+����	�%�'J�AƈP��%ULڝ.�N   f)���1]�@<��*6"`z7��7��2?+&�@��A�Y@>����jDl��=�H��]�L��:�
   ���D���W�j�.y �a�FeK��o-,1�C���S��C\��/��Ȧ��'���R   o��¿�\��:�        ��<_�? 0AˇA  �?����jDl��:�H��]�L��:�   ���D���W�j�.y �h_����9� ���i������AƈP��%ULڝ.�N   "m��¹8�@<�E�P�s����}?uG�_x8A�kAAW+@>����j2M��=�#����$��:�
   ���D���W�j�.y �h�vL]G\�T�s��w�fuS��C\��/��Ȧ��'���R   iݸ�b�8��:�        U��}?8�3A��3A  �?����j2M��:�#����$��:�   ���D���W�j�.y �o*�9R����{*TmUN�K��AƈP��%ULڝ.�N   gշ�l��@<��^���㶆;?w����7A�+EAi(@>����7%��=�O����@���:�
   ���D���W�j�.y �o��! �����(�!���w�S��C\��/��Ȧ��'���R   A[������:�        P����I?��0A��5A  �?����7%��:�O����@���:�   ���D���W�j�.y �v�D{Y[����rW8�Ħc4�AƈP��%ULڝ.�N   ����k�@@<��w�6�z7JpC?�X%?�p
   ���D���W�j�.y �v_tgp ㍲!);����S��C\��/��Ȧ��'���R   ;��DӨ@�:�        �ե��(?09A�]$A  �?i����i?�:��S��'�A�:�   ���D���W�j�.y �}0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   bލ��?^A@<�              �?��(A  �@  @>i���? A�=��S����A�:�
   ���D���W�j�.y �}Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   bލ��?^A�:�              �?��(A  �@  �?i���? A�:��S����A�:�   ���D���W�j�.y ���Wd�O�&#�;�ɦG���AƈP��%ULڝ.�N   :D��[<�@<�mȠ���6 b2��7?��QA�A%@>.r��pV��=���[�P�"��:�
   ���D���W�j�.y ����kS��NL�YT�8yPޙ̓S��C\��/��Ȧ��'���R   �>���<��:�        _c���?ԑA9�MA  �?.r��pV��:���[�P�"��:�   ���D���W�j�.y ��0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   O7���o�@<�              �?}�A�~?A  @>.r���̃��=���[��W��:�
   ���D���W�j�.y ��Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   O7���o��:�              �?}�A�~?A  �?.r���̃��:���[��W��:�   ���D���W�j�.y �����ͳ�˪	^h��Fb�a3�_����_�7h�=�P9Q   ���Cb��3@<����7�.���<�%�,?KU�Ay#YA�hA>4����a���=��S��G̥��:�]   ���D���W�j�.y �����Ֆy�A�wJl�9���ZhS��C\��/��Ȧ��'���R   �"������:�        �:2=��?�*aAV��A  �?4����a���:��S��G̥��:�   ���D���W�j�.y ���XX�DXw��S�6�e�� ){[�=`O�L ����tIj����   P��(����Bq�<��?<Ï1�.���=x,�B��:@.n��X���V�B�1��#�1A �B$   ���D���W�j�.y ��?�\_��;�U�lȗ;��}{[�=`O�L ����tIj����   �Ә©�A��B        :�k8  �?O�>AI�A��:@b>����Z?V�Bi����A �B   ���D���W�j�.y ����
jqk6�!6'm̌��Ү��{[�=`O�L ����tIj����   ���U«�B��  �?�'㯸�.���>��A��:@�ǻ��̃�V�B.r��M�"� �B   ���D���W�j�.y ����=O��X@L��cy�{[�=`O�L ����tIj����   �c�jkI� PB              �?TU�>R��A@U
+�2��=.؋B{�F@����jDl�V�	B���]�-A Bn   ���D���W�j�.y ��ci�����O~��dg�V�=�{[�=`O�L ����tIj����   �c���k«zB              �?TU�>���@��r@�0��jDz�V�B��-��]� B   ���D���W�j�.y ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   �)���z«�B              �?v9A ��=��F@��J�jDz�V�	B�0���y� B   ���D���W�j�.y ���XX�DXw��S�6�e�� ){[�=`O�L ����tIj����   P��(���?JAq�<��?�Ï1�1���=x,�B��:@.n��X��ª�2A�1��#�1AR�aA$   ���D���W�j�.y ���0G� h�!�<���{[�=`O�L ����tIj����   �¾!rAT�DA�{9? q0�"a.+-.uU�>�� BPU
jqk6�!6'm̌��Ү��{[�=`O�L ����tIj����   ���U��?JA��  �?s(��.���>��A��:@�ǻ��̃ª�2A.r��M�"�R�aA   ���D���W�j�.y ����=O��X@L��cy�{[�=`O�L ����tIj����   �c�׻?�U�DA              �?TU�>�MAPU
+�2��=.؋B|�F@����jDlª�=A���]�-AR�oAn   ���D���W�j�.y ��ci�����O~��dg�V�=�{[�=`O�L ����tIj����   �c���i��?QA              �?TU�>D.A��r@�0��jDzª�2A��-��xY�R�oA   ���D���W�j�.y ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   �)���z���VA              �?v9A ��=��F@��J�jDzª�=A�0���y�R�oA   ���D���W�j�.y ���XX�DXw��S�6�e�� ){[�=`O�L ����tIj����   P��(�����?q�<��?�Ï1�1���=x,�B��:@.n��X��������1��#�1AJU6@$   ���D���W�j�.y ���0G� h�!�<���{[�=`O�L ����tIj����   �¾!rA���?�{9? q0�"a.+-.uU�>�� BPU
jqk6�!6'm̌��Ү��{[�=`O�L ����tIj����   ���U����?��  �?'㯷�.���>��A��:@�ǻ��̃�����.r��M�"�JU6@   ���D���W�j�.y ����=O��X@L��cy�{[�=`O�L ����tIj����   �c�׻?¤��?              �?TU�>�MAPU
@ls51  �?$?�
+�2��=.؋B{�F@����jDl¨�?���]�-AJUn@n   ���D���W�j�.y ��ci�����O~��dg�V�=�{[�=`O�L ����tIj����   �c���i����?              �?TU�>D.A��r@�0��jDz�������-��xY�JUn@   ���D���W�j�.y ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   �)���z���
@              �?v9A ��=��F@��J�jDz¨�?�0���y�JUn@   ���D���W�j�.y ���XX�DXw��S�6�e�� ){[�=`O�L ����tIj����   P��(���j.�q�<��?HÏ1q/���=x,�B��:@.n��X����E��1��#�1AX�$   ���D���W�j�.y ��E�|�_x�6�����z�{[�=`O�L ����tIj����   �¾!rAW4�        &�̼��?*6 BD��@XU
jqk6�!6'm̌��Ү��{[�=`O�L ����tIj����   ���U­j.���  �?'�'*.���>��A��:@�ǻ��̃��E�.r��M�"�X�   ���D���W�j�.y ��Dt�Ɲ:$�h:h��5�{[�=`O�L ����tIj����   =�������!�Ws51  �?(?�� +�2��=-؋B��F@����jDl��:����]�-AX	�n   ?T�Bl�-�zNc�� Bo�U�����;T��iqBJ���AƈP��%ULڝ.�N   <����p�U5�A��5�B��.�?����*^�A��8A� @>��J��̃�Uu�A�M:A.NZ�U��A   ?T�Bl�-�zNc�� Bo�Uŏr�_g����e�]�j�S��C\��/��Ȧ��'���R   �Y�n�p�U��A        uI��7�?�m�A&�8A  �?��J��̃�U��A�M:A.NZ�U��A   ��6�H��ݒFT�� �D!-��L�䥈(fŢ��R�Q��3�ޒ�8�����ġ���   h�K�/tfB �B�5?�5?Q`�4yKH4�j
?�3�A�U�?a�}�Z_eB��Bo���gBU�Bx  ��6�H��ݒFT�� �\`�\n��ݫ_Fd��4�c���Q��3�ޒ�8�����ġ���   $���/tfB �B�5?�5?����i�|��j
?K<�A�U�?�-�Z_eB��B�=B��gBU�B  ��6�H��ݒFT�� ޥ���1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
9·�tB �B��4JO5  �?D��3�j
?}��@�U�?�:¯�gB��B�7���BU�B@  ��6�H��ݒFT�� �����1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
Y·�tB �B��4JO5  �?D��3�j
?}��@�U�?�Z¯�gB��B�W���BU�B@  ��6�H��ݒFT�� ����1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   ������tB �B��4JO5  �?D��3�j
?}��@�U�?C����gB��B������BU�B@  ��6�H��ݒFT�� ����1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �����tB �B��4JO5  �?D��3�j
?}��@�U�?C����gB��B������BU�B@  ��6�H��ݒFT�� �.s{,����^J����H��wQ��3�ޒ�8�����ġ���   ":v�S&A �B<��   �?I 5M�]�K�`@�j
?ZU�?A}���!A��B73o¨d*AU�B�  �1K�'j�lK 	4/!>0ϫk
?�
?�y�A�U�?A}��lB��BB�BU�B�  ���a�@͂)gu�E2� ψP����)����Ew0\ �(hQ��3�ޒ�8�����ġ���   �$����A �B�5��5?��4
o4�j
?�
o4�j
?�
o4�j
?�
o4�j
?�
o4�j
?�
o4�j
?�
?\U�?A}�����B��.��U�Bl  ���a�@͂)gu�E2� ��Ʈ��ޕ�Z�X�<���d�Q��3�ޒ�8�����ġ���   �KM��d�� �Bm�s����  �?$��&nԿA�j
?YU�?A}�����B�V�?;��U�B�  ���a�@͂)gu�E2� �6
?ZU�?A}�w�	���Bo���� �U�Bl  ���a�@͂)gu�E2� �S�%��H��q0��f�0�@�Q��3�ޒ�8�����ġ���   ��L�PTJ@ �B��#��4  �?8
?XU�?A}��9@��B4¦�[@U�B@  @yvɠG���w��<� ��0���_�݄i������K��Q�}$uJ�q�NeȊq�`�1��    >���I�J� ��        �5?�5?���@��*>  �@����I�X� �p��I�<� ��H   @yvɠG���w��<� �萤�f07L6���	��䬕��u	���B1������    ����I�J� ��        �5?�5?���@���<  �@���I5X� �>���I5=� �  @yvɠG���w��<� �M���f07L6���	��䬣}$uJ�q�NeȊq�`�1��    e���I�J�Ve�        �5?�5?TU�@�2@XU�>��
Z«: ��%���_;� ��   �xl�L��i�s;�� �ݪ���9�1�*n�26l�O�����
*��=ܩyL�܀   ������@$kL���}:��}��5��5?���@��@H��@�U����@����=���A���   �xl�L��i�s;�� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0����@����        �5��5?���@UU)@  �>=+����@V5������AV5��   �xl�L��i�s;�� ���YB�n�������Fҫԕ��u	���B1������   ������@�jL��6��6<9�4�:�4?TUm@XD�>��@���½Y�@�������4�AW�  �xl�L��i�s;�� �ު���9�1�*n�26l�O�����
*��=ܩyL�܀   ����\A$kL���}:��}��5��5?���@��@H��@�U��;A����=���}A���   �xl�L��i�s;�� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0��\A����        �5��5?���@UU)@  �>=+��8AV5�������k�AV5��   �xl�L��i�s;�� ���YB�n�������Fҫԕ��u	���B1������   ����\A�jL��6��6<9�4�:�4?TUm@XD�>��@�����,?A�������4�zAW�  �xl�L��i�s;�� ��9�)�h:�������wJ��]���e���C�'�a�8�~.�   ������@N��5��5?�;�o�� �@uxR?)
�����Ij��~��|@*����,   �5F�¾ѣ��5��5?���0��>���?x�@�u���l��%.��"����Vu��   �5Kn������Q �P�Cj΅���l�lq��f���{[�=`O�L ����tIj����   ��L´Y�BUu�A              �?X��A �*>���?o��
/�B��Aa
A �*>���?
eBUu�A        ���  �?8��A|�*>���?
/�B��A.�F�_��B���A   �5Kn������Q ��Y���E�D��J�~7�ʝ�3{[�=`O�L ����tIj����   c^�BUu�A        �m	�  �?�A��*>���?���ĀB��A�;��5�B���A   �5Kn������Q ��k$�49%vϸkv�Y��<{[�=`O�L ����tIj����   ~{�Z�gBUu�A        o�K�  �?��@��*>���?�����gB��A^zA��3hB���A   �5Kn������Q ��Ь����b�[�b]��� `WU{[�=`O�L ����tIj����   b���
eBUu�A        ٓ	�  �?�H�A԰*>���?�°�dB��A>D�Z_eB���A   �5Kn������Q ��Ь����b�[�b]��� `WU{[�=`O�L ����tIj����   6��K	KBUu�A        ��	�  �?�H�Aְ*>���?8����JB��A_#E��^KB���A   �5Kn������Q �С�Y^u+>��'�x��mT{[�=`O�L ����tIj����   yd���4HBUu�A        a�  �?���A�*>���?!� �GB��AaO�K�HB���A   �5Kn������Q �ߡ�Y^u+>��'�x��mT{[�=`O�L ����tIj����   k9����BUu�A        b�  �?���A�*>���?��B��AF�P�2AB���A   �5Kn������Q �ࡠY^u+>��'�x��mT{[�=`O�L ����tIj����   Y`���BUu�A        �3�  �?w��A�*>���?K)�2�B��A;�P��lB���A   �5Kn������Q ��Y^u+>��'�x��mT{[�=`O�L ����tIj����   ������AUu�A        14�  �?v��Ap�*>���?{��<.�A��A�XR����A���A   �5Kn������Q ��Y^u+>��'�x��mT{[�=`O�L ����tIj����   5+��<0�AUu�A        �d�  �?x��A�*>���?����A��A�qR����A���A   �5Kn������Q ����Y^u+>��'�x��mT{[�=`O�L ����tIj����   K�����oAUu�A        �d�  �?w��A�*>���?���o�nA��A�S�MqA���A   �5Kn������Q ����Y^u+>��'�x��mT{[�=`O�L ����tIj����   ����p�dAUu�A        I@�  �?x��Ar�*>���?��QcA��AT���eA���A   �5Kn������Q �)� -.kLJ�|x�]yH�{[�=`O�L ����tIj����   ��·�tBUu�A        �a�;d�?�@�>n��@���?�V°3hB��AMt��ĀB���A   �5Kn������Q �@�H��H�"Un5�c�܊n�E#�{[�=`O�L ����tIj����   K}�i0BUu�A        u2�;d�?[\�>,z>A���?"�2AB��Au� �GB���A   �5Kn������Q �YNT��T��[�+����ӡ��{[�=`O�L ����tIj����   ����AUu�A        �6�;d�?L�>�*A���?���A��A�~�2�B���A   �5Kn������Q �x+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   +h��AUu�A        �6�;d�?�>�)A���?K��MqA��A���A���A   �5Kn������Q ��;����|�{���ڥ�� _Q{[�=`O�L ����tIj����   0���
Kݾ_Uo��$ȳoe���n[��]��0�    Hr[A1}���ʛA4�>ni?�� :���9L�?�ʰ@T��@�F:AS
[.xla]�?�dy��k<O�t����JR� ��}��G   =3m@��&B��A        ���<��?��UAv��A   AZ�#��1BUՅ@)�A�4GB��bA<    Vd�Y_DK�B��R� U��l�H��Ix\b�"�A,�KO�t����JR� ��}��G   5���<�A��A        :�5���?�DA�A   A�E8��(�AUՅ@�-?KU�A��bA    Vd�Y_DK�B��R� Uҿu�# ��A�ܝ�=�����!O�t����JR� ��}��G   ۴���yNA��A        �ʵ;��?��EA�}A   Aa�9��P	AUՅ@�-?1ӉA��bA(    Vd�Y_DK�B��R� U�p���2����X����F�x�O�t����JR� ��}��G   �y%ACȵA��A        �ؽD�~?��;B)B   Au7� wV@UՅ@�pB��B��bA�    b���(D�S+���� ��I1
����@jI�^�
 `e�}$uJ�q�NeȊq�`�1��    hv��py��Y*A�Zl;
�<��l?���>UU�@���?~�@ɇ��lɁ��b�@֕���o��?fA@    b���(D�S+���� ����f07L6���	��䬕��u	���B1������    ,T�+y©�,A        ^�l?��>UU�@��*=���@y���7����@�����r�T�cA   b���(D�S+���� �J}��\�$� �qC�Y��3�א�� �s�gtQ�#�e;$,�   ���@�z�
����@jI�^�
 `e�}$uJ�q�NeȊq�`�1��    hv��py��,�A�Zl;
�<��l?���>UU�@���?~�@ɇ��lɁ½X�A֕���o���A@    b���(D�S+���� ����f07L6���	��䬕��u	���B1������    ,T�+y�Uu�A        ^�l?��>UU�@��*=���@y���7����A�����rª��A   b���(D�S+���� �J}��\�$� �qC�Y��3�א�� �s�gtQ�#�e;$,�   ���@�z�A���>�k?b.�=�0=  �@�tI?h9�?wm�������A�,�¤�p�Uu�A$    ��,��J̫�GS�N ��ְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   ���¼O������e&��e&��5?�5?���@^@�A�U�¼�!«���=��¼¬ʥ��    ��,��J̫�GS�N �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0�¼O«���        �5?�5?���@UU)@  �>���¼O"«���=��¼O«���    ��,��J̫�GS�N ��W����T ����{��ۭ���u	���B1������   ���¼O«���J�<H�<95?95?TUm@vk�>4?	A����f� � ��������Vu��   ��,��J̫�GS�N �ְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   ���¼� ������e&��e&��5?�5?���@^@�A�U�¼	«���=���w���ʥ��    ��,��J̫�GS�N ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0�¼� «���        �5?�5?���@UU)@  �>���¼�	«���=���w�������    ��,��J̫�GS�N �W����T ����{��ۭ���u	���B1������   ���¼� «���J�<H�<95?95?TUm@vk�>4?	A����f:� ������"���Vu��   ��,��J̫�GS�N �9�)�h:�������wJ��]���e���C�'�a�8�~.�   ����{O�N��5��5?�;�o�� �@uxR?)
���=����t���*��$    ��,��J̫�GS�N �}}s�v$�\�^ڀ�D�ٍ�O
«ʥ�=����t��Vu��$    ��,��J̫�GS�N ��}s�v$�\�^ڀ�D�ٍ�O
�A        U��<�?ҫ{A&��?  Ao�z«��AP�;�gf�V%B   !�_J#�ٖ{ۀ� j+w��h*>���y�AS7�V�{[�=`O�L ����tIj����   �{���  �A        ��<�?��A�$�?��Aŧ�1ª�vA2���[«��A   !�_J#�ٖ{ۀ� j+�������,����-�ɭG��}$uJ�q�NeȊq�`�1��   �7��&>�  �A        gk�<��?Xa2=6+�>��A@=��1ª�vA2��i«��A   !�_J#�ٖ{ۀ� j,����rO.����>xΡ��f��}$uJ�q�NeȊq�`�1��   Y��3�P�  �A        �q�<��?�H@w�A��A|����Ӄª�vA@=�³«��A   !�_J#�ٖ{ۀ� j,���Ѥ wl��`�8h�{[�=`O�L ����tIj����   Y��3�P�  �A        Bq�<��?PH@w�A��A|����Ӄª�vA@=�³«��A   !�_J#�ٖ{ۀ� l����f07L6���	���{[�=`O�L ����tIj����   }a���xY�  �A              �?UU,A U�>��Ai�6�.NZª�vA@a(���X«��A   !�_J#�ٖ{ۀ� l�v�eW�[��qqfDεA�{[�=`O�L ����tIj����   ��@x[@�J�Av:?��/��(R����Փ�> iBTUA�c:�zG@��vA�4�AUT�@��A   !�_J#�ٖ{ۀ� l���I��!h���&��w9����{[�=`O�L ����tIj����   ;n��,�A  �A        �k��  �?�7AJl�>��A�9�֥A��vA����P	A���A   !�_J#�ٖ{ۀ� l��r��d;nk�Q�1^s){[�=`O�L ����tIj����   g𥾘�@  �A        �a�9��?b��>�Ϛ@��A�M���T@��vA���֥A���A   !�_J#�ٖ{ۀ� l�䤗��̠{Ƨ݇�i(c��{[�=`O�L ����tIj����   S���\5h@  �A        u&�  �?��1Am�>��A�;:��Z@��vA�M���u@���A   !�_J#�ٖ{ۀ� l�p��mӵ�$G�dv�;3V_�{[�=`O�L ����tIj����   ���A�,kA  �A        ��ط  �?@R�@l~�>��Apy�Aq�gA��vA ��A�nA���A   !�_J#�ٖ{ۀ� l�[0
?�(�AbU�?LT.AeBU��A�R�A0B���A{
?B�9AZU�?YͿeBU��Aw  A0B���Ac  !�2��nM�K'���"� ��B�Fx��O\�
49�@��5?�5?�j
?&�A\U�?��/�eBU��A���0B���A�  !�2��nM�K'���"� �����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   q�At6�A���A�5?�5?���'~<2�j
?�(�AbU�?��,A��AU��A��A`�A���A{
L�WCߴ  �?��&
�A�j
?YU�?Yk1���AU��A�jA`�A���A�  !�2��nM�K'���"� �K����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   @��A�lhA���A�5?�5?����~<2�j
?�(�AbU�?�#+A�dAU��A���A>�lA���A{
?
�AwU�?3��dAU��A��A>�lA���A�
?�(�AbU�?�)AMf0@U��Ab��A� S@���A{
��&�$�A�j
?WU�?=
5�Mf0@U��AC?A� S@���A�  !�2��nM�K'���"� ������5U�	���,���p�E�Q��3�ޒ�8�����ġ���   ��A�����A�5?�5?���'~<2�j
?�(�AbU�?\�'Am��U��A�'�A�?����A{
?WU�?ܭ6�m��U��A��A�?����A�  !�2��nM�K'���"� ����
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   �E�A�ɟ����A�D$��4  �?Dm�&�(�A�j
?XU�?vb&A6��U��AZ�A៝����A�
?
�AwU�?I�7�6��U��A�A៝����A�
?�(�AbU�?��$A6���U��A3��A������A{
?�ĨAdU�?d;�6���U��A~A������A�
?�(�AbU�?�6#A��,�U��AU��A��*ª��A{
?���AlU�?d;�q-�U��AS�A��*ª��A�
?�(�AbU�?�H"A��Z�U��A=M�A��Xª��A{
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   2㞿��Y����A    9�(3  �?    �.�A�j
?UU�?d;���Z�U��A�RA��Xª��A�
?]U�?�F��
?U
?U
?U
?��+AdU�?�3AqfXªz�A�U Ac-����A  !�2��nM�K'���"�  ���ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   ��A���U��A)
?��+AdU�?��Aqf*ªz�Al�!A5������A  !�2��nM�K'���"�  ���ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   BpA����U��A+
?��+AdU�?]_A�����z�A(�#A5Ƣ����A  !�2��nM�K'���"�  ���ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   � A�c�U��A,
?��+AdU�?�A�̜��z�A�%Ak�
?��+AdU�?ՊAę��z�A��&AV�)@���A  !�2��nM�K'���"� )��ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   v1#A�lAU��A���z�d�?��;�j
?��+AdU�?� A�Y@�z�A\B(A�sbA���A  !�2��nM�K'���"� F��ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   2�$At6�AU��A+
?��+AdU�?M�A<fnA�z�A�)A�9�A���A  !�2��nM�K'���"� b��ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   �\&At6�AU��A-
?��+AdU�?	L!A3�A�z�A�m+A�B���A  !�2��nM�K'���"� s��ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   ��'A:-BU��A,
?��+AdU�?��"A��B�z�A�-A�BB���A  !�2��nM�K'���"� ���ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   �� B:-BU��AJ�x�-
?��+AdU�?
?��+AdU�?���A�j�A�z�AȃB��B���A  !�2��nM�K'���"� ���ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   ų�At6�AU��A9�x�-
?��+AdU�?�+�A�nA�z�AYB=q�A���A  !�2��nM�K'���"� ���ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   ���A�lAU��A9�x�-
?��+AdU�?�`�A|T[@�z�A� By�bA���A  !�2��nM�K'���"� ���ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   	�A^L.�U��A9�x�-
?��+AdU�?��A�*��z�A{S B�+@���A  !�2��nM�K'���"� ���ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   +S�A�c�U��A��x�*
?��+AdU�?���A�̜��z�A���Ak�
?��+AdU�?���A�����z�A��A5Ƣ����A  !�2��nM�K'���"� )��xN��Ɓ��R\�a﷧�Q��3�ޒ�8�����ġ���   � B��U��A��;d�?�^ʴ7u�3�j
?Ȼ7A�U�?���A��+ªz�A?eB�2�����A,  !�2��nM�K'���"� @��ڗ�Mn5�Y]�)��nWQ��3�ޒ�8�����ġ���   ���A��B�U��A�z��5���d�?�j
?��+AdU�?j�AqfXªz�A{�Ac-����A  !�2��nM�K'���"� áoOGسo=؇��:�ll��Q��3�ޒ�8�����ġ���   X(�AG�p�U��A�����5�5��<4?��*A�j
?[U�?���A�
?0-AsU�?$��t��A
HB��4�        Ft;�  �?H.B��?UUA)n0�L�EBVEH,BL�JB p!�   $�./�	BA���a��X L�}��%8E��r��[�~B��[��հ�"�� �����i��Vil   �8�/ShB��4�        b��;��?s��?;�AUUA�nD�L�EBVEH-�	��B p!�   $�./�	BA���a��X M ��-J.��f����B)�ua�հ�"�� �����i��Vil   
ǯ�e��W�-a�;�ޞ�2��r`<\�{�E   �?�A��©�5A�d�>%�t�P�A?ϣ�D�?˙=?,h�A��ZA:�M��@W��A��R�~A�
  $���1Iz��I>{Pl} ��<�k=ٖ&��;��Uq(��ޞ�2��r`<\�{�E   ��A�:�4��AvU�����2p?�?� g?��?��[A��gA��R�|AW��A���Uu�A�  $���1Iz��I>{Pl} � J�_�=C�R\��gɆ������ޞ�2��r`<\�{�E   I)�A��U߲A��>F����<?���?=�9?Rj�A��ZA:�gr�AW��A���b�A�
  %:$1j9Bp��[.ӡ �c�T�u `�'����n:���}$uJ�q�NeȊq�`�1��   ���A�JE����?���<T^2�������{?m�c@!O�APF®*��W�A�D� a��   %:$1j9Bp��[.ӡ �c@jJ�1^e�AP9~�a�P�Q��3�ޒ�8�����ġ���   r{�A���^Ud�        ����?:$V@h��> V�=��A�M¶�g�A�A�k� a�   %:$1j9Bp��[.ӡ �c�����D�$��pc?�Yďw�}$uJ�q�NeȊq�`�1��   �v�A�¯*��        ����?��U@aЌ>`U�?h�A
*��=ܩyL�܀   �[�´:y�k`� O�� ��T�l?
����@jI�^�
 `e�}$uJ�q�NeȊq�`�1��    hv��py�Oc��Zl;
�<��l?���>UU�@���?~�@ɇ��lɁ����֕���o���H@@   %����PNڥq���glj 讐��f07L6���	��䬕��u	���B1������    ,T�+y�ժ�        ^�l?��>UU�@��*=���@y���7�� w������r�OU>@  %����PNڥq���glj ��y��#���!���D�	�UT�}$uJ�q�NeȊq�`�1��    St���ky± B�"�S�=;��þ��l?���@\Ҫ?���@	��¬ā�K��AK���۟o�LB�   %����PNڥq���glj ��
   %����PNڥq���glj �}d��f��T�ԣ�_Nw���<����u	���B1������    �y��wy�q B        �þ^�l?UU�@���>TU�@��D��yw�A����dr�g�Bh  %�N �K��H��g�- �>�OE^I�/MQ�[*�B��֣}$uJ�q�NeȊq�`�1��   W����D«jW��X,����Q5��5?� @�^�?��<A%���H�����ϥ��@«*��Z  %�N �K��H��g�- �Y p����Թ'X�ݳ{���}$uJ�q�NeȊq�`�1��   X���
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    赼´x�B9$A          �?���%  �@  �>�9�@��´8�BR��@赸´��B��UA�   '΀#�JX�u���� L@�B�wYC9�?}������ ���u�)���[��    ����^s�B�7$A          �?���%��j@���<���@=K��	n�B�*�@���´x�B&�RAv   '΀#�JX�u���� L@v
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    ���´x�B9$A          �?���%  �@  �>�9�@���´8�BR��@���´��B��UA�   '΀#�JX�u���� LA�B�wYC9�?}������ ���u�)���[��    =���^s�B�7$A          �?���%��j@���<���@�5��	n�B�*�@���´x�B&�RAv   '΀#�JX�u���� LAv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    =��´x�B9$A          �?���%  �@  �>�9�@=��´8�BR��@=��´��B��UA�   '΀#�JX�u���� LE�B�wYC9�?}������ ���u�)���[��    赼�^s�B.�|�          �?���%��j@���<���@�`��	n�B��y�=�´x�B1��?v   '΀#�JX�u���� LEv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    赼´x�B,n|�          �?���%  �@  �>�9�@��´8�B�*��赸´��BE@�   '΀#�JX�u���� LF�B�wYC9�?}������ ���u�)���[��    ����^s�B.�|�          �?���%��j@���<���@=K��	n�B��y����´x�B1��?v   '΀#�JX�u���� LFv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    ���´x�B,n|�          �?���%  �@  �>�9�@���´8�B�*�����´��BE@�   '΀#�JX�u���� LG�B�wYC9�?}������ ���u�)���[��    =���^s�B.�|�          �?���%��j@���<���@�5��	n�B��y����´x�B1��?v   '΀#�JX�u���� LGv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    =��´x�B,n|�          �?���%  �@  �>�9�@=��´8�B�*��=��´��BE@�   '΀#�JX�u���� LK�B�wYC9�?}������ ���u�)���[��    赼�^�B�rT�R�k&      �?    ��j@���<���@�`��	�B����=�´�B��%�v   '΀#�JX�u���� LKv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    赼´�B�qT�R�k&      �?      �@  �>�9�@��´؃B���赸´X�B##��   '΀#�JX�u���� LL�B�wYC9�?}������ ���u�)���[��    ����^�B�rT�R�k&      �?    ��j@���<���@=K��	�B�������´�B��%�v   '΀#�JX�u���� LLv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    ���´�B�qT�R�k&      �?      �@  �>�9�@���´؃B������´X�B##��   '΀#�JX�u���� LM�B�wYC9�?}������ ���u�)���[��    =���^�B�rT�R�k&      �?    ��j@���<���@�5��	�B�������´�B��%�v   '΀#�JX�u���� LMv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    =��´�B�qT�R�k&      �?      �@  �>�9�@=��´؃B���=��´X�B##��   '΀#�JX�u���� LO�a�Ʈ�U��|2CO�P�c� ���u�)���[��    =���^ӄBwy��              �?��j@���<N4�@�5��	΄B �����´؄B�ҭ�v   '΀#�JX�u���� LO�f�s�j�Ъ�{�x�Gq��}$uJ�q�NeȊq�`�1��    =��´؄B�x��              �?  �@  �>z��@=��´��BVu��=��´�B8|���   '΀#�JX�u���� LP�a�Ʈ�U��|2CO�P�c� ���u�)���[��    赼�^ӄBwy��              �?��j@���<N4�@�`��	΄B ��=�´؄B�ҭ�v   '΀#�JX�u���� LP�f�s�j�Ъ�{�x�Gq��}$uJ�q�NeȊq�`�1��    赼´؄B�x��              �?  �@  �>z��@��´��BVu��赸´�B8|���   '΀#�JX�u���� LQ_�^"�0�[�% ���nDM� ���u�)���[��    ����^ӄB����5?�5?/�,�/�,����<UU�@��@=K��	΄B �����´؄B����   '΀#�JX�u���� LQ��B�<���Ѧ ]>nJ���}$uJ�q�NeȊq�`�1��    ���´؄B����              �?  �@  �>ȝ�@���´��BVu�����´�B䍸��   'Ԑi�J�q�9:5�� l��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W���TBUu�A        �5��5?��^@��J?��
?ŧ��NB�J�A�/��4�[B���A   'Ԑi�J�q�9:5�� q�C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W�����!BUu�A        �5��5?��^@��J?��
?ŧ�0�B�J�A�/��(B���A   'Ԑi�J�q�9:5�� q4�C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W������AUu�A        �5��5?��^@��J?��
?ŧ¤��A�J�A�/��W~�A���A   'Ԑi�J�q�9:5�� qD�C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W����[kAUu�A        �5��5?��^@��J?��
?ŧ�+�OA�J�A�/��I��A���A   'Ԑi�J�q�9:5�� qT�C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W���{�?Uu�A        �5��5?��^@��J?��
?ŧV�=�J�A�/��R�c@���A   'Ԑi�J�q�9:5�� qd�C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W���=1�Uu�A        �5��5?��^@��J?��
?ŧ��M��J�A�/��jb����A   'Ԑi�J�q�9:5�� qt�C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W����Ŀ�Uu�A        �5��5?��^@��J?��
?ŧ�(����J�A�/��tױ����A   'Ԑi�J�q�9:5�� q��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W����S�Uu�A        �5��5?��^@��J?��
?ŧJªJ�A�/��A]����A   'Ԑi�J�q�9:5�� q��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W����D�Uu�A        �5��5?��^@��J?��
?ŧ���KªJ�A�/��q�=����A   'Ԑi�J�q�9:5�� q��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    (����D�Uu�A              �?��^@��J?��
?~2��s�FªJ�A�;���YC����A   'Ԑi�J�q�9:5�� q��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    J]��D�Uu�A              �?��^@��J?��
?�@d�s�FªJ�AWSV��YC����A   'Ԑi�J�q�9:5�� q��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    v�$��D�Uu�A              �?��^@��J?��
?#�+�s�FªJ�A����YC����A   'Ԑi�J�q�9:5�� q��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    �����D�Uu�A              �?��^@��J?��
?���s�FªJ�A=����YC����A   +����'A&�׺ERH ��#e(�������ZB7�`�?^��ɬ�@MQ��
x>�Pr$   �w�Ami-������3v���?��:7R�.�>>�@�Aב�A�=^� p!�J]�A/*���
��   +����'A&�׺ERH ��(>��������;�Ra�$��E�Ee>@r�
��   +����'A&�׺ERH ���b8
�              �?�f�>  �?��4A��A�=^� p!�J]�A�=^�����   +����'A&�׺ERH ��	U�J����e�`�R��R�?^��ɬ�@MQ��
x>�Pr$   &��Az˟������u���?����.~@7O��>��@(�AޱA� p!�<p�A����
��   +����'A&�׺ERH ��j�ܖ�Ū��]|j4��caN�1
�              �?�f�>  �?��4AޱA��� p!ª3�A�������   +����'A&�׺ERH ��k��	D$�"�r�p֝+?^��ɬ�@MQ��
x>�Pr$   K�AY4�������;u���?3ԕ�Elk7_��>`��@���A_�A+� p!�6�A6t���
��   +����'A&�׺ERH ��j�ܖ�Ū��]|j4��caN�1
�              �?�f�>  �?��4A_�A6t�� p!��]�A6t������   +����'A&�׺ERH ��}�\?�t�[�$|}��ԋ�?^��ɬ�@MQ��
x>�Pr$   ���A>��V���        )>����?��A��o?UգA�A��� p! � Bp¬
��   +����'A&�׺ERH ��إ�*��ʑa*�6
��aN�1
�\͕�t�[�4?�5?�A+>ɺ�?��4AS�A�=^� p!¥n�A�[�����   +����'A&�׺ERH �����@Sނ�`��O�;GD�aN�1
�C����,��f�4?�
�        g9  �?V�?X+>��4A�e�A6t�� p!�Jk�A�������   +����'A&�׺ERH ���u�
5Dis)z��d���Q��aN�1
�+��x����4?�5?d+>�װ?��4A�]�A���� p!�Jk�A6t������   +����'A&�׺ERH �/���f07L6���	���aN�1
x>�Pr$   ���A�=z�V���h��/YC�2��?��u���>!�j@��GA��Ayҋ� p8�A��\��
��   +����'A&�׺ERH �2�}�
tm2�<3k����?^��ɬ�@MQ��
x>�Pr$   OʴA����H����pu���?vz;��·4��>jxg@k�GA�2�A�'�� p��b�A`w���
��   +�T�@BA���!�õ\� &�`��b�w��&���΋e�ohO�t����JR� ��}��G   �����pBTu�A              �?��$A   A��AI���pB��vA�S���p$BSu�A   +�T�@BA���!�õ\� &��sR�`xW�q�4d���O)���O�t����JR� ��}��G   }H���\bBTu�A        ?%�:�?bd0A9��A��A�H��af<B��vA�S��^c�BSu�A    +�T�@BA���!�õ\� &���5-��+�c����d|6�O�t����JR� ��}��G   �������ATu�A              �?��$AXU�@��AI��$7�A��vA�S��=�BSu�A   ,f�|�)IH���%�Be< O�m�*z~?�T�Z�.ή�{[�=`O�L ����tIj����   ��q�;��� ��Asj�:��?�q�<Y�\9��>֖�@/A,�r¼�����vA�(q¸������A   ,f�|�)IH���%�Be< P+���f07L6���	���{[�=`O�L ����tIj����   �q¼���Uu�A        �5?�5?��?@Y��=  �@�Wq¼�����vA��p¼���Uu�A   ,f�|�)IH���%�Be< P+(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   �oe¼���U��A        �5?�5?��O@��?  �@W¼�����vAW¼���Uu�A   ,f�|�)IH���%�Be< P+�f��V]�I���ʪ����0����$P�����L��m�   ��q¼���U��A(�8'�8�5?�5?��O@j) ?] �@��r¼�����vA��p¼���Uu�A<   -g�ـ�A�����2~ T4��6&��T�
̲��ѳ ���u�)���[��    0f��^��B�qA              �?��j@���<���@���	��BT�9A���´��BhAv   -g�ـ�A�����2~ T4Y�{,�������F��J�=�}$uJ�q�NeȊq�`�1��    0f�´��Br�qA              �?  �@  �>$��@0f�´X�B��6A0f�´؅B�A�   -g�ـ�A�����2~ TE��6&��T�
̲��ѳ ���u�)���[��    0f��^��BH4v@              �?��j@���<���@���	��B}��>���´��B�	�@v   -g�ـ�A�����2~ TEY�{,�������F��J�=�}$uJ�q�NeȊq�`�1��    0f�´��B�9v@              �?  �@  �>$��@0f�´X�BK�:>0f�´؅Bvd�@�   -g�ـ�A�����2~ TV��6&��T�
̲��ѳ ���u�)���[��    0f��^3�B����              �?��j@���<���@���	.�B�j.����´8�B��y�v   -g�ـ�A�����2~ TVY�{,�������F��J�=�}$uJ�q�NeȊq�`�1��    0f�´8�B���              �?  �@  �>$��@0f�´��BW1�0f�´x�B7o��   -g�ـ�A�����2~ Td��6&��T�
̲��ѳ ���u�)���[��    0f��^ӄB̎��              �?��j@���<���@���	΄B�������´؄B풁�v   -g�ـ�A�����2~ TdY�{,�������F��J�=�}$uJ�q�NeȊq�`�1��    0f�´؄B���              �?  �@  �>$��@0f�´��B��0f�´�B8<���   -�Մ�C�c7���� 	,molA��j�5QK˛��N&KQ�!��(�!D����;�   6�Bl�hA�ʋA        ��;d�?��!A|��?  8AI�yB�faAR�;A�
�BW pA�ʹA   -�Մ�C�c7���� 	,m�K����R��\�ø���_�(l{[�=`O�L ����tIj����   6�Bl�hA�ʋA        ��;d�?��!A��?  8AI�yB�faAR�;A�
�BW pA�ʹA   .V�`�4Jm�b~�V�g 	(���QL;eW�_�P�Ki�PR�N&KQ�!��(�!D����;�   HKB�3BVE4B        �%�;b�?3�?��6A   ADnB��BVE B;(BL�JBVEHB   .V�`�4Jm�b~�V�g 	(�f3��Gɸ9[kvuW ���{[�=`O�L ����tIj����   HKB�3BVE4B        a�;d�?�փ?��6A   ADnB��BVE B;(BL�JBVEHB   .V�`�4Jm�b~�V�g 	)\���c?ѳf�Z��B��
C
���2�T��[��Y�xr��(;�{p9DC}�\ə�   �<B�3S� P�              �?UUu?UUu?  !A�:BDU� p1�D�=B�HQ� 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   4uBz�S� P�              �?UUu?UUu?  !A�1sB$�U� p1��wB��Q� 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   �b�B�T� P�              �?UUu?UUu?  !A�m�B1�U� p1�>X�B�R� 0	�   .�M�&N#��T	�4� �
�� P�              �?UUu?UUu?  !A���B_Ɯ� p1�Y|�B��� 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�    ��B�͗� P�              �?UUu?UUu?  !A���BD��� p1�U{�B���� 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   "�GBᮖ� P�              �?UUu?UUu?  !Ax
FB6��� p1���IB�ْ� 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   VHBJ
�� P�              �?UUu?UUu?  !AhkFB�/� p1½@JB���� 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   x��B���� P�              �?UUu?UUu?  !A#��B�m� p1�ͫ�B,1�� 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   |��Bv	� P�              �?UUu?UUu?  !A&¤B!�	� p1�Ѭ�B���� 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   �BV9@ P�              �?UUu?UUu?  !A��Br�@ p1�nݦB� X@ 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   �B�nB@ P�              �?UUu?UUu?  !A��BJ�#@ p1�k܅B�a@ 0	�   .�M�&N#��T	�4� ����2�T��[��Y�xr��(;�{p9DC}�\ə�   M�HBcgK@ P�              �?UUu?UUu?  !A��FB��,@ p1���JBj@ 0	�   /v�;�O������� ��{�y}ډ�j]
�!����Zא�� �s�gtQ�#�e;$,�   �[�³:yª��Av�8��o��þ^�l?��dA�?k51B����«*��Qy���uc� �B  /v�;�O������� ��5��㖟�[���b�Tш`Fא�� �s�gtQ�#�e;$,�   X�����{�~�B���>wQl?�=��~<HMA֨T?L�@�^��M���V�B���½�i� �B$   /v�;�O������� ����1�+Y�)�YԮ��7$ȳoe���n[��]��0�   sJ��,{�B#�`�����\l?���>yfOA�z�?"(�>����%����Bq��'Th�NL B   /�M��I@�!���� 
�?�o?VUA��A쇁����,9�A@'�¬j�   1ǧ {G%��M�V�. C�,Y
}�S!�+
��p
fO{[�=`O�L ����tIj����   ��A
�u�Vi�        q��>fv?�Aj?D��?VUA��uA��w����
h�����]�Uv���:{[�=`O�L ����tIj����   �gARq�Vi�        <��>or?�Jq?��*@VUA��VA�!u�����yAu�m¬j�   1ǧ {G%��M�V�. F�e�>�w���ド&�2�a{[�=`O�L ����tIj����   W�YAG�k�Vi�        �Î���u?�H�?	f}?VUA�NA��o�����bAʼh¬j�   1ǧ {G%��M�V�. Gs��M>Y�g���ǅe��U{[�=`O�L ����tIj����   sMA��f�Vi�         8T�(qz?LI�?&;�?VUA�FA�ui�����TA	Hd¬j�   1ǧ {G%��M�V�. G���t��@�׍1�G��RX)���{[�=`O�L ����tIj����   ��FA6c�Wi�        �cC��K{?8]?��_?VUAAA��d����+LA�Ka¬j�   1ǧ {G%��M�V�. H#stNt8��7v�/�+Q{[�=`O�L ����tIj����   P�@Ar@_�Vi�        ��1�\|?���?Zٜ?VUA�<:As�a�����WGA��\¬j�   1ǧ {G%��M�V�. H�����TA���L���T�z�O�{[�=`O�L ����tIj����   �|;A*z[�Vi�        �0 �"�|?}&G?1Z?VUA,~6A�*]������@Ac�Y¬j�   1ǧ {G%��M�V�. I����_T���J�[PV�k�{[�=`O�L ����tIj����   �k7A�!X�Vi�        �L�{}?1�b?k��?VUA�
2A&IZ������<A�U¬j�   1ǧ {G%��M�V�. J=
���硫ې���`��|Զ{[�=`O�L ����tIj����   \c3A�8T�Wi�        U�5`~?+�Q?��?VUA�U.A�gV�����8A�R¬j�   1ǧ {G%��M�V�. J|'f�'�@�X��L5y�y�]{[�=`O�L ����tIj����   H�/A�P�Wi�        �JĽI�~?i�J?j��?VUA�+AAdR������4A��M¬j�   1ǧ {G%��M�V�. KF!b�u��9�^)�+�K{[�=`O�L ����tIj����   �	-AL�Wi�        m����5?�2?��?VUA}�(A�N������1A��I¬j�   1ǧ {G%��M�V�. Kn��������5���!�w�{[�=`O�L ����tIj����   ��*A#H�Vi�        �c{�t�?�6(? /�?VUAw}&AP6J�����#/As�E¬j�   1ǧ {G%��M�V�. K�
�7Jv�PQ��Ϫ`��qE�;{[�=`O�L ����tIj����   >/)A�D�Wi�        5!�9�?��?.��?VUA�C%A\F�����-A�B¬j�   1ǧ {G%��M�V�. L6�����u�M�j�n0_c��{[�=`O�L ����tIj����   7=(A�@�Wi�        񻬼n�?�� ?�G�?VUA��$A�0B������+Az�=¬j�   1ǧ {G%��M�V�. L�#�}�PI��ɀC��{��{[�=`O�L ����tIj����   ��'A��;�Vi�        �ʕ9��?��>m�?VUA��$Af>����,<+A��9¬j�   1ǧ {G%��M�V�. Lȵ���e�N]�6��I��HC{[�=`O�L ����tIj����   .(A>�7�Wi�        �S�<b�?��>8$�?VUA��$Al�9������+A�5¬j�   1ǧ {G%��M�V�. MM��Ί��݀���ÿ�V
�.1�1(G?H&T?��z?���>VUAuH(A��-�����(3A�Y*¬j�   1ǧ {G%��M�V�. Q�gh��Q��~��ت�I!+�{[�=`O�L ����tIj����   =�A8-µ�_���м{��<�9���0?�S�>㠮A�DA�1A0����Ɠ B-n*�X
�   1ǧ {G%��M�V�. S$���f07L6���	���{[�=`O�L ����tIj����   pNPAxz,��}�        =����?  @@Z��=  �@�J8AF�,����[RhA��+��E�   1ǧ {G%��M�V�. S$(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   �NAY&8��|�        =����?  P@  �?  �@E%4ALt8�����hAf�7��C�   1ǧ {G%��M�V�. S$�f��V]�I���ʪ����0����$P�����L��m�   9xPA��+��|���98$v��=����?  P@k) ?] �@�O6Aa�,�����jAN*��C�<   4C�	=M������ ���XX�DXw��S�6�e�� ){[�=`O�L ����tIj����   P��(��  �Aq�<��?Cď1�8���=x,�B��:@.n��X���Uu�A�1��#�1A���A$   5	�<�O[�Ѷ�_
}� �C��
jqk6�!6'm̌��Ү��{[�=`O�L ����tIj����   ���U�  �A��  �?�&�?�.���>��A��:@�ǻ��̃�Uu�A.r��M�"«��A   5��_:B���Q8[՟� 	p`̾� ������m Q���$#�{[�=`O�L ����tIj����   fi�
��@�p3�̼ٝ�?ձn;�Ѿ��U�>`HA��A�k�k�?X}���f�bA���   5��_:B���Q8[՟� 	q��\��[2�\҂�Mɹ�\�{[�=`O�L ����tIj����   ��G;@�j3� q0?�{9?�~�����cU�>O BP�A"g���?X}��G���B�@���    5��_:B���Q8[՟� 	r˃�{ ��b� ���"��{[�=`O�L ����tIj����   S����)"A�c�        *�̼��?s��?8X@A  $A+���%��@���{r���C�A��   5��_:B���Q8[՟� 	s˃�{ ��b� ���"��{[�=`O�L ����tIj����   �A�H1
A�j3�        +�̼��?s��?7X@AVUA�$C��M'@X}��?��jA���   5��_:B���Q8[՟� 	u���f07L6���	����0����$P�����L��m�   �c�����A���        ��?&�̼+��@��*>  �>B���>}A���Å�����A���   5��_:B���Q8[՟� 	w���2�T��[��Y�x�}�9�H
1ћfb��   R���9a|A�}�        ��?&�̼ �?���=  �@N���~P{A���V����q}A�E�   5��_:B���Q8[՟� 	y���2�T��[��Y�x�}�9�H
1ћfb��   ����%{A�}�        '��<��?��:@��*=  �@ �T�yA������f�|A�E�   5��_:B���Q8[՟� 	y&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   w���87zA���        '��<��?���=  �>  @?�A���/wA���q���>}A���   5��_:B���Q8[՟� 	{���2�T��[��Y�x�0����$P�����L��m�   �`�;�sA���        ��?&�̼VUMA��*>  �>{4��CmA���� ±.zA���   5��_:B���Q8[՟� 	}���2�T��[��Y�x�}�9�H
1ћfb��   �;��	G~A�}�        ��?&�̼��:@��*=  �@����q}A��������8�A�E�   5��_:B���Q8[՟� 	}Vz��������A�����2��0����$P�����L��m�   p����5A���        ��?&�̼���= �>  @?�Q��.|A���	�����A���   5��_:B���Q8[՟� 	���2�T��[��Y�x�}�9�H
1ћfb��   VB�%flA�}�        ��?&�̼ �?���=  �@�WD�jUkA����T@��vmA�E�   5��_:B���Q8[՟� 	����2�T��[��Y�x�}�9�H
1ћfb��   *J��*kA�}�        '��<��?��:@��*=  �@��O�@�iA���xUD�R�lA�E�   5��_:B���Q8[՟� 	�&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   .�N�$<jA���        '��<��?���=  �>  @?�	O��gA����N�(�mA���   5��_:B���Q8[՟� 	����f07L6���	����0����$P�����L��m�   ��]�KfA���        ��?&�̼,f�@��*>  �>�mj�nbbA���x�P3jA���   5��_:B���Q8[՟� 	����2�T��[��Y�x�}�9�H
1ћfb��   W�:��KnA�}�        ��?&�̼��:@��*=  �@�X@�l�lA���ί4�}�oA�E�   5��_:B���Q8[՟� 	�Vz��������A�����2��0����$P�����L��m�   *�5:oA���        ��?&�̼���= �>  @?^6�	3lA�����5�+BrA���   5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �a���i�As���        ��?&�̼+��@���=��@�;���}A����䇔��	�A:n��  5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �_�dsAs���        ��?&�̼VUMA���=��@I4���mA����� �/yA:n��  5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �]���eAs���        ��?&�̼,f�@���=��@Sjj¨�bA������P��3iA:n��  5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �a���i�A�W�        ��?&�̼+��@���=�8@�;���}A:Ni�䇔��	�A�E�  5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �_�dsA�W�        ��?&�̼VUMA���=�8@I4���mA:Ni�� �/yA�E�  5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �]���eA�W�        ��?&�̼,f�@���=�8@Sjj¨�bA:Ni���P��3iA�E�  5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �a���i�AW{�        ��?&�̼+��@���=�8@�;���}A:n��䇔��	�A:Ni�  5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �_�dsAW{�        ��?&�̼VUMA���=�8@I4���mA:n��� �/yA:Ni�  5��_:B���Q8[՟� 	����f07L6���	��䬕��u	���B1������   �]���eAW{�        ��?&�̼,f�@���=�8@Sjj¨�bA:n����P��3iA:Ni�  5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   ��]�gA:Ni�į�<~�4�ǯ�<~�4?���=  �<,f�@?lj�ubdA��i�ަP½�iA��h�   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   Qc�N�tA:Ni�į�<~�4�ǯ�<~�4?���=  �<VUMA54��CoA��i�l� ���yA��h�   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   i����A:Ni�į�<~�4�ǯ�<~�4?���=  �<+��@�?���>A��i������V�A��h�   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   ��]�gA:n��į�<~�4�ǯ�<~�4?���=  �<,f�@?lj�ubdA�Æ�ަP½�iA���   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   i����A:n��į�<~�4�ǯ�<~�4?���=  �<+��@�?���>A�Æ������V�A���   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   Qc�N�tA:n��į�<~�4�ǯ�<~�4?���=  �<VUMA54��CoA�Æ�l� ���yA���   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   ��]�KfA�jD�į�<~�4�ǯ�<~�4?��*>��*>,f�@�mj�nbbA�E�x�P3jAWC�   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �SB±�kA�jD�į�<~�4�ǯ�<~�4?��*>��*> �?�WD jA�E�ZP@��vmAWC�
�+�(������ְ�P��M�   f5��ZG}A�jD�į�<~�4�ǯ�<~�4?��*>��*>��:@����#�zA�E������AWC�
   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   �c�����A�jD�į�<~�4�ǯ�<~�4?��*>��*>+��@B���>}A�jD�Å�����A�A�   5��_:B���Q8[՟� 	�0]�����!E�U�=7O(
�+�(������ְ�P��M�   %�:�FLmA�jD�į�<~�4�ǯ�<~�4?��*>��*>��:@�X@��jA�E�j�4�}�oAWC�
   5��_:B���Q8[՟� 	���6�l���c�r��f��r��+�(������ְ�P��M�   ����/&zA�jD�į�<~�4�ǯ�<~�4?��*>��*>��:@ ���wA�E�B���f�|AWC�
   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   �`�;�sA�jD�į�<~�4�ǯ�<~�4?��*>��*>VUMA{4��CmA�E�� ±.zAWC�   5��_:B���Q8[՟� 	���6�l���c�r��f��r��+�(������ְ�P��M�   �&J�+jA�jD�į�<~�4�ǯ�<~�4?��*>��*>��:@��O��gA�E�OD�R�lAWC�
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����A�Q��        '��<��?��*>��*>�8@Ζ���4�AV5���0��Ś�A:n��
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����AW{�        '��<��?��*>��*>�8@Ζ���4�A:n���0��Ś�A:Ni�
�+�(������ְ�P��M�   �����A����        '��<��?��*>��*>���>Z��W=�A���f���K��AV5��
   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   �c�����AV5��į�<~�4�ǯ�<~�4?��*>��*>+��@B���>}A���Å�����A����   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   �`�;�sAV5��į�<~�4�ǯ�<~�4?��*>��*>VUMA{4��CmA���� ±.zA����   5��_:B���Q8[՟� 	����f07L6���	����+�(������ְ�P��M�   ��]�KfAV5��į�<~�4�ǯ�<~�4?��*>��*>,f�@�mj�nbbA���x�P3jA����   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����~AW{�$�̼��?       ���*>��*>�8@�����-}A:n��������A:Ni�
�+�(������ְ�P��M�   �����~A�1V�$�̼��?��
   5��_:B���Q8[՟� 	���6�l���c�r��f��r��+�(������ְ�P��M�   �����~A����$�̼��?       ���*>��*>���>�����}A���1����AV5��
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �����~A�Q��%�̼��?ǈ^-�#N���*>��*>�8@�����AV5��B��=I�A:n��
�+�(������ְ�P��M�   rX4¡�nA�1V�$�̼��?       ���*>��*>��@�4­!mA:Ni���3�oAWC�
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   rX4¡�nAW{�$�̼��?       ���*>��*>�8@�\4¹2mA:n����3¡�oA:Ni�
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   rX4¡�nA�Q��$�̼��?       ���*>��*>�8@�\4¹2mAV5����3¡�oA9n��
�+�(������ְ�P��M�   �OP���hA�1V�$�̼��?����8�1&��*>��*>��@�SP�ؚgA:Ni�ʠO��fjAWC�
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �OP���hAW{�$�̼��?       ���*>��*>�8@�SP�ؚgA:n��ʠO��fjA:Ni�
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   i ���xAW{�$�̼��?       ���*>��*>�8@Rm ��wA:n���t���azA:Ni�
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   i ���xA�Q��$�̼��?       ���*>��*>�8@Rm ��wAV5���t���azA9n��
�+�(������ְ�P��M�   i ���xA�1V�$�̼��?       ���*>��*>��@Rm ��wA:Ni��t���azAWC�
   5��_:B���Q8[՟� 	�0]�����!E�U�=7O(
�+�(������ְ�P��M�   }�j�K�cA�1V�$�̼��?       ���*>��*>��@�k�W@bA:Ni� ej�?eAWC�
   5��_:B���Q8[՟� 	�-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   }�j�K�cA�Q��$�̼��?       ���*>��*>�8@�k�W@bAV5�� ej�?eA9n��
   6#ː�Oy���3B� ��9��t�݈�

%�V�B   6�ßILf�W��
��I�O�t����JR� ��}��G   ����J�����A        #w+=��?
�jA�a4A   A=��-�����A���8���V�B   6�ßILf�W��
�A���xh��_�A�   89JT�HHP��/j�>yg 
o�\-�aN�1
���A�&�A�&�5?�5?�A�A���>  @?wfn��C«
��wfl�;� «
��   8|N~��O���߼� �ې��f07L6���	���r��(;�{p9DC}�\ə�   wfm�o�f«
���A���A�&�5��5?CU�A���>  @?wfn�5j�«
��wfl��)G«
��   8|N~��O���߼� �吤�f07L6���	���r��(;�{p9DC}�\ə�   ,�-¬^"«
���A�&�A�&�5?�5?�A�A���>  @?,�.��C«
��,�,�;� «
��   8|N~��O���߼� �搤�f07L6���	���r��(;�{p9DC}�\ə�   ,�-�o�f«
���A���A�&�5��5?CU�A���>  @?,�.�5j�«
��,�,��)G«
��   8|N~��O���߼� ��f07L6���	���r��(;�{p9DC}�\ə�   �~���^"«
���A�&�A�&�5?�5?�A�A���>  @?�~���C«
���~��;� «
��   8|N~��O���߼� ��f07L6���	���r��(;�{p9DC}�\ə�   �~��o�f«
���A���A�&�5��5?CU�A���>  @?�~��5j�«
���~���)G«
��   8�2s��@v��5
�"� ����7o��'��O(�!�[2{[�=`O�L ����tIj����   �w�A6���Uu�A        | ��  �?��AԮ*>���?�A�����A�B�J�����A   8�2s��@v��5
�"� ����7o��'��O(�!�[2{[�=`O�L ����tIj����   %��A���Uu�A        ���  �?��AE�*>���?��A�H����AB� B6������A   9H�oO�H���k�4k�! 	��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   R~�/tfB��A        ^1��  �?v�NBm
?  �?
A��D� ��              �?��AA   ?  @?JY��E� P���(��C� P�   <�{gC���3=Yn2 � ���f07L6���	���r��(;�{p9DC}�\ə�   ����D� ��              �?  @A   ?  @?�� ��E� P����C� P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�   �����D� ��              �?��/A   ?  @?�����E� P�s��C� P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�    ط�A��B ��   '`W�  �?���&G�A   ?  @?�5��A�B P�Wz��A�B P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�   ���A��B ��              �?���A   ?  @?Wz��A�B P·ӄ�A�B P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�   ��� �yB ��              �?���A   ?  @?Wz�� �xB P·ӄ� �zB P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�    ط� �yB ��   '`W�  �?���&G�A   ?  @?�5�� �xB P�Wz�� �zB P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�   ����cB ��              �?���A   ?  @?Wz���bB P·ӄ��dB P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�    ط��cB ��   '`W�  �?���&G�A   ?  @?�5���bB P�Wz���dB P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�   ���!�KB ��              �?���A   ?  @?Wz��!�JB P·ӄ�!�LB P�   <�{gC���3=Yn2 �	���f07L6���	���r��(;�{p9DC}�\ə�    ط�!�KB ��   '`W�  �?���&G�A   ?  @?�5��!�JB P�Wz��!�LB P�   <�{gC���3=Yn2 �
���f07L6���	���r��(;�{p9DC}�\ə�   ���&>B ��              �?���A   ?  @?Wz��&=B P·ӄ�&?B P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�   ���֝&B ��              �?���A   ?  @?Wz��֝%B P·ӄ�֝'B P�   <�{gC���3=Yn2 ����f07L6���	���r��(;�{p9DC}�\ə�    ط�&>B ��   '`W�  �?���&G�A   ?  @?�5��&=B P�Wz��&?B P�   <�{gC���3=Yn2 �
�@����X���X�A��Eg���A   =V�6L��J���� �x���f07L6���	����+�(������ְ�P��M�   *c���1�8��A�N?6�>�N?6�����=���<�(�@1Ȯ��%��X�A#�����A   =V�6L��J���� �y���f07L6���	����+�(������ְ�P��M�   �
�y|�8��A�N?6�>�N?6�����=���<��@TT��vk���X�A����Qr�A   =V�6L��J���� �z���f07L6���	����+�(������ְ�P��M�   �y����f�8��A�N?6�>�N?6�����=���<���@�İ��rq��X�A/���b\�A   =V�6L��J���� �{$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y��8��A�N?6�>�N?6�����=���<���@�F�µH���X�A����4�����A   =V�6L��J���� �|���f07L6���	����+�(������ְ�P��M�   �
���i@8��A�N?6�>�N?6�����=���<x��@Fo����=�X�At�����@��A   =V�6L��J���� �}$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3�8��A�N?6�>�N?6�����=���<��@�w��<�?��X�A+Į�rI&�A   =V�6L��J���� �~$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l�8��A�N?6�>�N?6�����=���<���@�4��a����X�A@k�§Ľ��A   =V�6L��J���� ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y���A�N?6�>�N?6�����=���<���@�F�µH��Ƒ�A����4���q<�A   =V�6L��J���� ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3��A�N?6�>�N?6�����=���<��@�w��<�?�Ƒ�A+Į�rI&�q<�A   =V�6L��J���� �����f07L6���	����+�(������ְ�P��M�   �
���i@�A�N?6�>�N?6�����=���<x��@Fo����=Ƒ�At�����@q<�A   =V�6L��J���� ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l��A�N?6�>�N?6�����=���<���@�4��a���Ƒ�A@k�§Ľq<�A   =V�6L��J���� �����f07L6���	����+�(������ְ�P��M�   �y����f��A�N?6�>�N?6�����=���<���@�İ��rq�Ƒ�A/���b\�q<�A   =V�6L��J���� �����f07L6���	����+�(������ְ�P��M�   "D��t}���A�N?6�>�N?6�����=���<
�@����X��Ƒ�A��Eg�q<�A   =V�6L��J���� �����f07L6���	����+�(������ְ�P��M�   *c���1��A�N?6�>�N?6�����=���<�(�@1Ȯ��%�Ƒ�A#�����q<�A   =V�6L��J���� �����f07L6���	����+�(������ְ�P��M�   �
�y|��A�N?6�>�N?6�����=���<��@TT��vk��Ƒ�A����Qr�q<�A   =�LU�B�Z�0�I� �=���f07L6���	��䬕��u	���B1������   b����yA�X�A        �5��5?<`�@���=��@�3���?VAT�}A
   =�LU�B�Z�0�I� �;���f07L6���	����+�(������ְ�P��M�   
�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �>-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �G0]�����!E�U�=7O(
�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �H-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �R-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �T-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �Z-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �\-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �f-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�+�(������ְ�P��M�   
   =�LU�B�Z�0�I� �h-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
�����F�{[�=`O�L ����tIj����   #���/B�~�A�%>         �}? U�>WZ�@!A͇�&B��vAx��·�:B���A   >
	E���D?�kA�-����{[�=`O�L ����tIj����   S����)"A�J�A(�̼��?3�/���˱oU�>��@ATUA+���%��@��vA{r���C�A��A   >
A�J�A        g ͼz�?q�?n�1ATUA
�V$G@��vA=G��cA��A   >
A�J�A        +�̼��?s��?7X@ATUA�$C��M'@��vA�?��jA��A   >
�AI4?I4?C��C��`U�>�ǔ@�0(AZw5��8_���vA��$�@�X����A   >
���SW����vA�����������A   >
����������A   >
�X�߫F�G5��
�A�
�A�pf7*nc?P�м�A��,AQ��@dP�B!Ae�Uu�A�"�B�(����A�   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   P�B��dªʑA        �m4?��5?ď��)�@?���@ʏ�BjGe©�zA5�B�Bd�  �A4   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �O�B��dªʑA        �m4?��5?ď��)�@?���@o��BhGe©�zA��B�Bd�  �A4   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   1P�B��dªʑA        �m4?��5?ď��)�@?���@ޏ�B"$e©�zAH�B�d�  �A4   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   EP�BQdªʑA        �m4?��5?ď��)�@?���@�B� e©�zA\�B?�c�  �A4   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   VP�Br`dªʑA        �m4?��5?ď��)�@?���@��B��d©�zAm�Ba�c�  �A4   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   'ۿB�"4ªʑA        ��?��U;Ï��(�@?���@���B��5©�zA��B��2���A4   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �ɿB�"DªʑA        ��?��U;Ï��(�@?���@���Be�E©�zAH
�B��B���A4   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ෿B�"TªʑA        ��?��U;Ï��(�@?���@Wv�B>�U©�zA���Bi�R���A4   >*�Dq��4!*JT� bj�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   .�B�"*ªʑA        ��?��U;Ï��(�@?���@���B��+©�zA�&�BϠ(���A4   >*�Dq��4!*JT� bp�Ĕ�T�Р���/,��U�Cl�ޞ�2��r`<\�{�E   �%�B6-a�	`�A鮫78���6�"F3?���?!c�AX[�@�kB��d�Uu�A�l�B�\©J�A8  >*�Dq��4!*JT� bp�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   sj�BXd���A        �m4?5?����(�@?WU�@��B��d©�zA�+�B�cªʸA4   >*�Dq��4!*JT� bp�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��|B�c���A        �m4?5?����(�@?WU�@�T{B�-d©�zA�W~B)cªʸA4   >*�Dq��4!*JT� bp�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �j�B^�c���A        �m4?5?����(�@?WU�@k��B�Pd©�zA�+�BLLcªʸA4   >*�Dq��4!*JT� bp�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �j�B��c���A        �m4?5?����(�@?WU�@W��B/td©�zA�+�B�ocªʸA4   >*�Dq��4!*JT� bp�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �j�B�d���A        �m4?5?����(�@?WU�@D��Bw�d©�zA�+�BےcªʸA4   >*�Dq��4!*JT� bp�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �j�B59d���A        �m4?5?����(�@?WU�@0��B��d©�zA�+�B#�cªʸA4   >*�Dq��4!*JT� bp�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   |7lBň^���A        ��U���?����%�@?SU�@�kB�
`©�zA��lB]©ʸA4   >*�Dq��4!*JT� bp�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   [2lB��`���A        ��U���?����%�@?SU�@ҰkB
^b©�zAm�lB5[_©ʸA4   >*�Dq��4!*JT� bv�$u�_z��sU~�I�!bڛF�ޞ�2��r`<\�{�E   �ҿB�8��`�A�<4��5?��ŷ��7�A$ ?}U�@��B�"(�Uu�A���BXP��J�A�   >*�Dq��4!*JT� bv�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �c�BI�`���A        ��?��U;����'�@?SU�@T"�B�f���zA���B��Z��ʸA4   >*�Dq��4!*JT� bv�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��B#&���A        ��?��U;����'�@?SU�@��B��'©�zA\+�B٠$©ʸA4   >*�Dq��4!*JT� bv�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   f�B1lX���A        ��?��U;����'�@?SU�@�$�B�n^���zA��BycR��ʸA4   >*�Dq��4!*JT� bv�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��B)#���A        ��?��U;����'�@?SU�@}��BУ©�zA�:�B��©ʸA4   >*�Dq��4!*JT� bv�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��BP#���A        ��?��U;����'�@?SU�@!ʿB��	©�zAoL�B"�©ʸA4   >*�Dq��4!*JT� bv�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   N�B�F����A        ��?��U;����'�@?SU�@�ۿB<H����zA^�B�B���ʸA4   >*�Dq��4!*JT� bv�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �.�B;G����A        ��?��U;����'�@?SU�@i��B�H����zA�o�B�B���ʸA4   >*�Dq��4!*JT� bv�]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �@�B�G����A        ��?��U;����'�@?SU�@
�AĮ!?{F?uk��`os�  �A�?
[A�qjBi����nA�q~By~�@���A�  >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��|B�����ʜA        f�=��~?���>&�@?UU%A�%|B������fA�}B�x{���A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   @�kBK�@�ʜA        f�=��~?���>&�@?UU%A))kB�s�@��fAD�lB,�@��A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ^�{B�i��ʜA        f�=��~?���>&�@?UU%AG�zB��o���fAbV|B��c���A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   
�nB�n�?�ʜA        f�=��~?���>&�@?UU%A��mBe.?��fAeoB��?��A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   _rB~�5��ʜA        f�=��~?���>&�@?UU%AH:qB.O���fAd�rB�����A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �AuB3Z���ʜA        f�=��~?���>&�@?UU%A�vtB������fA��uBo9����A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   	~xB��*��ʜA        f�=��~?���>&�@?UU%A�wBx&1���fAyB1J%���A4   >*�Dq��4!*JT� b�2'��fj1�Ж�������F�ޞ�2��r`<\�{�E   �B,K���n���;R�?̶���Զx�B�?[A�{B��Q����gC�B>�C��j��  >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ���B*SL�Ws�        :4?X�5?���>(�@?UU%A���Bn_N���A�BMJ��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��B�K�Ws�        :4?X�5?���>(�@?UU%A���BO�M���%A�B��I��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   #��B�8K�Ws�        :4?X�5?���>(�@?UU%Aο�B0EM���8A�B�2I��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   }B��H�Ws�        :4?X�5?���>(�@?UU%AY�{B;�J���.�~B�F��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   7��BΫJ�Ws�        :4?X�5?���>(�@?UU%A῜B�L���LA�B��H��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   逽BI�L�Ws�        :4?X�5?���>(�@?UU%A���B��N����@�B6�J��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   J��B�J�Ws�        :4?X�5?���>(�@?UU%A���B�*L���_A�B�H��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �A�B4�L�Ws�        :4?X�5?���>(�@?UU%AJ��BxO�����B"�J��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ^��B��I�Ws�        :4?X�5?���>(�@?UU%A��BԝK���sA�B~�G��j �4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   q��BrI�Ws�        :4?X�5?���>(�@?UU%A��B�K����A�B`�F��j �4   >*�Dq��4!*JT� b�hk���]J�-��4����p�[<�F�Lt��չa/g�rj�   �&lB
~?��3A��APU5@�F`B����nA��{Bt}@��Ax   >*�Dq��4!*JT� b���=O��X@L��cy��}$uJ�q�NeȊq�`�1��   � aB" @��xA        �L�=�~?��*>��*>  @ݛ`B���?��fA%eaBWl@Uu�A   >*�Dq��4!*JT� b���=O��X@L��cy��}$uJ�q�NeȊq�`�1��   U�oB�F����xA        �L�=�~?��*>��*>  @�KoB�����fA�pB��~�Uu�A   >*�Dq��4!*JT� b���=O��X@L��cy��}$uJ�q�NeȊq�`�1��   �-jB�D���xA        �L�=�~?��*>��*>  @��iBY����fA5�jB9��Uu�A   >*�Dq��4!*JT� b���=O��X@L��cy��}$uJ�q�NeȊq�`�1��   p�cBԺ����xA        �L�=�~?��*>��*>  @�fcBSOÿ��fA0dBU&��Uu�A   >*�Dq��4!*JT� b���=O��X@L��cy��}$uJ�q�NeȊq�`�1��   ��yB?����xA        {F?Ю!?��*>��*>  @�yBG�����fA�]zB��}�Uu�A   >*�Dq��4!*JT� b���=O��X@L��cy��}$uJ�q�NeȊq�`�1��   ��fB$����xA        �L�=�~?��*>��*>  @ݗfBDA����fA%agB���Uu�A   >*�Dq��4!*JT� b���=O��X@L��cy��}$uJ�q�NeȊq�`�1��   �^mB��R���xA        �L�=�~?��*>��*>  @��lB�T���fAF�mB�hQ�Uu�A   >*�Dq��4!*JT� b��X�����K)]V��/L�ޞ�2��r`<\�{�E   ��fB5� @`�A��
8������d�?��J@K ?~U�@�9`B2�
   >*�Dq��4!*JT� b�����|�Q��0K�6e/Đp�[<�F�Lt��չa/g�rj�   VsB��®�FA        ��;d�?���@�U0A  �?g�B�s.®�FAE�B��®�FA   >*�Dq��4!*JT� b�Y̞*Z��c�M� ʘ�����ޞ�2��r`<\�{�E   rB�Z� �A"�����c�Q?��?��MA�_�@���@�B>v.ª�nA�B�q����A�   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��B�	ªʇA        %4?n�5?ŏ�>)�@?���@{B��©�fA�}B����A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��B��ªʇA        %4?n�5?ŏ�>)�@?���@4{B�m©�fA	~B#i���A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   ��B*ªʇA        %4?n�5?ŏ�>)�@?���@�zB;�©�fA�}B�����A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   #aB�"ªʇA        
x���?ď�>'�@?���@�B;J$©�fA��BfG!���A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   j�B8�ªʇA        
x���?ď�>'�@?���@YBbJ©�fA�B�G���A4   >*�Dq��4!*JT� b��]f�	�U���.~^Z<��}$uJ�q�NeȊq�`�1��   �KB*t,ªʇA        
x���?ď�>'�@?���@��BT�-©�fAX�B~�*���A4   >*�Dq��4!*JT� b��n�	.Ȇ��m�0X��h\�M�(
�"��'��Oױ�ܵ/�%�*�,V�V   	�x�B����Hp�A�F�.��>�}N?�Ⱦ���?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	�7�B����Hp�A~L5>���>�eR?\��>���?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	`�Bh��Hp�A|��>��%>��>g�U?���?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	���B���Hp�Ae��>�`	��;����Z?���?��7?
�Uu�Av�B�����A�  >*�Dq��4!*JT� b�@JF�������
�"��'��Oױ�ܵ/�%�*�,V�V   	�A�B��Hp�A�y�>'ߠ�c#�b�!?���?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	�7�Be�Hp�A)�s>y�>��A?�	�>���?��7?
�Uu�A��B8\���A�  >*�Dq��4!*JT� b�@JF�������
�"��'��Oױ�ܵ/�%�*�,V�V   	��B�3�Hp�A�5�>Ĵ->_
�"��'��Oױ�ܵ/�%�*�,V�V   	���B$y4�Hp�A�J�>7�u>�>|�@?���?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	�4�BTr'�Hp�A�z^��S�>3�G?�{ᾫ��?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	�4�Ba�8�Hp�A���>�0/�����ݸS?���?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	��B�L!�Hp�A��>1m�>�Y[?o��>���?��7?h�?#ݐB߯%���Ar�B�\�A�   >*�Dq��4!*JT� b��ߪݏ�s���!��%Vj�##$�H쟒�L�vt�G����   	��B�	!�w̍A�T
�"��'��Oױ�ܵ/�%�*�,V�V   	α�B��3�Hp�AlCA����>�O?��þ���?��7?h�?�1�B��7���Ai�B �0�A�   >*�Dq��4!*JT� b��ߪݏ�s���!��%Vj�##$�H쟒�L�vt�G����   	���B�\3�w̍A Q?({~>�
�"��'��Oױ�ܵ/�%�*�,V�V   	��B �D�Hp�A��>솾���=j8?���?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	���B%eE�Hp�A9��>ӽ���}�r�e?���?��7?
�"��'��Oױ�ܵ/�%�*�,V�V   	��B�]3�Hp�AW��<#C�>wQe?�0=���?��7?h�?~��B�87���A�p�B{'1�A�   >*�Dq��4!*JT� b��ߪݏ�s���!��%Vj�##$�H쟒�L�vt�G����   	�$�B�
3�w̍Ax�?Yͼn
,��P?n��?��+@�j�?�b�B��7�Uu�A�¥Bu�0���A�  >*�Dq��4!*JT� b����2�T��[��Y�xr��(;�{p9DC}�\ə�   ��MB�m.@��RA        ��d�?UUu?UUu?PUu@LB�@�?4A��OB�[M@R�qA   >*�Dq��4!*JT� b����2�T��[��Y�xr��(;�{p9DC}�\ə�   ��MB�����RA        ��d�?UUu?UUu?PUu@ҡKB9k��?4A�OBs���R�qA   >*�Dq��4!*JT� b����2�T��[��Y�xr��(;�{p9DC}�\ə�   �mLBQ>����RA        ��d�?UUu?UUu?PUu@�~JB���?4A�\NB�`��R�qA   >*�Dq��4!*JT� b����2�T��[��Y�xr��(;�{p9DC}�\ə�   
V©ʂA   >*�Dq��4!*JT� b����2�T��[��Y�xr��(;�{p9DC}�\ə�   .�B7�&¨�\A        ��d�?UUu?UUu?���@��B�(��?4A�ںBW�$©ʂA   >*�Dq��4!*JT� c ���2�T��[��Y�xr��(;�{p9DC}�\ə�   _�B5�����\A        ��d�?UUu?UUu?���@��B�����?4A�	�Bu���ʂA   >*�Dq��4!*JT� c���2�T��[��Y�xr��(;�{p9DC}�\ə�   �B�B	����\A        ��d�?UUu?UUu?���@hK�B����?4AH:�BQ+���ʂA   >*�Dq��4!*JT� c���2�T��[��Y�xr��(;�{p9DC}�\ə�   G�B/���RA        ��d�?UUu?UUu?PUu@g�B��
��?4A'�!B^���R�qA   >*�Dq��4!*JT� c���2�T��[��Y�xr��(;�{p9DC}�\ə�   <sB�s����RA        ��d�?UUu?UUu?PUu@\�BKQ���?4Ab B˕��R�qA   >*�Dq��4!*JT� c���2�T��[��Y�xr��(;�{p9DC}�\ə�   �B����RA        ��d�?UUu?UUu?PUu@�#B�����?4A� BZ3��R�qA   >*�Dq��4!*JT� c���2�T��[��Y�xr��(;�{p9DC}�\ə�    	BY�#©�RA        ��d�?UUu?UUu?PUu@ B9�%��?4A��By�!�R�qA   >*�Dq��4!*JT� c���2�T��[��Y�xr��(;�{p9DC}�\ə�   �BʩT©�RA        ��d�?UUu?UUu?PUu@�,B��V��?4A�
B�R�R�qA   >*�Dq��4!*JT� c���2�T��[��Y�xr��(;�{p9DC}�\ə�   n7 B�	@��RA        ��d�?UUu?UUu?PUu@�HB<~�?�?4AN&"B�(@R�qA   >*�Dq��4!*JT� dt��:�ڢ�%��w�@\oP{|Ža�"�x�����D�<�wc�Q�   ���B����S�7A.�j-z`
��(��(�<mrb��O�t����JR� ��}��G   ��VB�!ATu�A        	�;��?�IAxA��AD�=Bs|�@��vA�oB9�lASu�A   >H�,CC��K��/�K  ���@E}7(gou�iK��Q�'O�t����JR� ��}��G   o�>B� ��Tu�A        A_z<Y�?�4�A��qB��AҏB܊\ª�vA��{B8�@Su�A4   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�   ]&�B�!$¯*��              �?UUu?UUu?TUA1�BN&��)���B�6"�lU��   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �3GB� #¯*��              �?UUu?UUu?TUA+IEB9�$��)��IB�!�lU��   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �<B�3S¯*��              �?UUu?UUu?TUA�:BDU��)�D�=B�HQ�lU��   ?��k�O�O�u��nA �,���2�T��[��Y�xr��(;�{p9DC}�\ə�   4uBz�S¯*��              �?UUu?UUu?TUA�1sB$�U��)��wB��Q�lU��   ?��k�O�O�u��nA �T���2�T��[��Y�xr��(;�{p9DC}�\ə�   �b�B�T¯*��              �?UUu?UUu?TUA�m�B1�U��)�>X�B�R�lU��   ?��k�O�O�u��nA �|���2�T��[��Y�xr��(;�{p9DC}�\ə�    �BE�T¯*��              �?UUu?UUu?TUA�*�B�mV��)�p�B��R�lU��   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�   2�GB/����*��              �?UUu?UUu?TUA��EB�p���)��~IB����lU��   ?��k�O�O�u��nA ����2�T��[��Y�xr��(;�{p9DC}�\ə�   �U�B=����*��              �?UUu?UUu?TUA3`�B�����)��J�B����lU��   ?��k�O�O�u��nA �.���2�T��[��Y�xr��(;�{p9DC}�\ə�   �V�BX����*��              �?UUu?UUu?TUA6a�B�����)��K�B��lU��   ?��k�O�O�u��nA �V���2�T��[��Y�xr��(;�{p9DC}�\ə�   ��B
���*��              �?UUu?UUu?TUA���B_Ɯ��)�Y|�B���lU��   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�    ��B�͗��*��              �?UUu?UUu?TUA���BD����)�U{�B����lU��   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�   "�GBᮖ��*��              �?UUu?UUu?TUAx
FB6����)���IB�ْ�lU��   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�   VHBJ
���*��              �?UUu?UUu?TUAhkFB�/��)��@JB����lU��   ?��k�O�O�u��nA �)���2�T��[��Y�xr��(;�{p9DC}�\ə�   x��B�����*��              �?UUu?UUu?TUA#��B�m��)�ͫ�B,1��lU��   ?��k�O�O�u��nA �H���2�T��[��Y�xr��(;�{p9DC}�\ə�   |��Bv	��*��              �?UUu?UUu?TUA&¤B!�	��)�Ѭ�B����lU��   ?��k�O�O�u��nA �u���2�T��[��Y�xr��(;�{p9DC}�\ə�   �BV9@�*��              �?UUu?UUu?TUA��Br�@�)�nݦB� X@lU��   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �B�nB@�*��              �?UUu?UUu?TUA��BJ�#@�)�k܅B�a@lU��   ?��k�O�O�u��nA �����2�T��[��Y�xr��(;�{p9DC}�\ə�   M�HBcgK@�*��              �?UUu?UUu?TUA��FB��,@�)���JBj@lU��   @|)��H���� �� N���RL֜cK��r|i��Y+$O�t����JR� ��}��G   F3¥�A��A        
�ż��?d�AB�pA   A,�A���(@UՅ@�Ƒ�Mo�A��bA4   @|)��H���� �� N�oxĝkw�����;l�e^O�t����JR� ��}��G   �U�A��A        �̼��?a
*��=ܩyL�܀   j�������<\q���:        ��?  �@�K�?@k�@j��5"��XՀ�j���̃���@�   @��a�NM��B%�]�b $a���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   j����7��XՄ�              �?  �@VU�?  �>j�������XՈ�j���5"��XՀ�   @��a�NM��B%�]�b $a�G%r|V��n5�W�J�Kv�����u	���B1������   j����W��nUq��E�        ��?UUm@LmM?Զ@�[��5҄�[Ut�������IU�?  @��a�NM��B%�]�b $b!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   j����2���28@�q��        �c?UU�@^_X?�Q�?����܆���@�[���W�¥�c@$   @��a�NM��B%�]�b $gr��A }e]��枚<�{�*���
*��=ܩyL�܀   �$���<\q���:        ��?  �@�K�?@k�@�T,�5"��XՀ�����̃���@�   @��a�NM��B%�]�b $g���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �$7��XՄ�              �?  �@VU�?  �>�-���XՈ���5"��XՀ�   @��a�NM��B%�]�b $g�G%r|V��n5�W�J�Kv�����u	���B1������   �$W��nUq��E�        ��?UUm@LmM?Զ@M+�5҄�[Ut�����IU�?  @��a�NM��B%�]�b $h!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �$��2���28@�q��        �c?UU�@^_X?�Q�?�)/��܆���@M�W�¥�c@$   @��a�NM��B%�]�b $lr��A }e]��枚<�{�*���
*��=ܩyL�܀   �`���<\q���:        ��?  �@�K�?@k�@%i�5"��XՀ��X��̃���@�   @��a�NM��B%�]�b $l���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �`7��XՄ�              �?  �@VU�?  �>�i���XՈ��W�5"��XՀ�   @��a�NM��B%�]�b $l�G%r|V��n5�W�J�Kv�����u	���B1������   �`W��nUq��E�        ��?UUm@LmM?Զ@�Oh�5҄�[Ut�rzY��IU�?  @��a�NM��B%�]�b $m!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �`��2���28@�q��        �c?UU�@^_X?�Q�?r�k��܆���@��UW�¥�c@$   @��a�NM��B%�]�b $qr��A }e]��枚<�{�*���
*��=ܩyL�܀   }�����<\q���:        ��?  �@�K�?@k�@}��5"��XՀ�}����̃���@�   @��a�NM��B%�]�b $q���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   }��7��XՄ�              �?  �@VU�?  �>}A����XՈ�}A��5"��XՀ�   @��a�NM��B%�]�b $q�G%r|V��n5�W�J�Kv�����u	���B1������   }��W��nUq��E�        ��?UUm@LmM?Զ@�v��5҄�[Ut�'���IU�?  @��a�NM��B%�]�b $r!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   }����2���28@�q��        �c?UU�@^_X?�Q�?'L���܆���@�6�W�¥�c@$   @��a�NM��B%�]�b $vr��A }e]��枚<�{�*���
*��=ܩyL�܀   �#����<\q���:        ��?  �@�K�?@k�@�C��5"��XՀ�����̃���@�   @��a�NM��B%�]�b $v���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �#�7��XՄ�              �?  �@VU�?  �>������XՈ�����5"��XՀ�   @��a�NM��B%�]�b $v�G%r|V��n5�W�J�Kv�����u	���B1������   �#�W��nUq��E�        ��?UUm@LmM?Զ@�ذ�5҄�[Ut�=n���IU�?  @��a�NM��B%�]�b $w!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �#���2���28@�q��        �c?UU�@^_X?�Q�?=����܆���@蘧W�¥�c@$   @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   �����<�$A*A������?���&  �@�K�?@k�@����¨*�@�Ü�5����?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ��7�¨*�@          �?���&  �@VU�?  �>�c��5��¨*�@�c���̃¨*�@   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   ��W�©�$A��$�E=��?���&UUm@LmM?Զ@蘤�༅�R��@=.��5�©�RA  @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   ������<�$A*A������?���&  �@�K�?@k�@�����¨*�@0�|�5����?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���7�¨*�@          �?���&  �@VU�?  �>���5��¨*�@0|��̃¨*�@   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   ���W�©�$A��$�E=��?���&UUm@LmM?Զ@�D��༅�R��@��}�5�©�RA  @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   b^H���<�$A*A������?���&  �@�K�?@k�@b�P��¨*�@b@�5����?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   b^H7�¨*�@          �?���&  �@VU�?  �>b^Q�5��¨*�@b^?��̃¨*�@   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   b^HW�©�$A��$�E=��?���&UUm@LmM?Զ@�O�༅�R��@��@�5�©�RA  @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   �����<�$A*A������?���&  �@�K�?@k�@����¨*�@�U�5����?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ��7�¨*�@          �?���&  �@VU�?  �>���5��¨*�@����̃¨*�@   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   ��W�©�$A��$�E=��?���&UUm@LmM?Զ@X �༅�R��@+�5�©�RA  @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   j�������<�$A*A������?���&  �@�K�?@k�@j�����¨*�@j��5����?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   j����7�¨*�@          �?���&  �@VU�?  �>j���5��¨*�@j����̃¨*�@   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   j����W�©�$A��$�E=��?���&UUm@LmM?Զ@�[��༅�R��@���5�©�RA  @��a�NM��B%�]�b $���F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   ����2�µbA�]%�q�=�c?�b�&UU�@^_X?�Q�?=n���l���?VA�X��©�lA$   @��a�NM��B%�]�b $���F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   �����2�µbA�]%�q�=�c?�b�&UU�@^_X?�Q�?C���l���?VA�	z�©�lA$   @��a�NM��B%�]�b $���F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   b^H��2�µbA�]%�q�=�c?�b�&UU�@^_X?�Q�?�sS��l���?VA
*��=ܩyL�܀   j�������<�$A��:        ��?  �@�K�?@k�@j��5"�¨*�@j���̃��?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   j����7�¨*�@              �?  �@VU�?  �>j������¨*�@j���5"�¨*�@   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   j����W�©�$A�E�        ��?UUm@LmM?Զ@�[��5҄�R��@�����©�RA  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   j����2�µbA�q��        �c?UU�@^_X?�Q�?����܆��?VA�[���W�©�lA$   @��a�NM��B%�]�b $�r��A }e]��枚<�{�*���
*��=ܩyL�܀   �$���<�$A��:        ��?  �@�K�?@k�@�T,�5"�¨*�@����̃��?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �$7�¨*�@              �?  �@VU�?  �>�-��¨*�@��5"�¨*�@   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   �$W�©�$A�E�        ��?UUm@LmM?Զ@M+�༅�R��@���5�©�RA  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �$��2�µbA�q��        �c?UU�@^_X?�Q�?�)/��܆��?VAM�W�©�lA$   @��a�NM��B%�]�b $�r��A }e]��枚<�{�*���
*��=ܩyL�܀   �`���<�$A��:        ��?  �@�K�?@k�@%i�5"�¨*�@�X��̃��?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �`7�¨*�@              �?  �@VU�?  �>�i��¨*�@�W�5"�¨*�@   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   �`W�©�$A�E�        ��?UUm@LmM?Զ@�Oh�༅�R��@rzY�5�©�RA  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �`��2�µbA�q��        �c?UU�@^_X?�Q�?r�k��܆��?VA��UW�©�lA$   @��a�NM��B%�]�b $�r��A }e]��枚<�{�*���
*��=ܩyL�܀   }�����<�$A��:        ��?  �@�K�?@k�@}��5"�¨*�@}����̃��?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   }��7�¨*�@              �?  �@VU�?  �>}A���¨*�@}A��5"�¨*�@   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   }��W�©�$A�E�        ��?UUm@LmM?Զ@�v��༅�R��@'��5�©�RA  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   }����2�µbA�q��        �c?UU�@^_X?�Q�?'L���܆��?VA�6�W�©�lA$   @��a�NM��B%�]�b $�r��A }e]��枚<�{�*���
*��=ܩyL�܀   �#����<�$A��:        ��?  �@�K�?@k�@�C��5"�¨*�@����̃��?VA�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �#�7�¨*�@              �?  �@VU�?  �>�����¨*�@����5"�¨*�@   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   �#�W�©�$A�E�        ��?UUm@LmM?Զ@�ذ�༅�R��@=n��5�©�RA  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �#���2�µbA�q��        �c?UU�@^_X?�Q�?=����܆��?VA蘧W�©�lA$   @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   �����u�A*A������?���&  �@�K�?@k�@����ªʓA�Ü�5�����A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ��7�ªʒA          �?���&  �@VU�?  �>�c��5��ªʑA�c���̃ªʓA   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   ��W��Uu�A��$�E=��?���&UUm@LmM?Զ@蘤�5҄�Uu�A=.���Uu�A  @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   ������u�A*A������?���&  �@�K�?@k�@�����ªʓA0�|�5�����A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���7�ªʒA          �?���&  �@VU�?  �>���5��ªʑA0|��̃ªʓA   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   ���W��Uu�A��$�E=��?���&UUm@LmM?Զ@�D��5҄�Uu�A��}��Uu�A  @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   b^H���u�A*A������?���&  �@�K�?@k�@b�P��ªʓAb@�5�����A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   b^H7�ªʒA          �?���&  �@VU�?  �>b^Q�5��ªʑAb^?��̃ªʓA   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   b^HW��Uu�A��$�E=��?���&UUm@LmM?Զ@�O�༅�Uu�A��@�5��Uu�A  @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   �����u�A*A������?���&  �@�K�?@k�@����ªʓA�U�5�����A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ��7�ªʒA          �?���&  �@VU�?  �>���5��ªʑA����̃ªʓA   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   ��W��Uu�A��$�E=��?���&UUm@LmM?Զ@X �༅�Uu�A+�5��Uu�A  @��a�NM��B%�]�b $�u6��0wX՘��/���)�����
*��=ܩyL�܀   j�������u�A*A������?���&  �@�K�?@k�@j�����ªʓAj��5�����A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   j����7�ªʒA          �?���&  �@VU�?  �>j���5��ªʑAj����̃ªʓA   @��a�NM��B%�]�b $��5��|p�#^��E^�h�Mq���u	���B1������   j����W��Uu�A��$�E=��?���&UUm@LmM?Զ@�[��༅�Uu�A���5��Uu�A  @��a�NM��B%�]�b $���F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   ����2��Z�A�]%�q�=�c?�b�&UU�@^_X?�Q�?=n���l����A�X���Uu�A$   @��a�NM��B%�]�b $���F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   �����2��Z�A�]%�q�=�c?�b�&UU�@^_X?�Q�?C���l����A�	z��Uu�A$   @��a�NM��B%�]�b $���F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   b^H��2��Z�A�]%�q�=�c?�b�&UU�@^_X?�Q�?�sS��l����A
*��=ܩyL�܀   j�������u�A��:        ��?  �@�K�?@k�@j��5"�ªʓAj���̃���A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   j����7�ªʒA              �?  �@VU�?  �>j���5��ªʑAj����̃ªʓA   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   j����W��Uu�A�E�        ��?UUm@LmM?Զ@�[��5҄�Uu�A������Uu�A  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   j����2��Z�A�q��        �c?UU�@^_X?�Q�?����܆���A�[���W��Uu�A$   @��a�NM��B%�]�b $�r��A }e]��枚<�{�*���
*��=ܩyL�܀   �$���u�A��:        ��?  �@�K�?@k�@�T,�5"�ªʓA����̃���A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �$7�ªʒA              �?  �@VU�?  �>�-�5��ªʑA���̃ªʓA   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   �$W��Uu�A�E�        ��?UUm@LmM?Զ@M+�5҄�Uu�A����Uu�A  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �$��2��Z�A�q��        �c?UU�@^_X?�Q�?�)/��܆���AM�W��Uu�A$   @��a�NM��B%�]�b $�r��A }e]��枚<�{�*���
*��=ܩyL�܀   �`���u�A��:        ��?  �@�K�?@k�@%i�5"�ªʓA�X��̃���A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �`7�ªʒA              �?  �@VU�?  �>�i��ªʑA�W�5"�ªʓA   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   �`W��Uu�A�E�        ��?UUm@LmM?Զ@�Oh�5҄�Uu�ArzY��Uu�A  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �`��2��Z�A�q��        �c?UU�@^_X?�Q�?r�k��܆���A��UW��Uu�A$   @��a�NM��B%�]�b $�r��A }e]��枚<�{�*���
*��=ܩyL�܀   }�����u�A��:        ��?  �@�K�?@k�@}��5"�ªʓA}����̃���A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   }��7�ªʒA              �?  �@VU�?  �>}A��5��ªʑA}A���̃ªʓA   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   }��W��Uu�A�E�        ��?UUm@LmM?Զ@�v��༅�Uu�A'��5��Uu�A  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   }����2��Z�A�q��        �c?UU�@^_X?�Q�?'L���܆���A�6�W��Uu�A$   @��a�NM��B%�]�b $�r��A }e]��枚<�{�*���
*��=ܩyL�܀   �#����u�A��:        ��?  �@�K�?@k�@�C��5"�ªʓA����̃���A�   @��a�NM��B%�]�b $����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �#�7�ªʒA              �?  �@VU�?  �>����5��ªʑA�����̃ªʓA   @��a�NM��B%�]�b $��G%r|V��n5�W�J�Kv�����u	���B1������   �#�W��Uu�A�E�        ��?UUm@LmM?Զ@�ذ�༅�Uu�A=n��5��Uu�A  @��a�NM��B%�]�b $�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   �#���2��Z�A�q��        �c?UU�@^_X?�Q�?=����܆���A蘧W��Uu�A$   BW� �C�� ɗ�� �����r�5��|�ے�#�OwN�f�(i�mk�UR�2��   	<�� ��ٖA�=�<zJ?�ȴѾ{i?�^@���@��@�J� G����vA�L6�(N_�Uu�A0   BW� �C�� ɗ�� ֙i,K�)g�ڌ�6�m��õ�}$uJ�q�NeȊq�`�1��   	U$8� I��U�A��^>���#�ž��d?���@�+�@�2A�d��q����vA�O���^����At   BW� �C�� ɗ�� ֔�YW:����O�f��@�^*������5/���&9����   	�J������A "�m:���  �?��?���=  �)�J� G����A�J�u�����A   BW� �C�� ɗ�� &P�
E�����]6�X
.?�d�wN�f�(i�mk�UR�2��   	�g?�+���&�A���;0 ���2��P?�+@Fѹ@��@�J�u�����vA�L6�|G��Uu�A0   BW� �C�� ɗ�� &�� ؖ����
��.>ݳ�}$uJ�q�NeȊq�`�1��   	��9��ˠ����A�IJ?�?
B   B����DK��>|q� ɡ���f07L6���	���aN�1
B   B����DK��>|q� ɢ�fnS�������w��?^��ɬ�@MQ��
x>�Pr$   ���A�=z��zB        �x�o�?� ?�B`@��2@��A���V�
B�3�A�=^� B   B����DK��>|q� ɣ���k~c?s���秙����?^��ɬ�@MQ��
x>�Pr$   MȴA�~���zBJ�v���?Ř�2ÇA�UǕ>�`@��2@�2�A6t��V�
B�]�A`w�� B   B����DK��>|q� ɦ���f07L6���	���aN�1
x>�Pr$   ���A�=z��?YA        �x�o�?� ?�B`@��2@��A�����BA�3�A�=^�R�oA   B����DK��>|q� ɩ���k~c?s���秙����?^��ɬ�@MQ��
x>�Pr$   MȴA�~���?YAJ�v���?���2kA�UǕ>�`@��2@�2�A6t����BA�]�A`w��R�oA   B����DK��>|q� ɬ���f07L6���	���aN�1
x>�Pr$   ���A�=z���@        �x�o�?� ?�B`@��2@��A�����n?�3�A�=^�JUn@   B����DK��>|q� ɯ���k~c?s���秙����?^��ɬ�@MQ��
x>�Pr$   MȴA�~����@J�v���? ��2PlA�UǕ>�`@��2@�2�A6t����n?�]�A`w��JUn@   Cp��E��G���fH ��f����s?{��<�2�����
*��=ܩyL�܀   ����i�Q�kL��A^:�A^��5��5?TU]@Xu@���@�U���X«���=��¾�J����   Cp��E��G���fH �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0��i�Q«���        �5��5?TUu@UU)@  �>�����Y«���=��¾7J«���   Cp��E��G���fH ���YB�n�������Fҫԕ��u	���B1������   ����i�Q¬jL��6��6<9�4�:�4?��B@�D�>��@���¾�W���������K�V�  Cp��E��G���fH ��f����s?{��<�2�����
*��=ܩyL�܀   ���¾G>�kL��A^:�A^��5��5?TU]@Xu@���@�U��i2E«���=���]7����   Cp��E��G���fH �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0�¾G>«���        �5��5?TUu@UU)@  �>����i�E«���=����6«���   Cp��E��G���fH ���YB�n�������Fҫԕ��u	���B1������   ���¾G>¬jL��6��6<9�4�:�4?��B@�D�>��@����]D��������i28�V�  Cp��E��G���fH ��H$�6X,�g��}��{����e���C�'�a�8�~.�   �3��?�Q�%��5?�5�[�;d� ����@��?#v�?�p����Z�������H���   Cp��E��G���fH �d5�AN�?��X�fr��E)!�3:�,9�I��<�cr   =3��X�Q��a�Iɝ��a��m�?Z�2���?���@�7�?�p��i"Z�������i�I­*��$   Cp��E��G���fH �o�0�u�>#�ќ17��L�O
���� ����Wq�ڒz	�Sֶ�H�א�� �s�gtQ�#�e;$,�   ����j�@���
B�:iJ5?3�4?���|�@��Apc�B=+��wTi«:�=���	��B�*��5  D����rH���
���� �� 
�jbpaS7� .4��:�={[�=`O�L ����tIj����   ����]�@�����;��I���?c&o��@wN�B"��A=+��wTi«:�=���	��B�*��m  D����rH���
���� �P�.�2=��~늴�6�|aj�J�i�s�u���x���f|�   �e��U�J�Z%��  �?����H�*r!a���*>��@�@-A����H�X«��=;��H�<�/լ�p  D����rH���
���� �Pә�<����Y{����;𡓕��u	���B1������   �e��H�J�%����2  �?b�{��������< �@A)A=k��H5X«:`��H5=��ԭ�) D����rH���
���� �Q�<��l�r5CLx���CP>fh��/�	OR�$�Zuqq'3�   ���H�J«ʱ��%
���  �?��2��>TUA���@=+���_^� �����
7�Vu���   D����rH���
���� �QK�L:�Mg_��I��f)�
�����Ij��~��|@*����,   ���H�J¾ѣ���2  �?�CJ��Mh���>���?x�@=+����N�%.�����°�F�Vu��   D�J���AV�';7�� 	'�
����� V�.��z�U����}$uJ�q�NeȊq�`�1��   !K��/.G«�±�0?��0?x2>x2> �*>WQ�@Q��@;P���G� p!�+ק���F�V��   D��!�BG�w��6j: 
���f07L6���	��䬣}$uJ�q�NeȊq�`�1��   ���/.D�V��              �?��*>���@   ?�����S�V��;P���4�V��   D�W>#N�\T�$Ê 	rFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��� �IB��A              �?
?  �?]�|�K�HB��A1�=���JB��A   D�W>#N�\T�$Ê 	�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   V±�B��A              �?GB�j
?  �?]�|��lB��A<V���B��A   D�W>#N�\T�$Ê 	�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ./�A��A              �?�]KB�j
?  �?o�����A��A<V�<.�A��A   D�W>#N�\T�$Ê 	�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ~���OjA��A              �?�b�A�j
?  �?y|���eA��A,Y�o�nA��A   D�W>#N�\T�$Ê 	�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   T1�QTJ@��A              �?
?  �?[�}��9@��A6�Z���[@��A   D�W>#N�\T�$Ê 	�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ���"9���A              �?
?  �?�~�w�	���A�V\��� ���A   D�W>#N�\T�$Ê 	�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ���GX����A              �?
?  �?�~�����A�V\��.����A   F��jA�����+�� j�/��F�ƒ�%�q��nm�^�א�� �s�gtQ�#�e;$,�   _�S �µ��N�Ѻ�~��O5�j5?�}@��B�h�A�h���l�«:�4NS��̃«*��B  F��jA�����+�� j���e|!�I���Lx���v{[�=`O�L ����tIj����   ^�Sº�¸��%fö��?���`-���B'+@s(�A�h���l�«:�4NS��̃«*��~  F�a��A]��)I��� #��狸�+��P��N,�x{[�=`O�L ����tIj����   �$A.&� ��A        ��K>�z?�2�?��?��4A���@��L���vA,MA�q����A   F�a��A]��)I��� #A�fX?I��-߹�V2\� �{[�=`O�L ����tIj����   w������ ��A        ���v:v?j��?��?��4A���K����vA�n��������A   G'A�_DS��[M�:s� ���t��H�Հy�E,����|-%���
*��=ܩyL�܀   �h��52��kL�    �(����?    UU]@Yu@���@�ݰ��«���C���̃����   G'A�_DS��[M�:s� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �h��5r�«���          �?    UUu@VU)@  �>�=��«���C����̃«���   G'A�_DS��[M�:s� ��"�O���S�VŶ뽠��S?�j���u	���B1������   �h��5�¬jL�    QĀ<��?    ��B@�D�>��@Cs�g������]���V�  G1Pc��@`��8@l�$� bl�Cj΅���l�lq��f���հ�"�� �����i��Vil   67�KXA��4�              �?XU�?:t�BUUA�nD�N���VEH���)�L�EB p!�   G1Pc��@`��8@l�$� cK橻��y��+���������\հ�"�� �����i��Vil   �3:��f����4��5?�5?#�G�#�G�PU�?��@n�A��J�� �VEH���)�N�����!�   G�%��G����9K� '�h��:�<jE��G��b�f>�}$uJ�q�NeȊq�`�1��    �;Bh�B� B��;�>�=�~?�[1;,��>LA�@�>B�Tª��A�8B��0ª:B|   G�%��G����9K� '�|��+�~Bg�J�Ԃ^~U����u	���B1������    �(B6�B��RBG��<���;����=�?πY>�A!��@\�B�9T���A��B<�1� �B   G�<�Hҩ�;1��� :�L�^�Y�a_J7.���Ob���@jjᆵ6���k�q)���   #��AN�IB*����o���`���?���&UU)A��@�
AΧ�AL�FB�:�<)BQ?MB����   G�<�Hҩ�;1��� >���f07L6���	��䬹@jjᆵ6���k�q)���   ���@��FBVu��          �?v�&  A��*>  A�|\?L�FB�:���A�4GBVu��   H/����C��.�i�ɝ� �K���f07L6���	����0����$P�����L��m�   ^0��,�+©�xA        �5��5?m��@��*>  �>	ۻ�C�4©�vA����o"©�zA   H/����C��.�i�ɝ� �����2�T��[��Y�x{[�=`O�L ����tIj����   p|����V�U5�A              �? A�U�>  �@p����Wª�vA��[�pV�U��A   H/����C��.�i�ɝ� �%���2�T��[��Y�x�}�9�H
1ћfb��   ������VªʖA        �5��5?��?���=���@	ۻ���X©�vA^0����T���A   H/����C��.�i�ɝ� �N���2�T��[��Y�x�}�9�H
1ћfb��   ^����^ªʖA        �5?�5?��:@��*=���@	ۻ�q�d©�vA������X���A   H/����C��.�i�ɝ� �N&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   ^����dc�Uu�A        �5?�5?���=���>  @?^0����d�Uu�A^0��.md�Uu�A   H/����C��.�i�ɝ� �y���f07L6���	����0����$P�����L��m�   ^0���m©�xA        �5��5?�~�@��*>  �>	ۻ���u©�vA����:e©�zA   H/����C��.�i�ɝ� ����2�T��[��Y�x�}�9�H
1ћfb��   ^���qOªʖA        �5��5?��:@��*=���@^0����T©�vA	ۻ�:I���A   H/����C��.�i�ɝ� �Vz��������A�����2��0����$P�����L��m�   ^����dJ�Uu�A        �5��5?���=���>  @?����]\I�Uu�A����I�Uu�A   H/����C��.�i�ɝ� �����f07L6���	����0����$P�����L��m�   ^0����~©�xA        �5��5?�ӂ@��*>  �>	ۻ��w�©�vA������v©�zA   H/����C��.�i�ɝ� �O���f07L6���	����0����$P�����L��m�   ^0���?©�xA        �5��5?,�@��*>  �>	ۻ�p�H©�vA�����5©�zA   H/����C��.�i�ɝ� �P���f07L6���	��䬕��u	���B1������   ���,�+��X�A        �5��5?m��@���=��@	[��C�4�T�}A^���o"��A  H/����C��.�i�ɝ� �Q���f07L6���	��䬕��u	���B1������   ����?��X�A        �5��5?,�@���=��@	[��p�H�T�}A^����5��A  H/����C��.�i�ɝ� �U���f07L6���	��䬕��u	���B1������   ����m��X�A        �5��5?�~�@���=��@	[����u�T�}A^���:e��A  H/����C��.�i�ɝ� �V���f07L6���	��䬕��u	���B1������   �����~��X�A        �5��5?�ӂ@���=��@	[���w��T�}A^�����v��A  H�;h�]I�v,=;�z �>zhTx#�����D�73��w��{[�=`O�L ����tIj����   ��A�Y� �        q�;:�?�^7>��-? `�BMbA��Z� p!��$AFDX� PB   H�;h�]I�v,=;�z �{�������*�`9S��Ex�A{[�=`O�L ����tIj����   ��A������A�\�;��?��s7fw6��,>k3?�\B �A6�������JA��� PBH   H�;h�]I�v,=;�z ��.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   �A3��JU�?        =�;�?�4>}?UňBk!A��«:��Aݐ� PB   H�;h�]I�v,=;�z ��8�*��`�W����,KGU}X{[�=`O�L ����tIj����   �AU�JU�?        h�;�?�4>e?UňB>�Amj��:��qA�?� PB   H�;h�]I�v,=;�z ��.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   S�A��@@JU�?        h�;�?�4>e?UňB�JANf0@�:­A�Q@ PB   H�;h�]I�v,=;�z ��.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   |?A�hAJU�?        G�;�?��4>`?UňB"�A��dA�:�֝A=�lA PB   H�;h�]I�v,=;�z ��.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   8�AtU�AJU�?        G�;�?��4>`?UňB�vA�J�A�:3A`�A PB   H�;h�]I�v,=;�z ��.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   �jA�BJU�?        =�;�?�4>}?UňB�AeB�:�N�AB PB   H�;h�]I�v,=;�z �.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   � A:DBJU�?        =�;�?�4>}?UňBW�A�CB�:�
_ A�EB PB   H�;h�]I�v,=;�z �,.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   ��A�[Z� �        ��;�?a�4>}? `�BR�A*a[� p!¬_�AVY� PB   H�;h�]I�v,=;�z �L.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   �A7ß�JU�?        p�;�?]�4>m?UňB�a�A�͡��:�F��A���� PB   H�;h�]I�v,=;�z �_.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   ���AU�JU�?        ~�;�?]�4>e?UňB�,�Amj��:�$��A�?� PB   H�;h�]I�v,=;�z �{.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   զ�A��@@JU�?        ~�;�?]�4>e?UňB���ANf0@�:�V�A�Q@ PB   H�;h�]I�v,=;�z ��zhTx#�����D�73��w��{[�=`O�L ����tIj����   +s�A>�iAJU�?        H�;:�?v^7>��-?UňB���A�dA�:��#�A��nA PB   H�;h�]I�v,=;�z ��.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   �<�AtU�AJU�?        ��;�?^�4>]?UňBd��A�J�A�:¾��A`�A PB   H�;h�]I�v,=;�z ��.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   o�A�*BJU�?        T�;�?]�4>}?UňBBX�Ae%B�:��A0B PB   H� +�FE��2�]2� v�K�J�-쏱�Q}6'To�O�t����JR� ��}��G   @VA�N2«���        tz>�?x?��eB~�hB�j�A�#J��w�� p!�
^�� �Bҋ�ҋ��5?�5?�&A�j
?VU�?���?h����B�}��T��U�B�  J-��
���`� �B񜖵𜖵�5?�5?��+A�j
?cU�?��[����B�}�x2�U�B�  J-��
�H%� �B�赵�赵�5?�5?��+A�j
?fU�?������B�}��n2@U�B�  J-��
#Q8�J��'xþ��Q��3�ޒ�8�����ġ���   �
�g��@ �B�u2�u2�5?�5?'�@�j
?UU�?��§9b@��B�}�� AU�B  J-��
�|!�A �B?�"�>�"��5?�5?O8�A�j
?WU�?��ª
,A��B�}¤=�AU�B�  J-��
���B �B`��3�85x��  �?�j
?�[AeU�?����6�A��B�}�u�BU�Bm  J-��
��0B �B���2  �?na4�T"4�j
?��@AqU�?��� �B��B�}�� HBU�B�  J-��
�yfB �B  �?���Mf��^<�4�j
?$�ZA�U�?���vKB��B�}�_�BU�B�  J-��
���<4?�5?�A�j
?VU�?���@h����B;#��T��U�B�  J-��
?[U�??F[����B��u2�U�B�  J-��
?eU�?�����B�X�o2@U�B�  J-��
?eU�?�{9b@��B|���UdAU�B�  J-��
?eU�?��nHpA��B3����AU�B�  J-��
?eU�?7��:�A��B�(�u�BU�B�  J-��
?t�@AsU�?{1��B��B���� HBU�B�  J-��
?�iZAbU�?���uKB��B��ހBU�B�  J-��
?ZU�?a�}� VcA��B��o���kAU�B�  J-��
?���A�U�?�)l«dcA��B����nAU�B 
*��=ܩyL�܀   ���UT�u�A��f���f��5?�5?���@�K�?@k�@�����\ªʓA=���L���A�   J=�[�OM
*��=ܩyL�܀   ����;�u�A��f���f��5?�5?���@�K�?@k�@���DªʓA�`���3���A�   J=�[�OM
*��=ܩyL�܀   ��¼O�u�A��f���f��5?�5?���@�K�?@k�@��¼�!ªʓA�`�¼���A�   J=�[�OM
*��=ܩyL�܀   ��¼� �u�A��f���f��5?�5?���@�K�?@k�@��¼	ªʓA�`��w����A�   J=�[�OM
*��=ܩyL�܀   ���o���u�A��f���f��5?�5?���@�K�?@k�@���o���ʓA�`��o����A�   J=�[�OM
*��=ܩyL�܀   ���o���u�A��f���f��5?�5?���@�K�?@k�@����o���ʓA=����&n���A�   J=�[�OM
*��=ܩyL�܀   ��¼-��u�A��f���f��5?�5?���@�K�?@k�@�������ʓA=��½-����A�   J=�[�OM
*��=ܩyL�܀   ����ȿu�A��f���f��5?�5?���@�K�?@k�@����y[h��ʓA=���8$�>��A�   J=�[�OM
*��=ܩyL�܀   �����@u�A��f���f��5?�5?���@�K�?@k�@������@�ʓA=���A��A�   J=�[�OM
*��=ܩyL�܀   ���\Au�A��f���f��5?�5?���@�K�?@k�@����;A�ʓA=���}A��A�   J=�[�OM
*��=ܩyL�܀   ����s�Au�A��f���f��5?�5?���@�K�?@k�@������A�ʓA=������A��A�   J=�[�OM
*��=ܩyL�܀   ����s�Au�A��f���f��5?�5?���@�K�?@k�@�������A�ʓA=������A��A�   J=�[�OM
*��=ܩyL�܀   �����Bu�A��f���f��5?�5?���@�K�?@k�@�����B�ʓA=����'"B��A�   J=�[�OM
*��=ܩyL�܀   ����g2Bu�A��f���f��5?�5?���@�K�?@k�@�����'*B�ʓA=����:B��A�   J=�[�OM
*��=ܩyL�܀   ���VBu�A��f���f��5?�5?���@�K�?@k�@���jNB�ʓA=���^B��A�   J=�[�OM
*��=ܩyL�܀   ��*oBu�A��f���f��5?�5?���@�K�?@k�@����fB�ʓA=��jwB��A�   J=�[�OM
��.zkp��_���O�t����JR� ��}��G   ���B���A        ����y?ϓ!B��cB   A=��5A���A�S��^c�BV�BL   L8���HѾ\��cQ� F��5-��+�c����d|6�O�t����JR� ��}��G   �������A���A              �?��$AXU�@   AI��$7�A���A�S��=�BV�B   L8���HѾ\��cQ� F^���k��?E�#��h�s�O�t����JR� ��}��G   �����pB���A              �?��$A   A   AI���pB���A�S���p$BV�B   L8���HѾ\��cQ� F������
�sR�`xW�q�4d���O)���O�t����JR� ��}��G   }H���\bB���A        ?%�:�?cd0A:��A   A�H��af<B���A�S��^c�BV�B    L8���HѾ\��cQ� F�J#0Ź�pB�̸Rr��qx�O�t����JR� ��}��G   �e����A���A        u#=�?R�DA��A   A�S��nRY?���A�S����AV�B    NR�\O�IL�x׌�6� �*FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   ���A*Y� �        ����  �?	�?��*> `�BS
�AVY� p!�r
-x���{[�=`O�L ����tIj����   ���A��mAJU�?        �ĸ  �?���?��*>UňB� �A=DlA�:�nB��nA PB   NR�\O�IL�x׌�6� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   �M�A>�bAJU�?        _T��  �?/ȱ?�*>UňB���A�naA�:�nB�dA PB   NR�\O�IL�x׌�6� �����f07L6���	���{[�=`O�L ����tIj����   �B�.hAJU�?              �?��*>��?UňBa�B�dA�:�nB=DlA PB   NR�\O�IL�x׌�6� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   Z B�
�AJU�?        ���  �?	�?��*>UňBe��A`�A�:�{�Bu��A PB   NR�\O�IL�x׌�6� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   ] B��AJU�?        _T��  �?/ȱ?�*>UňBs��Au��A�:�{�B�J�A PB   NR�\O�IL�x׌�6� �����f07L6���	���{[�=`O�L ����tIj����   &~BtU�AJU�?              �?��*>��?UňB�(B�J�A�:�{�B`�A PB   NR�\O�IL�x׌�6� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   �t Be�BJU�?        [���  �?	�?��*>UňBCa�A0B�:��8B��B PB   NR�\O�IL�x׌�6� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   �q B�BJU�?        �T��  �?/ȱ?��*>UňBQU�A�zB�:��8Be%B PB   NR�\O�IL�x׌�6� �����f07L6���	���{[�=`O�L ����tIj����   ��B�*BJU�?              �?��*>��?UňB?�Be%B�:��8B0B PB   NR�\O�IL�x׌�6� �ښ��O8r?�"���bp#�{[�=`O�L ����tIj����   �~�a�BZY�?U5?�5�G=:V'=�H�*>��?�ƈB��7�0B�:�s孿��B PB   NR�\O�IL�x׌�6� �ۗDq�Ҷy"�>�O/3�=��1{[�=`O�L ����tIj����   ў���BJU�?        K Ը  �?�s�?��*>UňB��!��[B�:�s孿eB PB   NR�\O�IL�x׌�6� �ݐ��f07L6���	���{[�=`O�L ����tIj����   ���:BJU�?              �?��*>�j
?UňB�:ÿeB�:�s孿0B PB   NR�\O�IL�x׌�6� ����ׅA2�w�T�HkZ��{[�=`O�L ����tIj����   �D2�Vh�AJU�?        ������?ι?+>UňB�7����A�:�(w-��A PB   NR�\O�IL�x׌�6� ����ׅA2�w�T�HkZ��{[�=`O�L ����tIj����   �S2���AJU�?        ����?�?�+>UňB�07�W��A�:�(w-��=�A PB   NR�\O�IL�x׌�6� ��f07L6���	���{[�=`O�L ����tIj����   ~�.����AJU�?              �?��*>  0?UňB�!0��=�A�:�(w-����A PB   NR�\O�IL�x׌�6� ���ׅA2�w�T�HkZ��{[�=`O�L ����tIj����   ��3�W3oAJU�?        
Bs>�?�O�t����JR� ��}��G   ��AB�q@Vu��        a9�<��?w�@B�պB   A��J���+«:pB�4GBVu���  R
6� O�t����JR� ��}��G   �\B,%AVu��        ��;��?�ZqA�� A   A��=B3��@�:*zB��dAVu��   R
�Ae�*>���?�A�?��?VA^�B� �R�oA   R��� LM���<�;�9 	HP�Hb�/����jG��
��7o��'��O(�!�[2{[�=`O�L ����tIj����   �)��nA��bA        Й��  �?�G�A�*>���?�8�=�lA�?VA��%A�joAR�oA   R��� LM���<�;�9 	H��7o��'��O(�!�[2{[�=`O�L ����tIj����   �(�>�bA��bA        ����  �?IA�Ay�*>���?�8��naA�?VA��#A�dAR�oA   R��� LM���<�;�9 	Hl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   v�A�nA��bA        _���  �?>�A�*>���?��%A=�lA�?VA<�B�joAR�oA   R��� LM���<�;�9 	H
�A��bA        Te��  �?~ӱA�*>���?a7�`�A�?VA��,Au��AR�oA   R��� LM���<�;�9 	Hl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ��ξb�A��bA        >���  �?���Ak�*>���?V-7�u��A�?VA�=*A��AR�oA   R��� LM���<�;�9 	Hl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   Q"�A�
�A��bA        p۷�  �?��A�*>���?��,A`�A�?VA��Bu��AR�oA   R��� LM���<�;�9 	Hl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ܆�Ab�A��bA        ~Q��  �?�ϰAj�*>���?�=*Au��A�?VAm�B��AR�oA   R��� LM���<�;�9 	H&M�_(���m(!Np?�>�{[�=`O�L ����tIj����   ����e�B��bA        Fp��  �?ȱ�Aޭ*>���?�~5�0B�?VA��%A��BR�oA   R��� LM���<�;�9 	H&M�_(���m(!Np?�>�{[�=`O�L ����tIj����   ����B��bA        ����  �?���A�*>���?��5��[B�?VA��#AeBR�oA   R��� LM���<�;�9 	H��7o��'��O(�!�[2{[�=`O�L ����tIj����   TܬAe�B��bA        r���  �?�ӳAۭ*>���?��%A0B�?VAcB��BR�oA   R��� LM���<�;�9 	H��7o��'��O(�!�[2{[�=`O�L ����tIj����   �L�A�B��bA        �`��  �?�ٴAԮ*>���?��#A�[B�?VA�\BeBR�oA   R��� LM���<�;�9 	H�iukc.�~�|�W��X	�[�{[�=`O�L ����tIj����   ��|��N[¨�bA              �? j�A �*>���?�4;�F�[��?VAG�A��Z�R�oA   R��� LM���<�;�9 	Ha���ƹ���h���C�!�{[�=`O�L ����tIj����   �ɢA�=[©�bA              �?���A �*>���?G�AF�[��?VAU��A��Z�R�oA   R��� LM���<�;�9 	H�Cj΅���l�lq��f���{[�=`O�L ����tIj����   ��L´Y�B��bA              �?X��A �*>���?o��
/�B�?VAa
A �*>���?
eB��bA        ���  �?8��A|�*>���?
/�B�?VA.�F�_��BR�oA   R��� LM���<�;�9 	H,Y���E�D��J�~7�ʝ�3{[�=`O�L ����tIj����   c^�B��bA        �m	�  �?�A��*>���?���ĀB�?VA�;��5�BR�oA   R��� LM���<�;�9 	H-k$�49%vϸkv�Y��<{[�=`O�L ����tIj����   ~{�Z�gB��bA        m�K�  �?��@��*>���?�����gB�?VA^zA��3hBR�oA   R��� LM���<�;�9 	H.Ь����b�[�b]��� `WU{[�=`O�L ����tIj����   b���
eB��bA        ؓ	�  �?�H�A԰*>���?�°�dB�?VA>D�Z_eBR�oA   R��� LM���<�;�9 	H/Ь����b�[�b]��� `WU{[�=`O�L ����tIj����   6��K	KB��bA        �	�  �?�H�Aհ*>���?8����JB�?VA_#E��^KBR�oA   R��� LM���<�;�9 	H0��Y^u+>��'�x��mT{[�=`O�L ����tIj����   yd���4HB��bA        `�  �?���A�*>���?!� �GB�?VAaO�K�HBR�oA   R��� LM���<�;�9 	H1��Y^u+>��'�x��mT{[�=`O�L ����tIj����   k9����B��bA        a�  �?���A�*>���?��B�?VAF�P�2ABR�oA   R��� LM���<�;�9 	H2��Y^u+>��'�x��mT{[�=`O�L ����tIj����   Y`���B��bA        �3�  �?w��A�*>���?K)�2�B�?VA;�P��lBR�oA   R��� LM���<�;�9 	H3��Y^u+>��'�x��mT{[�=`O�L ����tIj����   ������A��bA        /4�  �?w��Ap�*>���?{��<.�A�?VA�XR����AR�oA   R��� LM���<�;�9 	H4��Y^u+>��'�x��mT{[�=`O�L ����tIj����   5+��<0�A��bA        �d�  �?x��A�*>���?����A�?VA�qR����AR�oA   R��� LM���<�;�9 	H5��Y^u+>��'�x��mT{[�=`O�L ����tIj����   K�����oA��bA        �d�  �?x��A�*>���?���o�nA�?VA�S�MqAR�oA   R��� LM���<�;�9 	H6��Y^u+>��'�x��mT{[�=`O�L ����tIj����   ����p�dA��bA        H@�  �?x��Ar�*>���?��QcA�?VAT���eAR�oA   R��� LM���<�;�9 	H7� -.kLJ�|x�]yH�{[�=`O�L ����tIj����   ��·�tB��bA        �a�;d�?�@�>o��@���?�V°3hB�?VAMt��ĀBR�oA   R��� LM���<�;�9 	H8�H��H�"Un5�c�܊n�E#�{[�=`O�L ����tIj����   K}�i0B��bA        u2�;d�?[\�>,z>A���?"�2AB�?VAu� �GBR�oA   R��� LM���<�;�9 	H9NT��T��[�+����ӡ��{[�=`O�L ����tIj����   ����A��bA        �6�;d�?L�>�*A���?���A�?VA�~�2�BR�oA   R��� LM���<�;�9 	H:+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   +h��A��bA        �6�;d�?�>�)A���?K��MqA�?VA���AR�oA   R��� LM���<�;�9 	H;��v�R8��G�����
{[�=`O�L ����tIj����   0���
^��  �?:��A+�*>���?
��{[�=`O�L ����tIj����   ǻL¦�3@��bA         t��  �?��AF�*>���?
��{[�=`O�L ����tIj����   �kL�� ����bA        ����  �?�-�AD�*>���?Y�|��� ��?VA���Dv��R�oA   R��� LM���<�;�9 	H@v� TW�߂G��'�/
��{[�=`O�L ����tIj����   oL���
���bA        ����  �?!�AR�*>���?Y�|�"7��?VA���w�	�R�oA   R��� LM���<�;�9 	HAt/���$0�x0"��Ht<Ys{[�=`O�L ����tIj����   ��L�����bA�5?�5?�iL9��M9��*>e�AI\�?Y�|.���?VA�E�Fٚ�R�oA"   R��� LM���<�;�9 	HB!�)�a����/|��Ss�{[�=`O�L ����tIj����   ��L,����bA�5?�5?q]�85W�8d�*>��A+9�?Y�|�Fס��?VA�����R�oA    R��� LM���<�;�9 	HC@���E0��H��X�h;��{[�=`O�L ����tIj����   u�������bA�5?�5�@֪�{�8��*>�O�A�f�?�.���?VA��Y�Fٚ�R�oA$   R��� LM���<�;�9 	HD@���E0��H��X�h;��{[�=`O�L ����tIj����   ����,����bA�5?�5�$���`��8��*>�O�A�f�?�#�Fס��?VA��Y���R�oA$   R��� LM���<�;�9 	HE��Y^u+>��'�x��mT{[�=`O�L ����tIj����   ����� ����bA        �  �?��A��*>���?�
���bA        J�  �? O�A��*>���?���"7��?VA1\X�w�	�R�oA    R��� LM���<�;�9 	HG��Y^u+>��'�x��mT{[�=`O�L ����tIj����   0	����`@��bA        S'�  �?��A��*>���?`�¦�[@�?VA@�U�PLf@R�oA   R��� LM���<�;�9 	HH��Y^u+>��'�x��mT{[�=`O�L ����tIj����   �����3@��bA        *�  �?��A��*>���?���P\.@�?VA5�U��9@R�oA   R��� LM���<�;�9 	HI��
)A���?Պ�����?VA���P\.@R�oA   R��� LM���<�;�9 	HN��tݖ���5�2��B�A{[�=`O�L ����tIj����   J^C��	XB��bA        [�;d�?:0�>�`�@���?@)E���JB�?VAS�A�Z_eBR�oA   R��� LM���<�;�9 	HO�H��H�"Un5�c�܊n�E#�{[�=`O�L ����tIj����   �FQ�i0B��bA        J2�;d�?k\�>,z>A���?�mS�2AB�?VABO���GBR�oA   R��� LM���<�;�9 	HPNT��T��[�+����ӡ��{[�=`O�L ����tIj����   ��R���A��bA        97�;d�?��>�*A���?�U����A�?VA�P�2�BR�oA   R��� LM���<�;�9 	HQ+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   R�T��A��bA        W7�;d�?o�>�)A���?ИV�MqA�?VA�wR����AR�oA   R��� LM���<�;�9 	HR+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   sV�rA��bA        �6�;d�?/�>�)A���?�-X�PLf@�?VA�T�QcAR�oA   R��� LM���<�;�9 	HSܾ����.*���/��!<�{[�=`O�L ����tIj����   ��W�H%���bA        P7�;d�?���>@�)A���?@�Y�Dv���?VA�U�P\.@R�oA   R��� LM���<�;�9 	HT�[�"���=n�sp`E�a��
�{[�=`O�L ����tIj����   GrZ���`���bA7�;b�?�:��)6��*>0�)A�1�?|�\�Fٚ��?VAbX�"7�R�oA   R��� LM���<�;�9 	HU`�����']��]Vs�oa�{[�=`O�L ����tIj����   �[�C	����bA        h>�;d�?fb�>��A���?e�]�?;���?VA��Y�Fס�R�oA   R��� LM���<�;�9 	HV;����� ���ކu�p�#a�4{[�=`O�L ����tIj����   ��}�=F%���bA)9          �? �*>]�)A��?
/�BR�oA   R��� LM���<�;�9 	H^��=O��X@L��cy�{[�=`O�L ����tIj����   [D���;B��bA              �? �*>�R}A���?o�¯�B�?VA���U:[BR�oA   R��� LM���<�;�9 	H_��=O��X@L��cy�{[�=`O�L ����tIj����   [D����@��bA              �? �*>1�@���?o��p�a@�?VA���4�1AR�oA   R��� LM���<�;�9 	H`��=O��X@L��cy�{[�=`O�L ����tIj����   [D�¼H�A��bA              �? �*>D�A���?o��4�1A�?VA��¯�BR�oA   R��� LM���<�;�9 	Ha��=O��X@L��cy�{[�=`O�L ����tIj����   ��l�E]
A��qR���Y{[�=`O�L ����tIj����   "M�����bA              �?TU�A �*>���?Y�|�?;���?VA�L�����R�oA   R��� LM���<�;�9 	Hj~PB1��q�cf�R�}N N{[�=`O�L ����tIj����   Q@��������bA�5?�5?�	������*>��A�h�?q��?;���?VA��]�����R�oA   R��� LM���<�;�9 	Hk9��?���Q��AB�Z�{[�=`O�L ����tIj����   
]B�
7�;d�?�3�>;*A���?,+M�PLf@�?VA	I��cAR�oA   R��� LM���<�;�9 	H~E�xO0��:�EB~�C|E�y9j{[�=`O�L ����tIj����   �I�5�A��bA        7�;d�?�3�>;*A���?
�K�MqA�?VA�sG����AR�oA   R��� LM���<�;�9 	HE�xO0��:�EB~�C|E�y9j{[�=`O�L ����tIj����   ��G��A��bA        �6�;d�?�3�>
B�r
?  �?�4>�6����?VA�d�A����?VA   R��� LM���<�;�9 	H��H :5��<�#�(� S�'{[�=`O�L ����tIj����   ��A��+��?VA        {Np�  �?AZ+B��?  �?d�=�p-��?VAU��A��*��?VA   R��� LM���<�;�9 	H��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   �`�@7���?VA        ��5  �?�	Bs
?  �?��>�����?VA��A�����?VA   R��� LM���<�;�9 	H��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   ��@���?VA        o��5  �?pB�r
?  �?1�=�m���?VAj��A�?��?VA   R��� LM���<�;�9 	H��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�A��A@�?VA        ѷ�  �?��+B�l
?  �?�1<�Nf0@�?VA2�A� S@�?VA   R��� LM���<�;�9 	H��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�A�lhA�?VA        ѷ�  �?��+B�l
?  �?�1<��dA�?VA2�A=�lA�?VA   R��� LM���<�;�9 	H��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�At6�A�?VA        ѷ�  �?��+B�l
?  �?�1<���A�?VA2�A`�A�?VA   R��� LM���<�;�9 	H���Ð|z鶷�q�Qc�|�4g{[�=`O�L ����tIj����   s�A�B�?VA        *9��  �?��+B?p
?  �?�q7��B�?VA8a�Aq-B�?VA   R��� LM���<�;�9 	H�/!>0ϫk
?  �?�3��CB�?VA�4�A�0EB�?VA   R��� LM���<�;�9 	H�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��� �IB�?VA              �?
?  �?]�|�K�HB�?VA1�=���JB�?VA   R��� LM���<�;�9 	H�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   V±�B�?VA              �?GB�j
?  �?]�|��lB�?VA<V���B�?VA   R��� LM���<�;�9 	H�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ./�A�?VA              �?�]KB�j
?  �?o�����A�?VA<V�<.�A�?VA   R��� LM���<�;�9 	H�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ~���OjA�?VA              �?�b�A�j
?  �?y|���eA�?VA,Y�o�nA�?VA   R��� LM���<�;�9 	H�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   T1�QTJ@�?VA              �?
?  �?[�}��9@�?VA6�Z���[@�?VA   R��� LM���<�;�9 	H�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ���"9��?VA              �?
?  �?�~�w�	��?VA�V\��� ��?VA   R��� LM���<�;�9 	H�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ���GX���?VA              �?
?  �?�~����?VA�V\��.���?VA   R��� LM���<�;�9 	H��`���Ö|�1����sK�x�v{[�=`O�L ����tIj����   áN�S�hA�?VA        f<��~�?��A[�o?  �?o��_�bA�?VAye�G�nA�?VA   R��� LM���<�;�9 	I Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��m�DLA�?VA              �?�j
?��*A  �?�o¦�[@�?VA��l��aA�?VA   R��� LM���<�;�9 	IFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   u�u�S&A�?VA              �? �W@�j
?  �?]�|���!A�?VA�o¨d*A�?VA   R��� LM���<�;�9 	I�i�߱�����1��,,kr<{[�=`O�L ����tIj����   ����?9����bA              �?SF�A��*>���?q�������?VA�\�����R�oA   R��� LM���<�;�9 	I
?  �?�~����?VA	���?;���?VA   R��� LM���<�;�9 	I
۪,=�G�����<ߡ%�#.{[�=`O�L ����tIj����   �E�!�uB�?VA        :��?5�KB���@  �?-}��gB�?VA~�E�
/�B�?VA   R��� LM���<�;�9 	I2�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   R~�/tfB�?VA        ^1��  �?v�NBm
?  �?
�Ae�*>���?�A�?���@^�B� �JUn@   R��� LM���<�;�9 	M2P�Hb�/����jG��
�A��;@        Te��  �?~ӱA�*>���?a7�`�A��@��,Au��AJUn@   R��� LM���<�;�9 	M<l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ��ξb�A��;@        >���  �?���Ak�*>���?V-7�u��A��@�=*A��AJUn@   R��� LM���<�;�9 	M=l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   Q"�A�
�A��;@        p۷�  �?��A�*>���?��,A`�A��@��Bu��AJUn@   R��� LM���<�;�9 	M>l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ܆�Ab�A��;@        ~Q��  �?�ϰAj�*>���?�=*Au��A��@m�B��AJUn@   R��� LM���<�;�9 	M?&M�_(���m(!Np?�>�{[�=`O�L ����tIj����   ����e�B��;@        Fp��  �?ȱ�Aޭ*>���?�~5�0B��@��%A��BJUn@   R��� LM���<�;�9 	M@&M�_(���m(!Np?�>�{[�=`O�L ����tIj����   ����B��;@        ����  �?���A�*>���?��5��[B��@��#AeBJUn@   R��� LM���<�;�9 	MAl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   TܬAe�B��;@        r���  �?�ӳAۭ*>���?��%A0B��@cB��BJUn@   R��� LM���<�;�9 	MBl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   �L�A�B��;@        �`��  �?�ٴAԮ*>���?��#A�[B��@�\BeBJUn@   R��� LM���<�;�9 	MC�iukc.�~�|�W��X	�[�{[�=`O�L ����tIj����   ��|��N[¢�;@              �? j�A �*>���?�4;�F�[���@G�A��Z�JUn@   R��� LM���<�;�9 	MDa���ƹ���h���C�!�{[�=`O�L ����tIj����   �ɢA�=[¢�;@              �?���A �*>���?G�AF�[���@U��A��Z�JUn@   R��� LM���<�;�9 	ME�Cj΅���l�lq��f���{[�=`O�L ����tIj����   ��L´Y�B��;@              �?X��A �*>���?o��
/�B��@a
A �*>���?
eB��;@        ���  �?8��A|�*>���?
/�B��@.�F�_��BJUn@   R��� LM���<�;�9 	MYY���E�D��J�~7�ʝ�3{[�=`O�L ����tIj����   c^�B��;@        �m	�  �?�A��*>���?���ĀB��@�;��5�BJUn@   R��� LM���<�;�9 	MZk$�49%vϸkv�Y��<{[�=`O�L ����tIj����   ~{�Z�gB��;@        m�K�  �?��@��*>���?�����gB��@^zA��3hBJUn@   R��� LM���<�;�9 	M[Ь����b�[�b]��� `WU{[�=`O�L ����tIj����   b���
eB��;@        ؓ	�  �?�H�A԰*>���?�°�dB��@>D�Z_eBJUn@   R��� LM���<�;�9 	M\Ь����b�[�b]��� `WU{[�=`O�L ����tIj����   6��K	KB��;@        �	�  �?�H�Aհ*>���?8����JB��@_#E��^KBJUn@   R��� LM���<�;�9 	M]��Y^u+>��'�x��mT{[�=`O�L ����tIj����   yd���4HB��;@        `�  �?���A�*>���?!� �GB��@aO�K�HBJUn@   R��� LM���<�;�9 	M^��Y^u+>��'�x��mT{[�=`O�L ����tIj����   k9����B��;@        a�  �?���A�*>���?��B��@F�P�2ABJUn@   R��� LM���<�;�9 	M_��Y^u+>��'�x��mT{[�=`O�L ����tIj����   Y`���B��;@        �3�  �?w��A�*>���?K)�2�B��@;�P��lBJUn@   R��� LM���<�;�9 	M`��Y^u+>��'�x��mT{[�=`O�L ����tIj����   ������A��;@        /4�  �?w��Ap�*>���?{��<.�A��@�XR����AJUn@   R��� LM���<�;�9 	Ma��Y^u+>��'�x��mT{[�=`O�L ����tIj����   5+��<0�A��;@        �d�  �?x��A�*>���?����A��@�qR����AJUn@   R��� LM���<�;�9 	Mb��Y^u+>��'�x��mT{[�=`O�L ����tIj����   K�����oA��;@        �d�  �?x��A�*>���?���o�nA��@�S�MqAJUn@   R��� LM���<�;�9 	Mc��Y^u+>��'�x��mT{[�=`O�L ����tIj����   ����p�dA��;@        H@�  �?x��Ar�*>���?��QcA��@T���eAJUn@   R��� LM���<�;�9 	Md� -.kLJ�|x�]yH�{[�=`O�L ����tIj����   ��·�tB��;@        �a�;d�?�@�>o��@���?�V°3hB��@Mt��ĀBJUn@   R��� LM���<�;�9 	Me�H��H�"Un5�c�܊n�E#�{[�=`O�L ����tIj����   K}�i0B��;@        u2�;d�?[\�>,z>A���?"�2AB��@u� �GBJUn@   R��� LM���<�;�9 	MfNT��T��[�+����ӡ��{[�=`O�L ����tIj����   ����A��;@        �6�;d�?L�>�*A���?���A��@�~�2�BJUn@   R��� LM���<�;�9 	Mg+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   +h��A��;@        �6�;d�?�>�)A���?K��MqA��@���AJUn@   R��� LM���<�;�9 	Mh��v�R8��G�����
{[�=`O�L ����tIj����   0���
^��  �?:��A+�*>���?
��{[�=`O�L ����tIj����   ǻL¦�3@��;@         t��  �?��AF�*>���?
��{[�=`O�L ����tIj����   �kL�� ����;@        ����  �?�-�AD�*>���?Y�|��� ���@���Dv��JUn@   R��� LM���<�;�9 	MmX��_�����հP��� �{[�=`O�L ����tIj����   oL���
�Ȭ;@�5?�5?\��99V�9��*>r#�AF��?Y�|�"7���@���w�	�JUn@   R��� LM���<�;�9 	Mnt/���$0�x0"��Ht<Ys{[�=`O�L ����tIj����   ��L���̫;@�5?�5?�iL9��M9��*>e�AI\�?Y�|.����@�E�Fٚ�JUn@"   R��� LM���<�;�9 	Mo!�)�a����/|��Ss�{[�=`O�L ����tIj����   ��L,��ª;@�5?�5?q]�85W�8d�*>��A+9�?Y�|�Fס���@�����JUn@    R��� LM���<�;�9 	Mp@���E0��H��X�h;��{[�=`O�L ����tIj����   u�������;@�5?�5�@֪�{�8��*>�O�A�f�?�.����@��Y�Fٚ�JUn@$   R��� LM���<�;�9 	Mq@���E0��H��X�h;��{[�=`O�L ����tIj����   ����,����;@�5?�5�$���`��8��*>�O�A�f�?�#�Fס���@��Y���JUn@$   R��� LM���<�;�9 	Mr��Y^u+>��'�x��mT{[�=`O�L ����tIj����   ����� ����;@        �  �?��A��*>���?�
���;@        J�  �? O�A��*>���?���"7���@1\X�w�	�JUn@    R��� LM���<�;�9 	Mt��Y^u+>��'�x��mT{[�=`O�L ����tIj����   0	����`@��;@        S'�  �?��A��*>���?`�¦�[@��@@�U�PLf@JUn@   R��� LM���<�;�9 	Mu��Y^u+>��'�x��mT{[�=`O�L ����tIj����   �����3@��;@        *�  �?��A��*>���?���P\.@��@5�U��9@JUn@   R��� LM���<�;�9 	Mv��
)A���?Պ������@���P\.@JUn@   R��� LM���<�;�9 	M{��tݖ���5�2��B�A{[�=`O�L ����tIj����   J^C��	XB��;@        [�;d�?:0�>�`�@���?@)E���JB��@S�A�Z_eBJUn@   R��� LM���<�;�9 	M|�H��H�"Un5�c�܊n�E#�{[�=`O�L ����tIj����   �FQ�i0B��;@        J2�;d�?k\�>,z>A���?�mS�2AB��@BO���GBJUn@   R��� LM���<�;�9 	M}NT��T��[�+����ӡ��{[�=`O�L ����tIj����   ��R���A��;@        97�;d�?��>�*A���?�U����A��@�P�2�BJUn@   R��� LM���<�;�9 	M~+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   R�T��A��;@        W7�;d�?o�>�)A���?ИV�MqA��@�wR����AJUn@   R��� LM���<�;�9 	M+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   sV�rA��;@        �6�;d�?/�>�)A���?�-X�PLf@��@�T�QcAJUn@   R��� LM���<�;�9 	M�ܾ����.*���/��!<�{[�=`O�L ����tIj����   ��W�H%���;@        P7�;d�?���>@�)A���?@�Y�Dv����@�U�P\.@JUn@   R��� LM���<�;�9 	M��[�"���=n�sp`E�a��
�{[�=`O�L ����tIj����   GrZ���`���;@7�;b�?�:��)6��*>0�)A�1�?|�\�Fٚ���@bX�"7�JUn@   R��� LM���<�;�9 	M�`�����']��]Vs�oa�{[�=`O�L ����tIj����   �[�C	����;@        h>�;d�?fb�>��A���?e�]�?;����@��Y�Fס�JUn@   R��� LM���<�;�9 	M�;����� ���ކu�p�#a�4{[�=`O�L ����tIj����   ��}�=F%���;@)9          �? �*>]�)A��?
/�BJUn@   R��� LM���<�;�9 	M���=O��X@L��cy�{[�=`O�L ����tIj����   [D���;B��;@              �? �*>�R}A���?o�¯�B��@���U:[BJUn@   R��� LM���<�;�9 	M���=O��X@L��cy�{[�=`O�L ����tIj����   [D����@��;@              �? �*>1�@���?o��p�a@��@���4�1AJUn@   R��� LM���<�;�9 	M���=O��X@L��cy�{[�=`O�L ����tIj����   [D�¼H�A��;@              �? �*>D�A���?o��4�1A��@��¯�BJUn@   R��� LM���<�;�9 	M���=O��X@L��cy�{[�=`O�L ����tIj����   ��l�E]
A��qR���Y{[�=`O�L ����tIj����   "M�����;@              �?TU�A �*>���?Y�|�?;����@�L�����JUn@   R��� LM���<�;�9 	M�~PB1��q�cf�R�}N N{[�=`O�L ����tIj����   Q@��������;@�5?�5?�	������*>��A�h�?q��?;����@��]�����JUn@   R��� LM���<�;�9 	M�9��?���Q��AB�Z�{[�=`O�L ����tIj����   
]B�
7�;d�?�3�>;*A���?,+M�PLf@��@	I��cAJUn@   R��� LM���<�;�9 	M�E�xO0��:�EB~�C|E�y9j{[�=`O�L ����tIj����   �I�5�A��;@        7�;d�?�3�>;*A���?
�K�MqA��@�sG����AJUn@   R��� LM���<�;�9 	M�E�xO0��:�EB~�C|E�y9j{[�=`O�L ����tIj����   ��G��A��;@        �6�;d�?�3�>
B�r
?  �?�4>�6�����@�d�A�����@   R��� LM���<�;�9 	M��H :5��<�#�(� S�'{[�=`O�L ����tIj����   ��A��+���@        {Np�  �?AZ+B��?  �?d�=�p-���@U��A��*���@   R��� LM���<�;�9 	M��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   �`�@7����@        ��5  �?�	Bs
?  �?��>������@��A������@   R��� LM���<�;�9 	M��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   ��@����@        o��5  �?pB�r
?  �?1�=�m����@j��A�?���@   R��� LM���<�;�9 	M��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�A��A@��@        ѷ�  �?��+B�l
?  �?�1<�Nf0@��@2�A� S@��@   R��� LM���<�;�9 	M��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�A�lhA��@        ѷ�  �?��+B�l
?  �?�1<��dA��@2�A=�lA��@   R��� LM���<�;�9 	M��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�At6�A��@        ѷ�  �?��+B�l
?  �?�1<���A��@2�A`�A��@   R��� LM���<�;�9 	M囨Ð|z鶷�q�Qc�|�4g{[�=`O�L ����tIj����   s�A�B��@        *9��  �?��+B?p
?  �?�q7��B��@8a�Aq-B��@   R��� LM���<�;�9 	M�/!>0ϫk
?  �?�3��CB��@�4�A�0EB��@   R��� LM���<�;�9 	M�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��� �IB��@              �?
?  �?]�|�K�HB��@1�=���JB��@   R��� LM���<�;�9 	M�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   V±�B��@              �?GB�j
?  �?]�|��lB��@<V���B��@   R��� LM���<�;�9 	NFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ./�A��@              �?�]KB�j
?  �?o�����A��@<V�<.�A��@   R��� LM���<�;�9 	N
Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ~���OjA��@              �?�b�A�j
?  �?y|���eA��@,Y�o�nA��@   R��� LM���<�;�9 	NFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   T1�QTJ@��@              �?
?  �?[�}��9@��@6�Z���[@��@   R��� LM���<�;�9 	NFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ���"9���@              �?
?  �?�~�w�	���@�V\��� ���@   R��� LM���<�;�9 	NFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ���GX����@              �?
?  �?�~�����@�V\��.����@   R��� LM���<�;�9 	N&�`���Ö|�1����sK�x�v{[�=`O�L ����tIj����   áN�S�hA��@        f<��~�?��A[�o?  �?o��_�bA��@ye�G�nA��@   R��� LM���<�;�9 	N-Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��m�DLA��@              �?�j
?��*A  �?�o¦�[@��@��l��aA��@   R��� LM���<�;�9 	N4Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   u�u�S&A��@              �? �W@�j
?  �?]�|���!A��@�o¨d*A��@   R��� LM���<�;�9 	N9�i�߱�����1��,,kr<{[�=`O�L ����tIj����   ����?9����;@              �?SF�A��*>���?q��������@�\�����JUn@   R��� LM���<�;�9 	N:�i�߱�����1��,,kr<{[�=`O�L ����tIj����   "M�?9����;@              �?TU�A��*>���?Y�|�������@�L���JUn@   R��� LM���<�;�9 	N=Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   Z=��d����@              �?� B�j
?  �?�~�����@	���?;����@   R��� LM���<�;�9 	ND
۪,=�G�����<ߡ%�#.{[�=`O�L ����tIj����   �E�!�uB��@        :��?5�KB���@  �?-}��gB��@~�E�
/�B��@   R��� LM���<�;�9 	N_�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   R~�/tfB��@        ^1��  �?v�NBm
?  �?
�*>-�A��?�A��� PB�B�J��V�B   R��� LM���<�;�9 	SYXvط�h�a(;p�,xN �?{[�=`O�L ����tIj����   R��A����zB�5?�5���7lDʷv�*>���AT��?>�A�H�� PBB� B6���V�B   R��� LM���<�;�9 	SZ���f07L6���	���{[�=`O�L ����tIj����   �Y��
�A�zB        Ue��  �?~ӱA�*>���?a7�`�A PB��,Au��AV�B   R��� LM���<�;�9 	Skl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ��ξb�A�zB        @���  �?���Ak�*>���?V-7�u��A PB�=*A��AV�B   R��� LM���<�;�9 	Sll$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   Q"�A�
�A�zB        r۷�  �?��A�*>���?��,A`�A PB��Bu��AV�B   R��� LM���<�;�9 	Sml$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ܆�Ab�A�zB        �Q��  �?�ϰAj�*>���?�=*Au��A PBm�B��AV�B   R��� LM���<�;�9 	SnuC)������9��v�����{[�=`O�L ����tIj����   ����e�B�zB�5?�5��B 8^ ��*>"��A���?�~5�0B PB��%A��BV�B   R��� LM���<�;�9 	So���r+�ko��(X=H��O�{[�=`O�L ����tIj����   ����B�zB�5?�5��+8kG��*>嫬A���?��5��[B PB��#AeBV�B   R��� LM���<�;�9 	Spl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   TܬAe�B�zB        s���  �?�ӳAڭ*>���?��%A0B PBcB��BV�B   R��� LM���<�;�9 	Sql$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   �L�A�B�zB        �`��  �?�ٴAԮ*>���?��#A�[B PB�\BeBV�B   R��� LM���<�;�9 	Sr�iukc.�~�|�W��X	�[�{[�=`O�L ����tIj����   ��|��N[«zB              �? j�A �*>���?�4;�F�[� PBG�A��Z�V�B   R��� LM���<�;�9 	Ssa���ƹ���h���C�!�{[�=`O�L ����tIj����   �ɢA�=[«zB              �?���A �*>���?G�AF�[� PBU��A��Z�V�B   R��� LM���<�;�9 	St�Cj΅���l�lq��f���{[�=`O�L ����tIj����   ��L´Y�B�zB              �?X��A �*>���?o��
/�B PBa
A �*>���?
eB�zB        ���  �?8��A|�*>���?
/�B PB.�F�_��BV�B   R��� LM���<�;�9 	S�Y���E�D��J�~7�ʝ�3{[�=`O�L ����tIj����   c^�B�zB        �m	�  �?�A��*>���?���ĀB PB�;��5�BV�B   R��� LM���<�;�9 	S�k$�49%vϸkv�Y��<{[�=`O�L ����tIj����   ~{�Z�gB�zB        o�K�  �?��@��*>���?�����gB PB^zA��3hBV�B   R��� LM���<�;�9 	S�Ь����b�[�b]��� `WU{[�=`O�L ����tIj����   b���
eB�zB        ٓ	�  �?�H�A԰*>���?�°�dB PB>D�Z_eBV�B   R��� LM���<�;�9 	S�Ь����b�[�b]��� `WU{[�=`O�L ����tIj����   6��K	KB�zB        ��	�  �?�H�Aְ*>���?8����JB PB_#E��^KBV�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   yd���4HB�zB        a�  �?���A�*>���?!� �GB PBaO�K�HBV�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   k9����B�zB        b�  �?���A�*>���?��B PBF�P�2ABV�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   Y`���B�zB        �3�  �?w��A�*>���?K)�2�B PB;�P��lBV�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   ������A�zB        14�  �?v��Ap�*>���?{��<.�A PB�XR����AV�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   5+��<0�A�zB        �d�  �?x��A�*>���?����A PB�qR����AV�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   K�����oA�zB        �d�  �?w��A�*>���?���o�nA PB�S�MqAV�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   ����p�dA�zB        I@�  �?x��Ar�*>���?��QcA PBT���eAV�B   R��� LM���<�;�9 	S�� -.kLJ�|x�]yH�{[�=`O�L ����tIj����   ��·�tB�zB        �a�;d�?�@�>n��@���?�V°3hB PBMt��ĀBV�B   R��� LM���<�;�9 	S��H��H�"Un5�c�܊n�E#�{[�=`O�L ����tIj����   K}�i0B�zB        u2�;d�?[\�>,z>A���?"�2AB PBu� �GBV�B   R��� LM���<�;�9 	S�NT��T��[�+����ӡ��{[�=`O�L ����tIj����   ����A�zB        �6�;d�?L�>�*A���?���A PB�~�2�BV�B   R��� LM���<�;�9 	S�+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   +h��A�zB        �6�;d�?�>�)A���?K��MqA PB���AV�B   R��� LM���<�;�9 	S���v�R8��G�����
{[�=`O�L ����tIj����   0���
��{[�=`O�L ����tIj����   ǻL¦�3@�zB        t��  �?��AE�*>���?
��{[�=`O�L ����tIj����   �kL�� ���zB        ����  �?�-�AD�*>���?Y�|��� � PB���Dv��V�B   R��� LM���<�;�9 	S��3��K4F|�9���G>��{[�=`O�L ����tIj����   oL���
��zB�5?�5?۲&9Ō'9$�*>}"�A�?Y�|�"7� PB���w�	�V�B   R��� LM���<�;�9 	S��%�:�٪-ftBieV$�a�{[�=`O�L ����tIj����   ��L����zB�5?�5?:��8	`�8-�*>Qd�AS��?Y�|.�� PB�E�Fٚ�V�B"   R��� LM���<�;�9 	S��Wv:qL�1�f�d	�Dv{[�=`O�L ����tIj����   ��L,���zB�5?�5?��!8H�%8�*>��AI�?Y�|�Fס� PB�����V�B    R��� LM���<�;�9 	S�@�[/�j
��zB        (�  �? O�A��*>���?���"7� PB1\X�w�	�V�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   0	����`@�zB        T'�  �?��A��*>���?`�¦�[@ PB@�U�PLf@V�B   R��� LM���<�;�9 	S���Y^u+>��'�x��mT{[�=`O�L ����tIj����   �����3@�zB        +�  �?��A��*>���?���P\.@ PB5�U��9@V�B   R��� LM���<�;�9 	S���
/�BV�B   R��� LM���<�;�9 	S���=O��X@L��cy�{[�=`O�L ����tIj����   [D���;B�zB              �? �*>�R}A���?o�¯�B PB���U:[BV�B   R��� LM���<�;�9 	S���=O��X@L��cy�{[�=`O�L ����tIj����   [D����@�zB              �? �*>1�@���?o��p�a@ PB���4�1AV�B   R��� LM���<�;�9 	S���=O��X@L��cy�{[�=`O�L ����tIj����   [D�¼H�A�zB              �? �*>D�A���?o��4�1A PB��¯�BV�B   R��� LM���<�;�9 	S��߬on�_��Ɏ{�����Dj{[�=`O�L ����tIj����   ��l�M&
A��qR���Y{[�=`O�L ����tIj����   "M����zB              �?TU�A �*>���?Y�|�?;�� PB�L�����V�B   R��� LM���<�;�9 	SƗ+�����O��2��D?�l�{[�=`O�L ����tIj����   R@�������zB�5?�5?$�N���N���*>���A	�?q��?;�� PB��]�����V�B   R��� LM���<�;�9 	S�9��?���Q��AB�Z�{[�=`O�L ����tIj����   
]B�
�Rs
0B�zB        ��;d�?>ʿ>�*AA���?QnH��B PB�D��/HBV�B   R��� LM���<�;�9 	S�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��"A���� PB              �?6�0B�j
?  �?�4>�6��� PBB��� PB   R��� LM���<�;�9 	S��H :5��<�#�(� S�'{[�=`O�L ����tIj����   ��A��+� PB        {Np�  �?AZ+B��?  �?d�=�p-� PBU��A��*� PB   R��� LM���<�;�9 	S��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   &��@7�� PB        �"�5  �?��	Bs
?  �?��>���� PBc��A���� PB   R��� LM���<�;�9 	T�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   [�@�� PB        R0�5  �?��Bs
?  �?1�=�m�� PBG��A�?� PB   R��� LM���<�;�9 	T�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�A��A@ PB        ѷ�  �?��+B�l
?  �?�1<�Nf0@ PB2�A� S@ PB   R��� LM���<�;�9 	T�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�A�lhA PB        ѷ�  �?��+B�l
?  �?�1<��dA PB2�A=�lA PB   R��� LM���<�;�9 	T!�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�At6�A PB        ѷ�  �?��+B�l
?  �?�1<���A PB2�A`�A PB   R��� LM���<�;�9 	T(�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   t�A�B PB        �з�  �?��+Bml
?  �?�q7��B PB8a�Aq-B PB   R��� LM���<�;�9 	TV��7o��'��O(�!�[2{[�=`O�L ����tIj����   �g�@��BB�zB        �s#�  �?�B��*>���?�4�:[BB PB�4�A�CBV�B   R��� LM���<�;�9 	TWl$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ���@�EB�zB        ܝ#�  �?�B��*>���?��3��0EB PB�4�A:�EBV�B   R��� LM���<�;�9 	TZ�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   �m�@:DB PB        G��  �?hBB�
?  �?�3��CB PB�4�A�0EB PB   R��� LM���<�;�9 	TdFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��� �IB PB              �?
?  �?]�|�K�HB PB1�=���JB PB   R��� LM���<�;�9 	TkFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   V±�B PB              �?GB�j
?  �?]�|��lB PB<V���B PB   R��� LM���<�;�9 	TrFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ./�A PB              �?�]KB�j
?  �?o�����A PB<V�<.�A PB   R��� LM���<�;�9 	TyFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ~���OjA PB              �?�b�A�j
?  �?y|���eA PB,Y�o�nA PB   R��� LM���<�;�9 	T�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   T1�QTJ@ PB              �?
?  �?[�}��9@ PB6�Z���[@ PB   R��� LM���<�;�9 	T�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ���"9� PB              �?
?  �?�~�w�	� PB�V\��� � PB   R��� LM���<�;�9 	T�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ���GX�� PB              �?
?  �?�~��� PB�V\��.�� PB   R��� LM���<�;�9 	T��`���Ö|�1����sK�x�v{[�=`O�L ����tIj����   áN�S�hA PB        f<��~�?��A[�o?  �?o��_�bA PBye�G�nA PB   R��� LM���<�;�9 	T�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��m�DLA PB              �?�j
?��*A  �?�o¦�[@ PB��l��aA PB   R��� LM���<�;�9 	T�(1���F�g��'N�
? �W@  z,]�|���!A PB�o¨d*A PB   R��� LM���<�;�9 	T��i�߱�����1��,,kr<{[�=`O�L ����tIj����   ����?9���zB              �?SF�A��*>���?q������ PB�\�����V�B   R��� LM���<�;�9 	T��i�߱�����1��,,kr<{[�=`O�L ����tIj����   "M�?9���zB              �?TU�A��*>���?Y�|����� PB�L���V�B   R��� LM���<�;�9 	T�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ����d�� PB              �?
?  �?�~��� PB�V\�?;�� PB   R��� LM���<�;�9 	T�
۪,=�G�����<ߡ%�#.{[�=`O�L ����tIj����   �E�!�uB PB        :��?5�KB���@  �?-}��gB PB~�E�
/�B PB   R��� LM���<�;�9 	T��ܝ@��=&�NҲ��{[�=`O�L ����tIj����   R~�/tfB PB        ^1��  �?v�NBm
?  �?
�d BM�Wd�O�&#�;�ɦG���AƈP��%ULڝ.�N   :D��[<�U5�AmȠ���6 b2��7?��QA�A%@>.r��pV�Uu�A��[�P�"�U��A
   S�X�z�KP�d��
�d BM��kS��NL�YT�8yPޙ̓S��C\��/��Ȧ��'���R   �>���<�U��A        _c���?ԑA9�MA  �?.r��pV�U��A��[�P�"�U��A   S�X�z�KP�d��
�d BU0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   O7���o�U5�A              �?}�A�~?A  @>.r���̃�Uu�A��[��W�U��A
   S�X�z�KP�d��
�d BUFc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   O7���o�U��A              �?}�A�~?A  �?.r���̃�U��A��[��W�U��A   S�X�z�KP�d��
�d B]�9=����k���X>�ٞ�AƈP��%ULڝ.�N   ������>�V5�AL�8E�`���?8�<��bJA�7`Ag�B>��J���X�Uu�A�0��Ȟ$�U��A   S�X�z�KP�d��
�d B]_h�0kA�e.H���h�}��L�S��C\��/��Ȧ��'���R   ����;�?�U��A        D��?�PDAU6PA  �?��J���X�U��A�0��Ȟ$�U��A   T��!8J%�0c?��!� 	h��c�`P���?�����ik[�8{[�=`O�L ����tIj����   �|�A,ªJ�A        s*�<��?@��A)K@TUA!�IA�.ª�vA��A]|)���A   T��!8J%�0c?��!� 	h��G�3!����q�g/)�C�+{[�=`O�L ����tIj����   
�[�9��  �A        �ۿ<�?��zA��?��A� {ª�vA�9<��«��A   T�ؾ�O����{� 
*��=ܩyL�܀   ����o���$kL���}:��}��5��5?���@��@H��@�U��o������=���o�����   Tμ1��A�kg��� �N���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0��o�������        �5��5?���@UU)@  �>=+��o���V5������o���V5��   Tμ1��A�kg��� �N�YB�n�������Fҫԕ��u	���B1������   ����o����jL��6��6<9�4�:�4?TUm@XD�>��@�����h������������W�  Tμ1��A�kg��� �O����9�1�*n�26l�O�����
*��=ܩyL�܀   ����o���$kL���}:��}��5��5?���@��@H��@�U��o������=����&n����   Tμ1��A�kg��� �O���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0��o�������        �5��5?���@UU)@  �>=+��o���V5�������&k�V5��   Tμ1��A�kg��� �O�YB�n�������Fҫԕ��u	���B1������   ����o����jL��6��6<9�4�:�4?TUm@XD�>��@�����h���������4|q�W�  Tμ1��A�kg��� �Pְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   ����o��������e&��e&��5?�5?���@^@�A�U��o������=���o���ʥ��   Tμ1��A�kg��� �P���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0��o�������        �5?�5?���@UU)@  �>����o�������=���o�������   Tμ1��A�kg��� �PW����T ����{��ۭ���u	���B1������   ����o�������J�<H�<95?95?TUm@vk�>4?	A�����h�� ���������Vu��  Tμ1��A�kg��� �Qְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   ����o��������e&��e&��5?�5?���@^@�A�U��o������=����&n��ʥ��   Tμ1��A�kg��� �Q���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0��o�������        �5?�5?���@UU)@  �>����o�������=����&k�����   Tμ1��A�kg��� �QW����T ����{��ۭ���u	���B1������   ����o�������J�<H�<95?95?TUm@vk�>4?	A�����h�� ������4|q�Vu��  Tμ1��A�kg��� �R9�)�h:�������wJ��]���e���C�'�a�8�~.�   �����N��5��5?�;�o�� �@uxR?)
*��=ܩyL�܀   ���½-��$kL���}:��}��5��5?���@��@H��@�U��������=��½-�����   Tμ1��A�kg��� �g���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0�½-������        �5��5?���@UU)@  �>=+����V5�����½-��V5��   Tμ1��A�kg��� �g�YB�n�������Fҫԕ��u	���B1������   ���½-���jL��6��6<9�4�:�4?TUm@XD�>��@������������hغ�W�  Tμ1��A�kg��� �h����9�1�*n�26l�O�����
*��=ܩyL�܀   �����ȿ$kL���}:��}��5��5?���@��@H��@�U��y[h�����=���8$�>���   Tμ1��A�kg��� �h���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0���ȿ����        �5��5?���@UU)@  �>=+��y[t�V5�������.?V5��   Tμ1��A�kg��� �h�YB�n�������Fҫԕ��u	���B1������   �����ȿ�jL��6��6<9�4�:�4?TUm@XD�>��@����#[�������y�>W�  Tμ1��A�kg��� �iְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   ���¼-�������e&��e&��5?�5?���@^@�A�U��������=��½-���ʥ��   Tμ1��A�kg��� �i���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0�¼-������        �5?�5?���@UU)@  �>����������=��½-������   Tμ1��A�kg��� �iW����T ����{��ۭ���u	���B1������   ���¼-������J�<H�<95?95?TUm@vk�>4?	A����� ������hغ�Vu��  Tμ1��A�kg��� �jְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   �����ȿ�����e&��e&��5?�5?���@^@�A�U��y[h�����=���8$�>�ʥ��   Tμ1��A�kg��� �j���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0���ȿ����        �5?�5?���@UU)@  �>����y[t�����=����.?����   Tμ1��A�kg��� �jW����T ����{��ۭ���u	���B1������   �����ȿ����J�<H�<95?95?TUm@vk�>4?	A����#[� �����y�>Vu��  Tμ1��A�kg��� �k9�)�h:�������wJ��]���e���C�'�a�8�~.�   ���»+��N��5��5?�;�o�� �@uxR?)
*��=ܩyL�܀   �����s�A$kL���}:��}��5��5?���@��@H��@�U����A����=������A���   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0���s�A����        �5��5?���@UU)@  �>=+���s�AV5�������s�AV5��   Tμ1��A�kg��� ���YB�n�������Fҫԕ��u	���B1������   �����s�A�jL��6��6<9�4�:�4?TUm@XD�>��@����o��A�������I�AW�  Tμ1��A�kg��� ������9�1�*n�26l�O�����
*��=ܩyL�܀   �����s�A$kL���}:��}��5��5?���@��@H��@�U�����A����=������A���   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0���s�A����        �5��5?���@UU)@  �>=+���s�AV5�������s�AV5��   Tμ1��A�kg��� ���YB�n�������Fҫԕ��u	���B1������   �����s�A�jL��6��6<9�4�:�4?TUm@XD�>��@����o��A�������I�AW�  Tμ1��A�kg��� ��ְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   �����s�A�����e&��e&��5?�5?���@^@�A�U����A����=������A�ʥ��   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0���s�A����        �5?�5?���@UU)@  �>�����s�A����=����s�A����   Tμ1��A�kg��� ��W����T ����{��ۭ���u	���B1������   �����s�A����J�<H�<95?95?TUm@vk�>4?	A����o��A ������I�AVu��  Tμ1��A�kg��� ��ְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   �����s�A�����e&��e&��5?�5?���@^@�A�U�����A����=������A�ʥ��   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0���s�A����        �5?�5?���@UU)@  �>�����s�A����=����s�A����   Tμ1��A�kg��� ��W����T ����{��ۭ���u	���B1������   �����s�A����J�<H�<95?95?TUm@vk�>4?	A����o��A ������I�AVu��  Tμ1��A�kg��� ��9�)�h:�������wJ��]���e���C�'�a�8�~.�   ����Et�AN��5��5?�;�o�� �@uxR?)
*��=ܩyL�܀   ������B$kL���}:��}��5��5?���@��@H��@�U���B����=����'"B���   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0����B����        �5��5?���@UU)@  �>������B����=�����"B����   Tμ1��A�kg��� ���YB�n�������Fҫԕ��u	���B1������   ������B�jL��6��6<9�4�:�4?TUm@XD�>��@����6}B������R!BW�  Tμ1��A�kg��� ������9�1�*n�26l�O�����
*��=ܩyL�܀   �����g2B$kL���}:��}��5��5?���@��@H��@�U���'*B����=����:B���   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0���g2B����        �5��5?���@UU)@  �>=+���g)BV5�������g;BV5��   Tμ1��A�kg��� ���YB�n�������Fҫԕ��u	���B1������   �����g2B�jL��6��6<9�4�:�4?TUm@XD�>��@����6�*B�������9BW�  Tμ1��A�kg��� ��ְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   ������B�����e&��e&��5?�5?���@^@�A�U���B����=����'"B�ʥ��   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0����B����        �5?�5?���@UU)@  �>������B����=�����"B����   Tμ1��A�kg��� ��W����T ����{��ۭ���u	���B1������   ������B����J�<H�<95?95?TUm@vk�>4?	A����6}B �����R!BVu��  Tμ1��A�kg��� ��ְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   �����g2B�����e&��e&��5?�5?���@^@�A�U���'*B����=����:B�ʥ��   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0���g2B����        �5?�5?���@UU)@  �>�����g)B����=����g;B����   Tμ1��A�kg��� ��W����T ����{��ۭ���u	���B1������   �����g2B����J�<H�<95?95?TUm@vk�>4?	A����6�*B ������9BVu��  Tμ1��A�kg��� ��9�)�h:�������wJ��]���e���C�'�a�8�~.�   ����!�BN��5��5?�;�o�� �@uxR?)
*��=ܩyL�܀   ����VB$kL���}:��}��5��5?���@��@H��@�U�jNB����=���^B���   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0��VB����        �5��5?���@UU)@  �>=+��MBV5������_BV5��   Tμ1��A�kg��� ���YB�n�������Fҫԕ��u	���B1������   ����VB�jL��6��6<9�4�:�4?TUm@XD�>��@�����?OB�������,^BW�  Tμ1��A�kg��� ������9�1�*n�26l�O�����
*��=ܩyL�܀   ���*oB$kL���}:��}��5��5?���@��@H��@�U��fB����=��jwB���   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0�*oB����        �5��5?���@UU)@  �>=+�*fBV5�����*xBV5��   Tμ1��A�kg��� ���YB�n�������Fҫԕ��u	���B1������   ���*oB�jL��6��6<9�4�:�4?TUm@XD�>��@����׿gB�������,�vBW�  Tμ1��A�kg��� ��ְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   ����VB�����e&��e&��5?�5?���@^@�A�U�jNB����=���^B�ʥ��   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0��VB����        �5?�5?���@UU)@  �>����MB����=���_B����   Tμ1��A�kg��� ��W����T ����{��ۭ���u	���B1������   ����VB����J�<H�<95?95?TUm@vk�>4?	A�����?OB ������,^BVu��  Tμ1��A�kg��� ��ְ^>,��?�FR�i�4.�A����
*��=ܩyL�܀   ���*oB�����e&��e&��5?�5?���@^@�A�U��fB����=��jwB�ʥ��   Tμ1��A�kg��� �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0�*oB����        �5?�5?���@UU)@  �>���*fB����=��*xB����   Tμ1��A�kg��� ��W����T ����{��ۭ���u	���B1������   ���*oB����J�<H�<95?95?TUm@vk�>4?	A����׿gB ������,�vBVu��  Tμ1��A�kg��� ��9�)�h:�������wJ��]���e���C�'�a�8�~.�   ����ªVBN��5��5?�;�o�� �@uxR?)
@�����[���4NS�	��B[Ո��   W����J9���UO¾ �5�Cj΅���l�lq��f���հ�"�� �����i��Vil   ���®�8@�:�              �?  (@0�B���@�e����i�VEH��%��	^�B �+�   W����J9���UO¾ �6uD˜�!_p�Q����1���QI�}$uJ�q�NeȊq�`�1��   ���­�9@V��5U:        ��?  $@�H�BN*A�U����i� �+��5��	n�B�:¨   W����J9���UO¾ �6 >u��;�
�Mcƌ�ef�{[�=`O�L ����tIj����   ���±�9@V�Rv�        ��?  $@�D�B��(A�U����i� �+��5��	n�B�:�x   W����J9���UO¾ �P�Cj΅���l�lq��f���հ�"�� �����i��Vil   #�S�«:�              �?�&�B��'@���@\�����VEH�4NS��g�� �+�   W����J9���UO¾ �Q����T�`��ʹ����d�泥}$uJ�q�NeȊq�`�1��   "�S��Vª����8�5��5?��#@f(�B(D'A\����� �+�4NS��w�«:�@   W����J9���UO¾ �QkĻ����nZ�P�0||���{[�=`O�L ����tIj����   #�S��V��5?�5?C�8C�8��#@�'�B�
*��=ܩyL�܀   11_�52��kL�    �(����?    UU]@Yu@���@�f��«����FX��̃����   [&f�D3��z?�)? �k���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   11_�5r�«���          �?    UUu@VU)@  �>��f��l�«�����W�5"�«���   [&f�D3��z?�)? �k"�O���S�VŶ뽠��S?�j���u	���B1������   11_�5�¬jL�    QĀ<��?    ��B@�D�>��@�Feg������Y��W�  [&f�D3��z?�)? �l�H$�6X,�g��}��{����e���C�'�a�8�~.�   [1_�*u��%���?�b5�A�D�b����@��?#v�? h�5������FV7����   [&f�D3��z?�)? �ld5�AN�?��X�fr��E)!�3:�,9�I��<�cr   B7_��t���a��IB��IB;�5��5?���?���@�7�?1qg�5�����1�V7�­*��$   [&f�D3��z?�)? �lo�0�u�>#�ќ17��L�O
*��=ܩyL�܀   ��K�52��kL�    �(����?    UU]@Yu@���@1�R��«���ܫD��̃����   [&f�D3��z?�)? �m���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ��K�5r�«���          �?    UUu@VU)@  �>1AS�«�����C��̃«���   [&f�D3��z?�)? �m"�O���S�VŶ뽠��S?�j���u	���B1������   ��K�5�¬jL�    QĀ<��?    ��B@�D�>��@ܫQg�����1�E��W�  [&f�D3��z?�)? �n�H$�6X,�g��}��{����e���C�'�a�8�~.�   ��K�*u��%���?�b5�A�D�b����@��?#v�?V�T�5����� �B7����   [&f�D3��z?�)? �nd5�AN�?��X�fr��E)!�3:�,9�I��<�cr   ��K��t���a��IB��IB;�5��5?���?���@�7�?��S�5������VC7�­*��$   [&f�D3��z?�)? �no�0�u�>#�ќ17��L�O
*��=ܩyL�܀   1a!�52��kL�    �(����?    UU]@Yu@���@�K(��l�«����v�5������   [&f�D3��z?�)? �����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   1a!�5r�«���          �?    UUu@VU)@  �>�)�«�������̃«���   [&f�D3��z?�)? ��"�O���S�VŶ뽠��S?�j���u	���B1������   1a!�5�¬jL�    QĀ<��?    ��B@�D�>��@�v'�52������K�5҇�V�  [&f�D3��z?�)? ���H$�6X,�g��}��{����e���C�'�a�8�~.�   [a!�*u��%���?�b5�A�D�b����@��?#v�? L*�5������v7����   [&f�D3��z?�)? ��d5�AN�?��X�fr��E)!�3:�,9�I��<�cr   Bg!��t���a��IB��IB;�5��5?���?���@�7�?1�)�5�����1!7�­*��$   [&f�D3��z?�)? ��o�0�u�>#�ќ17��L�O
*��=ܩyL�܀   ��
*��=ܩyL�܀   b"��52��kL�    �(����?    UU]@Yu@���@�����l�«���
*��=ܩyL�܀   
��5������a���7�­*��   [&f�D3��z?�)? �ȥ.�2=��~늴�6�|aj�J�i�s�u���x���f|�   虉���Z%���5?�5? 1� 1���*>��@�@-A�5҇«����|��/լ�p  [&f�D3��z?�)? ��ә�<����Y{����;𡓕��u	���B1������   ���%���5��5?�-2��-23���< �@A)A�Y��ଇ«:��ق�5����ԭ�) [&f�D3��z?�)? ���<��l�r5CLx���CP>fh��/�	OR�$�Zuqq'3�   �5F�«ʱ�;��;�2�5��5?��>UUA���@Co���l�� ��1���Vu���   [&f�D3��z?�)? ��K�L:�Mg_��I��f)�
�����Ij��~��|@*����,   �5F�¾ѣ��5��5?���0��>���?x�@�����l��%.��"����Vu��   [&f�D3��z?�)? ���.�2=��~늴�6�|aj�J�i�s�u���x���f|�   �cU���Z%���5?�5? 1� 1���*>��@�@-A�cc�5҇«���cG��|��/լ�p  [&f�D3��z?�)? ��ә�<����Y{����;𡓕��u	���B1������   �cU���%���5��5?�-2��-23���< �@A)A��b�ଇ«:���G�5����ԭ�) [&f�D3��z?�)? ���<��l�r5CLx���CP>fh��/�	OR�$�Zuqq'3�   �cU�5F�«ʱ�;��;�2�5��5?��>UUA���@�i��l�� ��1�A��Vu���   [&f�D3��z?�)? ��K�L:�Mg_��I��f)�
�����Ij��~��|@*����,   �cU�5F�¾ѣ��5��5?���0��>���?x�@tKY��l��%.��D|Q��Vu��   [&f�D3��z?�)? ���.�2=��~늴�6�|aj�J�i�s�u���x���f|�   ϓ���Z%���5?�5? 1� 1���*>��@�@-Aܓ%�5҇«��ܓ	��|��/լ�p  [&f�D3��z?�)? ��ә�<����Y{����;𡓕��u	���B1������   ܓ���%���5��5?�-2��-23���< �@A)A�%�ଇ«:��
�5����ԭ�) [&f�D3��z?�)? ���<��l�r5CLx���CP>fh��/�	OR�$�Zuqq'3�   ܓ�5F�«ʱ�;��;�2�5��5?��>UUA���@�>+��l�� ��1���Vu���   [&f�D3��z?�)? ��K�L:�Mg_��I��f)�
�����Ij��~��|@*����,   ܓ�5F�¾ѣ��5��5?���0��>���?x�@t{��l��%.��D���Vu��   [&f�D3��z?�)? �	�.�2=��~늴�6�|aj�J�i�s�u���x���f|�   ��������Z%���5?�5? 1� 1���*>��@�@-A����5҇«�·����|��/լ�p  [&f�D3��z?�)? �	ә�<����Y{����;𡓕��u	���B1������   ��������%���5��5?�-2��-23���< �@A)A����ଇ«:·���5����ԭ�) [&f�D3��z?�)? �
�<��l�r5CLx���CP>fh��/�	OR�$�Zuqq'3�   ����5F�«ʱ�;��;�2�5��5?��>UUA���@
K�L:�Mg_��I��f)�
�����Ij��~��|@*����,   ����5F�¾ѣ��5��5?���0��>���?x�@�V���l��%.���������Vu��   [�i�N�1:՛� 
���kg'gF�u�b;W����}$uJ�q�NeȊq�`�1��    ����UT��B���;���;�5?�5?���@n�?��@
5�¾�]��,�A=���i�J��B�   [�i�N�1:՛� 
�Ǯ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    =k��UT��m
��8M������S�f��y2�3Ha���u	���B1������    =���UTª:B        �5?�5?��r@���>���@� ��i�[���A�u�¾�L�U�B`  [�i�N�1:՛� ��f"F'�)L%�j��
�AQB��<�9]k; ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ��(A:DBVUN��J	�N��5?�5?d�)?a�O?���B�@"A��BB p1�3:/A�nEBV�Bh5  \
�AQB��<�9]k; ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �''A:BVUN��J	�N��5?�5?d�)?a�O?���B"� A��B p1�w�-A�nBV�Bh5  \
�AQB��<�9]k; �b�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �%At6�AVUN��J	�N��5?�5?d�)?a�O?���BfA��A p1»,A���AV�Bh5  \
�AQB��<�9]k; ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   T�#A�lhAVUN��J	�N��5?�5?d�)?a�O?���B�A>cA p1��x*A��mAV�Bh5  \
�AQB��<�9]k; �@�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �f"A��A@VUN��J	�N��5?�5?d�)?a�O?���B��A�x,@ p1�C�(AM�V@V�Bh5  \
�AQB��<�9]k; ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �� A��VUN��J	�N��5?�5?d�)?a�O?���B2TA��� p1M'AmD�V�Bh5  \
�AQB��<�9]k; ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���    ;A�ɟ�VUN��J	�N��5?�5?d�)?a�O?���Bv�A�p�� p1�˷%A6"��V�Bh5  \
�AQB��<�9]k; ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   d�A����VUN��J	�N��5?�5?d�)?a�O?���B�(A�p�� p1�"$A6"��V�Bh5  \
�AQB��<�9]k; �M�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �A��+�VUN��J	�N��5?�5?d�)?a�O?���B��Aq8-� p1�S�"A�*�V�Bh5  \
�AQB��<�9]k; ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �yA��Y�VUN��J	�N��5?�5?d�)?a�O?���BA�Aq8[� p1� A�X�V�Bh5  \
�AQB��<�9]k; ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �,�:BVUN��J	�N��5?�5?d�)?a�O?���B-���B p1°sҿ�nBV�Bh5  \
�AQB��<�9]k; �,�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ��8�t6�AVUN��J	�N��5?�5?d�)?a�O?���BX?���A p1�2����AV�Bh5  \
�AQB��<�9]k; ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ��6�:BVUN��J	�N��5?�5?d�)?a�O?���B�y=���B p1�G�0��nBV�Bh5  \
�AQB��<�9]k; �T�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   j(:��lhAVUN��J	�N��5?�5?d�)?a�O?���B�@�>cA p1¿�3���mAV�Bh5  \
�AQB��<�9]k; �6�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �1<���A@VUN��J	�N��5?�5?d�)?a�O?���B>�B��x,@ p1��5�M�V@V�Bh5  \
�AQB��<�9]k; ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   1�=���VUN��J	�N��5?�5?d�)?a�O?���B�QD���� p1X7�mD�V�Bh5  \
�AQB��<�9]k; �*�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ��>��ɟ�VUN��J	�N��5?�5?d�)?a�O?���BHfE��p�� p1��l8�6"��V�Bh5  \
�AQB��<�9]k; �5�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �2B�����VUN��J	�N��5?�5?d�)?a�O?���Bd�H��p�� p1��;�6"��V�Bh5  \
�AQB��<�9]k; �F�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �2B���+�VUN��J	�N��5?�5?d�)?a�O?���Bd�H�q8-� p1��;��*�V�Bh5  \
�AQB��<�9]k; �	�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �2B���Y�VUN��J	�N��5?�5?d�)?a�O?���Bd�H�q8[� p1��;��X�V�Bh5  \I+�JГPEC��w �Ő��f07L6���	���{[�=`O�L ����tIj����   �<�q�C�Uu�A              �?��*>��0A���?d�=���Y���A�4;��-«��A   \I+�JГPEC��w �Ɛ��f07L6���	���{[�=`O�L ����tIj����   ��G���+�Uu�A              �?��*> �A���?�3I���Y���AJ�F��������A   \�T��YF)���?>�� G���W��D��)v�N�sհ�"�� �����i��Vil   ��B������4�ܴZ:�\�d�?�b�;��?f�BJ�A�Y�A���VEH�?�B�HtA p!�$   \�X��F���>�� {퐤�f07L6���	���r��(;�{p9DC}�\ə�   �$�����A              �?���A   ?  @?Wz�$�����A�S�$�����A   \�X��F���>�� |	���f07L6���	���r��(;�{p9DC}�\ə�   ��$�����A   '`W�  �?���&�C�A   ?  @?=��$�����AWz�$�����A   \�X��F���>�� |!���f07L6���	���r��(;�{p9DC}�\ə�   �6�����A              �?���A   ?  @?Wz�6�����A�S�6�����A   \�X��F���>�� |A���f07L6���	���r��(;�{p9DC}�\ə�   ��6�����A   '`W�  �?���&�C�A   ?  @?=��6�����AWz�6�����A   \�X��F���>�� |����f07L6���	���r��(;�{p9DC}�\ə�   ��¢�]����A   ',�K  �?��{'�C�A   ?  @?=��¢�^����AWz�¢�\����A   \�X��F���>�� |����f07L6���	���r��(;�{p9DC}�\ə�   G9��o�f����A�A���A�&�5��5?CU�A���>  @?G����̃����AG����E����A   \�X��F���>�� |����f07L6���	���r��(;�{p9DC}�\ə�   6���o�f����A�A���A�&�5��5?CU�A���>  @?68���̃����A68���E����A   \�X��F���>�� |ِ��f07L6���	���r��(;�{p9DC}�\ə�   m6��o�f����A�A���A�&�5��5?CU�A���>  @?m����̃����Am����E����A   \�X��F���>�� |����f07L6���	���r��(;�{p9DC}�\ə�   \���o�f����A�A���A�&�5��5?CU�A���>  @?\5���̃����A\5���E����A   \�X��F���>�� }Z���f07L6���	���r��(;�{p9DC}�\ə�   �h|¬� ����A�A�&�A�&�5?�5?�A�A���>  @?�h}��C����A�h{�v������A   \�X��F���>�� }����f07L6���	���r��(;�{p9DC}�\ə�   wfm¬� ����A�A�&�A�&�5?�5?�A�A���>  @?wfn��C����Awfl�v������A   \�X��F���>�� }����f07L6���	���r��(;�{p9DC}�\ə�   �b\�� ����A�A�&�A�&�5?�5?�A���>  @?�b]��YC����A�b[�v������A   \�X��F���>�� }����f07L6���	���r��(;�{p9DC}�\ə�   �`M¬� ����A�A�&�A�&�5?�5?�A�A���>  @?�`N��C����A�`L�v������A   \�X��F���>�� }Ȑ��f07L6���	���r��(;�{p9DC}�\ə�   M�<¬� ����A�A�&�A�&�5?�5?�A�A���>  @?M�=��C����AL�;�v������A   \�X��F���>�� }㐤�f07L6���	���r��(;�{p9DC}�\ə�   ,�-¬� ����A�A�&�A�&�5?�5?�A�A���>  @?,�.��C����A,�,�v������A   \�X��F���>�� }����f07L6���	���r��(;�{p9DC}�\ə�   ��¬� ����A�A�&�A�&�5?�5?�A�A���>  @?����C����A���v������A   \�X��F���>�� ~���f07L6���	���r��(;�{p9DC}�\ə�   x�
��u������A   \�X��F���>�� �h���f07L6���	���r��(;�{p9DC}�\ə�   _���A�0����A              �?��mA   ?  @?Wz��A�1����Ag���A�/����A   \�X��F���>�� �����f07L6���	���r��(;�{p9DC}�\ə�   ⹖�M#����A              �?Z|A   ?  @?Wz��M$����Al���M"����A   \�X��F���>�� �����f07L6���	���r��(;�{p9DC}�\ə�   �D��Ǚ����A              �?��A   ?  @?Wz��Ǚ
1ћfb��   
1ћfb��   b>��|�A�ʖA        �5��5?��?���=���@�S��|�A��vA
1ћfb��   
��~vB\lGB����   ]�]:{�Iހ����m� 	 F븑���ъE���|I��!�
+a�d��n�Kn:��e7   &A$������        (�����?D'?BU)�B  �?��J��̃����~vB�4GB���*   ]�]:{�Iހ����m� 	 ���kG��w!�z7�q�%�%��[�H�_����˖���dn`   q�%A�P�����i
8n}����?^a�<:Q?B��B�H?��J��̃�[���~vB\lGB�*��f   ]�]:{�Iހ����m� 	 ��A4d0���tO��Q�m:�|�-�6�QBڍ��a�1t   /�AA� ��*��        ��Q<��?��@B���B  �?��J��̃«*��~vB�4GB�*��   ]�]:{�Iހ����m� 	 ����\w?����:�^���!�
+a�d��n�Kn:��e7   �R A���*��        ��3>%|?��fB��]B  �?��J��T.«*���2B1S�@�*��   ]�]:{�Iހ����m� 	 �A��&�p�<]w}�e���*��[�H�_����˖���dn`   ��%AD�p{@��%j"��?Q�<6?B��B
+a�d��n�Kn:��e7   �)A�O��UՅ@        %kW>nEz?+�mB'�nB  �?��J�pD,�UՅ@�2B1S�@UՅ@   ]�]:{�Iހ����m� 	8`f�X�	��ŷm�O�t)C���[�H�_����˖���dn`   ��%A�M���rA4��7�ꄷ��?ޤ<�B?B�
�B��?��J��̃�R�nA~vB\lGB��vAf   ]�]:{�Iހ����m� 	8\�ǹ�PJ�l-n�Z��c��6|�-�6�QBڍ��a�1t   F�A�� ���vA        ��K<��?Ȝ@B�z�B  �?��J��̃ª�vA~vB�4GB��vA   ]�]:{�Iހ����m� 	8������u7�L�s�S[R�!�
+a�d��n�Kn:��e7   g�(A�B����vA        :7P>�z?�@lB<�mB  �?��J�=,ª�vA�2B1S�@��vA   ]�]:{�Iހ����m� 	�%Ek��g=�W8�&=H��)[�H�_����˖���dn`   ֊%AL�R��A��7�0����?���<9?Bx	�Bx�?��J��̃����A~vB\lGB���Af   ]�]:{�Iހ����m� 	�\�ǹ�PJ�l-n�Z��c��6|�-�6�QBڍ��a�1t   G�A�� ����A        �<K<��?L�@B�y�B  �?��J��̃«��A~vB�4GB���A   ]�]:{�Iހ����m� 	���
+a�d��n�Kn:��e7   S�(APr�����A        �GN>��z?l�kBZmB  �?��J�pD,«��A�2B1S�@���A   ]�)�/L|��ҤQ	� �@�`PB��L���Vz,8{N&KQ�!��(�!D����;�   �مBe�hAXi��4���5?UGּ�p�<pUU?|��B�waB?�B��]A p!�)��B�tAR�3A�   ]�)�/L|��ҤQ	� �@��Ο���R�H��	��K��T{[�=`O�L ����tIj����   �مBe�hAXi�'64�?�5?A�G<��E�pUU?%:�B!dWB?�B��]A p!�)��B�tAR�3A�   ^{3HqI	����\G G�x詘��p@��բ���"�$O�t����JR� ��}��G   ?���Z[�����AU@��\%5��=��+?���A� [A  A5����a�����A�S��I̥�V�B�   ^{3HqI	����\G G���>��)���%q�^���O�t����JR� ��}��G   7:z¨/�����A        �x�zK}?�9�@%z�@   A)�¼������A,�r�؎��V�B,   _#�Y��K�yϲTj�� S�������H�%����͑O�t����JR� ��}��G   ��@������A���C���L��w�~?�_4B'��B   A��J��̃�UՅ@+B�^�@��bA6  _#�Y��K�yϲTj�� S��Ш������YV��rs��O�t����JR� ��}��G   u>�A�$Yª�A        �A2>b|?B��Aء�A   A�[�@�̃�UՅ@�� BFa-ª�bA�   _�"�ұMؗ�hֲ_ ���AJ�u�
+a�d��n�Kn:��e7   R;¬�P����A        �ҽK�~?H�_B��0B  �?)���������A�,F���u@���A   _�"�ұMؗ�hֲ_ ���fd�#߅X�.=�!����{[�H�_����˖���dn`   �$�������A��N���Ƿ�={?	�D�VC�B_~C��?=����̃����A��[�^c�B���A*   _�"�ұMؗ�hֲ_ ��u��&�44su�!-0�)�i|�-�6�QBڍ��a�1t   ��p��0����A        n81�#|?�g�Bs]C  �?=����̃«��A��[�^c�B���A   _�"�ұMؗ�hֲ_ ���p�h�u�����Ep\;���!�
+a�d��n�Kn:��e7   (j�^�����A        �3~>��w?+��B���B  �?����ı"«��A��[��5A���A   _�k�XA��~w]� Ҷ�[�i�,���?�p���qQ��3�ޒ�8�����ġ���   	��A�V�U��A        �_�!�?�L�@�B�? ��=W��Ap���_�A� B�«
�A   `��2�MO�e;p��֑ bn%V��*����%L�x�p�[<�F�Lt��չa/g�rj�   8��A{ �=&�A7?�?/������C�u@U�@Ym�AlA�'ª�tA5� B�d��b�A�   `��2�MO�e;p��֑ b�q`��I5C�G�����I���}$uJ�q�NeȊq�`�1��   �c�A�$(�H��A��?�?aG��<E��iwU>F�;@��AlAp�(�&gAң B�'��b�A,   `��2�MO�e;p��֑ b�g�u�D�sm��CH�¥4��}$uJ�q�NeȊq�`�1��   ~�A����A��?���b���`�>3xU>I�<@�ѝAlA�d�&gA�� Bp���b�A,   `��2�MO�e;p��֑ b�6��ڞ.��8�7�x2�%Usp�[<�F�Lt��չa/g�rj�   Є�A=d�Ax�?3�?J`�>}��>��w@M��?f� A0��A�©
�A�� Bn�«��AH   `��2�MO�e;p��֑ c?#��޷��k�L��bfs�ɨ�}$uJ�q�NeȊq�`�1��   L��A���Ss�A��۾=�㾥�?�?)XU>�1@4��A.QlA ���_�A�� B�=«��A<   `��2�MO�e;p��֑ c
jxe��-����|d�hOfI�}$uJ�q�NeȊq�`�1��   @��A�(��E�A�оU8ؾ�?��?�`U> G@�[&AL��A�8��_�A/�BF	«��A<   `�.]jOJ�jE)�� x��f07L6���	���aN�1
x>�Pr$   ���A�=z� ��A        �x�o�?� ?�B`@��2@��A���Uu�A�3�A�=^����A   `�.]jOJ�jE)�� y��fnS�������w��?^��ɬ�@MQ��
x>�Pr$   �ǴA6t�� ��A        �x�o�?� ?�B`@��2@�1�A6t��Uu�A�]�A6t�����A   a�u:��Dչ���"��� ɳZJI�Oz�)��E�i��ڰ?^��ɬ�@MQ��
x>�Pr$   I B|����1���t���?�I�2F��X�>�=�A  �A��B�,����
_��JҼ9D}�!O�t����JR� ��}��G   ��%?�����A_�_���y1ݘ_?ZR��^��A���A   A��=���UՅ@��FAR�.���bA�   c��.FR����N�a 49���v@?��B�97^�P�	א�� �s�gtQ�#�e;$,�   ^���\�`B�7��h��=        �u?  @?��A��WA^k�m=B�:�^�ЁB����    c��.FR����N�a 4:��
*��=ܩyL�܀   ���UT�<�$A��f���f��5?�5?���@�K�?@k�@�����\¨*�@=���L��?VA�   c�s��M"�k�e�� !h���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����UT¨*�@        �5?�5?���@UU�?  �>���U]¨*�@����UK¨*�@   c�s��M"�k�e�� !h�5��|p�#^��E^�h�Mq���u	���B1������   ���UT©�$Ar�<r�<��4?��4?TUm@KmM?Զ@={�¾�[�R��@����i�L©�RA  c�s��M"�k�e�� !iu6��0wX՘��/���)�����
*��=ܩyL�܀   ����;�<�$A��f���f��5?�5?���@�K�?@k�@����D¨*�@=����3��?VA�   c�s��M"�k�e�� !i���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����;¨*�@        �5?�5?���@UU�?  �>����D¨*�@�����2¨*�@   c�s��M"�k�e�� !i�5��|p�#^��E^�h�Mq���u	���B1������   ����;©�$Ar�<r�<��4?��4?TUm@KmM?Զ@={�¾?C�R��@����ij4©�RA  c�s��M"�k�e�� !ju6��0wX՘��/���)�����
*��=ܩyL�܀   ��¼O�<�$A��f���f��5?�5?���@�K�?@k�@���¼�!¨*�@=��¼��?VA�   c�s��M"�k�e�� !j���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���¼O¨*�@        �5?�5?���@UU�?  �>��¼O"¨*�@���¼O¨*�@   c�s��M"�k�e�� !j�5��|p�#^��E^�h�Mq���u	���B1������   ��¼O©�$Ar�<r�<��4?��4?TUm@KmM?Զ@={��f� �R��@�����©�RA  c�s��M"�k�e�� !ku6��0wX՘��/���)�����
*��=ܩyL�܀   ��¼� �<�$A��f���f��5?�5?���@�K�?@k�@���¼	¨*�@=���w���?VA�   c�s��M"�k�e�� !k���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���¼� ¨*�@        �5?�5?���@UU�?  �>��¼�	¨*�@����w����*�@   c�s��M"�k�e�� !k�5��|p�#^��E^�h�Mq���u	���B1������   ��¼� ©�$Ar�<r�<��4?��4?TUm@KmM?Զ@={��f:�R��@����"�����RA  c�s��M"�k�e�� !lu6��0wX՘��/���)�����
*��=ܩyL�܀   ���o���<�$A��f���f��5?�5?���@�K�?@k�@����o���*�@=���o���?VA�   c�s��M"�k�e�� !l���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����o����*�@        �5?�5?���@UU�?  �>���o����*�@����o����*�@   c�s��M"�k�e�� !l�5��|p�#^��E^�h�Mq���u	���B1������   ���o�����$Ar�<r�<��4?��4?TUm@KmM?Զ@={���h��R��@���������RA  c�s��M"�k�e�� !mu6��0wX՘��/���)�����
*��=ܩyL�܀   ���o���<�$A��f���f��5?�5?���@�K�?@k�@����o���*�@=����&n��?VA�   c�s��M"�k�e�� !m���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����o����*�@        �5?�5?���@UU�?  �>���o����*�@�����&k��*�@   c�s��M"�k�e�� !m�5��|p�#^��E^�h�Mq���u	���B1������   ���o�����$Ar�<r�<��4?��4?TUm@KmM?Զ@={���h��R��@����4|q���RA  c�s��M"�k�e�� !nu6��0wX՘��/���)�����
*��=ܩyL�܀   ��¼-��<�$A��f���f��5?�5?���@�K�?@k�@�������*�@=��½-���?VA�   c�s��M"�k�e�� !n���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���¼-���*�@        �5?�5?���@UU�?  �>������*�@���½-���*�@   c�s��M"�k�e�� !n�5��|p�#^��E^�h�Mq���u	���B1������   ��¼-����$Ar�<r�<��4?��4?TUm@KmM?Զ@={���R��@����hغ���RA  c�s��M"�k�e�� !ou6��0wX՘��/���)�����
*��=ܩyL�܀   ����ȿ<�$A��f���f��5?�5?���@�K�?@k�@����y[h��*�@=���8$�>�?VA�   c�s��M"�k�e�� !o���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����ȿ�*�@        �5?�5?���@UU�?  �>���y[t��*�@�����.?�*�@   c�s��M"�k�e�� !o�5��|p�#^��E^�h�Mq���u	���B1������   ����ȿ��$Ar�<r�<��4?��4?TUm@KmM?Զ@={��#[�R��@���y�>��RA  c�s��M"�k�e�� !pu6��0wX՘��/���)�����
*��=ܩyL�܀   �����@<�$A��f���f��5?�5?���@�K�?@k�@������@�*�@=���A�?VA�   c�s��M"�k�e�� !p���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ������@�*�@        �5?�5?���@UU�?  �>�����@�*�@����A�*�@   c�s��M"�k�e�� !p�5��|p�#^��E^�h�Mq���u	���B1������   �����@��$Ar�<r�<��4?��4?TUm@KmM?Զ@={�½Y�@R��@����4�A��RA  c�s��M"�k�e�� !qu6��0wX՘��/���)�����
*��=ܩyL�܀   ���\A<�$A��f���f��5?�5?���@�K�?@k�@����;A�*�@=���}A�?VA�   c�s��M"�k�e�� !q���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����\A�*�@        �5?�5?���@UU�?  �>���8A�*�@�����k�A�*�@   c�s��M"�k�e�� !q�5��|p�#^��E^�h�Mq���u	���B1������   ���\A��$Ar�<r�<��4?��4?TUm@KmM?Զ@={���,?AR��@����4�zA��RA  c�s��M"�k�e�� !ru6��0wX՘��/���)�����
*��=ܩyL�܀   ����s�A<�$A��f���f��5?�5?���@�K�?@k�@������A�*�@=������A�?VA�   c�s��M"�k�e�� !r���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����s�A�*�@        �5?�5?���@UU�?  �>����s�A�*�@�����s�A�*�@   c�s��M"�k�e�� !r�5��|p�#^��E^�h�Mq���u	���B1������   ����s�A��$Ar�<r�<��4?��4?TUm@KmM?Զ@={��o��AR��@����I�A��RA  c�s��M"�k�e�� !su6��0wX՘��/���)�����
*��=ܩyL�܀   ����s�A<�$A��f���f��5?�5?���@�K�?@k�@�������A�*�@=������A�?VA�   c�s��M"�k�e�� !s���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����s�A�*�@        �5?�5?���@UU�?  �>����s�A�*�@�����s�A�*�@   c�s��M"�k�e�� !s�5��|p�#^��E^�h�Mq���u	���B1������   ����s�A��$Ar�<r�<��4?��4?TUm@KmM?Զ@={��o��AR��@����I�A��RA  c�s��M"�k�e�� !tu6��0wX՘��/���)�����
*��=ܩyL�܀   �����B<�$A��f���f��5?�5?���@�K�?@k�@�����B�*�@=����'"B�?VA�   c�s��M"�k�e�� !t���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ������B�*�@        �5?�5?���@UU�?  �>�`����B�*�@=�����"B�*�@   c�s��M"�k�e�� !t�5��|p�#^��E^�h�Mq���u	���B1������   �����B��$Ar�<r�<��4?��4?TUm@KmM?Զ@={��6}BR��@���R!B��RA  c�s��M"�k�e�� !uu6��0wX՘��/���)�����
*��=ܩyL�܀   ����g2B<�$A��f���f��5?�5?���@�K�?@k�@�����'*B�*�@=����:B�?VA�   c�s��M"�k�e�� !u���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����g2B�*�@        �5?�5?���@UU�?  �>�`���g)B�*�@=����g;B�*�@   c�s��M"�k�e�� !u�5��|p�#^��E^�h�Mq���u	���B1������   ����g2B��$Ar�<r�<��4?��4?TUm@KmM?Զ@={��6�*BR��@����9B��RA  c�s��M"�k�e�� !vu6��0wX՘��/���)�����
*��=ܩyL�܀   ���VB<�$A��f���f��5?�5?���@�K�?@k�@���jNB�*�@=���^B�?VA�   c�s��M"�k�e�� !v���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����VB�*�@        �5?�5?���@UU�?  �>�`��MB�*�@=���_B�*�@   c�s��M"�k�e�� !v�5��|p�#^��E^�h�Mq���u	���B1������   ���VB��$Ar�<r�<��4?��4?TUm@KmM?Զ@={���?OBR��@����,^B��RA  c�s��M"�k�e�� !wu6��0wX՘��/���)�����
*��=ܩyL�܀   ��*oB<�$A��f���f��5?�5?���@�K�?@k�@����fB�*�@=��jwB�?VA�   c�s��M"�k�e�� !w���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���*oB�*�@        �5?�5?���@UU�?  �>�`�*fB�*�@=��*xB�*�@   c�s��M"�k�e�� !w�5��|p�#^��E^�h�Mq���u	���B1������   ��*oB��$Ar�<r�<��4?��4?TUm@KmM?Զ@={��׿gBR��@����,�vB��RA  c�s��M"�k�e�� !x!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   *����;�s`AGH�EH=L�4�L�4?TU�@]_X?�Q�?=���i�F�e�TA��¾�0�QkA$   c�s��M"�k�e�� !y��F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   *��¼O�s`AGH=EH=L�4?L�4?TU�@]_X?�Q�?=+��e$�e�TA���f:�QkA$   c�s��M"�k�e�� !z��F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   *���o���s`AGH=EH=L�4?L�4?TU�@]_X?�Q�?=+�����e�TA����h��QkA$   c�s��M"�k�e�� !{��F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   *��¼-��s`AGH=EH=L�4?L�4?TU�@]_X?�Q�?=+��3l'�e�TA������QkA$   c�s��M"�k�e�� !|��F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   *�����@s`AGH=EH=L�4?L�4?TU�@]_X?�Q�?=+��h�@e�TA����,'AQkA$   c�s��M"�k�e�� !}��F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   *����s�As`AGH=EH=L�4?L�4?TU�@]_X?�Q�?=+��I�Ae�TA���o��AQkA$   c�s��M"�k�e�� !~��F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   *�����Bs`AGH=EH=L�4?L�4?TU�@]_X?�Q�?=+��Be�TA���6�$BQkA$   c�s��M"�k�e�� !��F۵��}�c������K�jא�� �s�gtQ�#�e;$,�   *���VBs`AGH=EH=L�4?L�4?TU�@]_X?�Q�?=+��,�KBe�TA���׿aBQkA$   c�s��M"�k�e�� !�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   *��¼� �s`AGH�EH=L�4�L�4?TU�@]_X?�Q�?=�����e�TA����t��QkA$   c�s��M"�k�e�� !�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   *���〇�x�`AGH�EH=L�4�L�4?TU�@]_X?�Q�?=�������TA���q�b�m�kA$   c�s��M"�k�e�� !�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   *����ȿs`AGH�EH=L�4�L�4?TU�@]_X?�Q�?=���g؊�e�TA��¶�?QkA$   c�s��M"�k�e�� !�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   *���\As`AGH�EH=L�4�L�4?TU�@]_X?�Q�?=���4�0Ae�TA���o��AQkA$   c�s��M"�k�e�� !�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   *����s�As`AGH�EH=L�4�L�4?TU�@]_X?�Q�?=���I�Ae�TA���o��AQkA$   c�s��M"�k�e�� !�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   *����g2Bs`AGH�EH=L�4�L�4?TU�@]_X?�Q�?=��R'Be�TA���6}=BQkA$   c�s��M"�k�e�� !�!���A��Y��|�e��*�Sא�� �s�gtQ�#�e;$,�   *��*oBs`AGH�EH=L�4�L�4?TU�@]_X?�Q�?=���,dBe�TA����?zBQkA$   c�� zJ������� �����2�T��[��Y�xr��(;�{p9DC}�\ə�   Z%�B�#¯*��              �?UUu?UUu?TUA0�B�z%��)���Bk�!�lU��   d-��*+Gߗ��x�� J=�B�wYC9�?}������ ���u�)���[��    ����^s�B�8B          �?���%��j@���<���@=K��	n�B��A���´x�B4�Bv   d-��*+Gߗ��x�� J=v
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    ���´x�B�8B          �?���%  �@  �>�9�@���´8�B���A���´��B��B�   d-��*+Gߗ��x�� JZ�B�wYC9�?}������ ���u�)���[��    =���^s�B�8B          �?���%��j@���<���@�5��	n�B��A���´x�B4�Bv   d-��*+Gߗ��x�� JZv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    =��´x�B�8B          �?���%  �@  �>�9�@=��´8�B���A=��´��B��B�   d-��*+Gߗ��x�� J��B�wYC9�?}������ ���u�)���[��    �ռ�^s�B4q�A              �?��j@���<���@����	n�B��A=+�´x�Bh��Av   d-��*+Gߗ��x�� J�v
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    �ռ´x�B�q�A              �?  �@  �>�9�@���´8�B�ʓA�ո´��B�A�   d-��*+Gߗ��x�� Kx�B�wYC9�?}������ ���u�)���[��    ����^s�B4q�A              �?��j@���<���@=+��	n�B��A�թ´x�Bh��Av   d-��*+Gߗ��x�� Kxv
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    ���´x�B�q�A              �?  �@  �>�9�@���´8�B�ʓA���´��B�A�   d-��*+Gߗ��x�� K�u6��0wX՘��/���)�����
*��=ܩyL�܀   =k��	��B��A���        ��?  �@�K�?@k�@=���^c�BUu�A=K�´��B�ʴA�   d-��*+Gߗ��x�� K����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   =k��	΄BUu�A              �?  �@VU�?  �>=��^c�BUu�A=�´8�BUu�A   d-��*+Gߗ��x�� K��5��|p�#^��E^�h�Mq���u	���B1������   =k��	�B��A�E=        ��?UUm@LmM?Զ@� �´��B��A赚�^S�B��A  eP۶�K���`�
��� �b�x;��A{n�B�ujg`�n�-{[�=`O�L ����tIj����   l�H��� �KW��\����?�Z�7g�*>�:?.`�B��I��̃� p!�AG�qi�� PB   eP۶�K���`�
��� �c�x;��A{n�B�ujg`�n�-{[�=`O�L ����tIj����   ��:�"�����A�߱�[����?O��7�*>H�:?.`�B(A<��̃� p!�[�9�vi�� PB   eP۶�K���`�
��� �ej����X'�����G<Q���{[�=`O�L ����tIj����   
�A���� �        ���7  �?0?g�*> `�BAG�˾�� p!�A<�ri�� PB   eP۶�K���`�
��� ���x;��A{n�B�ujg`�n�-{[�=`O�L ����tIj����   ��1@�� �À��\����?K��7C�*>�:?-`�Bn,@�̃� p!�H7@qi�� PB   eP۶�K���`�
��� ���x;��A{n�B�ujg`�n�-{[�=`O�L ����tIj����   Wnh@"�� ��ݿ��[����?o��7L�*>J�:?.`�B�c@�̃� p!���m@vi�� PB   eP۶�K���`�
��� ��j����X'�����G<Q���{[�=`O�L ����tIj����   7M@��� �        �<�7  �?
0?z�*> `�B&7@˾�� p!�Hc@ri�� PB   eP۶�K���`�
��� �Ֆx;��A{n�B�ujg`�n�-{[�=`O�L ����tIj����   �djA�� �5��\����?R��7F�*>
��� �֖x;��A{n�B�ujg`�n�-{[�=`O�L ����tIj����   fxA"��  �Rḵ�[����?�L�7>�*>F�:?.`�B �vA�̃� p!��dyAvi�� PB   eP۶�K���`�
��� ��j����X'�����G<Q���{[�=`O�L ����tIj����   :qA��� �         ��7  �?0?��*> `�B�kA˾�� p!�"�vAri�� PB   eP۶�K���`�
��� ��x;��A{n�B�ujg`�n�-{[�=`O�L ����tIj����   
y�A�� �KF��\����?���7�*>�:?.`�BW��A�̃� p!½#�Aqi�� PB   eP۶�K���`�
��� ��7A�]'		jK���#�� {[�=`O�L ����tIj����   ^N�A�0�� �        ΋�7  �?�*>R`? `�B���A�̃� p!���A!��� PB   eP۶�K���`�
��� ��j����X'�����G<Q���{[�=`O�L ����tIj����   9�A��� �        ���7  �?dVE?��*> `�B�#�A̾�� p!�hN�Ari�� PB   f|���G0�h˳p�L -�7�\@0�ƍ�	�yޙ�o�O�t����JR� ��}��G   ���B�������        �r�<�?fl�BJ�B   Ay�B�����|��B��fA�=��   f|���G0�h˳p�L -�N�⁚N5X7R�Yc�`���O�t����JR� ��}��G   �3�B�rA���        hZ���?e��@��A   A�
|B_�@���b�B͵bA�=�   f|���G0�h˳p�L -�r�옚��X�[�h<z��O�t����JR� ��}��G   �\B,%A���        ��;��?�ZqA�� A   A��=B3��@���*zB��dA�=�   ig���G}� t�Y�* �Q���J�rf����.�VjTg1հ�"�� �����i��Vil   �=��\�x«:��þ^�l?,��2v/ϱ (@�6[A���@����{
��VEH�>�����a� �+�   ig���G}� t�Y�* �RiFƽV+qTQ�ֳ5cD��}$uJ�q�NeȊq�`�1��   �=��]�x�V��þ_�l?,c3R#� $@�6[AW�&A����+��� �+���c�a«:�   ig���G}� t�Y�* �R	<V�ʙ�E��Юu��M�{[�=`O�L ����tIj����   �=��]�x�V��þ_�l?���C��3 $@�6[AZ�&A����+��� �+���c�a«:�   i����,K�ӃO
=N� �J�t��H�Հy�E,����|-%���
*��=ܩyL�܀   ����52��kL�    �(����?    UU]@Yu@���@�����l�«���C��5������   i����,K�ӃO
=N� �J���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����5r�«���          �?    UUu@VU)@  �>�U��«���C����̃«���   i����,K�ӃO
=N� �J"�O���S�VŶ뽠��S?�j���u	���B1������   ����5�¬jL�    QĀ<��?    ��B@�D�>��@C��g������u���V�  i����,K�ӃO
=N� �K�H$�6X,�g��}��{����e���C�'�a�8�~.�   ����*u��%���?�b5�A�D�b����@��?#v�? ���5�����V�7����   i����,K�ӃO
=N� �Kd5�AN�?��X�fr��E)!�3:�,9�I��<�cr   �����t���a��IB��IB;�5��5?���?���@�7�?����5������`�7�­*��$   i����,K�ӃO
=N� �Ko�0�u�>#�ќ17��L�O
=N� �L�t��H�Հy�E,����|-%���
*��=ܩyL�܀   C���52��kL�    �(����?    UU]@Yu@���@�(���l�«����=��5������   i����,K�ӃO
=N� �L���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   C���5r�«���          �?    UUu@VU)@  �>����«����݀��̃«���   i����,K�ӃO
=N� �L"�O���S�VŶ뽠��S?�j���u	���B1������   C���5�¬jL�    QĀ<��?    ��B@�D�>��@g����������V�  i����,K�ӃO
=N� �M�H$�6X,�g��}��{����e���C�'�a�8�~.�   X���*u��%���?�b5�A�D�b����@��?#v�?�(��5����� >�7����   i����,K�ӃO
=N� �Md5�AN�?��X�fr��E)!�3:�,9�I��<�cr   K����t���a��IB��IB;�5��5?���?���@�7�?Cӈ�5�����C��7�­*��$   i����,K�ӃO
=N� �Mo�0�u�>#�ќ17��L�O
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
���J�D2�
����0�'.� =PM
A�|A@��`����A�`���
�D  j�Ҩ\@���&7��� �'���f07L6���	��䬕��u	���B1������    �ܧA����@L�          �?���&  "A��*=���@}�~A5���V5���\�A����V�  lnu�aOj�L#) d-�(�%�"�_��5�N~_?ZO�t����JR� ��}��G   z���6.=�VU�        �T����?2�$A#�MA   A	ۻ�pV«*����[�ؑ"ª�;@   lnu�aOj�L#) d/���>T��֛#O�(�a�W�NO�t����JR� ��}��G   ����o�VU�              �?3�A�~?A   A	ۻ��̃«*����[��Wª�;@   lnu�aOj�L#) d1��O\	���GU��s��O�t����JR� ��}��G   �����>�VU�        ��`���y? �zA5�uA   A��J�pV«*�����Ȟ$ª�;@    lnu�aOj�L#) d3�8է�~��_��Q�r�xNO�t����JR� ��}��G   '`����o�VU�        􏒾�Iu?�	�A��{A   A��J��̃«*��p���Wª�;@$   lnu�aOj�L#) d5�Ʋˢߘg0hN(F����O�t����JR� ��}��G   d��=�&BVU�        �J�;�?n�A1��A   A�6��5B�*���U5��4GB��;@   lnu�aOj�L#) d7k��,aɯ�$�lS|c�O�t����JR� ��}��G   ����|�@VU�        ��"���?�1AN��@   A�,:���u@�*���M�֥A��;@   lnu�aOj�L#) d9�`��d
�+�(������ְ�P��M�   
   l��h��BƝ�(����� �	0]�����!E�U�=7O(
�+�(������ְ�P��M�   
   l��h��BƝ�(����� �B���f07L6���	��䬕��u	���B1������   b��>y)A��A        �5��5?s��@���=�8@�3��¯�@q<�A
�+�(������ְ�P��M�   
   l��h��BƝ�(����� ����6�l���c�r��f��r��+�(������ְ�P��M�   
   l��h��BƝ�(����� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   
?  �?1�=�m����Aj��A�?���A   m"�gGSHԺ�P�L�R� �7�ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�A��A@��A        ѷ�  �?��+B�l
?  �?�1<�Nf0@��A2�A� S@��A   m"�gGSHԺ�P�L�R� ���ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�A�lhA��A        ѷ�  �?��+B�l
?  �?�1<��dA��A2�A=�lA��A   m"�gGSHԺ�P�L�R� ���ܝ@��=&�NҲ��{[�=`O�L ����tIj����   h�At6�A��A        ѷ�  �?��+B�l
?  �?�1<���A��A2�A`�A��A   m"�gGSHԺ�P�L�R� ����Ð|z鶷�q�Qc�|�4g{[�=`O�L ����tIj����   s�A�B��A        *9��  �?��+B?p
?  �?�q7��B��A8a�Aq-B��A   n�믬�C�W��V��w �x���K���l��uy��C{[�=`O�L ����tIj����   v9BVFZ�������9�N^���?H��cw�>�1�Ad75A�66B�q����7�<B�/��1�8   n�믬�C�W��V��w �y��y��e4�[~��� �� [V{[�=`O�L ����tIj����   �B�Y����        �m8  �?1TA���>  ,A��B�Y����8B\:X��1�   n�믬�C�W��V��w �zR��O�^�*Sk�\�@/����{[�=`O�L ����tIj����   wB�Q/����        ���<��?��HA���?  ,A��B&U1���2O6BM-��1�   n�믬�C�W��V��w �{���f07L6���	���{[�=`O�L ����tIj����   �b7B�E����        ��/�F:?  @@Y��=  �@�6BSK���\�7B�?��m�   n�믬�C�W��V��w �{(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   Y�+B��E�`��        ��/�F:?  P@��?  �@RZ+B�*L���a,B?0?��k�   n�믬�C�W��V��w �{�f��V]�I���ʪ����0����$P�����L��m�   aA8B��D�`��{38և����/�F:?  P@k) ?] �@��6BăK��� �9B'l>��k�<   n�믬�C�W��V��w �|���f07L6���	���{[�=`O�L ����tIj����   ��8B�`����        ��/�F:?  @@Y��=  �@)h8B��f���h�9BY�Z��m�   n�믬�C�W��V��w �|(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   fM-B"�a�`��        ��/�F:?  P@��?  �@^�,Byh���m�-B�$[��k�   n�믬�C�W��V��w �|�f��V]�I���ʪ����0����$P�����L��m�   m�9B��`�`��{38և����/�F:?  P@k) ?] �@�x8BPxg���4;B�`Z��k�<   o���cL��f��� {���f07L6���	��䬕��u	���B1������   �.���u|��X�A        80?"�9?��@���=��@����tj��T�}A԰ºr��A  o���cL��f��� {���f07L6���	��䬕��u	���B1������   "B�3��X�A        80?"�9?��@���=��@߬��8�?�T�}Ad׮��C&��A  o���cL��f��� {���f07L6���	��䬕��u	���B1������   r���0.��X�A        80?"�9?�(�@���=��@�����%�T�}A\��|���A  o���cL��f��� {���f07L6���	��䬕��u	���B1������   n��Zr���X�A        80?"�9?���@���=��@�{�®D��T�}A�����A  o���cL��f��� {���f07L6���	��䬕��u	���B1������   kh���u���X�A        80?"�9?�@���=��@Ѭ�T��T�}A����6/g��A  o���cL��f��� {!���f07L6���	��䬕��u	���B1������   g����`l��X�A        80?"�9?���@���=��@Uj��E}��T�}Az~���丽�A  o���cL��f��� {"���f07L6���	��䬕��u	���B1������   &/���j@�X�A        80?"�9?z��@���=��@�����	�=T�}A�������@�A  oT7i#@ϳل�� ��$K�!.�y���$��|��
�Ɓ+$Z����q̱�L{[�=`O�L ����tIj����   z�³x�B���AM5?M5?�\��\����?��B�?B���^c�B�*��)��	��B �B�  pH1u�[Ga��Ԓx�w( ��G�b
|B_�@�)��b�B͵bA �   p�Ut�@G\�˭c�[�f �EL��� ]s3�'W���⦏�ޞ�2��r`<\�{�E   �~�A�� �?����>c?�>�f,?f?�Z}?���? ��AXc{A:�������B�C����V  p�Ut�@G\�˭c�[�f �����͔��\� uZ�=}����ޞ�2��r`<\�{�E   !��A��[b��EBľ�N޾��
?�H}?�I�?�݃AW\�A:�[?����B�C���H@w
  p�Ut�@G\�˭c�[�f �ָ|8�[39J,�
1ћfb��   �\��~�V���A        o�9?&-0?��?���=���@ ���Xª��Aa�����Tª:B   q�z��Dإ�B�� �����2�T��[��Y�x�}�9�H
1ћfb��   ���N���A        &-0�o�9?��:@��*=���@4s��5�Tª��ACj��tIª:B   q�z��Dإ�B�� ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   �Ю��0Jª��A        &-0�o�9?���=  �>  @?sǿ�eJª��Am����Iª��A   q�z��Dإ�B�� ����2�T��[��Y�x�0����$P�����L��m�   ��ֿ�e7ª��A        o�9?&-0?��A��*>  �>����	dHª��A@���g&ª��A   q�z��Dإ�B�� �N���2�T��[��Y�x�}�9�H
1ћfb��   Xw���~^���A        o�9?&-0?��:@��*=���@b���Qdª��A�>u�F�Xª:B   q�z��Dإ�B�� �NVz��������A�����2��0����$P�����L��m�   $����'cª��A        o�9?&-0?���=���>  @?9���eZcª��AhN���bª��A   q�z��Dإ�B�� ࣐��f07L6���	��䬕��u	���B1������   >�^��u�8��A        o�9?&-0?  A���=��@�v���{����AX����d�q<�A  q�z��Dإ�B�� ৐��f07L6���	��䬕��u	���B1������   8Hٿ�f7�8��A        o�9?&-0?��A���=��@7S���bH���A9=��k&�q<�A  q�z��Dإ�B�� ᔐ��f07L6���	��䬕��u	���B1������   >�^��u�9B        o�9?&-0?  A���=9�@�v���{��AX����dª:B  q�z��Dإ�B�� �����f07L6���	��䬕��u	���B1������   >�^��u���A        o�9?&-0?  A���=�8@�v���{��q<�AX����d�A  q�z��Dإ�B�� �����f07L6���	��䬕��u	���B1������   8Hٿ�f7���A        o�9?&-0?��A���=�8@7S���bH�q<�A9=��k&�A  q�z��Dإ�B�� �~���f07L6���	��䬕��u	���B1������   8Hٿ�f7�9B        o�9?&-0?��A���=9�@7S���bH�A9=��k&ª:B  q�z��Dإ�B�� 䵲�6�l���c�r��f��r��+�(������ְ�P��M�   �	����d���A&-0?o�9?        ��*>��*>���>p����Yeª��AЄ|�>�d�Uu�A
   q�z��Dإ�B�� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �	����d��X�A&-0?o�9?        ��*>��*>�8@���u�d�Uu�A�	S�Hd�q<�A
�+�(������ְ�P��M�   �	����dsB&-0?o�9?        ��*>��*>�8@p����Ye�AЄ|�>�d�U�B
   q�z��Dإ�B�� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �V����H��X�A&-0?o�9?        ��*>��*>�8@@��tI�Uu�A
   q�z��Dإ�B�� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   �V����HsB&-0?o�9?        ��*>��*>�8@��ÿ�cI�A����=�H�U�B
   q�z��Dإ�B�� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   .�����V� �B�&���U��&���U?��*>��*>  �?������Xª:Ba�����T�U�B
�+�(������ְ�P��M�   }t��H�^� �B�&���U��&���U?��*>��*>��:@���
Zdª:B�����X�U�B
   q�z��Dإ�B�� �ǲ�6�l���c�r��f��r��+�(������ְ�P��M�   �뮿6�N� �B�&���U��&���U?��*>��*>��:@|mÿ��Tª:BDj��tI�U�B
   q�z��Dإ�B�� �Ȑ��f07L6���	����+�(������ְ�P��M�   ςY���u� �B�&���U��&���U?��*>��*>  AH ��*|�ª:B
�u�d�U�B   q�z��Dإ�B�� �ɐ��f07L6���	����+�(������ְ�P��M�   ��ֿ�e7� �B�&���U��&���U?��*>��*>��A����	dHª:B@���g&�U�B   q�z��Dإ�B�� �ѐ��f07L6���	����+�(������ְ�P��M�   ςY���u�Uu�A�&���U��&���U?��*>��*>  AH ��*|�ª��A
�u�d���A   q�z��Dإ�B�� �Ґ��f07L6���	����+�(������ְ�P��M�   ��ֿ�e7�Uu�A�&���U��&���U?��*>��*>��A����	dHª��A@���g&���A   q�z��Dإ�B�� �ڐ��f07L6���	����+�(������ְ�P��M�   �L�/�u�q<�A�&���U��&���U?���=  �<  A� ���x����A�"���d�Ǒ�A   q�z��Dإ�B�� �ې��f07L6���	����+�(������ְ�P��M�    6п(c7�q<�A�&���U��&���U?���=  �<��AP���E]H���A�n��i&�Ǒ�A   q�z��Dإ�B�� �ސ��f07L6���	����+�(������ְ�P��M�   �L�/�u�A�&���U��&���U?���=  �<  A� ���x��8��A�"���d��X�A   q�z��Dإ�B�� �ߐ��f07L6���	����+�(������ְ�P��M�    6п(c7�A�&���U��&���U?���=  �<��AP���E]H�8��A�n��i&��X�A   q�z��Dإ�B�� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   :���&���A&-0?o�9?        ��*>��*>�8@��鿳g&�q<�A~aӿB�%�A
�+�(������ְ�P��M�   :���&sB&-0?o�9?        ��*>��*>�8@>���p&�A5��E�%�U�B
   q�z��Dإ�B�� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   :���&��X�A&-0?o�9?        ��*>��*>�8@��鿳g&�Uu�A~aӿB�%�q<�A
   q�z��Dإ�B�� ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   w�������X�A        &-0�o�9?��*>��*>�8@�
��̃�Uu�A�ѻ�(s��q<�A
��̃�q<�A�ѻ�(s��A
   q�z��Dإ�B�� ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   w��������A        &-0�o�9?��*>��*>���>�`5�aуª��Ao���w��Uu�A
   r�
 �xA�M��������$???��*=��@��@�ֶArv��3VA0~�A�����A(   r�Ώ�N'�9+v�<� �0>��rTl.	ɮ�"�!GQ��3�ޒ�8�����ġ���   r{�A�1�Tu�A        P����?eAu>+? V�=G-lA��©
�AA�A�k��ߗA   r�Ώ�N'�9+v�<� �0�T�u `�'����n:���}$uJ�q�NeȊq�`�1��   ,mkA~���A��?���<T^2�������{?m�c@B�jA*�©�vA�:lA����ߗA�   r�Ώ�N'�9+v�<� �0�}d7�A�\֢.�K5��o�}$uJ�q�NeȊq�`�1��   @�A&R�=y�A��?���<��0�Ep�����.�
̲��ѳ ���u�)���[��    0f��^��B��A              �?��j@���<���@���	��B��A���´��B��Av   r���I����$ޣ6 O�Y�{,�������F��J�=�}$uJ�q�NeȊq�`�1��    0f�´��B��A              �?  �@  �>$��@0f�´X�B�ʵA0f�´؅Bsn�A�   r�˵��L��a�Q�� n76��
[�V��',���✟{[�=`O�L ����tIj����   	�Bf�AQյ@        �w�;d�?4�?b{ATU1A�B�=�@��>��B�_AR�3A   r�˵��L��a�Q�� n;*����p�Ҡ�s�أ���{[�=`O�L ����tIj����   ��B
��@Qյ@�5?�5?��Ӻ��Ӻ4_�>(��A7�3A�7�B��u@��>1��B�=�@R�3A>   r�˵��L��a�Q�� nFr��z�X�'����3MoT��{[�=`O�L ����tIj����   v9BVFZ�Qյ@$��9M�k���?e��w�>�g�A<;A�66B�q� �>7�<B�/�R�3A8   r�˵��L��a�Q�� nJ��y��e4�[~��� �� [V{[�=`O�L ����tIj����   �B�Y�Qյ@        ]�8  �?1TA���>TU1A��B�Y �>�8B\:X�R�3A   r�˵��L��a�Q�� nNR��O�^�*Sk�\�@/����{[�=`O�L ����tIj����   wB�Q/�Qյ@        ���<��?��HA���?TU1A��B&U1 �>2O6BM-�R�3A   r�˵��L��a�Q�� nU�Ѩ.�		l�$V�c�k,Fz}{[�=`O�L ����tIj����   _� B�/�@Qյ@��4?��4��<��@�<+��>55hA�DCAM�B3��@��>q<B���@R�3A4   s.f�`�F`�eS�?��� ����f07L6���	��䬣}$uJ�q�NeȊq�`�1��    !'A�����@          �?���&UB�>r?XU�>���]���R��@��A�̃¨*�@   s.f�`�F`�eS�?��� 䐤�f07L6���	��䬣}$uJ�q�NeȊq�`�1��    !'A�����A          �?���&UB�>r?XU�>���]���Uu�A��A�̃ªʓA   s.f�`�F`�eS�?��� 
���f07L6���	��䬣}$uJ�q�NeȊq�`�1��    !'A�����A          �?���&UB�>r?XU�>���]���Uu�A��A�̃ª��A   s.f�`�F`�eS�?��� A���f07L6���	��䬣}$uJ�q�NeȊq�`�1��    !'A��«
��          �?���&UB�>r?XU�>���]���V�����A�̃�`��   t��M�vI?��`�B�Ӣ d��C�]t�s�Mټ>g�V5`[AO�t����JR� ��}��G   x�A�|�VU�        ���=>�~?� �A�|#B   AlA:�«*��+B��[@��;@X   t�9�@5�e�G6P ��hf;�"�D8f���P3���}$uJ�q�NeȊq�`�1��   	�U��b-.�AC�{>�hm>�?[A?_�A�>A�ǐ@�_��>ªJ�A��A������A  t�9�@5�e�G6P ����wc�	�Y�ZY�Ȳ`�S�@JT`}��������]܄���}   	OF¶�:�U��AA�~?�����; @Ž���?T��?q@�H³�=©jyA��C¸/7�U��A0   t�9�@5�e�G6P ���ǰ���sǿ���Y���{[�=`O�L ����tIj����   	e�S�(�U5�A�6��9w&}�ξ''j?��?k�5@��*=��l��x,ª
�A�ec�`z"��_�A�   t�9�@5�e�G6P ��V����Eo2O{/�M%b�`9���Ѐ&�A ���l�o�O�   	�NF»�:«*xA�Z�6���9�?(��<SU�?�V�?�� >v�H§�=©�vA�DH7©jyA  t�9�@5�e�G6P ��r,`S#�-;��Z��+:&�^*������5/���&9����   	�1H�T{:©�vAC�!��ɣ��:�&�.?)"�?�\>  �?cu��$©�vA��tª�©�vA   t�9�@5�e�G6P ��Wy�f�s7-���^�ϣۨ�������Hd�xw
�A,z¢4&��_�A�   t�9�@5�e�G6P �����H�"i�!��J.�����Ѐ&�A ���l�o�O�   	��#�E�;«*xA����[�6(����?SU�?�V�?�� >`�%�1%?©�vAvM!��8©jyA  t�9�@5�e�G6P ��?��$���je�#l��?7 ^*������5/���&9����   	L�!�<©�vAC�!����#�y7���2?)"�?�\>  �?B*��I$*©�vA�����B$©�vA   t�9�@5�e�G6P �����L[��K�;�
o�\-�aN�1
�A7N�2~S��_�A�   t�9�@5�e�G6P ��V����Eo2O{/�M%b�`9���Ѐ&�A ���l�o�O�   	r%%�]«*xAbZ�60��9�?L��<SU�?�V�?�� >o'�F`©�vA.�"���Y©jyA  t�9�@5�e�G6P ��&v,>��ޔ�����i��E�"^*������5/���&9����   	D#��4]©�vA        ��2?�y7?)"�?�\>  �?'�#&`©�vA��"��DZ©�vA   t�9�@5�e�G6P ��4�D�Î�y6v��2T��������Hd�xw
�ApjQ��{P��_�A�   t�9�@5�e�G6P ����H�"i�!��J.�����Ѐ&�A ���l�o�O�   	��F³�D«*xA;[ȶ�����?L��<SU�?�V�?�� >I���G©�vA#�D�ǉA©jyA  t�9�@5�e�G6P �?��$���je�#l��?7 ^*������5/���&9����   	7�H��D©�vA�?]�갌��2?�y7?)"�?�\>  �?cI��G©�vAHH�H�A©�vA   t�9�@5�e�G6P ����L[��K�;�
o�\-�aN�1
�B�BªJ�A�#��.�!���A  t�9�@5�e�G6P ���wc�	�Y�ZY�Ȳ`�S�@JT`}��������]܄���}   	@r���N>�U��AA�~?�����; @Ž���?T��?q@�%�;W?©jyA���@�8�U��A0   t�9�@5�e�G6P ��ǰ���sǿ���Y���{[�=`O�L ����tIj����   	����g,�U5�A�6��9w&}�ξ''j?��?k�5@��*=���
�A�OB&��_�A�   t�9�@5�e�G6P �V����Eo2O{/�M%b�`9���Ѐ&�A ���l�o�O�   	�q���J>«*xA�Z�6���9�?(��<SU�?�V�?�� >*���A©�vAW����;©jyA  t�9�@5�e�G6P ��r,`S#�-;��Z��+:&�^*������5/���&9����   	�7���C>©�vAC�!��ɣ��:�&�.?)"�?�\>  �?� ­?©�vA�( �29©�vA   t�9�@5�e�G6P �Wy�f�s7-���^�ϣۨ�������Hd�xw
����?���<��0�Ep�����.�
��(  y���D����%(<G ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ��m�v�gAVUN��J	�N��5?�5?d�)?a�O?���B�o��ZbA p1Tl� �lAV�Bh5  y���D����%(<G �t�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   1�=� �IBVUN�N�J	.�5��5?d�)?a�O?���B�QD�uKHB p1X7���JBV�Bh5  y�,�28K��LrTB�: ?Sc��߼�z�.�g`����K�~�AƈP��%ULڝ.�N   �յ½;�@S5�A�:�5[���>3?��6?�V+A_�CA:F@>�����uJ>Uu�A5b���[.AU��A
   y�,�28K��LrTB�: ?S,�H�J%�'���s�fJ���S��C\��/��Ȧ��'���R   [���ﳱ@U��A        �f!<��?/GA��.A  �?�����uJ>U��A5b���[.AU��A   zN��L�GƷH�n�!J� a�;_ܥyh�"fe�O5���RO�t����JR� ��}��G   	�oB)����@        8Խ��~?�݄Bm��B   Ay�B�� �>�o�B3��@�?"A|   {6u��M��4��}' �[�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �
� �IBVUN��J	�N��5?�5?d�)?a�O?���BU��uKHB p1·k}���JBV�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ��� �IBVUN��J	�N��5?�5?d�)?a�O?���B�T�uKHB p1�a���JBV�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   m:��pBVUN�N�J	.�5��5?d�)?a�O?���B���B p1�B��u�BV�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �
��pBVUN�N�J	.�5��5?d�)?a�O?���BU��B p1·k}�u�BV�Bh5  {6u��M��4��}' �7�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ���AVUN�N�J	.�5��5?d�)?a�O?���B�>�<]�A p1 ���AV�Bh5  {6u��M��4��}' �6�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ��OjAVUN��J	�N��5?�5?d�)?a�O?���B(��p eA p1��e�ƝoAV�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   *�O�OjAVUN��J	�N��5?�5?d�)?a�O?���B�&V�p eA p1�-I�ƝoAV�Bh5  {6u��M��4��}' ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   N���AVUN��J	�N��5?�5?d�)?a�O?���B��T�<]�A p1�]�G���AV�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   QL���BVUN��J	�N��5?�5?d�)?a�O?���B��R�.B p1§F�\�BV�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   L?Q�PTJ@VUN��J	�N��5?�5?d�)?a�O?���B��W��5@ p1¡�J���_@V�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   Fj�PTJ@VUN��J	�N��5?�5?d�)?a�O?���Bq	¦5@ p1�����_@V�Bh5  {6u��M��4��}' �\�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �
�PTJ@VUN��J	�N��5?�5?d�)?a�O?���BU�¦5@ p1·k}���_@V�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �
�S&AVUN��J	�N��5?�5?d�)?a�O?���BU�¨� A p1·k}��_+AV�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �
�O:�AVUN�N�J	.�5��5?d�)?a�O?���BU�����A p1·k}¤��AV�Bh5  {6u��M��4��}' �6�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �
�"9�VUN�N�J	.�5��5?d�)?a�O?���BU��͇
� p1·k}�����V�Bh5  {6u��M��4��}' �0�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �
��d��VUN�N�J	.�5��5?d�)?a�O?���BU��?�� p1·k}���V�Bh5  {6u��M��4��}' ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �
�FX��VUN�N�J	.�5��5?d�)?a�O?���BU���� p1·k}���V�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ���"9�VUN�N�J	.�5��5?d�)?a�O?���B�n�͇
� p1�o0�����V�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �4�FX��VUN�N�J	.�5��5?d�)?a�O?���B����� p1����V�Bh5  {6u��M��4��}' �H�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ����d��VUN�N�J	.�5��5?d�)?a�O?���B*,�?�� p1������V�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   0�U��d��VUN�N�J	.�5��5?d�)?a�O?���B�F\�?�� p1MO�����V�Bh5  {6u��M��4��}' �b�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   )iT�FX��VUN��J	�N��5?�5?d�)?a�O?���B��Z����� p1�~�M���V�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ��R�"9�VUN��J	�N��5?�5?d�)?a�O?���BEQY�͇
� p1��WL�����V�Bh5  {6u��M��4��}' �N�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �J�A��BVUN��J	�N��5?�5?d�)?a�O?���B���k�B p1�_��G�BV�Bh5  {6u��M��4��}' �,�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ����BVUN��J	�N��5?�5?d�)?a�O?���B[��µ��B p1�a~�_S�BV�Bh5  {6u��M��4��}' ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �1<����BVUN��J	�N��5?�5?d�)?a�O?���B>�B����B p1��5�uN�BV�Bh5  {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   Z%�B�#����              �?UUu?UUu?��A0�B�z%�V�¯�Bk�!�V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   ]&�B�!$����              �?UUu?UUu?��A1�BN&�V�³�B�6"�V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �3GB� #����              �?UUu?UUu?��A+IEB9�$�V�IB�!�V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �<B�3S����              �?UUu?UUu?��A�:BDU�V��D�=B�HQ�V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   4uBz�S����              �?UUu?UUu?��A�1sB$�U�V���wB��Q�V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �b�B�T����              �?UUu?UUu?��A�m�B1�U�V��>X�B�R�V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�    �BE�T����              �?UUu?UUu?��A�*�B�mV�V��p�B��R�V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   2�GB/������              �?UUu?UUu?��A��EB�p��V���~IB����V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �U�B=������              �?UUu?UUu?��A3`�B����V���J�B����V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �V�BX������              �?UUu?UUu?��A6a�B����V���K�B��V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   ��B
�����              �?UUu?UUu?��A���B_Ɯ�V��Y|�B���V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�    ��B�͗����              �?UUu?UUu?��A���BD���V��U{�B����V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   "�GBᮖ����              �?UUu?UUu?��Ax
FB6���V����IB�ْ�V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   VHBJ
�����              �?UUu?UUu?��AhkFB�/�V�½@JB����V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   x��B�������              �?UUu?UUu?��A#��B�m�V��ͫ�B,1��V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   |��Bv	����              �?UUu?UUu?��A&¤B!�	�V��Ѭ�B����V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �BV9@���              �?UUu?UUu?��A��Br�@V��nݦB� X@V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   �B�nB@���              �?UUu?UUu?��A��BJ�#@V��k܅B�a@V���   {�8�dH��!��E �����2�T��[��Y�xr��(;�{p9DC}�\ə�   M�HBcgK@���              �?UUu?UUu?��A��FB��,@V����JBj@V���   }F壈�H��uz�}a d E�rΛj�/ݿ�}0�j+O�t����JR� ��}��G   ��:��AVU���k0�:	���;�?�XB9��B   A)�������*���:�^�B��;@�  }F壈�H��uz�}a dǢp3!�%��Л����pG8O�t����JR� ��}��G   F3¥�AVU�        	�ż��?d�AB�pA   A,�A���(@�*���Ƒ�Mo�A��;@,   }F壈�H��uz�}a dK<�Z���-���
 A*� �VU�        ����x�?l�3Bk��B   A��J��̃«*���pB�4GB��;@  }F壈�H��uz�}a d0 w��L��6�H�,�i�;�.MO�t����JR� ��}��G   �W��Zf�VU�~R�'5���DU?z�
��O�t����JR� ��}��G   o��f��VU�        ��_=@�?�kgA�%HA   A=��®%«*������7�����;@   }F壈�H��uz�}a d\� J�����^�^�L
��I�O�t����JR� ��}��G   ����J��VU�        #w+=��?
�jA�a4A   A=��-���*�����8�����;@   }F壈�H��uz�}a d�����h`��8�߫S�"�NO�t����JR� ��}��G   �	���zv�VU�        W�#=v�?��rAl�4A   A=���F���*����©
%���;@   }F壈�H��uz�}a d�9�2������C��Y`DoO�t����JR� ��}��G   <x��|���VU�        N<1=��?��}A>GA   A=���*��*���a���N?��;@   }F壈�H��uz�}a d�D�Z[�")p�N~���O�t����JR� ��}��G   �ܸ�i��@VU�        ��?<��?C~A+�0A   A=���E>�*��|7���[.A��;@   ~���.LH�3��/=rs }����f07L6���	��䬕��u	���B1������   =����f��X�A        80?"�9?���@���=��@,����pq�T�}AMB��]]\��A  ~k�c��L]�S��1 A=D���V8 B&�����cfm��Z�AƈP��%ULڝ.�N   U�a�AU5�AA�.-�*B-�{9? q0?�N=ASUA  @>0ci�@Uu�A�@�fAU��A
   ~k�c��L]�S��1 A=��^�X�q���O�۝��S��C\��/��Ȧ��'���R   U�a�AU��A        (�̼��?�s+A��KA  �?0ci�@U��A�@�fAU��A   ~k�c��L]�S��1 An'\]�E ���
   ~k�c��L]�S��1 Ax��^�X�q���O�۝��S��C\��/��Ȧ��'���R   �l����AU��A        9�̼��?�s+A��KA  �?	���h@U��A�Ƒ�9�~AU��A   ~�#eZE��ڂ���!� Gu6��0wX՘��/���)�����
*��=ܩyL�܀   �����<\q�*A������?���&  �@�K�?@k�@�����XՀ��Ü�5�����@�   ~�#eZE��ڂ���!� G���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ��7��XՄ�          �?���&  �@VU�?  �>�c��5���XՈ��c���̃�XՀ�   ~�#eZE��ڂ���!� G�5��|p�#^��E^�h�Mq���u	���B1������   ��W��nUq���$�E=��?���&UUm@LmM?Զ@蘤�༅�[Ut�=.��5��IU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   ������<\q�*A������?���&  �@�K�?@k�@����5"��XՀ�0�|��̃���@�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���7��XՄ�          �?���&  �@VU�?  �>���5���XՈ�0|��̃�XՀ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   ���W��nUq���$�E=��?���&UUm@LmM?Զ@�D��༅�[Ut���}�5��IU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   ���UT������f���f��5?�5?���@�K�?@k�@�����\�XՄ�=���L��� @�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����UT�XՈ�        �5?�5?���@UU�?  �>�`��U]�XՌ�=���UK�XՄ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   ���UT·���r�<r�<��4?��4?TUm@KmM?Զ@={�¾�[�[U|�����i�L�IU�?  ~�#eZE��ڂ���!� u6��0wX՘��/���)�����
*��=ܩyL�܀   ����;������f���f��5?�5?���@�K�?@k�@����D�XՄ�=����3��� @�   ~�#eZE��ڂ���!� ���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����;�XՈ�        �5?�5?���@UU�?  �>�`���D�XՌ�=����2�XՄ�   ~�#eZE��ڂ���!� �5��|p�#^��E^�h�Mq���u	���B1������   ����;·���r�<r�<��4?��4?TUm@KmM?Զ@={�¾?C�[U|�����ij4�IU�?  ~�#eZE��ڂ���!� 1u6��0wX՘��/���)�����
*��=ܩyL�܀   ��¼O������f���f��5?�5?���@�K�?@k�@���¼�!�XՄ�=��¼��� @�   ~�#eZE��ڂ���!� 1���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���¼O�XՈ�        �5?�5?���@UU�?  �>�`�¼O"�XՌ�=��¼O�XՄ�   ~�#eZE��ڂ���!� 1�5��|p�#^��E^�h�Mq���u	���B1������   ��¼O·���r�<r�<��4?��4?TUm@KmM?Զ@={��f� �[U|�������IU�?  ~�#eZE��ڂ���!� Ju6��0wX՘��/���)�����
*��=ܩyL�܀   ��¼� ������f���f��5?�5?���@�K�?@k�@���¼	�XՄ�=���w���� @�   ~�#eZE��ڂ���!� J���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���¼� �XՈ�        �5?�5?���@UU�?  �>�`�¼�	�XՌ�=���w���XՄ�   ~�#eZE��ڂ���!� J�5��|p�#^��E^�h�Mq���u	���B1������   ��¼� ·���r�<r�<��4?��4?TUm@KmM?Զ@={��f:�[U|�����"���IU�?  ~�#eZE��ڂ���!� au6��0wX՘��/���)�����
*��=ܩyL�܀   ���o��������f���f��5?�5?���@�K�?@k�@����o��XՄ�=���o���� @�   ~�#eZE��ڂ���!� a���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����o���XՈ�        �5?�5?���@UU�?  �>�`��o���XՌ�=���o���XՄ�   ~�#eZE��ڂ���!� a�5��|p�#^��E^�h�Mq���u	���B1������   ���o�������r�<r�<��4?��4?TUm@KmM?Զ@={���h��[U|��������IU�?  ~�#eZE��ڂ���!� u6��0wX՘��/���)�����
*��=ܩyL�܀   ���o��������f���f��5?�5?���@�K�?@k�@����o��XՄ�=����&n��� @�   ~�#eZE��ڂ���!� ���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����o���XՈ�        �5?�5?���@UU�?  �>�`��o���XՌ�=����&k�XՄ�   ~�#eZE��ڂ���!� �5��|p�#^��E^�h�Mq���u	���B1������   ���o�������r�<r�<��4?��4?TUm@KmM?Զ@={���h��[U|�����4|q�IU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   ��¼-�������f���f��5?�5?���@�K�?@k�@������XՄ�=��½-���� @�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���¼-��XՈ�        �5?�5?���@UU�?  �>�`����XՌ�=��½-��XՄ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   ��¼-������r�<r�<��4?��4?TUm@KmM?Զ@={���[U|�����hغ�IU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   ����ȿ�����f���f��5?�5?���@�K�?@k�@����y[h�XՄ�=���8$�>�� @�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����ȿXՈ�        �5?�5?���@UU�?  �>�`��y[t�XՌ�=����.?XՄ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   ����ȿ����r�<r�<��4?��4?TUm@KmM?Զ@={��#[�[U|����y�>IU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   �����@�����f���f��5?�5?���@�K�?@k�@������@XՄ�=���A�� @�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ������@XՈ�        �5?�5?���@UU�?  �>�`����@XՌ�=���AXՄ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   �����@����r�<r�<��4?��4?TUm@KmM?Զ@={�½Y�@[U|�����4�AIU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   ���\A�����f���f��5?�5?���@�K�?@k�@����;AXՄ�=���}A�� @�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����\AXՈ�        �5?�5?���@UU�?  �>�`��8AXՌ�=����k�AXՄ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   ���\A����r�<r�<��4?��4?TUm@KmM?Զ@={���,?A[U|�����4�zAIU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   ����s�A�����f���f��5?�5?���@�K�?@k�@������AXՄ�=������A�� @�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����s�AXՈ�        �5?�5?���@UU�?  �>�`���s�AXՌ�=����s�AXՄ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   ����s�A����r�<r�<��4?��4?TUm@KmM?Զ@={��o��A[U|�����I�AIU�?  ~�#eZE��ڂ���!� u6��0wX՘��/���)�����
*��=ܩyL�܀   ����s�A�����f���f��5?�5?���@�K�?@k�@�������AXՄ�=������A�� @�   ~�#eZE��ڂ���!� ���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����s�AXՈ�        �5?�5?���@UU�?  �>�`���s�AXՌ�=����s�AXՄ�   ~�#eZE��ڂ���!� �5��|p�#^��E^�h�Mq���u	���B1������   ����s�A����r�<r�<��4?��4?TUm@KmM?Զ@={��o��A[U|�����I�AIU�?  ~�#eZE��ڂ���!� u6��0wX՘��/���)�����
*��=ܩyL�܀   �����B�����f���f��5?�5?���@�K�?@k�@�����BXՄ�=����'"B�� @�   ~�#eZE��ڂ���!� ���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ������BXՈ�        �5?�5?���@UU�?  �>�`����BXՌ�=�����"BXՄ�   ~�#eZE��ڂ���!� �5��|p�#^��E^�h�Mq���u	���B1������   �����B����r�<r�<��4?��4?TUm@KmM?Զ@={��6}B[U|����R!BIU�?  ~�#eZE��ڂ���!� 9u6��0wX՘��/���)�����
*��=ܩyL�܀   ����g2B�����f���f��5?�5?���@�K�?@k�@�����'*BXՄ�=����:B�� @�   ~�#eZE��ڂ���!� 9���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �����g2BXՈ�        �5?�5?���@UU�?  �>�`���g)BXՌ�=����g;BXՄ�   ~�#eZE��ڂ���!� 9�5��|p�#^��E^�h�Mq���u	���B1������   ����g2B����r�<r�<��4?��4?TUm@KmM?Զ@={��6�*B[U|�����9BIU�?  ~�#eZE��ڂ���!� Nu6��0wX՘��/���)�����
*��=ܩyL�܀   ���VB�����f���f��5?�5?���@�K�?@k�@���jNBXՄ�=���^B�� @�   ~�#eZE��ڂ���!� N���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ����VBXՈ�        �5?�5?���@UU�?  �>�`��MBXՌ�=���_BXՄ�   ~�#eZE��ڂ���!� N�5��|p�#^��E^�h�Mq���u	���B1������   ���VB����r�<r�<��4?��4?TUm@KmM?Զ@={���?OB[U|�����,^BIU�?  ~�#eZE��ڂ���!� eu6��0wX՘��/���)�����
*��=ܩyL�܀   ��*oB�����f���f��5?�5?���@�K�?@k�@����fBXՄ�=��jwB�� @�   ~�#eZE��ڂ���!� e���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ���*oBXՈ�        �5?�5?���@UU�?  �>�`�*fBXՌ�=��*xBXՄ�   ~�#eZE��ڂ���!� e�5��|p�#^��E^�h�Mq���u	���B1������   ��*oB����r�<r�<��4?��4?TUm@KmM?Զ@={��׿gB[U|�����,�vBIU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   b^H���<\q�*A������?���&  �@�K�?@k�@b�P�5"��XՀ�b@��̃���@�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   b^H7��XՄ�          �?���&  �@VU�?  �>b^Q�5���XՈ�b^?��̃�XՀ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   b^HW��nUq���$�E=��?���&UUm@LmM?Զ@�O�༅�[Ut���@�5��IU�?  ~�#eZE��ڂ���!� �u6��0wX՘��/���)�����
*��=ܩyL�܀   �����<\q�*A������?���&  �@�K�?@k�@���5"��XՀ��U��̃���@�   ~�#eZE��ڂ���!� ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   ��7��XՄ�          �?���&  �@VU�?  �>���5���XՈ�����̃�XՀ�   ~�#eZE��ڂ���!� ��5��|p�#^��E^�h�Mq���u	���B1������   ��W��nUq���$�E=��?���&UUm@LmM?Զ@X �5҄�[Ut�+��IU�?  ~�#eZE��ڂ���!� 
*��=ܩyL�܀   j�������<\q�*A������?���&  �@�K�?@k�@j��5"��XՀ�j���̃���@�   ~�#eZE��ڂ���!� 
5��fz
��,�A=���"J���B�   ~�#eZE��ڂ���!� $Ǯ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    =k�¼� ��m
5������,�A=���4|h��B�   ~�#eZE��ڂ���!� �Ǯ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    =k��o����m
5��#��,�A=����<Y?�B�   ~�#eZE��ڂ���!� �Ǯ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    =k���ȿ�m
5���,6A�,�A=�����A�B�   ~�#eZE��ڂ���!� �Ǯ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    =k��\A�m
5��o�A�,�A=�����A�B�   ~�#eZE��ڂ���!� Ǯ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    =k���s�A�m
5��6=B�,�A=���#B�B�   ~�#eZE��ڂ���!� Ǯ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    =k����B�m
5��6�(B�,�A=��<B�B�   ~�#eZE��ڂ���!� 
5���eB�,�A=���,�xB�B�   ~�#eZE��ڂ���!� Ǯ�lOy�(p{�����GL��א�� �s�gtQ�#�e;$,�    =k�*oB�m
*��=ܩyL�܀   ���¼O�$kL���}:��}��5��5?���@��@H��@�U�¼�!«���=��¼����   �Q���I{��|��$# ����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   �0�¼O«���        �5��5?���@UU)@  �>=+�¼O"�V5�����¼O�V5��   �Q���I{��|��$# ��YB�n�������Fҫԕ��u	���B1������   ���¼O¬jL��6��6<9�4�:�4?TUm@XD�>��@����f� ����������W�  �Q���I{��|��$# �
*��=ܩyL�܀   ���¼� �$kL���}:��}��5��5?���@��@H��@�U�¼	«���=���w�����   �Q���I{��|��$# �
A0�y@@��`��!�eA�`���
�D  ���G͆i���E �Ґ��f07L6���	��䬕��u	���B1������    w)A����@L�          �?���&  "A��*=���@�R�@5���V5��w)cA����V�  ���G͆i���E ���{�Ɔ���+Yw�������}$uJ�q�NeȊq�`�1��    �t/�����J����<�<��4?$�4?ٗ�>O/A�M
A���@��`��6@�`���
�D  ���G͆i���E ���f07L6���	��䬕��u	���B1������    �t/�����@L�          �?���&  "A��*=���@Q���5���V5��]�@����V�  �n�_F=�#Ih n*�ͥ�j1�>`�۰L��ЉO�t����JR� ��}��G   K���`���e�        �pC<V�?���A��,A   A	���T��������I������   �n�_F=�#Ih n,�Cgw��=����$�V]�AO�t����JR� ��}��G   8����[���e�        �~O�۫?�A�A��A   A	���u������hH���E���$   �n�_F=�#Ih n. ӽ�������پN
�ط�O�t����JR� ��}��G   �4�h���e�        ��s���?b-NA�'bA   A�J�u������0��8U���   �n�_F=�#Ih n0�2��h*f�`DVy�tF�֯O�t����JR� ��}��G   ����^����e�9���65�=�V�,?���AیWA  A4���a��������奠����   �n�_F=�#Ih n2+4D��c�+��k��vK&yO�t����JR� ��}��G   s'f­���e�        @Wp=�?�cMA4�aA   AY�|�u�������O��8U���   �n�_F=�#Ih n4H�.E�㌰H)|V
ϗ�_"O�t����JR� ��}��G   �Lf��q���e�              �?TU5A  H@   AY�|���������O�������   �n�_F=�#Ih n6��1��*�d��P.)�z�Y/O�t����JR� ��}��G   Y�3��q���e�              �?TU5A  H@   A�J���������L�������   �n�_F=�#Ih n8o�qW�BL�U�fF���L�j�O�t����JR� ��}��G   �S)�$.��e�              �?(:�@n<�@   AZw5�@�X����0�	p���   �n�_F=�#Ih n:N!-��X�&�%�֖]	��O�t����JR� ��}��G   ~�p�$.��e�              �?���@n<�@   AY�|�@�X������d�	p���   �n�_F=�#Ih n<έ
4�v�ܸ\V}�O�t����JR� ��}��G   ����c	�@�e�        Q�ý��~?��<A�)A   A�S��nRY?������'�A��   �Q��0�C��Up��� ���/}��4l�|v�06�>ON&KQ�!��(�!D����;�   @[5��(iB`��        ���;��?Ś?�
�D�Z[�")p�N~���O�t����JR� ��}��G   �ܸ�i��@�e�        ��?<��?C~A+�0A   A=���E>���|7���[.A��   �����K=���U�3$ n�9�2������C��Y`DoO�t����JR� ��}��G   <x��|����e�        N<1=��?��}A>GA   A=���*�����a���N?��   �����K=���U�3$ n�����h`��8�߫S�"�NO�t����JR� ��}��G   �	���zv��e�        W�#=v�?��rAl�4A   A=���F�������©
%���   �����K=���U�3$ n\� J�����^�^�L
��I�O�t����JR� ��}��G   ����J���e�        #w+=��?
�jA�a4A   A=��-��������8�����   �����K=���U�3$ n��jv~x�3�RL���dr
��O�t����JR� ��}��G   o��f���e�        ��_=@�?�kgA�%HA   A=��®%��������7�����   �����K=���U�3$ nB7%%7�[�u�·��u2-`O�t����JR� ��}��G   Ф�²�8��e�        ��J=}�?��[A5}7A   A=����6M��������
u?�?�A��[A   A=����̃�����ǯ�zHL���   �Y�_�L����gJr�A �(��x
?ŧ��NB�zB�/��4�[BU�B   �Y�_�L����gJr�A ���C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W�����!B �B        �5��5?��^@��J?��
?ŧ�0�B�zB�/��(BU�B   �Y�_�L����gJr�A ���C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W������A �B        �5��5?��^@��J?��
?ŧ¤��A�zB�/��W~�AU�B   �Y�_�L����gJr�A � �C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W����[kA �B        �5��5?��^@��J?��
?ŧ�+�OA�zB�/��I��AU�B   �Y�_�L����gJr�A ��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W���{�? �B        �5��5?��^@��J?��
?ŧV�=�zB�/��R�c@U�B   �Y�_�L����gJr�A ��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W���=1� �B        �5��5?��^@��J?��
?ŧ��M��zB�/��jb�U�B   �Y�_�L����gJr�A ��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W����Ŀ� �B        �5��5?��^@��J?��
?ŧ�(����zB�/��tױ�U�B   �Y�_�L����gJr�A ��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W����S� �B        �5��5?��^@��J?��
?ŧJªzB�/��A]�U�B   �Y�_�L����gJr�A ��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W����D� �B        �5��5?��^@��J?��
?ŧ���KªzB�/��q�=�U�B   �Y�_�L����gJr�A ��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    (����D� �B              �?��^@��J?��
?~2��s�FªzB�;���YC�U�B   �Y�_�L����gJr�A ��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    J]��D� �B              �?��^@��J?��
?�@d�s�FªzBWSV��YC�U�B   �Y�_�L����gJr�A ��C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    v�$��D� �B              �?��^@��J?��
?#�+�s�FªzB����YC�U�B   �Y�_�L����gJr�A �	�C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    �����D� �B              �?��^@��J?��
?���s�FªzB=����YC�U�B   �Y�_�L����gJr�A �
���f07L6���	���r��(;�{p9DC}�\ə�   ���A��BU%B   '`W�  �?���&�C�A   ?  @?=���A�BU�BWz��A�BU�B   �Y�_�L����gJr�A ����f07L6���	���r��(;�{p9DC}�\ə�   ��A��BU%B              �?���A   ?  @?Wz��A�BU�B�S��A�BU�B   �Y�_�L����gJr�A ����f07L6���	���r��(;�{p9DC}�\ə�   �� �yBU%B              �?���A   ?  @?Wz�� �xBU�B�S�� �zBU�B   �Y�_�L����gJr�A �
�¬� �U%B�p�1z����?�wJ?�ۏA   ?  @?�	���C�U�B�
��u���U�B   �Y�_�L����gJr�A �R���f07L6���	���r��(;�{p9DC}�\ə�   _���A�0�U%B              �?��mA   ?  @?Wz��A�1�U�Bg���A�/�U�B   �Y�_�L����gJr�A �S���f07L6���	���r��(;�{p9DC}�\ə�   ⹖�M#�U%B              �?Z|A   ?  @?Wz��M$�U�Bl���M"�U�B   �Y�_�L����gJr�A �T���f07L6���	���r��(;�{p9DC}�\ə�   �D��Ǚ�U%B              �?��A   ?  @?Wz��Ǚ
)��jp��p�[<�F�Lt��չa/g�rj�   �ѹA� �h[A�\?�@?�;��%
����u@�H@ �AlA�'�UՁ@5� B�d�R�NA�   ���r�N���X���� ]Le��kD)=L�韔�����}$uJ�q�NeȊq�`�1��   ;2�A�$(��	A��?��?�B���@���zU>ءA@%��AlAp�(�:*K@ң B�'�R�NA,   ���r�N���X���� ]W��7.��e�5�0�� y[�}$uJ�q�NeȊq�`�1��   XL�A��/	A��?����^���\�>L{U>�rB@(��AlA�d�:*K@�� Bp��R�NA,   ��W��7OC�iC&�4p :5��=:�c!�[��s���ޞ�2��r`<\�{�E   ��?��xT�'��xǴ>�Ǵ���0�?� >'�U?�|A K��ٸT�N&�V�J?�8T� p��  ��W��7OC�iC&�4p 
M~�e��[�l���wk�ޞ�2��r`<\�{�E   �9��EF��M¥��;bV>(K?%���2'?�7]?�A K���#G�N&�V�J?..D� p�7  �\D���Eq�tJc��� $��1�N��.D���z�UduG�������Hd�xw
��@��h@              �?  @@Z��=  �@�ڬB\~@��>�ڲB\��@��@   �t.�C���)���� ]��:-��'�%r<�t��7�6A�}$uJ�q�NeȊq�`�1��   �گB&s@��l@              �?  P@  �?  �@К�B�f�?��>��B�f�?��@   �t.�C���)���� ]�����,��u�+�~{�A^-}�0����$P�����L��m�   �گB
��@��l@:�          �?  P@k) ?] �@К�B
�@��>��Bˏ@��@<   �t.�C���)���� ]����f07L6���	���{[�=`O�L ����tIj����   &�B
��@��h@          �?      @@Z��=  �@&�B�Æ@��>&�BaR�@��@   �t.�C���)���� ]�(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   &�B]�@��l@          �?      P@  �?  �@&��B]�@��>&0�B]�@��@   �t.�C���)���� ]��f��V]�I���ʪ����0����$P�����L��m�   &�B
��@��l@    :8  �?      P@k) ?] �@&��B&s@��>&0�B
��@��@<   �t.�C���)���� ]����f07L6���	���{[�=`O�L ����tIj����   �3B�'�@��h@          �?      @@Z��=  �@�-B�`�@��>�9B5��@��@   �t.�C���)���� ]�(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   �3B�PA��l@          �?      P@  �?  �@��,B�PA��>��9B�PA��@   �t.�C���)���� ]��f��V]�I���ʪ����0����$P�����L��m�   �3B�/�@��l@    :8  �?      P@k) ?] �@��,B�/�@��>��9B�/�@��@<   �t.�C���)���� ]����2�T��[��Y�x{[�=`O�L ����tIj����   k�B�'�@��h@              �?  @@Z��=  �@k�B���@��>k�B/7�@��@   �t.�C���)���� ]��:-��'�%r<�t��7�6A�}$uJ�q�NeȊq�`�1��   k�B�/�@��l@              �?  P@  �?  �@k,B�G@��>k,B�G@��@   �t.�C���)���� ]�����,��u�+�~{�A^-}�0����$P�����L��m�   k�B�/�@��l@:�          �?  P@k) ?] �@k,B�g�@��>k,B�g�@��@<   �JՋϡ@�a�1��W�  >��+}>��<L2�&V�{[�=`O�L ����tIj����   ]՛���� `�A�3H�3�3�!�G?+
��I�����vAi��¡L���J�A   �JՋϡ@�a�1��W�  y}���I�j������I{[�=`O�L ����tIj����   ������ `�A        �^V�/�?.��?Z�@��A����N�����vAO7��SU���J�A   �JՋϡ@�a�1��W�  ���*<<)�۲4:1Rr�/����{[�=`O�L ����tIj����   /���� `�A        ��7�  �?���>�l�@��A���������vA�"��즊��J�A   �JՋϡ@�a�1��W�  �'g�#7Bd�ƤCƈY^��{[�=`O�L ����tIj����   ����;r� `�A        ��y=�?wh�?bk�@��A����ۊ���vA�����N��J�A   �JՋϡ@�a�1��W�  �+B��c^JCn価�r A��{[�=`O�L ����tIj����   �����#� `�A        �><�}?�S@g�@��A���qP���vA
���   �'�J���In	�| ��h �5�]HUqy���*2;oAu{[�=`O�L ����tIj����   b����AV����Y��        ��?���?,[�BL
WA�ӄ�;� � P�)��^�B�
��w   �6s�;$A�ǡj�" ���2q�>M���U�<(�#�U{[�=`O�L ����tIj����   [D��pu�Uu�A��9          �? �*>��6A��?o��Dv����A���p�a@���A   �6s�;$A�ǡj�" ��Ck��N
A��qR���Y{[�=`O�L ����tIj����   "M���Uu�A              �?TU�A �*>���?Y�|�?;����A�L��������A   �6s�;$A�ǡj�" �8~PB1��q�cf�R�}N N{[�=`O�L ����tIj����   R@������Uu�A�5?�5?
��9����*>��A�h�?q��?;����A��]��������A   ���XnG���q��_ 	?�`���Ö|�1����sK�x�v{[�=`O�L ����tIj����   áN�S�hA��A        f<��~�?��A[�o?  �?o��_�bA��Aye�G�nA��A   ���XnG���q��_ 	jFc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   ��m�DLA��A              �?�j
?��*A  �?�o¦�[@��A��l��aA��A   ���XnG���q��_ 	�Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   u�u�S&A��A              �? �W@�j
?  �?]�|���!A��A�o¨d*A��A   ���XnG���q��_ 	��i�߱�����1��,,kr<{[�=`O�L ����tIj����   ����?9��Uu�A              �?SF�A��*>���?q��������A�\��������A   ���XnG���q��_ 	��i�߱�����1��,,kr<{[�=`O�L ����tIj����   "M�?9��Uu�A              �?TU�A��*>���?Y�|�������A�L������A   ���XnG���q��_ 	Fc�Rf��Ni��YKlڹT��{[�=`O�L ����tIj����   Z=��d����A              �?� B�j
?  �?�~�����A	���?;����A   ���XnG���q��_ 	
۪,=�G�����<ߡ%�#.{[�=`O�L ����tIj����   �E�!�uB��A        :��?5�KB���@  �?-}��gB��A~�E�
/�B��A   ��kӭAl��x�lz�� G|y�a�wD*�k2��L2�O�t����JR� ��}��G   �<�������A        ��9=f�?B��A���A   A ���>����ASF��m@V�BL   ��kӭAl��x�lz�� G~H���urS�^�=�N/�a�jO�t����JR� ��}��G   �3P�������A�ܰ�����?@�n=���A�-�A  A)��@�N����A ¦�{@V�B�   ��kӭAl��x�lz�� G���fܯ�|��#lMz��UiO�t����JR� ��}��G   �_��������A:X%.�q�.�
�������V�BT   ��kӭAl��x�lz�� G��v���<�o��Wm�63�O�t����JR� ��}��G   �q���������A        �F����?(�A��A   A	����������A��I����V�B   ��kӭAl��x�lz�� G���.n��\��)n�`�0�rҧO�t����JR� ��}��G   8����[�����A        �~O�۫?�A�A��A   A	���u������AhH���E�V�B(   �0ǎ�G
I$��z3{[�=`O�L ����tIj����   {?��	��BV�              �?�YB  $@V�&A�U��	n�B �+�)��	��B�:�   �`B�U_Ap�������( D�HpP����٠�RMX���M�p�O�t����JR� ��}��G   o�A��X«��A        �XO>n�z?cB�A�&�A   A=�@�̃«��A�� B�V+�V�B`   �`B�U_Ap�������( D��8է�~��_��Q�r�xNO�t����JR� ��}��G   '`����o«��A        􏒾�Iu?�	�A��{A   A��J��̃«��Ap���W�V�B$   �`B�U_Ap�������( D���O\	���GU��s��O�t����JR� ��}��G   �����>«��A        ��`���y? �zA5�uA   A��J�pV«��A���Ȟ$�V�B    �`B�U_Ap�������( D����>T��֛#O�(�a�W�NO�t����JR� ��}��G   ����o«��A              �?3�A�~?A   A	ۻ��̃«��A��[��W�V�B   �`B�U_Ap�������( D��(�%�"�_��5�N~_?ZO�t����JR� ��}��G   z���6.=«��A        �T����?2�$A#�MA   A	ۻ�pV«��A��[�ؑ"�V�B   �i�K��A0�Nc��I� d�&� ԙ��m��
!��� %O�t����JR� ��}��G   .-��)U��VU������5��=�J�+?���A��^A  A4���a���*���S���E����;@�   �i�K��A0�Nc��I� d�+4D��c�+��k��vK&yO�t����JR� ��}��G   s'f­��VU�        @Wp=�?�cMA4�aA   AY�|�u����*���O��8U���;@   �i�K��A0�Nc��I� d� ӽ�������پN
�ط�O�t����JR� ��}��G   �4�h��VU�        ��s���?b-NA�'bA   A�J�u����*��0��8U���;@   �i�K��A0�Nc��I� d���1��*�d��P.)�z�Y/O�t����JR� ��}��G   Y�3��q��VU�              �?TU5A  H@   A�J������*���L�������;@   �i�K��A0�Nc��I� d�H�.E�㌰H)|V
ϗ�_"O�t����JR� ��}��G   �Lf��q��VU�              �?TU5A  H@   AY�|������*���O�������;@   �i�K��A0�Nc��I� d�N!-��X�&�%�֖]	��O�t����JR� ��}��G   ~�p�$.�VU�              �?���@n<�@   AY�|�@�X��*����d�	p���;@   �i�K��A0�Nc��I� d�o�qW�BL�U�fF���L�j�O�t����JR� ��}��G   �S)�$.�VU�              �?(:�@n<�@   AZw5�@�X��*��0�	p���;@   �i�K��A0�Nc��I� d��]�Lߣ�
W%.�C�����O�t����JR� ��}��G   ��}�X���VU�3W=��?�h�,2�3-u�@���A   A)�� G���*��,�r�G����;@�   ����mH��Á	�s�� ����f07L6���	���{[�=`O�L ����tIj����   
�ʐ��f07L6���	��䬣}$uJ�q�NeȊq�`�1��   5
�@/.D����              �?��*>���@   ?�_�@��S������@��4����   ���5?Lڎ�I��_�V 
ǹ�
��l�'��K@wC�H,[��}$uJ�q�NeȊq�`�1��   ,׏�/.4«	�s��s�>�A1��A1? �*>�2pAСSA;P'���4�V��pZA��3����   ���5?Lڎ�I��_�V 
���X �*��'��8����̣}$uJ�q�NeȊq�`�1��   ׁ��/.G«���*�0?*�0?��>��> �*>,�IAũLA;P���G�����_�@��F�V5��   ���5?Lڎ�I��_�V 
�j��_�"�~�����ڙ�Z�}$uJ�q�NeȊq�`�1��   ���/.T�/��������>6Q1�6Q1? �*>|p�AU�4@��)���T����pZA��S�V5��   �k�i�bF񰖐u� 
;��*?ۘ�2֕J£}$uJ�q�NeȊq�`�1��    赼´x�B�8B          �?���%  �@  �>�9�@��´8�B���A赸´��B��B�   ��oC��@��~����" ?a�2�L�&�l��V1�������AƈP��%ULڝ.�N   ��v��V5�A��H5z3嶣�~?���=��OA=�=A`(@>���§{*�Uu�Az���m,�>U��A
   ��oC��@��~����" ?a�'8�e�ʥ���nT~Y��S��C\��/��Ȧ��'���R   �<������U��A        FC�=��~?�tTAn|NA  �?���§{*�U��Az���m,�>U��A   ��oC��@��~����" ?i^�%ٱ���A�N�ȉ�+��AƈP��%ULڝ.�N   �E����w�U5�Aʟ)5aa��e?%��=)�=A�i%AR+@>����,=��Uu�A����4�'�U��A
   ��oC��@��~����" ?i�wɠ��L#@��-��<�S��C\��/��Ȧ��'���R   J˶�w�U��A        �n�=Fl?� CA��5A  �?����,=��U��A����4�'�U��A   ��oC��@��~����" ?q>;�ɋuk���,R��~����AƈP��%ULڝ.�N   4ȷ���V5�A��l5�*	���~?�پ=�7<A�+A�+@>���°$��Uu�A�����!��U��A
   ��oC��@��~����" ?q�VYL��."�^�t �aݳS��C\��/��Ȧ��'���R   �Q������U��A        ]<�=x�~?K@A�:A  �?���°$��U��A�����!��U��A   ��oC��@��~����" ?}"=�y+����	�%�'J�AƈP��%ULڝ.�N   f)���1]�S5�A�*6"`z7��7��2?*&�@��A�Y@>����jDl�Uu�AH��]�L�U��A
   ��oC��@��~����" ?}�FeK��o-,1�C���S��C\��/��Ȧ��'���R   o��¿�\�U��A        ��<_�? 0AˇA  �?����jDl�U��AH��]�L�U��A   ��oC��@��~����" ?�_����9� ���i������AƈP��%ULڝ.�N   "m��¹8�V5�AG�P�s����}?uG�`x8A�kAAW+@>����j2M�Uu�A#����$�U��A
   ��oC��@��~����" ?��vL]G\�T�s��w�fuS��C\��/��Ȧ��'���R   iݸ�b�8�U��A        U��}?8�3A��3A  �?����j2M�U��A#����$�U��A   ��oC��@��~����" ?�*�9R����{*TmUN�K��AƈP��%ULڝ.�N   gշ�l��U5�A�^���㶆;?w����7A�+EAi(@>����7%�Uu�AO����@��U��A
   ��oC��@��~����" ?���! �����(�!���w�S��C\��/��Ȧ��'���R   A[�����U��A        P����I?��0A��5A  �?����7%�U��AO����@��U��A   ��oC��@��~����" @3Dt�Ɲ:$�h:h��5�{[�=`O�L ����tIj����   =����� `�AYs51  �?-?�� +�2��=-؋B��F@����jDl�U��A���]�-A���An   ��oC��@��~����" @j�;\�OP�xSv�_z9��
�ط�O�t����JR� ��}��G   �4�h�����A        ��s���?b-NA�'bA   A�J�u������A0��8U�V�B   �`WQ�B܂}�ς�f F���1��*�d��P.)�z�Y/O�t����JR� ��}��G   Y�3��q�����A              �?TU5A  H@   A�J��������A�L�����V�B   �`WQ�B܂}�ς�f F�H�.E�㌰H)|V
ϗ�_"O�t����JR� ��}��G   �Lf��q�����A              �?TU5A  H@   AY�|��������A�O�����V�B   �`WQ�B܂}�ς�f F�9�
�͘�ɋV���O�O�t����JR� ��}��G   ~�p�$.����A              �?���@n<�@   AY�|�@�X����A��d�	p�V�B   �`WQ�B܂}�ς�f F��.o<��<M�?� :+ˑM^O�t����JR� ��}��G   �S)�$.����A              �?(:�@n<�@   AZw5�@�X����A0�	p�V�B   ��!�N����;��F� 
���	Q��_5����y�g;Rt]�}$uJ�q�NeȊq�`�1��   ����/.T«�¢�1?��1?s�>s�> �*>�
�@��@��)���T� p!�+ק���S�V��   �DInR�B*�*~�W#�� �T�
����/��/��N����E��b   Ӏ�X/��  �A��'�h�=U�~?ڋ?e
A����Q%����vA�S�
��  �A��'�i�=U�~?�ً?6<5��
A�"��^ ����vAm��4$|����A   �DInR�B*�*~�W#�� �T�,V߷K����	�>��$�kś{[�=`O�L ����tIj����   ���ߜ��  �A��뼾0(�R�=;�~?ڋ?���>YHA�"��Q%����vA�S�4$|����A   �DInR�B*�*~�W#�� ʡT�V!Q6���P�$�z��3�/��/��N����E��b   �S��5����ʝA        v�S=��?��?k ?TU	A���jQ����vA�ȗ������A   �DInR�B*�*~�W#�� ʡ�b8
   �DInR�B*�*~�W#�� ʭ=KG���hA�+AvW��YZ�/��/��N����E��b   ����\���ʝA        �c�<��?�a?=B@TU	A����a����vA���������A   �DInR�B*�*~�W#�� ʭR�s�7�=\���6��[nU�����n��\w&e�mO�[   ����)���ʝA              �?  �?��@TU	A����a����vA���������A   �DInR�B*�*~�W#�� ʭI��JL��2�\L!�Ui�{[�=`O�L ����tIj����   Q����)���ʝA              �? U�>��@TU	A����a����vA���������A   �DInR�B*�*~�W#�� ʱ�A��2A���9��Na�Z<p{[�=`O�L ����tIj����   /���u����ʝA�5?�5?�#��#��U�>��Y@�m	A��� G����vA�S��������A   �DInR�B*�*~�W#�� ʱ�F�����\\)5�u'�ҟ�����n��\w&e�mO�[   /��� G���ʝAR�3?R�3?�i���i��  �?�z�@�A��� G����vA�S�� G����A   �DInR�B*�*~�W#�� ʱ2R:�&��uA���*\͈�/��/��N����E��b   /��������ʝAR�3?R�3?�i���i��  �?�z�@�A���������vA�S��������A   ����3�K'�[�nB��� yE���f07L6���	���r��(;�{p9DC}�\ə�   ��+�B���A              �?���A   ?  @?Wz��+�B���A�S��+�B���A   ����3�K'�[�nB��� y[���f07L6���	���r��(;�{p9DC}�\ə�   ���+�B���A   '`W�  �?���&�C�A   ?  @?=���+�B���AWz��+�B���A   ����3�K'�[�nB��� yn���f07L6���	���r��(;�{p9DC}�\ə�   �»��A���A              �?���A   ?  @?Wz�»��A���A�S��]n B���A   ����3�K'�[�nB��� y����f07L6���	���r��(;�{p9DC}�\ə�   ��»��A���A   '`W�  �?���&�C�A   ?  @?=��»��A���AWz��]n B���A   ����3�K'�[�nB��� y����f07L6���	���r��(;�{p9DC}�\ə�   �¯��A���A              �?���A   ?  @?Wz�¯��A���A�S�¯��A���A   ����3�K'�[�nB��� y����f07L6���	���r��(;�{p9DC}�\ə�   ��¯��A���A   '⏁  �?��&�C�A   ?  @?=��¯��A���AWz�¯��A���A   ����3�K'�[�nB��� yА��f07L6���	���r��(;�{p9DC}�\ə�   �£�A���A              �?���A   ?  @?Wz�£�A���A�S�£�A���A   ����3�K'�[�nB��� y�f07L6���	���r��(;�{p9DC}�\ə�   ��£�A���A   '`W�  �?���&�C�A   ?  @?=��£�A���AWz�£�A���A   ����3�K'�[�nB��� z
���f07L6���	���r��(;�{p9DC}�\ə�   �»ԃA���A              �?���A   ?  @?Wz�»ԁA���A�S�»ԅA���A   ����3�K'�[�nB��� z&���f07L6���	���r��(;�{p9DC}�\ə�   ��»ԃA���A   '`W�  �?���&�C�A   ?  @?=��»ԁA���AWz�»ԅA���A   ��� ?UBR�`��+� �됤�f07L6���	����0����$P�����L��m�   �c�����A��xA        ��?&�̼+��@��*>  �>B���>}A��vAÅ�����A��zA   ��� ?UBR�`��+� ����2�T��[��Y�x�}�9�H
1ћfb��   R���9a|A�ʖA        ��?&�̼ �?���=���@N���~P{A��vAV����q}A��A   ��� ?UBR�`��+� �4���2�T��[��Y�x�}�9�H
1ћfb��   ����%{A�ʖA        '��<��?��:@��*=���@ �T�yA��vA���f�|A��A   ��� ?UBR�`��+� �4&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   w���87zAUu�A        '��<��?���=  �>  @?�S �P�vAUu�Ar���q}AUu�A   ��� ?UBR�`��+� ћ���2�T��[��Y�x�0����$P�����L��m�   �`�;�sA��xA        ��?&�̼VUMA��*>  �>{4��CmA��vA� ±.zA��zA   ��� ?UBR�`��+� �>���2�T��[��Y�x�}�9�H
1ћfb��   �;��	G~A�ʖA        ��?&�̼��:@��*=���@����q}A��vA�����8�A��A   ��� ?UBR�`��+� �>Vz��������A�����2��0����$P�����L��m�   p����5AUu�A        ��?&�̼���= �>  @?�����}AUu�A������AUu�A   ��� ?UBR�`��+� Ҵ���2�T��[��Y�x�}�9�H
1ћfb��   VB�%flA�ʖA        ��?&�̼ �?���=���@�WD�jUkA��vA�T@��vmA��A   ��� ?UBR�`��+� �����2�T��[��Y�x�}�9�H
1ћfb��   *J��*kA�ʖA        '��<��?��:@��*=���@��O�@�iA��vAxUD�R�lA��A   ��� ?UBR�`��+� ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   .�N�$<jAUu�A        '��<��?���=  �>  @?:P�<�fAUu�A��O�]mAUu�A   ��� ?UBR�`��+� �S���f07L6���	����0����$P�����L��m�   ��]�KfA��xA        ��?&�̼,f�@��*>  �>�mj�nbbA��vAx�P3jA��zA   ��� ?UBR�`��+� ә���2�T��[��Y�x�}�9�H
1ћfb��   W�:��KnA�ʖA        ��?&�̼��:@��*=���@[@��vmA��vA�4��upA��A   ��� ?UBR�`��+� әVz��������A�����2��0����$P�����L��m�   *�5:oAUu�A        ��?&�̼���= �>  @?��4��mAUu�Agv4��)sAUu�A   ��� ?UBR�`��+� ����f07L6���	��䬕��u	���B1������   �a���i�A�X�A        ��?&�̼+��@���=��@�;���}AT�}A䇔��	�A�A  ��� ?UBR�`��+� ����f07L6���	��䬕��u	���B1������   �_�dsA�X�A        ��?&�̼VUMA���=��@I4���mAT�}A� �/yA�A  ��� ?UBR�`��+� �	���f07L6���	��䬕��u	���B1������   �]���eA�X�A        ��?&�̼,f�@���=��@Sjj¨�bAT�}A��P��3iA�A  �-�-�Fl�m��� ����2�T��[��Y�x�}�9�H
1ћfb��   꾫�!SM��ʖA        80?"�9?��:@��*=���@��¿�d���vA/��6���A   �-�-�Fl�m��� �Vz��������A�����2��0����$P�����L��m�   -ޫ�@�_�Uu�A        80?"�9?���= �>  @?)?����`�Uu�A1}�$_�Uu�A   �-�-�Fl�m��� �)���2�T��[��Y�x�}�9�H
1ћfb��   �U��r���ʖA        #�9�80?��:@��*=���@����&���vA;$�¨�����A   �-�-�Fl�m��� �)&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   �6�¦4��Uu�A        #�9�80?���= �>  @?a�������Uu�Ai���D���Uu�A   �-�-�Fl�m��� �L���2�T��[��Y�x�}�9�H
1ћfb��   ���S.��ʖA        80?"�9? �?���=���@˷��s
6���vAcr��3�%���A   �-�-�Fl�m��� ����2�T��[��Y�x�}�9�H
1ћfb��   t��X�UªʖA        80?"�9?��:@��*=���@�����[©�vAl���,P���A   �-�-�Fl�m��� �Vz��������A�����2��0����$P�����L��m�   � ��`�Z�Uu�A        80?"�9?���= �>  @?�����Z�Uu�A���·ZZ�Uu�A   �-�-�Fl�m��� ����2�T��[��Y�x�}�9�H
1ћfb��   �Э�wGªʖA        80?"�9?��:@��*=���@���©�vAz�������A   �-�-�Fl�m��� �Vz��������A�����2��0����$P�����L��m�   ���~��Uu�A        80?"�9?���= �>  @?�P��&%�Uu�Aʎ��ֻ�Uu�A   �-�-�Fl�m��� �L���2�T��[��Y�x�}�9�H
1ћfb��   �g�D���ʖA        #�9�80?��:@��*=���@����������vA� ��>�����A   �-�-�Fl�m��� �L&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   LH����Uu�A        #�9�80?���= �>  @?����N`��Uu�AҬ­���Uu�A   �-�-�Fl�m��� �����2�T��[��Y�x�}�9�H
1ћfb��   �������ʖA        80?"�9? �?���=���@dɭ�����vA����u�����A   �-�-�Fl�m��� �����2�T��[��Y�x�}�9�H
1ћfb��   ����,AFªʖA        #�9�80?��:@��*=���@��L©�vAxQ�� o@���A   �-�-�Fl�m��� ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   >y��$�A�Uu�A        #�9�80?���= �>  @?�į��A�Uu�A��¸eA�Uu�A   �-�-�Fl�m��� �����2�T��[��Y�x�}�9�H
1ћfb��   �ׯ¤NªʖA        80?"�9? �?���=���@U���,P©�vA�L���A   �-�-�Fl�m��� �E���2�T��[��Y�x�}�9�H
1ћfb��   �x��x�
1ћfb��   =Q��i�+A�ʖA        80?"�9?VUU?���=���@�q��'%A��vA�0�¬n2A��A   ���;�L�Sҝ��f 鎵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
9·�tB���A��4JO5  �?D��3�j
?}��@�U�?�:¯�gBU��A�7���B���A@  ���;�L�Sҝ��f 鏵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
Y·�tB���A��4JO5  �?D��3�j
?}��@�U�?�Z¯�gBU��A�W���B���A@  ���;�L�Sҝ��f 鐵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   ������tB���A��4JO5  �?D��3�j
?}��@�U�?C����gBU��A������B���A@  ���;�L�Sҝ��f 鑵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �����tB���A��4JO5  �?D��3�j
?}��@�U�?C����gBU��A������B���A@  ���;�L�Sҝ��f �s{,����^J����H��wQ��3�ޒ�8�����ġ���   ":v�S&A���A<��   �?I 5M�]�K�`@�j
?ZU�?A}���!AU��A73o¨d*A���A�  ���;�L�Sҝ��f �u�ʅ��e������J�>5Q��3�ޒ�8�����ġ���   ��m�A���A�	ز  �?�@4h�^��j
?*AwU�?�o�RL^@U��A��l� �aA���A�  ���;�L�Sҝ��f 饵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
9·�tBT�fA��4JO5  �?D��3�j
?}��@�U�?�:¯�gB��^A�7���B��nA@  ���;�L�Sҝ��f 馵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
Y·�tBT�fA��4JO5  �?D��3�j
?}��@�U�?�Z¯�gB��^A�W���B��nA@  ���;�L�Sҝ��f 駵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   ������tBT�fA��4JO5  �?D��3�j
?}��@�U�?C����gB��^A������B��nA@  ���;�L�Sҝ��f 騵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �����tBT�fA��4JO5  �?D��3�j
?}��@�U�?C����gB��^A������B��nA@  ���;�L�Sҝ��f �s{,����^J����H��wQ��3�ޒ�8�����ġ���   ":v�S&AT�fA<��   �?I 5M�]�K�`@�j
?ZU�?A}���!A��^A73o¨d*A��nA�  ���;�L�Sҝ��f �u�ʅ��e������J�>5Q��3�ޒ�8�����ġ���   ��m�AT�fA�	ز  �?�@4h�^��j
?*AwU�?�o�RL^@��^A��l� �aA��nA�  ���;�L�Sҝ��f 鮵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
9·�tBOK@��4JO5  �?D��3�j
?}��@�U�?�:¯�gB�*@�7���B��k@@  ���;�L�Sҝ��f 鯵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
Y·�tBOK@��4JO5  �?D��3�j
?}��@�U�?�Z¯�gB�*@�W���B��k@@  ���;�L�Sҝ��f 鰵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   ������tBOK@��4JO5  �?D��3�j
?}��@�U�?C����gB�*@������B��k@@  ���;�L�Sҝ��f 鱵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �����tBOK@��4JO5  �?D��3�j
?}��@�U�?C����gB�*@������B��k@@  ���;�L�Sҝ��f �s{,����^J����H��wQ��3�ޒ�8�����ġ���   ":v�S&AOK@<��   �?I 5M�]�K�`@�j
?ZU�?A}���!A�*@73o¨d*A��k@�  ���;�L�Sҝ��f �u�ʅ��e������J�>5Q��3�ޒ�8�����ġ���   ��m�AOK@�	ز  �?�@4h�^��j
?*AwU�?�o�RL^@�*@��l� �aA��k@�  ���;�L�Sҝ��f 鷵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
9·�tB�:���4JO5  �?D��3�j
?}��@�U�?�:¯�gB`	��7���B�*��@  ���;�L�Sҝ��f 鸵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
Y·�tB�:���4JO5  �?D��3�j
?}��@�U�?�Z¯�gB`	��W���B�*��@  ���;�L�Sҝ��f 鹵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   ������tB�:���4JO5  �?D��3�j
?}��@�U�?C����gB`	�������B�*��@  ���;�L�Sҝ��f 麵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �����tB�:���4JO5  �?D��3�j
?}��@�U�?C����gB`	�������B�*��@  ���;�L�Sҝ��f �s{,����^J����H��wQ��3�ޒ�8�����ġ���   ":v�S&A�:�<��   �?I 5M�]�K�`@�j
?ZU�?A}���!A`	�73o¨d*A�*���  ���;�L�Sҝ��f �u�ʅ��e������J�>5Q��3�ޒ�8�����ġ���   ��m�A�:��	ز  �?�@4h�^��j
?*AwU�?�o�RL^@`	���l� �aA�*���  ���;�L�Sҝ��f �����1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
9·�tB�����4JO5  �?D��3�j
?}��@�U�?�:¯�gBV���7���B���@  ���;�L�Sҝ��f �����1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
Y·�tB�����4JO5  �?D��3�j
?}��@�U�?�Z¯�gBV���W���B���@  ���;�L�Sҝ��f �µ��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   ������tB�����4JO5  �?D��3�j
?}��@�U�?C����gBV��������B���@  ���;�L�Sҝ��f �õ��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �����tB�����4JO5  �?D��3�j
?}��@�U�?C����gBV��������B���@  ���;�L�Sҝ��f ��s{,����^J����H��wQ��3�ޒ�8�����ġ���   ":v�S&A���<��   �?I 5M�]�K�`@�j
?ZU�?A}���!AV��73o¨d*A����  ���;�L�Sҝ��f ��u�ʅ��e������J�>5Q��3�ޒ�8�����ġ���   ��m�A����	ز  �?�@4h�^��j
?*AwU�?�o�RL^@V����l� �aA����  ���;�L�Sҝ��f �ɵ��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
9·�tB D���4JO5  �?D��3�j
?}��@�U�?�:¯�gBVM��7���B�:�@  ���;�L�Sҝ��f �ʵ��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �
Y·�tB D���4JO5  �?D��3�j
?}��@�U�?�Z¯�gBVM��W���B�:�@  ���;�L�Sҝ��f �˵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   ������tB D���4JO5  �?D��3�j
?}��@�U�?C����gBVM�������B�:�@  ���;�L�Sҝ��f �̵��1Iqо��P�=1Y�3(�Q��3�ޒ�8�����ġ���   �����tB D���4JO5  �?D��3�j
?}��@�U�?C����gBVM�������B�:�@  ���;�L�Sҝ��f ��s{,����^J����H��wQ��3�ޒ�8�����ġ���   ":v�S&A D�<��   �?I 5M�]�K�`@�j
?ZU�?A}���!AVM�73o¨d*A�:¤  ���;�L�Sҝ��f ��u�ʅ��e������J�>5Q��3�ޒ�8�����ġ���   ��m�A D��	ز  �?�@4h�^��j
?*AwU�?�o�RL^@VM���l� �aA�:´  �&�8�I���n:!�� �.9�q���nd�RA	S����Q��3�ޒ�8�����ġ���   ���A�b©�MA        ���&�?旇@WJ�? ��=W��Ap���?MA�� B�5�R�NA   ���cH�Fʣ�%���j �gS�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A�=z���@        K5��5?0�@u�>�x�@:�Ae_��RՅ@2u�A��?�"'1A8   ���cH�Fʣ�%���j �gu�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A�=z���@        �5��5?At@b>�x�@s��Ae_��RՅ@7��A��[�"'1A   ���cH�Fʣ�%���j ��S�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A�=z�s�A        K5��5?0�@u�>�x�@:�Ae_����vA2u�A��?����A8   ���cH�Fʣ�%���j ��u�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A�=z�s�A        �5��5?At@b>�x�@s��Ae_����vA7��A��[����A   ���cH�Fʣ�%���j ��S�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A6t��s�A        K5��5?0�@u�>�x�@:�A������vA2u�A�3�����A8   ���cH�Fʣ�%���j ��u�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A6t��s�A        �5��5?At@b>�x�@s��A������vA7��A�3�����A   ��#���DՇb�F6
����              �? U�>8�A  ,A�o�B�̪���BE�B�=�@�1�   ��#���DՇb�F6
�PA��>  ,A��B�I������B\:H��1�   ���'�O������Y� ��ѡ6��Q��e��l~+�?^��ɬ�@MQ��
x>�Pr$   tk
BO�o�Qյ@        +u���?J[�?�vrATU1A��B6t����>��BD���R�3A   ���'�O������Y� ���:-��'�%r<�t��7�6AaN�1
B6t����>��B6t��R�3A   ���'�O������Y� ��.���y�U�E��M�1�?^��ɬ�@MQ��
x>�Pr$   �.B�;��Qյ@        ��u���? �%?�B�@TU1A�>B�  �>
B���R�3A   ���'�O������Y� ���Ӎ~6N�3M�>�0�}�J��aN�1
�9�2������C��Y`DoO�t����JR� ��}��G   <x��|�����A        N<1=��?��}A>GA   A=���*�UՅ@�a���N?��bA   ���"� B;��a��� N�����h`��8�߫S�"�NO�t����JR� ��}��G   �	���zv���A        W�#=v�?��rAl�4A   A=���F��UՅ@��©
%���bA   ���"� B;��a��� N\� J�����^�^�L
��I�O�t����JR� ��}��G   ����J����A        #w+=��?
�jA�a4A   A=��-��UՅ@���8�����bA   ���"� B;��a��� NyZ��*#�~]$�JXZ��5P`O�t����JR� ��}��G   o��f�ª�A        ��_=@�?�kgA�%HA   A=��®%�UՅ@����7�����bA   ���"� B;��a��� NB7%%7�[�u�·��u2-`O�t����JR� ��}��G   Ф�²�8ª�A        ��J=}�?��[A5}7A   A=����6M�UՅ@����
��I�O�t����JR� ��}��G   ����J��Tu�A        #w+=��?
�jA�a4A��A=��-����vA���8���Su�A   ���aS�BԜ�\��/� &=�����h`��8�߫S�"�NO�t����JR� ��}��G   �	���zv�Tu�A        W�#=v�?��rAl�4A��A=���F����vA��©
%�Su�A   ���aS�BԜ�\��/� &?�9�2������C��Y`DoO�t����JR� ��}��G   <x��|���Tu�A        N<1=��?��}A>GA��A=���*���vA�a���N?Su�A   ���aS�BԜ�\��/� &A�D�Z[�")p�N~���O�t����JR� ��}��G   �ܸ�i��@Tu�A        ��?<��?C~A+�0A��A=���E>��vA|7���[.ASu�A   ����pAݸhkዚ�� D#�AJ�u�
+a�d��n�Kn:��e7   !��A�:�        ���<V�?�7kBm�B  �?)�������:��:�^�B�:�   ���q�B,���j�;� y;監W����o�����:�Q��3�ޒ�8�����ġ���   m��AqO���=d�B�d�B>�Y.��Y.? V�=��@�jSA�AƄQh�+�B�JUl@   ���q�B,���j�;� y;xԦ�]GE����.o��}$uJ�q�NeȊq�`�1��   ��Aq������H���H>�-��-? �*=fvA�QlA�AƤ»���+�Bz�JU@(   ���q�B,���j�;� y;*�0�%_T���a^�-8uԣ}$uJ�q�NeȊq�`�1��   ���A:��� �2��?P��D�7����=Q)?��d@V\�A�#°_���A�$�j`��   ���q�B,���j�;� y;�T�u `�'����n:���}$uJ�q�NeȊq�`�1��   ��B�L��?� �2��?)���h7����=z?l�c@+�B�# �>�B�$�OUl@�   ���q�B,���j�;� y;�D&����A���a;#�z��}$uJ�q�NeȊq�`�1��   V\�Ah��m�?��?� ����6/s'����=�\?0�a@�A�# �>���A�$�U�j@�   ���q�B,���j�;� y;�}d7�A�\֢.�K5��o�}$uJ�q�NeȊq�`�1��   ���A&�o��� �2��?rv�Y�5����=-�
���HS��zX�%PX�v-�;M�Q��3�ޒ�8�����ġ���   ���[Q�_�)?��龟�?�9@�
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   �@�!YU�\�] ����?Z�5�v�P/���=3�?k؁@���/.V«�@��tOT�}���   ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   ����!YU��
���v� y�eubE23Fu���$�}$uJ�q�NeȊq�`�1��   T�~�DTU�T�� ��Z�?� C��`/���=�Q?@`@����/.V�'�!¨T�tOT�'���   ��R&P�I��s��z��  
��������R�����:~���|��}$uJ�q�NeȊq�`�1��   ����xA�Vp¹5��5?t��t�<���=�|�>�T`@��5��#B� p���	��xA� p�   ��R&P�I��s��z��  
��������R�����:~���|��}$uJ�q�NeȊq�`�1��   ����U�Vp�p�? �2k	^�SA����=�|�>�T`@�����[� p������P� p�   ��R&P�I��s��z��  
��������R�����:~���|��}$uJ�q�NeȊq�`�1��   ���/�S�Vp¹5��5?t��t�<���=�|�>�T`@��5��XT� p���	�/�S� p�   ��R&P�I��s��z��  
��������R�����:~���|��}$uJ�q�NeȊq�`�1��   �����F�Vp¹5��5?t��t�<���=�|�>�T`@��5�/�G� p���	���F� p�   ��R&P�I��s��z��  
������bm�)������ns��Q��3�ޒ�8�����ġ���   �7���C�H���6�O<J,�>>�l?�Zk�s�A�]�A0�A;� ��8V«�_�@�#2� ��|  ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   �iU@<3�c�����?;j�w�P�Z�5�����3�?j؁@�R@�4����kX@/.2¤k���   ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   ����!YU¹��;j���?Z�5�w�P�����3�?j؁@ K��/.V�V5��u���tOT������   ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   @�
�<3²V���?;j�w�P�Z�5�����3�?j؁@�@
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   T��<3�X����?;j�w�P�Z�5�����3�?j؁@�\���4�V������/.2�O���   ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   �@�!YU�c���;j���?Z�5�w�P�����3�?j؁@���/.V����@��tOT¤k���   ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   S�~�!YU¹��;j���?Z�5�w�P�����3�?j؁@����/.V�V5���T�tOT������   ��R&P�I��s��z��  
��8غVE��n`u�sT-i�գ}$uJ�q�NeȊq�`�1��   �iU@�EU�z��\�?ҍ*,�_/)�B�����G�	?�b@�R@/.V�V5��kX@tOT�	����   ��R&P�I��s��z��  
�߇v� y�eubE23Fu���$�}$uJ�q�NeȊq�`�1��   ����3�Y�Z�?�*��`�� C������Q?@`@ K���4��T�u���/.2��T��   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   �����F�V����5��5?t��t�<�����|�>�T`@��5���F«�����	��8F«���   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   ���/�4�Vp¹5��5?t��t�<�����|�>�T`@��5�/�4� p���	��4� p�   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   ���/�S�V����5��5?t��t�<�����|�>�T`@��5�/�S«�����	��S«���   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   FP�@/�S� 6���5?�5?t��t�������|�>�T`@��@�XT�V5��pZA/�S�V5��   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   FP�@��F� 6���5?�5?t��t�������|�>�T`@��@/�G�V5��pZA��F�V5��   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   FP�@�xA� 6���5?�5?t��t�������|�>�T`@��@�#B�V5��pZA�xA�V5��   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   FP�@/�4� 6���5?�5?t��t�������|�>�T`@��@�X5�V5��pZA/�4�V5��   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   5
�@�U� 6��p�?�',l	^/SA������|�>�T`@��@��[�V5��5
�@��P�V5��   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   ����U�V���p�?�',l	^/SA������|�>�T`@;P���[«��������P«���   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   ���l�2�Vp��',p�?SA�l	^/�����|�>�T`@�����7� p������,� p�   ��R&P�I��s��z��  
�ߌ�����R�����:~���|��}$uJ�q�NeȊq�`�1��   5
�@l�2� 6���',p�?SA�l	^/�����|�>�T`@5
�@��7�V5���_�@��,�V5��   ��R&P�I��s��z��  
�`�MR�K�
B�UM7*�E+"Q��3�ޒ�8�����ġ���   �L|�vI4�L0��:v$?�=?C~���s��u�@�"AN��A47�..D�\��5
�@�#-¬�|�  ��R&P�I��s��z��  
�`�u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   T��<3¹����?] ��v�P/Z�5����=3�?k؁@�\���4�V5������/.2������   ��R&P�I��s��z��  
�`�u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   �iU@<3�X����?] ��v�P/Z�5����=3�?k؁@�R@�4«���kX@/.2,~��   ��R&P�I��s��z��  
�`�u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   @�
�<3�X����?] ��v�P/Z�5����=3�?k؁@�@
�`8غVE��n`u�sT-i�գ}$uJ�q�NeȊq�`�1��   ����a3��j�� �2\�?)�B��_����=G�	?�b@ K���4«���u���/.2�^T���   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   ��.�F-«���p�? �2k	^�SA����=�|�>�T`@;P/���-������-��x,��}�   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   ���F-«���p�? �2k	^�SA����=�|�>�T`@�����2���������'����   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   ����F-«���p�? �2k	^�SA����=�|�>�T`@������2����u�����'����   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   �@�F-«���p�? �2k	^�SA����=�|�>�T`@�@���2����,����'����   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   S�~�F-«���p�? �2k	^�SA����=�|�>�T`@V�~���2����L����'����   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   �iU@F-«���p�? �2k	^�SA����=�|�>�T`@�iU@��2����k`@��'����   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   $ă@/..«����5��5?t��t�<���=�|�>�T`@�*@��.�����_�@/..����   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   $ă@��1«����5��5?t��t�<���=�|�>�T`@�*@/.2�����_�@��1����   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   ���l�2�V��� �2p�?SA�k	^����=�|�>�T`@;P���7«��������,«���   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   �����4�V����5��5?t��t�<���=�|�>�T`@��5�/N5«�����	���4«���   ��R&P�I��s��z��  
�`������R�����:~���|��}$uJ�q�NeȊq�`�1��   Cs��xA�V����5��5?t��t�<���=�|�>�T`@��6��#B«�����
��xA«���   ��R&P�I��s��z��  
�P�C��&j;��
��;=�Q��3�ޒ�8�����ġ���   �JG��D*�ߚ"�Ը#?�-���c�>Qf�>�
Au���.�E�n&�O�>�..D«:   ��R&P�I��s��z��  
�P�u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   ����<F��
�P�u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   �@�<F�\���?] ��v�P/Z�5����=3�?k؁@����G«�@��/.E�}���   ��R&P�I��s��z��  
�P�v� y�eubE23Fu���$�}$uJ�q�NeȊq�`�1��   T�~�F�T��Z�? ���`/� C����=�Q?@`@�����G�'�!¨T�/.E�'���   ��R&P�I��s��z��  
��̗��@!��=6;Z'Q��3�ޒ�8�����ġ���   ԁ��.~C����ڗ��ڗ�>�1 ��1 ? �>T�D@��NAu���..D«���h@.�B«����   ��R&P�I��s��z��  
��E��){�O�А8F��$r�(�ޞ�2��r`<\�{�E   x�� �B­��g���� ?�ڭ>餴��#B?h-?R	@A K��..D� ��5
�@�8A�V5��  ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   �iU@!YB�c���;j���?Z�5�w�P�����3�?j؁@�R@/.C����kX@tOA¤k���   ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   T��!YB�X��;j���?Z�5�w�P�����3�?j؁@�\��/.C�V������tOA�O���   ��R&P�I��s��z��  
���u?�#�[�}!�!�bh���}�}$uJ�q�NeȊq�`�1��   @�
�!YB²V�;j���?Z�5�w�P�����3�?j؁@�@
��v� y�eubE23Fu���$�}$uJ�q�NeȊq�`�1��   ����DTB�Y��*�Z�?� C��`������Q?@`@ K��/.C��T�u���tOA��T��   �����N��X~�&�"� K����p���Xph5��xu�{[�=`O�L ����tIj����   �t*�؇/B�: B�        ��?XU�>�@A�D.A��7���B���A-��4GB �B    �����N��X~�&�"� L����JH����<�b��*��+O�t����JR� ��}��G   ������%B���A        �&�@�}?��vA�:�A   A&6�M*B���As�
��        �9?�U�>7�A�QBA_C��u���UՅ@	���SW��R�aAD   �#m+�GC���s$0�# �w�7A�]'		jK���#�� {[�=`O�L ����tIj����   FV�� G���?A        5M�  �?�/�A�c�>��A	������UՅ@}I�u���R�aA   �#m+�GC���s$0�# �xa���ƹ���h���C�!�{[�=`O�L ����tIj����   _C������?A              �?��J@@U�>��A	�������UՅ@����SW��R�aA   �#m+�GC���s$0�# �y�Cj΅���l�lq��f���{[�=`O�L ����tIj����   _C��:A��?A              �?�U�>H�A��A
���SW��UՅ@��������R�aA   �#m+�GC���s$0�# �z���b���8 .��e�\0�{[�=`O�L ����tIj����   �b��FEB��?A        ���  �?�tA�f�>��A������E�UՅ@PYH���>�R�aA   �#m+�GC���s$0�# �{���f07L6���	���{[�=`O�L ����tIj����   `������?A              �?XU=@PU�>��A����	p�UՅ@
�������R�aA   �#m+�GC���s$0�# �|���2�T��[��Y�x{[�=`O�L ����tIj����   v��������?A              �?���@@U�>��A	���u���UՅ@�B�� G��R�aA   �#m+�GC���s$0�# �}�_DY�N��5����㛌8Y������n��\w&e�mO�[   oA��Rۖ��A1p2�j7?�:��p��<��A�m�?n�A���®���UՅ@���� T��R�MA?   �#m+�GC���s$0�# �}L�a
A����Q%��UՅ@�́�ie��R�MA
   �#m+�GC���s$0�# �!/�_���gA���T��������n��\w&e�mO�[   ����e
���?A"��'�i�=U�~?�ً?�5<5��
A�"��^ ��UՅ@m��4$|�R�MA   �#m+�GC���s$0�# ���Qwb��N�E�z
A����Q%��UՅ@�S�
   �#m+�GC���s$0�# �=KG���hA�+AvW��YZ�/��/��N����E��b   ����\��U�A        �c�<��?�a?=B@TU	A����a��UՅ@��������?LA   �#m+�GC���s$0�# �R�s�7�=\���6��[nU�����n��\w&e�mO�[   ����)��T�A              �?  �?��@TU	A����a��UՅ@��������?LA   �#m+�GC���s$0�# �I��JL��2�\L!�Ui�{[�=`O�L ����tIj����   Q����)��T�A              �? U�>��@TU	A����a��UՅ@��������?LA   �#m+�GC���s$0�# 膱A��2A���9��Na�Z<p{[�=`O�L ����tIj����   /���u���T�A�5?�5?�#��#��U�>��Y@�m	A��� G��UՅ@�S�������?LA   �#m+�GC���s$0�# �2R:�&��uA���*\͈�/��/��N����E��b   /�������T�AR�3?R�3?�i���i��  �?�z�@�A�������UՅ@�S�������?LA   �#m+�GC���s$0�# 膅F�����\\)5�u'�ҟ�����n��\w&e�mO�[   /��� G��T�AR�3?R�3?�i���i��  �?�z�@�A��� G��UՅ@�S�� G���?LA   �#m+�GC���s$0�# 臐��f07L6���	���{[�=`O�L ����tIj����   
E�����]6�X
.?�d�wN�f�(i�mk�UR�2��   	�g?�+����@���;0 ���2��P?�+@Fѹ@��@�J�u���RՅ@�L6�|G����2A0   �#m+�GC���s$0�# ��� ؖ����
��.>ݳ�}$uJ�q�NeȊq�`�1��   	��9��ˠ�(]	A�IJ?�?
?ȂU>��?Ǫ4AahA*�I�UՅ@��A ��R�wAH   �#m+�GC���s$0�# 謂#���Q]���N����g�#�{[�=`O�L ����tIj����   #As#��?A        �$Y>�-z?�:�?J��?��4A1� A*�I�UՅ@��A!�R�wA"   �#m+�GC���s$0�# �4��Q�����d�,�Rm��r��/��/��N����E��b   1)A�t��?A�u+�4-�t?
&����<��@��4A��A�˗�UՅ@N�2A�9�R�wA
   �#m+�GC���s$0�# 譂]c��x�~�=H� ��5�g������n��\w&e�mO�[   �#A�����?AJ�4"��-�t?&��ۗ�<4*@��4A��A����UՅ@�L-A*�I�R�wA
   �#m+�GC���s$0�# �Dp)�K�h_y��X���=!{[�=`O�L ����tIj����   �T&A;D|��?A        &��-�t?>�
�4��?A        d��>��l?ߴJ>�v;��4A���x�5�UՅ@"B���`3�R�wA   �#m+�GC���s$0�# �x���
yG1���{[�=`O�L ����tIj����   6R��qy:��?A        ���>�~w?��?0�_?��4A&=��ɈB�UՅ@����0�R�wA   �#m+�GC���s$0�# �*�.ُ
   �#m+�GC���s$0�# 谂��������b>��yYi۝<{[�=`O�L ����tIj����   ���3�I��?A        2�>~�}?��k?C1�?��4A���Q�R�UՅ@�[����@�R�wA   �#m+�GC���s$0�# ��ƩsC,�hgPL�ZB(n9�����n��\w&e�mO�[   �u��`O��?A        �U<m�?��m@�v?��4A=�Q�R�UՅ@����
L�R�wA   �#m+�GC���s$0�# �j�ܖ�Ū��]|j4��c�/��/��N����E��b   ���
L��?A              �?�pt@  �?��4A=��
L�UՅ@� ��
L�R�wA   �#m+�GC���s$0�# 豘��'{{�0�j�Ia���B�l{[�=`O�L ����tIj����   ���_O��?A�/5?$�4�������4���>}t@��4A=�Q�R�UՅ@� ��
L�R�wA   �#m+�GC���s$0�# �'+]@DV:�0������O�����n��\w&e�mO�[   �
\n�nI��{[�=`O�L ����tIj����   �T%�i���>A��4�X,5?���+:��>�C@@�4A�9=�����UՅ@�o
H���������n��\w&e�mO�[   ��x� ���?Ahv�7+��-�U��?HR�>���@¬4A&���a�UՅ@������R�wA&   �#m+�GC���s$0�# �U��Y��Z+J���;��s�P�/��/��N����E��b   XOn�L ��?AZ6�n�.�U��?d��>\O�@�4Ap��3��UՅ@�������R�wA&   �#m+�GC���s$0�# ����F�{�X;N��L-)��{[�=`O�L ����tIj����   WZo��y ��?A        �VO>��z?>?�@p�@��4A&���a�UՅ@�������R�wA    �#m+�GC���s$0�# 跐Y]}��ͪ�ZK�Y��W�I�������n��\w&e�mO�[   ��X?���?A�B�3)�3S�D?$?�F>8��?��4A��R��UՅ@��?t��R�wA6   �#m+�GC���s$0�# ��
�Лشw��?&H(>��4A������UՅ@���?��R�wA9   �#m+�GC���s$0�# ��N��*p��w�s��W�ri{[�=`O�L ����tIj����   �[?Y��?A        j)���~?f�?�c�?��4A��R��UՅ@��?��R�wA   �#m+�GC���s$0�# ��%ݯ�7~�`�����u^J�{[�=`O�L ����tIj����   �@wK��?A        LL���yu?.=?�y?��4A���?t��UՅ@˅#@X��R�wA   �#m+�GC���s$0�# �R}�m��חq��!Y[%����������n��\w&e�mO�[   ��@���?A�A6�0b5KL�>�yu?P`b?O(;��4A��?t��UՅ@˅#@��R�wA   �#m+�GC���s$0�# �eV�x vSE�v�z)�Ͼ��/��/��N����E��b   ��?0���?A��4�S�RL�>�yu?��_?��%;��4A���?��UՅ@�@X��R�wA   �#m+�GC���s$0�# �R�s�7�=\���6��[nU�/��/��N����E��b   ut6������?A              �?  �?�w�@��4Aut6�����UՅ@ut6�Q�R�R�wA   �#m+�GC���s$0�# ���4{T�jG���F,�1Ȍ�������n��\w&e�mO�[   =������?A              �?  �?�w�@��4A=�����UՅ@=�Q�R�R�wA   �#m+�GC���s$0�# ��V�E�1�-ԝkЌ��4�{[�=`O�L ����tIj����   ��9������?A              �?@U�>�w�@��4A=�����UՅ@ut6�Q�R�R�wA   �#m+�GC���s$0�# �R�s�7�=\���6��[nU�/��/��N����E��b   �6�E����?A              �?  �?;�@��4A�6��Z��UՅ@�6����R�wA   �#m+�GC���s$0�# ���4{T�jG���F,�1Ȍ�������n��\w&e�mO�[   �9=�E����?A              �?  �?;�@��4A�9=��Z��UՅ@�9=����R�wA   �#m+�GC���s$0�# ��V�E�1�-ԝkЌ��4�{[�=`O�L ����tIj����   i�9�E����?A              �?@U�>;�@��4A�9=��Z��UՅ@�6����R�wA   �#m+�GC���s$0�# �P�W�fp�Y̢B))��?8�/�/��/��N����E��b   ut6�&�+�d@A=�:        ��?  �?�)�@��4Aut6��
L�UՅ@ut6�m��R�wA   �#m+�GC���s$0�# ��	����;Zv܉���r�������n��\w&e�mO�[   =�&�+�d@A=�:        ��?  �?�)�@��4A=��
L�UՅ@=�m��R�wA   �#m+�GC���s$0�# 軎-4��V�������x�VU{[�=`O�L ����tIj����   ��9�`�+��@An�;        ��?@U�>��@8�4A=��
L�UՅ@ut6�m��R�wA   �BC
\�E
\�E
4AL��A�8�X7�UB�«*��<   �'��QoE��`X��: BA����ڌ�s_2��"�y��q�AƈP��%ULڝ.�N   �_-��wAV5�A������?�B���A�~@AT@>�A�vc(@Uu�A`���lnAU��A   �'��QoE��`X��: BA���y7 �p�lT��:TkS��C\��/��Ȧ��'���R   �Z-�AU��A        �P�,�?h�/A��MA  �?�A�vc(@U��A`���lnAU��A   �7�q aB���X���J� �G���f07L6���	���r��(;�{p9DC}�\ə�   W����*mB�
���A�&�A�&�5?�5?�4A���>  @?Wz��ݎVB�
��Wz��^�B�
��   �7�q aB���X���J� �H���f07L6���	���r��(;�{p9DC}�\ə�   W���2d;B�
���A���A�&�5��5?��?A���>  @?Wz��2d#B�
��Wz��2dSB�
��   �7�q aB���X���J� �I���f07L6���	���r��(;�{p9DC}�\ə�   W��®B�
���A���A�&�5��5?�nAA���>  @?Wz�©��A�
��Wz�9 B�
��   �7�q aB���X���J� �J���f07L6���	���r��(;�{p9DC}�\ə�   W���w�A�
���A���A�&�5��5?pAA���>  @?Wz��5�qA�
��Wz��Sf�A�
��   �7�q aB���X���J� �K���f07L6���	���r��(;�{p9DC}�\ə�   W�� 5A�
���A���A�&�5��5?ҡAA���>  @?Wz��ܒ
��Wz�eA�
��   �7�q aB���X���J� �L���f07L6���	���r��(;�{p9DC}�\ə�   W��½-���
���A���A�&�5��5?ҡAA���>  @?Wz����*��
��Wz��Vе?�
��   �7�q aB���X���J� �M���f07L6���	���r��(;�{p9DC}�\ə�   W��®1���
���A���A�&�5��5?ҡAA���>  @?Wz��#����
��Wz��s�7��
��   �7�q aB���X���J� �N���f07L6���	���r��(;�{p9DC}�\ə�   W���U6���
���A���A�&�5��5?pAA���>  @?Wz��«
��Wz��y����
��   �7�q aB���X���J� �O���f07L6���	���r��(;�{p9DC}�\ə�   W��!,«
���A���A�&�5��5?�9A���>  @?Wz���YC«
��Wz��C�«
��   �7�q aB���X���J� �P���f07L6���	���r��(;�{p9DC}�\ə�   W���g«
���A���A�&�5��5?�*�A���>  @?Wz���̃«
��Wz��s�F«
��   �7�q aB���X���J� �Q���f07L6���	���r��(;�{p9DC}�\ə�   (���D«
��   '`W�  �?���&��A   ?  @?=����E«
��ŧ��C«
��   �7�q aB���X���J� �R���f07L6���	���r��(;�{p9DC}�\ə�   �ؘ��D«
��              �?�nUA   ?  @?�/���E«
��Ӂ���C«
��   �7�q aB���X���J� �S���f07L6���	���r��(;�{p9DC}�\ə�   *\y��D«
��              �?��SA   ?  @?}���E«
��Y�^��C«
��   �7�q aB���X���J� �T���f07L6���	���r��(;�{p9DC}�\ə�   = A��D«
��              �?��TA   ?  @?��[��E«
��ˋ&��C«
��   �7�q aB���X���J� �U���f07L6���	���r��(;�{p9DC}�\ə�   !���D«
��              �?  TA   ?  @?!a#��E«
��A����C«
��   �7�q aB���X���J� �V���f07L6���	���r��(;�{p9DC}�\ə�   �4���D«
��              �?��DA   ?  @?�l���E«
����g��C«
��   �7�q aB���X���J� �d���f07L6���	���r��(;�{p9DC}�\ə�   ���A��B�
��   '`W�  �?���&�C�A   ?  @?=���A�B�
��Wz��A�B�
��   �7�q aB���X���J� �e���f07L6���	���r��(;�{p9DC}�\ə�   G��A��B�
��              �?���A   ?  @?Wz��A�B�
�����A�B�
��   �7�q aB���X���J� �f���f07L6���	���r��(;�{p9DC}�\ə�   G�� �yB�
��              �?���A   ?  @?Wz�� �xB�
����� �zB�
��   �7�q aB���X���J� �g���f07L6���	���r��(;�{p9DC}�\ə�   ��� �yB�
��   '`W�  �?���&�C�A   ?  @?=��� �xB�
��Wz�� �zB�
��   �7�q aB���X���J� �h���f07L6���	���r��(;�{p9DC}�\ə�   G���cB�
��              �?���A   ?  @?Wz���bB�
������dB�
��   �7�q aB���X���J� �i���f07L6���	���r��(;�{p9DC}�\ə�   ����cB�
��   '`W�  �?���&�C�A   ?  @?=����bB�
��Wz���dB�
��   �7�q aB���X���J� �j���f07L6���	���r��(;�{p9DC}�\ə�   G��!�KB�
��              �?���A   ?  @?Wz��!�JB�
�����!�LB�
��   �7�q aB���X���J� �k���f07L6���	���r��(;�{p9DC}�\ə�   ���!�KB�
��   '`W�  �?���&�C�A   ?  @?=���!�JB�
��Wz��!�LB�
��   �7�q aB���X���J� �l���f07L6���	���r��(;�{p9DC}�\ə�   G��&>B�
��              �?���A   ?  @?Wz��&=B�
�����&?B�
��   �7�q aB���X���J� �m���f07L6���	���r��(;�{p9DC}�\ə�   G��֝&B�
��              �?���A   ?  @?Wz��֝%B�
�����֝'B�
��   �7�q aB���X���J� �n���f07L6���	���r��(;�{p9DC}�\ə�   ���&>B�
��   '`W�  �?���&�C�A   ?  @?=���&=B�
��Wz��&?B�
��   �7�q aB���X���J� �o���f07L6���	���r��(;�{p9DC}�\ə�   ���֝&B�
��   '`W�  �?���&�C�A   ?  @?=���֝%B�
��Wz��֝'B�
��   �7�q aB���X���J� �p���f07L6���	���r��(;�{p9DC}�\ə�   G��+�B�
��              �?���A   ?  @?Wz��+�B�
�����+�B�
��   �7�q aB���X���J� �q���f07L6���	���r��(;�{p9DC}�\ə�   ���+�B�
��   '`W�  �?���&�C�A   ?  @?=���+�B�
��Wz��+�B�
��   �7�q aB���X���J� �r���f07L6���	���r��(;�{p9DC}�\ə�   G�»��A�
��              �?���A   ?  @?Wz�»��A�
�����]n B�
��   �7�q aB���X���J� �s���f07L6���	���r��(;�{p9DC}�\ə�   ��»��A�
��   '`W�  �?���&�C�A   ?  @?=��»��A�
��Wz��]n B�
��   �7�q aB���X���J� �t���f07L6���	���r��(;�{p9DC}�\ə�   G�¯��A�
��              �?���A   ?  @?Wz�¯��A�
����¯��A�
��   �7�q aB���X���J� �u���f07L6���	���r��(;�{p9DC}�\ə�   ��¯��A�
��   '⏁  �?��&�C�A   ?  @?=��¯��A�
��Wz�¯��A�
��   �7�q aB���X���J� �v���f07L6���	���r��(;�{p9DC}�\ə�   G�£�A�
��              �?���A   ?  @?Wz�£�A�
����£�A�
��   �7�q aB���X���J� �w���f07L6���	���r��(;�{p9DC}�\ə�   ��£�A�
��   '`W�  �?���&�C�A   ?  @?=��£�A�
��Wz�£�A�
��   �7�q aB���X���J� �x���f07L6���	���r��(;�{p9DC}�\ə�   G�»ԃA�
��              �?���A   ?  @?Wz�»ԁA�
����»ԅA�
��   �7�q aB���X���J� �y���f07L6���	���r��(;�{p9DC}�\ə�   ��»ԃA�
��   '`W�  �?���&�C�A   ?  @?=��»ԁA�
��Wz�»ԅA�
��   �7�q aB���X���J� �z���f07L6���	���r��(;�{p9DC}�\ə�   G��^�-A�
��              �?���A   ?  @?Wz��^�)A�
�����^�1A�
��   �7�q aB���X���J� �{���f07L6���	���r��(;�{p9DC}�\ə�   ���^�-A�
��   '`W�  �?���&�C�A   ?  @?=���^�)A�
��Wz��^�1A�
��   �7�q aB���X���J� �|���f07L6���	���r��(;�{p9DC}�\ə�   G�j�@�
��              �?���A   ?  @?Wz�j�@�
����j�@�
��   �7�q aB���X���J� �}���f07L6���	���r��(;�{p9DC}�\ə�   ��j�@�
��   '`W�  �?���&�C�A   ?  @?=��j�@�
��Wz�j�@�
��   �7�q aB���X���J� �~���f07L6���	���r��(;�{p9DC}�\ə�   ���r؍?�
��              �?���A   ?  @?W����[?�
�����rح?�
��   �7�q aB���X���J� ����f07L6���	���r��(;�{p9DC}�\ə�   �¸�r؍?�
��   'W�  �?���&.�|A   ?  @?=����[?�
��W���rح?�
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   G��~���
��              �?���A   ?  @?Wz��~���
�����~���
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ���~���
��   'z��  �?���&�C�A   ?  @?=���~���
��Wz��~���
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ���"9"��
��              �?���A   ?  @?W���"9&��
�����"9��
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   �¸�"9"��
��   'W�  �?���&.�|A   ?  @?=���"9&��
��W���"9��
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   G���Td��
��              �?���A   ?  @?Wz���Th��
������T`��
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ����Td��
��   '"�  �?���&�C�A   ?  @?=����Th��
��Wz���T`��
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   G�'���
��              �?���A   ?  @?Wz�'���
����'���
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ��'���
��   '"�  �?���&�C�A   ?  @?=��'���
��Wz�'���
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   G�$���
��              �?���A   ?  @?Wz�$���
����$���
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ��$���
��   '`W�  �?���&�C�A   ?  @?=��$���
��Wz�$���
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   G�6���
��              �?���A   ?  @?Wz�6���
����6���
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ��6���
��   '`W�  �?���&�C�A   ?  @?=��6���
��Wz�6���
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ��¢�]«
��   ',�K  �?��{'�C�A   ?  @?=��¢�^«
��Wz�¢�\«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   G9��o�f«
���A���A�&�5��5?CU�A���>  @?G���5j�«
��G����)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   6���o�f«
���A���A�&�5��5?CU�A���>  @?68��5j�«
��68���)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   m6��o�f«
���A���A�&�5��5?CU�A���>  @?m���5j�«
��m����)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   \���o�f«
���A���A�&�5��5?CU�A���>  @?\5��5j�«
��\5���)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   �h|¬^"«
���A�&�A�&�5?�5?�A�A���>  @?�h}��C«
���h{�;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   �b\�"«
���A�&�A�&�5?�5?�A���>  @?�b]��YC«
���b[�;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   �`M¬^"«
���A�&�A�&�5?�5?�A�A���>  @?�`N��C«
���`L�;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   M�<¬^"«
���A�&�A�&�5?�5?�A�A���>  @?M�=��C«
��L�;�;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ��¬^"«
���A�&�A�&�5?�5?�A�A���>  @?����C«
�����;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   x�
���A�&�A�&�5?�5?�A�A���>  @?x���C«
��x��;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   lz��"«
���A�&�A�&�5?�5?�A���>  @?lz���YC«
��lz��;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   Fs���^"«
���A�&�A�&�5?�5?�A�A���>  @?Fs���C«
��Fs��;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   o���^"«
���A�&�A�&�5?�5?�A�A���>  @?o���C«
��o��;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   f�y��^"«
���A�&�A�&�5?�5?�A�A���>  @?f�}��C«
��f�u�;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   �h|�o�f«
���A���A�&�5��5?CU�A���>  @?�h}�5j�«
���h{��)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   �b\�g«
���A���A�&�5��5?�*�A���>  @?�b]��̃«
���b[�s�F«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   �`M�o�f«
���A���A�&�5��5?CU�A���>  @?�`N�5j�«
���`L��)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   M�<�o�f«
���A���A�&�5��5?CU�A���>  @?M�=�5j�«
��L�;��)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ���o�f«
���A���A�&�5��5?CU�A���>  @?���5j�«
������)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   x�
���A���A�&�5��5?CU�A���>  @?x��5j�«
��x���)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   lz��g«
���A���A�&�5��5?�*�A���>  @?lz���̃«
��lz��s�F«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   Fs��o�f«
���A���A�&�5��5?CU�A���>  @?Fs���̃«
��Fs���E«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   o��o�f«
���A���A�&�5��5?CU�A���>  @?o���̃«
��o���E«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   f�y�o�f«
���A���A�&�5��5?CU�A���>  @?f�}�5j�«
��f�u��)G«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   @2��"«
���p�1z����?�wJ?ht�A   ?  @?-����YC¬
��Sn��;� «
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   _���A�0«
��              �?��mA   ?  @?Wz��A�1«
��g���A�/«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ⹖�M#«
��              �?Z|A   ?  @?Wz��M$«
��l���M"«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   �D��Ǚ«
��              �?��A   ?  @?Wz��Ǚ
�����Ǚ«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ���Ǚ«
��   '`W�  �?���&�C�A   ?  @?=���Ǚ
��Wz��Ǚ«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ���M#«
��   'b��  �?���&�C�A   ?  @?=���M$«
��Wz��M"«
��   �7�q aB���X���J� �����f07L6���	���r��(;�{p9DC}�\ə�   ���A�0«
��   'b��  �?���&�C�A   ?  @?=���A�1«
��Wz��A�/«
��   �s��5F��� � f� -��}�y�h"�|�Wɶ�i���O�t����JR� ��}��G   d;��J'��Tu�A        	�L=�?ܘhAD��A��A�"���a����vA�S��Ϧ��Su�A�   ��D��rA���?��+ ���Cj΅���l�lq��f���հ�"�� �����i��Vil   ���Y�yA�:�              �?  (@|J�B���@Y�����VEH���	^�B �+�   ��D��rA���?��+ ���r�d�Zõ9�\�#�}$uJ�q�NeȊq�`�1��   ���XFzA  �              �?  $@|J�B �AI���� �+�)��	n�B P�   ��D��rA���?��+ ��7��u��=�H�
   ��D��rA���?��+ �G��h��a�Q/	���N͏�{[�=`O�L ����tIj����   }}��1��V�              �?6�OB  $@V�&A)���� �+�J������:�
   ��D��rA���?��+ ���Cj΅���l�lq��f���հ�"�� �����i��Vil   �#_�;E«:�              �?  (@�jB���@�#t��!��VEH#J���� �+�   ��D��rA���?��+ ���>�	���%M���{Ǫr�}$uJ�q�NeȊq�`�1��   �#_�;�D�V�              �?  $@��BV�&A��s��!�� �+�J��«:�   ��D��rA���?��+ ���V�E�1�-ԝkЌ��4�{[�=`O�L ����tIj����   �#_�;�D�V�              �?  $@��BV�&A��s��!�� �+�J��«:�   ��U�0A�������x� U����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��    H�BM]�±�[�              �?   @��*? �B���A���V5��H�B����T�rA   ��U�0A�������x� _����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��    �:Bf��±�[�        ��d�?   @��*? �B9�5B�J��V5���?B:��T�rA   ��U�0A�������x� _����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��    ��rB�ׄ±�[�        ��d�?   @��*? �B��mB���V5��i�wB�'��T�rA   ��U�0A�������x� _����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��    ɟ�B�±�[�        ��d�?   @��*? �BW�B2���V5��<!�B�V��T�rA   ��U�0A�������x� _����2�T��[��Y�x�}$uJ�q�NeȊq�`�1��    ,��B�D�±�[�        ��d�?   @��*? �B��B���V5����B|���T�rA   ��U�0A�������x� `���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��    �}�B6��±�[�        ��d�?   @��*? �B!��Bc2��V5����B
҄�T�rA   �&�5(�@v��2�,Dܓ �(W���3���a��e*�%ۇs{[�=`O�L ����tIj����   ��Bb�
  ���eD=�?� �#�G �R�I+@�*�k�dW)*!ɺߖE\Q��3�ޒ�8�����ġ���   L��Aq�(��@A�p<��p<>�.��.? V�=�X)A��AlA�)�M��@� B�(�U��A   ���eD=�?� �#�G �RFZ��Du�\" %?�'Q�}$uJ�q�NeȊq�`�1��   �Aq�(¿�A�8@��8@>1�.�1�.? �*=hP4Ah��AlAƤ(���@� Bz(ª�rA(   ���eD=�?� �#�G �R*�0�%_T���a^�-8uԣ}$uJ�q�NeȊq�`�1��   XckA��'�@��?H��+D�7/P������Q)?��d@��jA�(�ї�@lAa�&�{��@�   ���eD=�?� �#�G �RS�l�u���C�� ���b�:�}$uJ�q�NeȊq�`�1��   +. B�(�"�jA�h���?���"�7������f?��c@� B�(�TNA�X Ba�&ª��A�   ���eD=�?� �#�G �R�}d7�A�\֢.�K5��o�}$uJ�q�NeȊq�`�1��   ���A��'�%�A��?OR�+Y�5/rv�����-�
   ���~G�A����t @�_tgp ㍲!);����S��C\��/��Ȧ��'���R   ;��DӨ@U��A        �ե��(?09A�]$A  �?i����i?U��A�S��'�AU��A   ���~G�A����t @�0]�����!E�U�=7O(
�AƈP��%ULڝ.�N   bލ��?^AU5�A              �?��(A  �@  @>i���? AUu�A�S����AU��A
   ���~G�A����t @�Fc�Rf��Ni��YKlڹT��S��C\��/��Ȧ��'���R   bލ��?^AU��A              �?��(A  �@  �?i���? AU��A�S����AU��A   �c j� E��H(�[�� d�m��0���ꢷ�DP����O�t����JR� ��}��G   OY�A�y�VU�              �?TU�@  A   A�n�A�ɝ��*���C�A�7���;@   �c j� E��H(�[�� dۊ�Օ���Á��p�K(6�v/O�t����JR� ��}��G   OY�A6t��VU�              �?TU�@TUA   A�n�A�����*���C�A�����;@   ���d�y@փ+���'� �.�Cj΅���l�lq��f���{[�=`O�L ����tIj����   �<�C�p�Uu�A              �?��*>��6A���?d�=��̃���A�4;���Y«��A   ���d�y@փ+���'� �/���f07L6���	���{[�=`O�L ����tIj����   ��G�C�p�Uu�A              �?��*>��6A���?�3I��̃���AJ�F���Y«��A   ��_z�`F��%F��l I!�m-[�ڲ���p�V��[�H�_����˖���dn`   E#��^�A�z2�����7j�?�N�<
+a�d��n�Kn:��e7   nz`�A p1�        �<	�?t�hBb"�B  �?)������ p1��:�^�B p1�   ��>pZK\��݄KE� �YK`� ��T��yh^y�,3�/�?^��ɬ�@MQ��
x>�Pr$   �v�AZB-�y�W��u���?yi�95������>!��@hg<A���A�=^����J]�AxF��[���   ��>pZK\��݄KE� �Y�b8
x>�Pr$   &��Az˟�v�W���u���?lɫ�O�{6I��>���@�b<AޱA����<p�A���[���   ��>pZK\��݄KE� �Zj�ܖ�Ū��]|j4��caN�1
x>�Pr$   ���A9{�KA Ap�1?r8??�<��|<r��>`�ZA�qBʎ�A�����(
��aN�1
x>�Pr$   y
x>�Pr$   ���A�=z�W��wȱ]�4y�?�Ux���>��j@]Uq@��Ayҋ��5��8�A��\�[���   ��>pZK\��݄KE� �yZP�ߡ�s� ��W�5L���?^��ɬ�@MQ��
x>�Pr$   PȴA(�����~v�b�?c=���
ƕ>�q@ ��@�2�A�'���5��b�A`w��[���   �����Fo�`����,1 �ϐ��f07L6���	���{[�=`O�L ����tIj����   �Y��
�Ad�*>���?�A�?���A^�B� ����A   �����Fo�`����,1 �	��7o��'��O(�!�[2{[�=`O�L ����tIj����   R��A�;
V^��O�Z��O8a�Ş{[�=`O�L ����tIj����   �y�AMVX@Uu�AK����h�5��5?�+>j׳Av��?u!A� S@��A�2B��]@���A   �����Fo�`����,1 ��l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   X*�A�+@Uu�A        \y��  �?�]�A��*>���?%�'A��%@��A�,BNf0@���A   �����Fo�`����,1 ��l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   �)��nAUu�A        ҙ��  �?�G�A�*>���?�8�=�lA��A��%A�joA���A   �����Fo�`����,1 ��l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   �(�>�bAUu�A        ����  �?IA�Ay�*>���?�8��naA��A��#A�dA���A   �����Fo�`����,1 ��l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   v�A�nAUu�A        a���  �?>�A�*>���?��%A=�lA��A<�B�joA���A   �����Fo�`����,1 ��l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ށ�A>�bAUu�A         n��  �?=D�A\�*>���?��#A�naA��A��B�dA���A   �����Fo�`����,1 �l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   k���
�AUu�A        Ue��  �?~ӱA�*>���?a7�`�A��A��,Au��A���A   �����Fo�`����,1 �l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ��ξb�AUu�A        @���  �?���Ak�*>���?V-7�u��A��A�=*A��A���A   �����Fo�`����,1 �l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   Q"�A�
�AUu�A        r۷�  �?��A�*>���?��,A`�A��A��Bu��A���A   �����Fo�`����,1 �l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   ܆�Ab�AUu�A        �Q��  �?�ϰAj�*>���?�=*Au��A��Am�B��A���A   �����Fo�`����,1 � &M�_(���m(!Np?�>�{[�=`O�L ����tIj����   ����e�BUu�A        Hp��  �?ȱ�A߭*>���?�~5�0B��A��%A��B���A   �����Fo�`����,1 �!&M�_(���m(!Np?�>�{[�=`O�L ����tIj����   ����BUu�A        ����  �?���A�*>���?��5��[B��A��#AeB���A   �����Fo�`����,1 �"l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   TܬAe�BUu�A        s���  �?�ӳAڭ*>���?��%A0B��AcB��B���A   �����Fo�`����,1 �#l$#�=Ӷ�����ҕ���{[�=`O�L ����tIj����   �L�A�BUu�A        �`��  �?�ٴAԮ*>���?��#A�[B��A�\BeB���A   �����Fo�`����,1 �y�iukc.�~�|�W��X	�[�{[�=`O�L ����tIj����   ��|��N[�Uu�A              �? j�A �*>���?�4;�F�[���AG�A��Z«��A   �����Fo�`����,1 �{a���ƹ���h���C�!�{[�=`O�L ����tIj����   �ɢA�=[�Uu�A              �?���A �*>���?G�AF�[���AU��A��Z«��A   �`կ��FՌ�к��Q ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   x� B:DBVUN��J	�N��5?�5?d�)?a�O?���B�p�A��BB p1¢vB�nEBV�Bh5  �`կ��FՌ�к��Q �6�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   	r B:BVUN��J	�N��5?�5?d�)?a�O?���B���A��B p1�3B�nBV�Bh5  �`կ��FՌ�к��Q ��))�
�4.�4�z���Q��3�ޒ�8�����ġ���   � Bt6�AVUN��J	�N��5?�5?d�)?a�O?���B���A��A p1�īB���AV�Bh5  �`կ��FՌ�к��Q �z�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   VN�A�lhAVUN��J	�N��5?�5?d�)?a�O?���B �A>cA p1�UFB��mAV�Bh5  �`կ��FՌ�к��Q ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   x��A��A@VUN��J	�N��5?�5?d�)?a�O?���B"E�A�x,@ p1��� BM�V@V�Bh5  �`կ��FՌ�к��Q �,�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ���A��VUN��J	�N��5?�5?d�)?a�O?���BDz�A��� p1�w{ BmD�V�Bh5  �`կ��FՌ�к��Q ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   ���A�ɟ�VUN��J	�N��5?�5?d�)?a�O?���Bf��A�p�� p1� B6"��V�Bh5  �`կ��FՌ�к��Q �4�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �"�A����VUN��J	�N��5?�5?d�)?a�O?���B���A�p�� p1�3a�A6"��V�Bh5  �`կ��FՌ�к��Q ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �W�A��+�VUN��J	�N��5?�5?d�)?a�O?���B��Aq8-� p1�U��A�*�V�Bh5  �`կ��FՌ�к��Q ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   !��A��Y�VUN��J	�N��5?�5?d�)?a�O?���B�N�Aq8[� p1�w��A�X�V�Bh5  �`կ��FՌ�к��Q �m�))�
�4.�4�z���Q��3�ޒ�8�����ġ���   �2B��̃�VUN�N�J	.�5��5?d�)?a�O?���Bd�H��v�� p1��;�#��V�Bh5  �`կ��FՌ�к��Q ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   xRK@�̃�VUN��J	�N��5?�5?d�)?a�O?���B�_1@�v�� p1�#Ee@#��V�Bh5  �`կ��FՌ�к��Q ���))�
�4.�4�z���Q��3�ޒ�8�����ġ���   n�pA�̃�VUN��J	�N��5?�5?d�)?a�O?���B�KjA�v�� p1�EwA#��V�Bh5  ���L�����	\�� �a���ƹ���h���C�!�א�� �s�gtQ�#�e;$,�   ���A5���
��?              �?�ގ@���>3҉B��A���«:��A�L�¼iB   ���L�����	\�� e�Cj΅���l�lq��f���א�� �s�gtQ�#�e;$,�   ��/�5���
��?              �?�ގ@���>3҉B4NS����«:�����L�¼iB   ���L�����	\�� �\�i�����o�͒ma��U�3א�� �s�gtQ�#�e;$,�   w)A5���B              �?ֻ2B���>��m@4NS����¼iB���A�L��VE B   ���L�����	\�� e���f07L6���	���א�� �s�gtQ�#�e;$,�   ���A5���
3��        ����  �?XU@���>�$T@;n�A���«:���A�L�¿���   ��MF,�M��-4��[ \���f07L6���	���{[�=`O�L ����tIj����   ��BlC$AQյ@              �?�U�>�X�@TU1Ai�B���@��> B�dAR�3A   ��'6!LKȲ�D���� Fބ���JE�Y9$څ����[�H�_����˖���dn`   P�B�N�� ��Y�ڶ���6��=���+?@c�B�ٓB�?�(B܂«��|��B��fAV��.   ��'6!LKȲ�D���� FS�|K�@�x��:�
��A��!�
+a�d��n�Kn:��e7   }�B!��V��        8pe=�?N�Bу�B  �?�(B܂�V��|��B��fAV��   ��'6!LKȲ�D���� F='�������E��N��n�j�[�H�_����˖���dn`   ��B�O��[���k+7s|��l�?S�<=���BR�B�W?�(B܂¬
��|��B��fA��"   ��'6!LKȲ�D���� F=�+�ԫh��e^��_��~�S5�!�
+a�d��n�Kn:��e7   )�B�����        ԵM=L�?�^�B/�B  �?�(B܂���|��B��fA��
   ��'6!LKȲ�D���� FS'�������E��N��n�j�[�H�_����˖���dn`   ��B�O����-�k+7s|��l�?S�<=���BR�B�W?�(B܂�X2�|��B��fA�)�"   ��'6!LKȲ�D���� FS�+�ԫh��e^��_��~�S5�!�
+a�d��n�Kn:��e7   )�B����)�        ԵM=L�?�^�B/�B  �?�(B܂��)�|��B��fA�)�
   ��'6!LKȲ�D���� Fh'�������E��N��n�j�[�H�_����˖���dn`   ��B�O���Z���j+73|��l�?W�<=���BR�B�W?�(B܂°�¾|��B��fA��>"   ��'6!LKȲ�D���� Fh�+�ԫh��e^��_��~�S5�!�
+a�d��n�Kn:��e7   )�B�����>        ԵM=L�?�^�B/�B  �?�(B܂ �>|��B��fA��>
   �clmG��G �)� �eh��&��ɼs�ϙC�\Q�{[�=`O�L ����tIj����    c�B����:�APz9����<�?z ��L�B:�@�D�?Q��A�J�©�vA��B�Ԁ¨X�A$   �g�5��B�� ��Y�O ��5?�'CV��[J���m%)���}$uJ�q�NeȊq�`�1��    ���Aq���\@?�4??�4?���� ��<+%�A836BlA��n���>�BƄ����A@   �g�5��B�� ��Y�O �@zIi5���xpb�(<hg
1ћfb��   ��
1ћfb��   ?a�nPªʖA        �5��5?
�J�Uu�A�°��eJ�Uu�A   ��=
�H©�vA����7©�zA   ��=
�H�T�}A����7��A  ��=
�A��A	{�A�_�A�   ���`YF����kR ʫ��H�"i�!��J.�����Ѐ&�A ���l�o�O�   	���A���A�*xA4�<�5�<9�5��5?TU�?�V�?�� >&��A��A��vA{4�AkB�A�jyA  ���`YF����kR �?��$���je�#l��?7 ^*������5/���&9����   	U��Ae2�A��vA        ��?| �*"�?�\>  �?{��Ak��A��vA{��Ak��A��vA   ���`YF����kR ʰ��L[��K�;�
o�\-�aN�1
�A��A�E�A�_�A�   ���`YF����kR ٫��H�"i�!��J.�����Ѐ&�A ���l�o�O�   	���A!�B�*xA4�<�5�<9�5��5?TU�?�V�?�� >&��A̻B��vA{4�AvB�jyA  ���`YF����kR �?��$���je�#l��?7 ^*������5/���&9����   	U��As�B��vA        ��?| �*"�?�\>  �?{��Av�B��vA{��Av>B��vA   ���`YF����kR ٰ��L[��K�;�
o�\-�aN�1
!B��A   ���`YF����kR ?L�{xp0�4����|��Yb��}$uJ�q�NeȊq�`�1��   	t~�@�B�9�Ah����]:�h<��{?g�@��A��s>\H@��A�J�A�A��B��A�  ���`YF����kR ?L��wc�	�Y�ZY�Ȳ`�S�@JT`}��������]܄���}   	�5D@�UBU��A�S�2(�~?�MŽ������?U��?q@�5@�B�jyA�5k@Q�BU��A0   ���`YF����kR ?L�ǰ���sǿ���Y���{[�=`O�L ����tIj����   	&U�@Y
BU5�A        Y�l?0��>��?k�5@��*=�
�AU��@L�B�_�A�   ���`YF����kR ?LV����Eo2O{/�M%b�`9���Ѐ&�A ���l�o�O�   	�5D@�QB�*xA$��9��m+:�����?SU�?�V�?�� >��!@Q0B��vAP�f@�rB�jyA  ���`YF����kR ?L�r,`S#�-;��Z��+:&�^*������5/���&9����   	�`b@�`B��vA        �=3?{�6?)"�?�\>  �?�`^@QpB��vA�`f@PPB��vA   ���`YF����kR ?LWy�f�s7-���^�ϣۨ�������Hd�xw
�AAOA�d<B�_�A�   ���`YF����kR A?���H�"i�!��J.�����Ѐ&�A ���l�o�O�   	�5D@�&B�*xA$����n+M��2��?SU�?�V�?�� >��!@��"B��vAP�f@?<)B�jyA  ���`YF����kR A??��$���je�#l��?7 ^*������5/���&9����   	�`b@�&B��vA        �=3�{�6?)"�?�\>  �?�`^@@#B��vA�`f@?�(B��vA   ���`YF����kR A?���L[��K�;�
o�\-�aN�1
!B��A   ���`YF����kR Ě{ɥ��W�<q� {�%��6�}$uJ�q�NeȊq�`�1��   	�<HA�B�9�A�]�i��9�{?�h<�g�@��A��s>jA��A�J�A5�A��B��A�  ���`YF����kR E̤�wc�	�Y�ZY�Ȳ`�S�@JT`}��������]܄���}   	��zA�UBU��A�S�2(�~?�MŽ������?U��?q@�.qA�B�jyARW�AP�BU��A0   ���`YF����kR E��ǰ���sǿ���Y���{[�=`O�L ����tIj����   	�QAAY
BU5�A        /��>Y�l?��?k�5@��*=w-A�B�
�A5�SAL�B�_�A�   ���`YF����kR E̫��H�"i�!��J.�����Ѐ&�A ���l�o�O�   	��zA�QB�*xA�X(�$�����?�2SU�?�V�?�� >NYrAP0B��vA���A�rB�jyA  ���`YF����kR E�?��$���je�#l��?7 ^*������5/���&9����   	�csA�`B��vA        {�6?�=3?)"�?�\>  �?�crAPpB��vA�ctAPPB��vA   ���`YF����kR Ḛ��L[��K�;�
�B�ʒA  ���`YF����kR E�������/�E�qx�
o�\-�aN�1
�A5�SA�d<B�_�A�   ���`YF����kR G�V����Eo2O{/�M%b�`9���Ѐ&�A ���l�o�O�   	��zA�&B�*xA~W(�$��9��?#��SU�?�V�?�� >NYrA��"B��vA���A@<)B�jyA  ���`YF����kR G��r,`S#�-;��Z��+:&�^*������5/���&9����   	�csA�&B��vA        {�6��=3?)"�?�\>  �?x�q@@#B��vAx�y@?�(B��vA   ���`YF����kR G�Wy�f�s7-���^�ϣۨ�������Hd�xw
�~�#QDғ�6��ޞ�2��r`<\�{�E   VBC��V5���=ƾuK; �?�? >�K,?��A�  B7��?ؗ�3�BO0�n����  ��$젆J��`��7P �S�l�u���C�� ���b�:�}$uJ�q�NeȊq�`�1��   sB��'�P���������?����29�����f?��c@�>B_�(�7�����B��&�n�|��   ��$젆J��`��7P �S�l�u���C�� ���b�:�}$uJ�q�NeȊq�`�1��   ��B;'�8���������?/���{29����qe?D�c@��B��'������Bq�%�uq���   ��$젆J��`��7P ��}d7�A�\֢.�K5��o�}$uJ�q�NeȊq�`�1��   ��B�b'�ܖ���?���<��0�Ep�����.�
�ۡ��Rs~ �m����솾���ɸfN��{[�=`O�L ����tIj����   Y��@i�a@���A�:?��/�����NE���>�BPUA�c:�zG@���Apy�A���@��B   ���ׯ�J
�ۡ��Rs~ �n��I��!h���&��w9����{[�=`O�L ����tIj����   ;n��,�AUu�A        �k��  �?�7AJl�>��A�9�֥A���A����P	A �B   ���ׯ�J
�ۡ��Rs~ �o�r��d;nk�Q�1^s){[�=`O�L ����tIj����   g𥾘�@Uu�A        �a�9��?b��>�Ϛ@��A�M���T@���A���֥A �B   ���ׯ�J
�ۡ��Rs~ �p䤗��̠{Ƨ݇�i(c��{[�=`O�L ����tIj����   S���\5h@Uu�A        t&�  �?��1Am�>��A�;:��Z@���A�M���u@ �B   ���ׯ�J
�ۡ��Rs~ �qp��mӵ�$G�dv�;3V_�{[�=`O�L ����tIj����   ���A�,kAUu�A        ��ط  �?@R�@l~�>��Apy�Aq�gA���A ��A�nA �B   ���ׯ�J
�ۡ��Rs~ �r�Cj΅���l�lq��f���{[�=`O�L ����tIj����   $�A-cAUu�A              �?@U�>��0A��Apy�A��[@���A���Aq�gA �B   ���ׯ�J
�ۡ��Rs~ �s	�z,@�`٠�������{[�=`O�L ����tIj����   ���A�i@Uu�Ak�4?j�4�rټ��<Ƀ�>���@Ì&A���A��[@���A56BNfv@ �B   ���ׯ�J
�ۡ��Rs~ �y���f07L6���	���{[�=`O�L ����tIj����   $�A� w@���A          �?      @@Z��=  �@$�A?d@���A$�A�k@U�B   ���ׯ�J
�ۡ��Rs~ �y(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   $�A���@�J�A          �?      P@  �?  �@$�A�G�>���A$�A�G�>UeB   ���ׯ�J
�ۡ��Rs~ �y�f��V]�I���ʪ����0����$P�����L��m�   $�A�i@�J�A    :8  �?      P@k) ?] �@$�A�Y@���A$�A�y@UeB<   ���ׯ�J
�ۡ��Rs~ �v�eW�[��qqfDεA�{[�=`O�L ����tIj����   ��@x[@T�Av:?��/�R(R�	���Փ�> iBTUA�c:�zG@UՅ@�4�AUT�@�?VA   ���ׯ�J
�ۡ��Rs~ ����I��!h���&��w9����{[�=`O�L ����tIj����   ;n��,�A�?A        �k��  �?�7AJl�>��A�9�֥AUՅ@����P	AR�aA   ���ׯ�J
�ۡ��Rs~ ���r��d;nk�Q�1^s){[�=`O�L ����tIj����   g𥾘�@�?A        �a�9��?b��>�Ϛ@��A�M���T@UՅ@���֥AR�aA   ���ׯ�J
�ۡ��Rs~ ��䤗��̠{Ƨ݇�i(c��{[�=`O�L ����tIj����   S���\5h@�?A        t&�  �?��1Am�>��A�;:��Z@UՅ@�M���u@R�aA   ���ׯ�J
�ۡ��Rs~ ��p��mӵ�$G�dv�;3V_�{[�=`O�L ����tIj����   ���A�,kA�?A        ��ط  �?@R�@l~�>��Apy�Aq�gAUՅ@ ��A�nAR�aA   ���ׯ�J
�ۡ��Rs~ ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   $�A-cA�?A              �?@U�>��0A��Apy�A��[@UՅ@���Aq�gAR�aA   ���ׯ�J
�ۡ��Rs~ ��	�z,@�`٠�������{[�=`O�L ����tIj����   ���A�i@�?Ak�4?j�4�rټ��<Ƀ�>���@Ì&A���A��[@UՅ@56BNfv@R�aA   ���ׯ�J
�ۡ��Rs~ ����I��!h���&��w9����{[�=`O�L ����tIj����   �������A�?A        3�׶  �?O�HA�j�>��A(7�KU�AUՅ@<ً?���AR�aA   ���ׯ�J
�ۡ��Rs~ ���N��U�	J��2D��a���{[�=`O�L ����tIj����   �,���%B�?A�͌;-?��$"���h�>��Am�\A��>�-�BUՅ@����4GBR�wA&   ���ׯ�J
�ۡ��Rs~ ���i����w,F��Ҩw�x͉�{[�=`O�L ����tIj����   =���?�B�?A        T�;d�?��A|�?��4A� 6�ڊBUՅ@�J>��BR�wA   ���ׯ�J
�ۡ��Rs~ �����2�T��[��Y�x{[�=`O�L ����tIj����   ��=�/`
�ۡ��Rs~ ���:-��'�%r<�t��7�6A�}$uJ�q�NeȊq�`�1��   ���\
�ۡ��Rs~ ������,��u�+�~{�A^-}�0����$P�����L��m�   ��/�C^
�ۡ��Rs~ �����f07L6���	���{[�=`O�L ����tIj����   �V8���
�ۡ��Rs~ ��"���i�OW"@r'f%A�)3�0����$P�����L��m�   ��;���
�ۡ��Rs~ ��(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   /}B�:�
�ۡ��Rs~ �����f07L6���	���{[�=`O�L ����tIj����   $�A� w@R��@          �?      @@Z��=  �@$�AJrs@RՅ@$�A��z@��2A   ���ׯ�J
�ۡ��Rs~ ��(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   $�A���@R��@          �?      P@  �?  �@$�A�G�>RՅ@$�A�G�>��4A   ���ׯ�J
�ۡ��Rs~ ���f��V]�I���ʪ����0����$P�����L��m�   $�A�i@R��@    :8  �?      P@k) ?] �@$�A�Y@RՅ@$�A�y@��4A<   ���ׯ�J
�ۡ��Rs~ ������ݮ6-�����g�����{[�=`O�L ����tIj����   �=��K_4@���;�/?�:?�`T���(��>"49ATUA�c:�zG@�*����� wV@��@   ���ׯ�J
�ۡ��Rs~ ����I��!h���&��w9����{[�=`O�L ����tIj����   ;n��,�A �        �k��  �?�7AJl�>��A�9�֥A�*������P	AJU6@   ���ׯ�J
�ۡ��Rs~ ���r��d;nk�Q�1^s){[�=`O�L ����tIj����   g𥾘�@ �        �a�9��?b��>�Ϛ@��A�M���T@�*�����֥AJU6@   ���ׯ�J
�ۡ��Rs~ ��䤗��̠{Ƨ݇�i(c��{[�=`O�L ����tIj����   S���\5h@ �        t&�  �?��1Am�>��A�;:��Z@�*���M���u@JU6@   ���ׯ�J
�ۡ��Rs~ ��p��mӵ�$G�dv�;3V_�{[�=`O�L ����tIj����   ���A�,kA �        ��ط  �?@R�@l~�>��Apy�Aq�gA�*�� ��A�nAJU6@   ���ׯ�J
�ۡ��Rs~ �����f07L6���	���{[�=`O�L ����tIj����   $�A��A �              �?@U�>�=*A��Apy�ANfv@�*�����Aq�gAJU6@   ���ׯ�J
�ۡ��Rs~ ��!u�G��87`�>cQj�� {[�=`O�L ����tIj����   ��A�i@ �s�4?�4�]��</�˼�j�>}�A��2AXceA��[@�*��56BNfv@JU6@%   ���ׯ�J
�ۡ��Rs~ ����4{T�jG���F,�1Ȍ�������n��\w&e�mO�[   XceA�i@ �              �?  �?`U�>��AXceA��[@�*��XceANfv@JU6@   ���ׯ�J
�ۡ��Rs~ ���N��U�	J��2D��a���{[�=`O�L ����tIj����   �,���%B
�ۡ��Rs~ ���i����w,F��Ҩw�x͉�{[�=`O�L ����tIj����   =���?�B ��        T�;d�?��A|�?��4A� 6�ڊB�*���J>��B�*�@   ���ׯ�J
�ۡ��Rs~ �����2�T��[��Y�x{[�=`O�L ����tIj����   ��=�/`
�ۡ��Rs~ ���:-��'�%r<�t��7�6A�}$uJ�q�NeȊq�`�1��   ���\
�ۡ��Rs~ ������,��u�+�~{�A^-}�0����$P�����L��m�   ��/�C^
�ۡ��Rs~ �����f07L6���	���{[�=`O�L ����tIj����   �V8���
�ۡ��Rs~ ��"���i�OW"@r'f%A�)3�0����$P�����L��m�   ��;���
�ۡ��Rs~ ��(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   /}B�:�
�ۡ��Rs~ �����f07L6���	���{[�=`O�L ����tIj����   $�A� w@[Ud�          �?      @@Z��=  �@$�A?d@�*��$�A�k@k���   ���ׯ�J
�ۡ��Rs~ ��(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   $�A���@[U`�          �?      P@  �?  �@$�A�G�>�*��$�A�G�>+�j=   ���ׯ�J
�ۡ��Rs~ ���f��V]�I���ʪ����0����$P�����L��m�   $�A�i@\U`�    :8  �?      P@k) ?] �@$�A�Y@�*��$�A�y@+�j=<   ���ׯ�J
�ۡ��Rs~ ����I��!h���&��w9����{[�=`O�L ����tIj����   ;n��,�A�jf�        �k��  �?�7AJl�>��A�9�֥A�������P	AX�   ���ׯ�J
�ۡ��Rs~ ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   f����@�jf�              �?TU�>_�@��A�M��\H@������֥AX�   ���ׯ�J
�ۡ��Rs~ ��䤗��̠{Ƨ݇�i(c��{[�=`O�L ����tIj����   S���\5h@�jf�        u&�  �?��1Am�>��A�;:��Z@����M���u@X�   ���ׯ�J
�ۡ��Rs~ ��p��mӵ�$G�dv�;3V_�{[�=`O�L ����tIj����   ���A�,kA�jf�        ��ط  �?@R�@l~�>��Apy�Aq�gA��� ��A�nAX�   ���ׯ�J
�ۡ��Rs~ ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   $�A-cA�jf�              �?@U�>��0A��Apy�A��[@������Aq�gAX�   ���ׯ�J
�ۡ��Rs~ ��	�z,@�`٠�������{[�=`O�L ����tIj����   ���A�i@�jf�k�4?j�4�hټ��<Ƀ�>���@Č&A���A��[@���56BNfv@X�   ���ׯ�J
�ۡ��Rs~ ��{}"*�{ƨ�=NdicOz"x��{[�=`O�L ����tIj����   ������A�jf�        ��G�  �?bjA�q�>��A(7�KU�A��������AX�   ���ׯ�J
�ۡ��Rs~ ���N��U�	J��2D��a���{[�=`O�L ����tIj����   �,���%B�j[��͌;-?��/"���h�>��As�\A��>�-�B�������4GBV�&   ���ׯ�J
�ۡ��Rs~ ���i����w,F��Ҩw�x͉�{[�=`O�L ����tIj����   =���?�B�j[�        T�;d�?��A|�?��4A� 6�ڊB����J>��BV�   ���ׯ�J
�ۡ��Rs~ �����2�T��[��Y�x{[�=`O�L ����tIj����   ��=�/`
�ۡ��Rs~ ���:-��'�%r<�t��7�6A�}$uJ�q�NeȊq�`�1��   ���\
�ۡ��Rs~ ������,��u�+�~{�A^-}�0����$P�����L��m�   ��/�C^
�ۡ��Rs~ �����f07L6���	���{[�=`O�L ����tIj����   �V8���
�ۡ��Rs~ ��"���i�OW"@r'f%A�)3�0����$P�����L��m�   ��;���
�ۡ��Rs~ ��(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   /}B�:�
�ۡ��Rs~ �����f07L6���	���{[�=`O�L ����tIj����   $�A� w@�}�          �?      @@Z��=  �@$�AJrs@���$�A��z@�E�   ���ׯ�J
�ۡ��Rs~ ��(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   $�A���@�|�          �?      P@  �?  �@$�A�G�>���$�A�G�>�C�   ���ׯ�J
�ۡ��Rs~ ���f��V]�I���ʪ����0����$P�����L��m�   $�A�i@�|�    :8  �?      P@k) ?] �@$�A�Y@���$�A�y@�C�<   �!��PF�����(�� �����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   �;�A:BT�fA�5?�5?���'~<2�j
?�(�AbU�?��.AeB��^A-��A0B��nA{
?B�9AZU�?YͿeB��^Aw  A0B��nAc  �!��PF�����(�� �B�Fx��O\�
49�@��5?�5?�j
?&�A\U�?��/�eB��^A���0B��nA�  �!��PF�����(�� ®���5U�	���,���p�E�Q��3�ޒ�8�����ġ���   q�At6�AT�fA�5?�5?���'~<2�j
?�(�AbU�?�`-A��A��^AO��A`�A��nA{
L�WCߴ  �?��&
�A�j
?YU�?Yk1���A��^A�jA`�A��nA�  �!��PF�����(�� Į���5U�	���,���p�E�Q��3�ޒ�8�����ġ���   @��A�lhAT�fA�5?�5?����~<2�j
?�(�AbU�?
?
�AwU�?3� VcA��^A��A��kA��nA�
?�(�AbU�?{5*AMf0@��^A�C�A� S@��nA{
��&�$�A�j
?WU�?=
5�Mf0@��^AC?A� S@��nA�  �!��PF�����(�� Ȯ���5U�	���,���p�E�Q��3�ޒ�8�����ġ���   ��A��T�fA�5?�5?���'~<2�j
?�(�AbU�?��(Am����^A�x�A�?���nA{
?WU�?ܭ6�m����^A��A�?���nA�  �!��PF�����(�� ʎ��
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   �E�A�Z��T�fA�D$��4  �?Dm�&�(�A�j
?XU�?vb&AS�����^AZ�A�0����nA�
?
�AwU�?I�7�S�����^A�A�0����nA�
?�(�AbU�?��$AVa����^A3��A����nA{
?�ĨAdU�?d;�Va����^A~A����nA�
?�(�AbU�?�6#A-�,���^AU��A�u*©�nA{
?���AlU�?d;�-�,���^AS�A�u*©�nA�
?�(�AbU�?�H"A��Z���^A=M�A��X©�nA{
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   2㞿��Y�T�fA    9�(3  �?    �.�A�j
?UU�?d;���Z���^A�RA��X©�nA�
?�(�AbU�?��.AeB��B-��A0BU�B{
?B�9AZU�?YͿeB��Bw  A0BU�Bc  �!��PF�����(�� �B�Fx��O\�
49�@��5?�5?�j
?&�A\U�?��/�eB��B���0BU�B�  �!��PF�����(�� 䮱��5U�	���,���p�E�Q��3�ޒ�8�����ġ���   q�At6�A �B�5?�5?���'~<2�j
?�(�AbU�?�`-A��A��BO��A`�AU�B{
L�WCߴ  �?��&
�A�j
?YU�?Yk1���A��B�jA`�AU�B�  �!��PF�����(�� 殱��5U�	���,���p�E�Q��3�ޒ�8�����ġ���   @��A�lhA �B�5?�5?����~<2�j
?�(�AbU�?
?
�AwU�?3� VcA��B��A��kAU�B�
?�(�AbU�?{5*AMf0@��B�C�A� S@U�B{
��&�$�A�j
?WU�?=
5�Mf0@��BC?A� S@U�B�  �!��PF�����(�� ꮱ��5U�	���,���p�E�Q��3�ޒ�8�����ġ���   ��A�� �B�5?�5?���'~<2�j
?�(�AbU�?��(Am����B�x�A�?�U�B{
?WU�?ܭ6�m����B��A�?�U�B�  �!��PF�����(�� ���
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   �E�A�Z�� �B�D$��4  �?Dm�&�(�A�j
?XU�?vb&AS�����BZ�A�0��U�B�
?
�AwU�?I�7�S�����B�A�0��U�B�
?�(�AbU�?��$AVa����B3��A��U�B{
?�ĨAdU�?d;�Va����B~A��U�B�
?�(�AbU�?�6#A-�,ª�BU��A�u*�U�B{
?���AlU�?d;�-�,ª�BS�A�u*�U�B�
?�(�AbU�?k�!A��Zª�B��A��X�U�B{
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   2㞿��Y� �B    9�(3  �?    �.�A�j
?UU�?d;���Zª�B�RA��X�U�B�
?�(�AbU�?��.AeB�*@-��A0B��k@{
?B�9AZU�?YͿeB�*@w  A0B��k@c  �!��PF�����(�� B�Fx��O\�
49�@��5?�5?�j
?&�A\U�?��/�eB�*@���0B��k@�  �!��PF�����(�� ����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   q�At6�AOK@�5?�5?���'~<2�j
?�(�AbU�?�`-A��A�*@O��A`�A��k@{
L�WCߴ  �?��&
�A�j
?YU�?Yk1���A�*@�jA`�A��k@�  �!��PF�����(�� ����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   @��A�lhAOK@�5?�5?����~<2�j
?�(�AbU�?
?
�AwU�?3� VcA�*@��A��kA��k@�
?�(�AbU�?{5*AMf0@�*@�C�A� S@��k@{
�Ʈ��ޕ�Z�X�<���d�Q��3�ޒ�8�����ġ���   �WN���A@OK@��.��  �?
��&�$�A�j
?WU�?=
5�Mf0@�*@C?A� S@��k@�  �!��PF�����(�� ����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   ��A��OK@�5?�5?���'~<2�j
?�(�AbU�?��(Am���*@�x�A�?���k@{
?WU�?ܭ6�m���*@��A�?���k@�  �!��PF�����(�� 
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   �E�A�Z��OK@�D$��4  �?Dm�&�(�A�j
?XU�?vb&AS����*@Z�A�0����k@�
?
�AwU�?I�7�S����*@�A�0����k@�
?�(�AbU�?��$AVa���*@3��A����k@{
?�ĨAdU�?d;�Va���*@~A����k@�
?�(�AbU�?�6#A-�,��*@U��A�u*¥�k@{
?���AlU�?d;�-�,��*@S�A�u*¥�k@�
?�(�AbU�?�H"A��Z��*@=M�A��X¥�k@{
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   2㞿��Y�OK@    9�(3  �?    �.�A�j
?UU�?d;���Z��*@�RA��X¥�k@�
?�(�AbU�?��.AeB`	�-��A0B�*��{
?B�9AZU�?YͿeB`	�w  A0B�*��c  �!��PF�����(�� %B�Fx��O\�
49�@��5?�5?�j
?&�A\U�?��/�eB`	����0B�*���  �!��PF�����(�� &����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   q�At6�A�:��5?�5?���'~<2�j
?�(�AbU�?�`-A��A`	�O��A`�A�*��{
L�WCߴ  �?��&
�A�j
?YU�?Yk1���A`	��jA`�A�*���  �!��PF�����(�� (����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   @��A�lhA�:��5?�5?����~<2�j
?�(�AbU�?
?
�AwU�?3� VcA`	���A��kA�*���
?�(�AbU�?{5*AMf0@`	��C�A� S@�*��{
��&�$�A�j
?WU�?=
5�Mf0@`	�C?A� S@�*���  �!��PF�����(�� ,����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   ��A���:��5?�5?���'~<2�j
?�(�AbU�?��(Am��`	��x�A�?��*��{
?WU�?ܭ6�m��`	���A�?��*���  �!��PF�����(�� .���
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   �E�A�Z���:��D$��4  �?Dm�&�(�A�j
?XU�?vb&AS���`	�Z�A�0���*���
?
�AwU�?I�7�S���`	��A�0���*���
?�(�AbU�?��$AVa��`	�3��A���*��{
?�ĨAdU�?d;�Va��`	�~A���*���
?�(�AbU�?�6#A-�,�`	�U��A�u*®*��{
?���AlU�?d;�-�,�`	�S�A�u*®*���
?�(�AbU�?�H"A��Z�`	�=M�A��X®*��{
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   2㞿��Y¬:�    9�(3  �?    �.�A�j
?UU�?d;���Z�`	��RA��X®*���
?�(�AbU�?��.AeBV��-��A0B���{
?B�9AZU�?YͿeBV��w  A0B���c  �!��PF�����(�� FB�Fx��O\�
49�@��5?�5?�j
?&�A\U�?��/�eBV�����0B����  �!��PF�����(�� G����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   q�At6�A����5?�5?���'~<2�j
?�(�AbU�?�`-A��AV��O��A`�A���{
L�WCߴ  �?��&
�A�j
?YU�?Yk1���AV���jA`�A����  �!��PF�����(�� I����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   @��A�lhA����5?�5?����~<2�j
?�(�AbU�?
?
�AwU�?3� VcAV����A��kA����
?�(�AbU�?{5*AMf0@V���C�A� S@���{
��&�$�A�j
?WU�?=
5�Mf0@V��C?A� S@����  �!��PF�����(�� M����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   ��A������5?�5?���'~<2�j
?�(�AbU�?2�'Am��V���$�A�?����{
?WU�?ܭ6�m��V����A�?�����  �!��PF�����(�� O���
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   �E�A�Z������D$��4  �?Dm�&�(�A�j
?XU�?vb&AS���V��Z�A�0������
?
�AwU�?I�7�S���V���A�0������
?�(�AbU�?��$AVa��V��3��A�����{
?�ĨAdU�?d;�Va��V��~A������
?�(�AbU�?�6#A-�,�V��U��A�u*����{
?���AlU�?d;�-�,�V��S�A�u*�����
?�(�AbU�?A�!A��Z�V��w��A��X����{
6��0�A=�o�^�4Q��3�ޒ�8�����ġ���   2㞿��Y«��    9�(3  �?    �.�A�j
?UU�?d;���Z�V���RA��X�����
?�(�AbU�?"O.AeBVM�gP�A0B�:�{
?B�9AZU�?YͿeBVM�w  A0B�:�c  �!��PF�����(�� gB�Fx��O\�
49�@��5?�5?�j
?&�A\U�?��/�eBVM����0B�:´  �!��PF�����(�� h����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   q�At6�A D��5?�5?���'~<2�j
?�(�AbU�?f�,A��AVM��A`�A�:�{
L�WCߴ  �?��&
�A�j
?YU�?Yk1���AVM»jA`�A�:��  �!��PF�����(�� j����5U�	���,���p�E�Q��3�ޒ�8�����ġ���   @��A�lhA D��5?�5?����~<2�j
?�(�AbU�?�#+A�dAVM«��A>�lA�:�{
?
�AwU�?3� VcAVM���A��kA�:§
?�(�AbU�?�)AMf0@VM�b��A� S@�:�{
��&�$�A�j
?WU�?=
5�Mf0@VM�C?A� S@�:��  �!��PF�����(�� o�Ʈ��ޕ�Z�X�<���d�Q��3�ޒ�8�����ġ���   �"h��� D�S���qy�  �?ʟ�&�+�A�j
?WU�?ܭ6�m��VM�A�?��:��  �!��PF�����(�� q��n��4i�V�� V�I�gE�Q��3�ޒ�8�����ġ���   �s}��Z�� D��5��5?�G`�z⩳�j
?
�AwU�?I�7�S���VM��A�0���:§
?�ĨAdU�?d;�Va��VM�~A���:��
u9A'��@]PDB/�eA���?�qB��mA��@|   �'2D�����ӥ* ���,Qm?�c�gb2�Dtr~L_���u	���B1������    ��ZB�$jA[��@{�ֺ�m<�^6�w�3?Me_>��1A�T�@�DB�lhAJU�?r�pBY�lA�*�@   �'2D�����ӥ* �܈'��6mep �d�V��l�}$uJ�q�NeȊq�`�1��    �
u9A'��@|��B�c`A���?�c�Bm�hA��@|   �'2D�����ӥ* ���,Qm?�c�gb2�Dtr~L_���u	���B1������    ��Bh�dA[��@{�ֺ�m<�^6�w�3?Me_>��1A�T�@�
�B�:bA���?^��BujA��@|   �'2D�����ӥ* ��;�#�����D@����
�y7���u	���B1������    n_�B!�fA[��@��m<���.5��4?Ne_>��1A�T�@%`�B�dAJU�?`�BťhA�*�@   �'2D�����ӥ* �ޘ7��t�S�aR�ys�eA]���}$uJ�q�NeȊq�`�1��    x�$B��kA�����f���^���#3?F 5?���>�NA3�0A/�
�B�:bA����^��BujA����|   �'2D�����ӥ* ���Y}�5��� rs�&1�MS���u	���B1������    ?^�B�fA��ʈ�<���mb5��}4?��R>j�7Ai�A%`�B�dAV5��`�BťhA��   �'2D�����ӥ* ����:���M�g��n��)si��}$uJ�q�NeȊq�`�1��    �%B~�kA����v�������3?��5?K�>5�=A�x�@/�
u9A'��@]PDB/�eA���qB��mA�m�|   �'2D�����ӥ* ���,Qm?�c�gb2�Dtr~L_���u	���B1������    ��ZB�$jAi^��{�ֺ�m<�^6�w�3?Me_>��1A�T�@�DB�lhA����r�pBY�lA�jp�   �'2D�����ӥ* ��'��6mep �d�V��l�}$uJ�q�NeȊq�`�1��    ��B
u9A'��@���B�c`A��f�BE�hA�m�|   �'2D�����ӥ* ���,Qm?�c�gb2�Dtr~L_���u	���B1������    ��B@�dAi^��{�ֺ�m<�^6�w�3?Me_>��1A�T�@��BYcA������B��gA�jp�   �'2D�����ӥ* ��g&�� ��O/�2?��ߣ}$uJ�q�NeȊq�`�1��    9`�B�WfA����d�<�{~<op4?�|5?A:�>u9A'��@
�B�:bA��^��BujA�m�|   �'2D�����ӥ* ��;�#�����D@����
�y7���u	���B1������    n_�B!�fAi^����m<���.5��4?Ne_>��1A�T�@%`�B�dA����`�BťhA�jp�   �'2D�����ӥ* ����:���M�g��n��)si��}$uJ�q�NeȊq�`�1��    �%B~�kA����v�������3?��5?K�>5�=A�x�@/�
u9A'��@]PDB/�eA���qB��mA g�|   �'2D�����ӥ* ���,Qm?�c�gb2�Dtr~L_���u	���B1������    ��ZB�$jA�y��{�ֺ�m<�^6�w�3?Me_>��1A�T�@�DB�lhAW�r�pBY�lA��q�   �'2D�����ӥ* ��'��6mep �d�V��l�}$uJ�q�NeȊq�`�1��    ��B �dA���Η���J��2�3?��5??:�>
u9A'��@���B�c`A���d�BY�hA g�|   �'2D�����ӥ* ���,Qm?�c�gb2�Dtr~L_���u	���B1������    ��BT�dA�y��{�ֺ�m<�^6�w�3?Me_>��1A�T�@��BmcAW���B�gA��q�   �'2D�����ӥ* ��g&�� ��O/�2?��ߣ}$uJ�q�NeȊq�`�1��    9`�B�WfA����d�<�{~<op4?�|5?A:�>u9A'��@
�B�:bA��^��BujA g�|   �'2D�����ӥ* ��;�#�����D@����
�y7���u	���B1������    n_�B!�fA�y����m<���.5��4?Ne_>��1A�T�@%`�B�dAW�`�BťhA��q�   �'2D�����ӥ* ����[�L�����R�E[k�c�V�6p��u|    R�B�kiA����        d�?�;���@UU�>  Av�Bw�eA����/�B�*mA����4   �'2D�����ӥ* �鐤�f07L6���	��䬕��u	���B1������    j�B��iA����        d�?�;TU�@��*=��
A�f�B�iAV5����B:zjA��  �'2D�����ӥ* �d� O��9̴����,�w��N&KQ�!��(�!D����;�   K��B� ��Wi�        ��;d�?��
����              �? U�>8�A  $A�o�B�̪��)�BE�B�=�@0 ��   ��iy�O������o� ��b�[7RCp�G���Ԛ�z{[�=`O�L ����tIj����   짰B"�����        ��.�  �?�2@���>  $A�߭B�̪��)��o�Bgw��0 ��   ��iy�O������o� �W���3���a��e*�%ۇs{[�=`O�L ����tIj����   ��Bb�
�PA���>  $A��B�I��)����B\:H�0 ��   ��~c�AJ��ۡ�J� � �%S�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A�=z�i�g�        K5��5?0�@u�>�x�@:�Ae_���*��2u�A��?�u76�8   ��~c�AJ��ۡ�J� � �%u�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A�=z�i�g�        �5��5?At@b>�x�@s��Ae_���*��7��A��[�u76�   ��~c�AJ��ۡ�J� � �5S�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A6t��i�g�        K5��5?0�@u�>�x�@:�A�����*��2u�A�3��u76�8   ��~c�AJ��ۡ�J� � �5u�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A6t��i�g�        �5��5?At@b>�x�@s��A�����*��7��A�3��u76�   ��~c�AJ��ۡ�J� � �ES�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A6t��š~�        K5��5?0�@u�>�x�@:�A�������2u�A�3����G�8   ��~c�AJ��ۡ�J� � �Eu�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A6t��š~�        �5��5?At@b>�x�@s��A�������7��A�3����G�   ��~c�AJ��ۡ�J� � �aS�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A�=z�š~�        K5��5?0�@u�>�x�@:�Ae_�����2u�A��?���G�8   ��~c�AJ��ۡ�J� � �au�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A�=z�š~�        �5��5?At@b>�x�@s��Ae_�����7��A��[���G�   ��~c�AJ��ۡ�J� � �wS�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A6t��q��        K5��5?0�@u�>�x�@:�A���� p!�2u�A�3�����8   ��~c�AJ��ۡ�J� � �wu�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A6t��q��        �5��5?At@b>�x�@s��A���� p!�7��A�3�����   ��~c�AJ��ۡ�J� � ȊS�u0vŞ��{�SL���N���}$uJ�q�NeȊq�`�1��   �W�A�=z�q��        K5��5?0�@u�>�x�@:�Ae_�� p!�2u�A��?����8   ��~c�AJ��ۡ�J� � Ȋu�PZ[R"�.c�\��veպ5o�>=�Մs>B)�!S   �F�A�=z�q��        �5��5?At@b>�x�@s��Ae_�� p!�7��A��[����   ����q�M�����$�� S�ʾ�CF�^�
��Wk�AƳ{[�=`O�L ����tIj����   �A�\B�?AG �G ;�5��5? U�>4u�AV� A'�#�-�BUՅ@&��A�1BR�aA4   ����q�M�����$�� Tu��@��#R�F7# ��|�?{[�=`O�L ����tIj����   {߯A�B�?A�

�A�ތ«Ky��_�A�   �%^�� E%����"! c-ŗ��`J�.�j�#�;��o�a�����!���ё�BH   	i���z�w�~$�A���>2�F>)K ?mPI? X@$o@Z�?����|ªʄA��� LsªʒA  �%^�� E%����"! c-KyW0�8�F���Mm5�����aN�1
:%�
����%�4�}$uJ�q�NeȊq�`�1��    w)A������g5?ߟ4�wh»EP�;�?O@��+A�M�A�P{@��� p!��~eA5���4  �cB�7bM�?(�R�� =����f07L6���	��䬕��u	���B1������    w)A5�������              �?  "A��*=�b�A�R�@���¦��w)cA�w�¬���  �v����K4�¡z��� ���f07L6���	���א�� �s�gtQ�#�e;$,�   Y��5���
3��              �?�pE?���>�$T@������«:¦���L�¿���   ���rpCj���B�*tj ��0���_�݄i������K��Q�}$uJ�q�NeȊq�`�1��    ��܅� ��          �?v�&  �@��*>  �@�� ���5��� ��H   ���rpCj���B�*tj �����f07L6���	��䬕��u	���B1������    �5�� ��          �?v�&  �@���<  �@�Y��� ��ق��܅� �  ���rpCj���B�*tj �����f07L6���	��䬣}$uJ�q�NeȊq�`�1��    �2��Ve�          �?v�&UU�@�2@XU�>�D���«: �C�g�� ��   ���rpCj���B�*tj ��0���_�݄i������K��Q�}$uJ�q�NeȊq�`�1��    �cU��܅� ��          �?v�&  �@��*>  �@�cc�� ���cG�5��� ��H   ���rpCj���B�*tj �ސ��f07L6���	��䬕��u	���B1������    �cU�5�� ��          �?v�&  �@���<  �@��b�� ���G��܅� �  ���rpCj���B�*tj �ߐ��f07L6���	��䬣}$uJ�q�NeȊq�`�1��    �cU�2��Ve�          �?v�&UU�@�2@XU�>1�d��«: Fg�� ��   ���rpCj���B�*tj ��0���_�݄i������K��Q�}$uJ�q�NeȊq�`�1��    ܓ��܅� ��          �?v�&  �@��*>  �@ܓ%�� ��ܓ	�5��� ��H   ���rpCj���B�*tj �����f07L6���	��䬕��u	���B1������    ܓ�5�� ��          �?v�&  �@���<  �@�%�� ��
��܅� �  ���rpCj���B�*tj �����f07L6���	��䬣}$uJ�q�NeȊq�`�1��    ܓ�2��Ve�          �?v�&UU�@�2@XU�>1�&��«: >g�� ��   ���rpCj���B�*tj �0���_�݄i������K��Q�}$uJ�q�NeȊq�`�1��    �����܅� ��          �?v�&  �@��*>  �@������� �¸���5��� ��H   ���rpCj���B�*tj ����f07L6���	��䬕��u	���B1������    ����5�� ��          �?v�&  �@���<  �@������� ¸����܅� �  ���rpCj���B�*tj ����f07L6���	��䬣}$uJ�q�NeȊq�`�1��    ����2��Ve�          �?v�&UU�@�2@XU�>b2�����«: �
�� P�������M����9���א�� �s�gtQ�#�e;$,�   R� B������A              �?P��?  @? ��A���A�L���?vA[$B�̃� �B   �O��ިKޥ�&4
�� P��	�il�|���u�g͉�J{[�=`O�L ����tIj����   R� B������A              �?P��?  @? ��A���A�L���?vA[$B�̃� �B   �d� ��E��_D�I&�6 ��J}��\�$� �qC�Y��3�א�� �s�gtQ�#�e;$,�   ���@�z�q4x@���>�k?b.�=�0=  �@�tI?h9�?wm�������H@�,�¤�p�RՑ@$   ��p�_RJ��=���7 Q�>[d���2M�~ʜ��`�SƦ�/��/��N����E��b   ��p?n�����A6R[�k�:��=aV?e2�?[�mA�4Ak:��� ���vA= A�q����AC   ��p�_RJ��=���7 Q�&�\)ټ�J�C����.���#�����n��\w&e�mO�[   tv�? і� ��As�?��U?�C6x� 6�r�?aA�4A����� ���vA���@j����AB   ��p�_RJ��=���7 Q��Rޅ��4�fj�s�#�����{[�=`O�L ����tIj����   M�?�#�� ��A        �eT��nz?��!A�/A��4Ak:��� ���vA= A�q����A4   ��p�_RJ��=���7 Q�4��Q�����d�,�Rm��r��/��/��N����E��b   ��(A��r� ��A���8�4�t?:u����<�l@��4A,MA�˗���vAN�2A��6����A
   ��p�_RJ��=���7 Q��]c��x�~�=H� ��5�g������n��\w&e�mO�[   ��#A�F�� ��A"}4Q۴��t?�Ֆ�m9�<�@��4A0A������vA�L-A��L����A
   ��p�_RJ��=���7 Q�4'Q���U)w|�i%I���{[�=`O�L ����tIj����   ��&A)�|� ��A        �����t?Z 
@�.�?��4A0A������vAN�2A��6����A   ��p�_RJ��=���7 Q��*K��~�;���〇��"x{[�=`O�L ����tIj����   >>��W-2� ��A        @�>�m?:�T>�s�>��4AD:��x�5���vA"B��Q�.����A   ��p�_RJ��=���7 Q�B���y��?���1��u���T�/��/��N����E��b   c ����/� ��A        @��>��l?pbK>)�v;��4AD:���0���vA����Q�.����A   ��p�_RJ��=���7 Q��i[�7�b�	�^�2�11s������n��\w&e�mO�[   z��
�4� ��A        d��>��l?ߴJ>�v;��4A���x�5���vA"B���`3����A   ��p�_RJ��=���7 Q�x���
yG1���{[�=`O�L ����tIj����   6R��qy:� ��A        ���>�~w?��?0�_?��4A&=��ɈB���vA����0����A   ��p�_RJ��=���7 Q�*�.ُ
   ��p�_RJ��=���7 Q����������b>��yYi۝<{[�=`O�L ����tIj����   ���3�I� ��A        2�>~�}?��k?C1�?��4A���Q�R���vA�[����@����A   ��p�_RJ��=���7 Q��ƩsC,�hgPL�ZB(n9�����n��\w&e�mO�[   �u��`O� ��A        �U<m�?��m@�v?��4A=�Q�R���vA����
L����A   ��p�_RJ��=���7 Q�j�ܖ�Ū��]|j4��c�/��/��N����E��b   ���
L� ��A              �?�pt@  �?��4A=��
L���vA� ��
L����A   ��p�_RJ��=���7 Q����'{{�0�j�Ia���B�l{[�=`O�L ����tIj����   ���_O� ��A�/5?$�4�M��7��4���>~}t@��4A=�Q�R���vA� ��
L����A   ��p�_RJ��=���7 Q�'+]@DV:�0������O�����n��\w&e�mO�[   �
���شw��?&H(>��4A�����ª�vA���?�«��A9   ��p�_RJ��=���7 Q��N��*p��w�s��W�ri{[�=`O�L ����tIj����   �[?Y� ��A        j)���~?f�?�c�?��4A��R�ª�vA��?�«��A   ��p�_RJ��=���7 Q��%ݯ�7~�`�����u^J�{[�=`O�L ����tIj����   �@wK� ��A        LL���yu?.=?�y?��4A���?t�ª�vA˅#@X�«��A   ��p�_RJ��=���7 Q�\�{�YN.m���r�O�Q������n��\w&e�mO�[   ��@�� ��AA661b5KL�>�yu?P`b?Q(;��4A��?t�ª�vA˅#@�«��A   ��p�_RJ��=���7 Q�8����'^���y�;|[=%��/��/��N����E��b   ��?0�� ��A^�4�]�S�RL�>�yu?��_?��%;��4A���?�ª�vA�@X�«��A   ��p�_RJ��=���7 Q���4{T�jG���F,�1Ȍ�������n��\w&e�mO�[   =����� ��A              �?  �?�w�@��4A=�������vA=�Q�R����A   ��p�_RJ��=���7 Q�R�s�7�=\���6��[nU�/��/��N����E��b   ut6����� ��A              �?  �?�w�@��4Aut6�������vAut6�Q�R����A   ��p�_RJ��=���7 Q��T�@��T]M�Sa"�{[�=`O�L ����tIj����   ��9����� ��A              �?@U�>�w�@��4A=�������vAut6�Q�R����A
   ��p�_RJ��=���7 Q���4{T�jG���F,�1Ȍ�������n��\w&e�mO�[   �9=�E��� ��A              �?  �?;�@��4A�9=��Z����vA�9=�������A   ��p�_RJ��=���7 Q���Zĺ"y�3���&J��Uj�/��/��N����E��b   �6�E��� ��A              �?  �?;�@��4A�6��Z����vA�6�������A   ��p�_RJ��=���7 Q��T�@��T]M�Sa"�{[�=`O�L ����tIj����   i�9�E��� ��A              �?@U�>;�@��4A�9=��Z����vA�6�������A
   ��p�_RJ��=���7 Q���4{T�jG���F,�1Ȍ�������n��\w&e�mO�[   =���-� ��A              �?  �?��p@��4A=��
L���vA=�������A   ��p�_RJ��=���7 Q� 	�-����
L���vAut6�������A   ��p�_RJ��=���7 Q��V�E�1�-ԝkЌ��4�{[�=`O�L ����tIj����   ��9���-� ��A              �?@U�>��p@��4A=��
L���vAut6�������A   ��%'A~��A�5�Gx %m���f07L6���	���sO�|P���=�����4�   Yw0� G����A          �?       @��*>UU�@Yw5�������vAYw+�u����ʰA   ��%'A~��A�5�Gx %m t��������6f�̳=�4^*������5/���&9����   Yw0� G����A          �?      @@UU�>UU�@Yw6�������vAYw*�u����ʲA   ��%'A~��A�5�Gx %m��D�����]�_���~��*��z���(L��X�?��'�l���   Yw0� G����A          �?      @@UU?UU�@Yw6�u�����vAYw*������ʲA8   ��%'A~��A�5�Gx %����f07L6���	���sO�|P���=�����4�   �Lj� G����A              �?   @��*>UU�@�Lo�������vA�Le�u����ʰA   ��%'A~��A�5�Gx %� t��������6f�̳=�4^*������5/���&9����   �Lj� G����A              �?  @@UU�>UU�@�Lp�������vA�Ld�u����ʲA   ��%'A~��A�5�Gx %�Oo���։ꕙا�0���v�z���(L��X�?��'�l���   �Lj� G����A              �?  @@UU?UU�@�Lp�u�����vA�Ld������ʲA8   �"c)\Eę0�&x=^v H�2�1H�mi�3��B�I~b���p�[<�F�Lt��չa/g�rj�   d�A_ �RX�W(?c?ZM�����K�u@�p�?��uA�A�'«*���B�d �>�   �"c)\Eę0�&x=^v H�.���>|wN<ij_��:����}$uJ�q�NeȊq�`�1��   ���A�$(�(�n���?;�?t��R
���U>�� @џ|A�Ap�(�F�0�B�' �>,   �"c)\Eę0�&x=^v Q�U�'3J�&_�
�]���e�}$uJ�q�NeȊq�`�1��   ��A�ªDn���?P���+���&�>��U>k�@�	}A�A�d�F�&Bp� �>,   �"c)\Eę0�&x=^v R_\��x\��S�;#�R��p�[<�F�Lt��չa/g�rj�   R�Av0�.�?��?�v?N��>y4�>2Xw@Ae�?��2A0��A�� �<>IB���UՅ@`   �"c)\Eę0�&x=^v RiNL�M�I�_����PY��eN�}$uJ�q�NeȊq�`�1��   M�A�¬�
*��=ܩyL�܀   C���52��kL�    �(����?    UU]@Yu@���@����l�«����%��5������   �;��ZH��N����c �$���2�T��[��Y�x�}$uJ�q�NeȊq�`�1��   C���5r�«���          �?    UUu@VU)@  �>�p���l�«����ş�5"�«���   �;��ZH��N����c �$"�O���S�VŶ뽠��S?�j���u	���B1������   C���5�¬jL�    QĀ<��?    ��B@�D�>��@g����������V�  �;��ZH��N����c �%�H$�6X,�g��}��{����e���C�'�a�8�~.�   X���*u��%���?�b5�A�D�b����@��?#v�?���5����� &�7����   �;��ZH��N����c �%d5�AN�?��X�fr��E)!�3:�,9�I��<�cr   K����t���a��IB��IB;�5��5?���?���@�7�?C���5�����C{�7�­*��$   �;��ZH��N����c �%o�0�u�>#�ќ17��L�O
��{[�=`O�L ����tIj����   .9��r�L��?Aq�<��?d �2���EA�U�>��A=����N�UՅ@��e�J�R�aA   �Y₁B���m���, �LԲ����	X0D�ٽ�(�
�{{[�=`O�L ����tIj����   0���$��?A<60�ѳ9?R�2Z�첫��>y�MA��A=���L�&�UՅ@�ٮ��a"�R�aA   �Y₁B���m���, �M^I�_���L�;��X�<���{[�=`O�L ����tIj����   F&�������?Aڸ�<|�?c�A1���0J�VA���>��A=����x��UՅ@$��¶���R�aA   �Y₁B���m���, �NI;E�� ۏ��[�%���D�{[�=`O�L ����tIj����   �����?Aͳ�<}�?�#�EU��h<_A���>��A=���V���UՅ@}��¸e��R�aA   �Y₁B���m���, �O�_����^j�o�C.Bb j{[�=`O�L ����tIj����   w����'��?A:��<~�?;�1�X�/�gA���>��A=����#1�UՅ@���§]�R�aA   �Y₁B���m���, �P�X�ZF38��P8�ܵ1���{[�=`O�L ����tIj����   ܋��U7�>�?Aª�<�?P&���[��pA���>��A=����_�UՅ@P���|?R�aA   �Y₁B���m���, �R���2�T��[��Y�x�0����$P�����L��m�   V۰�@�q�RՉ@        80?"�9?�*A��*>  �>R���!l��RՅ@Y"��?\\�RՍ@   �Y₁B���m���, �Z���2�T��[��Y�x�0����$P�����L��m�   wԮ��@$�RՉ@        80?"�9?\F\A��*>  �>����?�RՅ@g��^��RՍ@   �Y₁B���m���, �^���2�T��[��Y�x�0����$P�����L��m�   1���`��RՉ@        80?"�9? �IA��*>  �>����aK��RՅ@�߫¿*g�RՍ@   �Y₁B���m���, �d���2�T��[��Y�x�0����$P�����L��m�   Z���.-�RՉ@        80?"�9?��hA��*>  �>�t�����RՅ@���¶��@RՍ@   �Y₁B���m���, �h���f07L6���	��䬕��u	���B1������   �.���u|c�@        80?"�9?��@���=��@����tj�¨*�@԰ºr�o��@  �Y₁B���m���, �j���f07L6���	��䬕��u	���B1������   "B�3c�@        80?"�9?��@���=��@߬��8�?¨*�@d׮��C&�o��@  �Y₁B���m���, �k���f07L6���	��䬕��u	���B1������   r���0.c�@        80?"�9?�(�@���=��@�����%¨*�@\��|��o��@  �Y₁B���m���, �m���f07L6���	��䬕��u	���B1������   n��Zr���c�@        80?"�9?���@���=��@�{�®D���*�@����o��@  �Y₁B���m���, �n���f07L6���	��䬕��u	���B1������   kh���u���c�@        80?"�9?�@���=��@Ѭ�T���*�@����6/g�o��@  �Y₁B���m���, �p���f07L6���	��䬕��u	���B1������   g����`l��c�@        80?"�9?���@���=��@Uj��E}���*�@z~���丽o��@  �Y₁B���m���, �q���f07L6���	��䬕��u	���B1������   &/���j@�c�@        80?"�9?z��@���=��@�����	�=�*�@�������@o��@  �Y₁B���m���, �u���f07L6���	��䬕��u	���B1������   =����fc�@        80?"�9?���@���=��@,����pq¨*�@MB��]]\�o��@  �Y₁B���m���, �v���f07L6���	����+�(������ְ�P��M�   ���hN�S�1A�N?6�>�N?6����*>��*>���@s�¿�[��?0A�f��f@©�2A   �Y₁B���m���, �w���f07L6���	����+�(������ְ�P��M�   $��	j@S�1A�N?6�>�N?6����*>��*>x��@E���\W�=�?0A���µ��@��2A   �Y₁B���m���, �x���f07L6���	����+�(������ְ�P��M�   ����.�f�S�1A�N?6�>�N?6����*>��*>���@���tq��?0AY"��?\\©�2A   �Y₁B���m���, �y���f07L6���	����+�(������ְ�P��M�   �������S�1A�N?6�>�N?6����*>��*>���@'B�����?0A�5��a�����2A   �Y₁B���m���, �z$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3�S�1A�N?6�>�N?6����*>��*>��@����?��?0Ao��½B&©�2A   �Y₁B���m���, �{���f07L6���	����+�(������ְ�P��M�   ����2yAT�1A�N?6�>�N?6����*>��*>��o@y�·��@�?0A�0��2A��2A   �Y₁B���m���, �|���f07L6���	����+�(������ְ�P��M�   e���c�-�S�1A�N?6�>�N?6����*>��*>���@�0�½�d��?0A;$�������2A   �Y₁B���m���, �}���f07L6���	����+�(������ְ�P��M�   �]��x��S�1A�N?6�>�N?6����*>��*>
�@�۬��Z���?0A�߫¿*g���2A   �Y₁B���m���, �~���f07L6���	����+�(������ְ�P��M�   �|��M/�S�1A�N?6�>�N?6����*>��*>�(�@0��=�%��?0Ag��^�©�2A   �Y₁B���m���, ����f07L6���	����+�(������ְ�P��M�   ��´rl�S�1A�N?6�>�N?6����*>��*>���@�t������?0A�^��L�����2A   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   3$���v|�S�1A�N?6�>�N?6����*>��*>��@S���!l���?0A��r©�2A   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t��S�1A�N?6�>�N?6����*>��*>���@����`K���?0A����ʝ����2A   �Y₁B���m���, ����6�l���c�r��f��r��+�(������ְ�P��M�   %Y��3A�*�@#�9?80?        ��*>��*>���>�����\2ARՅ@N,��D*5A��@
   �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A6�@#�9?80?        ��*>��*>�8@�����\2A��@N,��D*5Ao��@
�+�(������ְ�P��M�   �k���¨*�@        #�9�80?��*>��*>���>ʘ��X���RՅ@?�©g����@
   �Y₁B���m���, ����6�l���c�r��f��r��+�(������ְ�P��M�   �k���#!A        #�9�80?��*>��*>�8@ʘ��X���p\A?�©g�©�2A
   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �|��M/���@�N?6�>�N?6����*>��*>�(�@0��=�%�PՍ@g��^�¨*�@   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   3$���v|���@�N?6�>�N?6����*>��*>��@S���!l�¦*�@��r���@   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   ��´rl���@�N?6�>�N?6����*>��*>���@�t�����PՍ@�^��L����*�@   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3���@�N?6�>�N?6����*>��*>��@����?�PՍ@o��½B&¨*�@   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   $��	j@��@�N?6�>�N?6����*>��*>x��@E���\W�=�*�@���µ��@��@   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   ����.�f���@�N?6�>�N?6����*>��*>���@���tq¦*�@Y"��?\\���@   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t����@�N?6�>�N?6����*>��*>���@����`K��PՍ@����ʝ���*�@   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �]��x����@�N?6�>�N?6����*>��*>
�@�۬��Z��PՍ@�߫¿*g��*�@   �Y₁B���m���, ����6�l���c�r��f��r��+�(������ְ�P��M�   sܰ���q�Ḳ@#�9?80?        ��*>��*>9�@K	�r�RՍ@����-kq�o��@
   �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �J��\�6�@#�9?80?        ��*>��*>�8@�y��e�\���@ ��\�o��@
   �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   &���R@�6�@#�9?80?        ��*>��*>�8@9���8�@���@�d���@�o��@
   �Y₁B���m���, ����6�l���c�r��f��r��+�(������ְ�P��M�   �߮���%�Ḳ@#�9?80?        ��*>��*>9�@��¬K&�RՍ@����N�%�o��@
   �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ��l�6�@#�9?80?        ��*>��*>�8@�H�	���@+��'h�o��@
   �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   5^������6�@#�9? 80?��0�e���*>��*>�8@�5�������@&ܬ�aK��n��@
   �Y₁B���m���, ����6�l���c�r��f��r��+�(������ְ�P��M�   Y���J���Ḳ@#�9?80?        ��*>��*>9�@1�§���RՍ@�����H��o��@
   �Y₁B���m���, ����6�l���c�r��f��r��+�(������ְ�P��M�   .�¿�e��*�@#�9?80?	802�9'���*>��*>���>5��yNg�RՅ@W۫��d���@
   �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   .�¿�e�6�@#�9? 80?��0�e���*>��*>�8@�߫�4rg���@��¾�d�n��@
   �Y₁B���m���, ����6�l���c�r��f��r��+�(������ְ�P��M�   冪��H)�Ḳ@#�9?80?        ��*>��*>9�@����}�ȽRՍ@Z��J4�=o��@
   �Y₁B���m���, ����6�l���c�r��f��r��+�(������ְ�P��M�   ©¶]�@�*�@#�9?80?        ��*>��*>���>�����H�@RՅ@
@�·��@��@
   �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ©¶]�@6�@#�9?80?        ��*>��*>�8@+���@��@}���p��@o��@
�+�(������ְ�P��M�   %Y��3A�#!A#�9?80?        ��*>��*>�8@�����\2Ap\AN,��D*5A��2A
   �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �k���¨*�@        #�9�80?��*>��*>�8@ʘ��X���o��@?�©g��p\A
�+�(������ְ�P��M�   sܰ���q#!A#�9?80?        ��*>��*>�8@����sr�p\Aر��e�q©�2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   �J��\#!A#�9? 80?,��08�e���*>��*>�8@Y"��n\�p\A�ȯ¿�[©�2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   &���R@#!A#�9?80?        ��*>��*>�8@9���8�@�p\A�d���@©�2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   �߮���%#!A#�9?80?        ��*>��*>�8@����&�p\A4���%©�2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ��l#!A#�9?80?        ��*>��*>�8@�H�	�p\A+��'h©�2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   5^�������#!A#�9? 80?,��08�e���*>��*>�8@�5�����p\A&ܬ�aK����2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   Y���J����#!A#�9?80?        ��*>��*>�8@l��Z��p\A����[����2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   .�¿�e��#!A#�9?80?        ��*>��*>�8@A7��W�h�p\A�ݫ���e���2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   �L�����#!A#�9? 80?,��08�e���*>��*>�8@;$���2��p\A�ʪ������2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   冪��H)��#!A#�9?80?        ��*>��*>�8@���¤z9�p\AI\���û��2A
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ©¶]�@�#!A#�9?80?        ��*>��*>�8@+���@p\A}���p��@��2A
   �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   �.���u|¨*�@        80?"�9?��@���=�8@����tj��o��@԰ºr�p\A  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   =����f¨*�@        80?"�9?���@���=�8@,����pq�o��@MB��]]\�p\A  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   "B�3¨*�@        80?"�9?��@���=�8@߬��8�?�o��@d׮��C&�p\A  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   r���0.¨*�@        80?"�9?�(�@���=�8@�����%�o��@\��|��p\A  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   n��Zr���*�@        80?"�9?���@���=�8@�{�®D��o��@����p\A  �Y₁B���m���, ���f07L6���	��䬕��u	���B1������   kh���u���*�@        80?"�9?�@���=�8@Ѭ�T��o��@����6/g�p\A  �Y₁B���m���, �Đ��f07L6���	��䬕��u	���B1������   g����`l��*�@        80?"�9?���@���=�8@Uj��E}��o��@z~���丽p\A  �Y₁B���m���, �Ő��f07L6���	��䬕��u	���B1������   &/���j@�*�@        80?"�9?z��@���=�8@�����	�=o��@�������@p\A  �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A�*�@#�9?80?        ��*>��*>�8@���¬�3Ao��@*��"6Ap\A
�@����X��űA��Eg�A   �Y₁B���m���, �Ր��f07L6���	����+�(������ְ�P��M�   *c���1�p\A�N?6�>�N?6�����=���<�(�@1Ȯ��%�ıA#�����A   �Y₁B���m���, �֐��f07L6���	����+�(������ְ�P��M�   �
�y|�p\A�N?6�>�N?6�����=���<��@TT��vk��űA����Qr�A   �Y₁B���m���, �א��f07L6���	����+�(������ְ�P��M�   �y����f�p\A�N?6�>�N?6�����=���<���@�İ��rq�űA/���b\�A   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y��p\A�N?6�>�N?6�����=���<���@�F�µH��űA����4���A   �Y₁B���m���, �ِ��f07L6���	����+�(������ְ�P��M�   �
���i@p\A�N?6�>�N?6�����=���<x��@Fo����=ıAt�����@A   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3�p\A�N?6�>�N?6�����=���<��@�w��<�?�űA+Į�rI&�A   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l�p\A�N?6�>�N?6�����=���<���@�4��a���ıA@k�§ĽA   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y��n��@�N?6�>�N?6�����=���<���@�F�µH��G�@����4������@   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3�n��@�N?6�>�N?6�����=���<��@�w��<�?�G�@+Į�rI&����@   �Y₁B���m���, �ސ��f07L6���	����+�(������ְ�P��M�   �
���i@n��@�N?6�>�N?6�����=���<x��@Fo����=G�@t�����@���@   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l�n��@�N?6�>�N?6�����=���<���@�4��a���G�@@k�§Ľ���@   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �y����f�n��@�N?6�>�N?6�����=���<���@�İ��rq�G�@/���b\����@   �Y₁B���m���, �ᐤ�f07L6���	����+�(������ְ�P��M�   "D��t}��n��@�N?6�>�N?6�����=���<
�@����X��G�@��Eg����@   �Y₁B���m���, �␤�f07L6���	����+�(������ְ�P��M�   *c���1�n��@�N?6�>�N?6�����=���<�(�@1Ȯ��%�G�@#��������@   �Y₁B���m���, �㐤�f07L6���	����+�(������ְ�P��M�   �
�y|�n��@�N?6�>�N?6�����=���<��@TT��vk��G�@����Qr����@   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   꾫�!SM��*�@        80?"�9?��:@��*=���@��¿�d�RՅ@/��6��?0A   �Y₁B���m���, ��Vz��������A�����2��0����$P�����L��m�   -ޫ�@�_�R��@        80?"�9?���= �>  @?)?����`�R��@1}�$_�R��@   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �U��r���*�@        #�9�80?��:@��*=���@����&�RՅ@;$�¨����?0A   �Y₁B���m���, ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   �6�¦4��R��@        #�9�80?���= �>  @?��������R��@�ժ�e���R��@   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   ���S.��*�@        80?"�9? �?���=���@˷��s
6�RՅ@cr��3�%��?0A   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   t��X�U¨*�@        80?"�9?��:@��*=���@/3�¿�[�RՅ@�ϯ��P��?0A   �Y₁B���m���, ��Vz��������A�����2��0����$P�����L��m�   � ��`�Z�R��@        80?"�9?���= �>  @?fl��C�Z�R��@m����\Z�R��@   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �Э�wG¨*�@        80?"�9?��:@��*=���@����RՅ@z������?0A   �Y₁B���m���, ��Vz��������A�����2��0����$P�����L��m�   ���~��R��@        80?"�9?���= �>  @?t;��b'�R��@|y����R��@   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �g�D���*�@        #�9�80?��:@��*=���@��������RՅ@� ��>����?0A   �Y₁B���m���, ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   LH����R��@        #�9�80?���= �>  @?H����[��R��@P��6���R��@   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �������*�@        80?"�9? �?���=���@dɭ���RՅ@����u����?0A   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   ����,AF¨*�@        #�9�80?��:@��*=���@��L�RՅ@xQ�� o@��?0A   �Y₁B���m���, ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   >y��$�A�R��@        #�9�80?���= �>  @?:گ���A�R��@B��|cA�R��@   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �ׯ¤N¨*�@        80?"�9? �?���=���@U���,P�RՅ@�L��?0A   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �x��x�
1ћfb��   =Q��i�+A�*�@        80?"�9?VUU?���=���@�q��'%ARՅ@�0�¬n2A�?0A   �Y₁B���m���, �v� TW�߂G��'�/
��{[�=`O�L ����tIj����   .9��r�L� �q�<��?m �24���EA�U�>��A=����N«*����e�J�JU6@   �Y₁B���m���, �Բ����	X0D�ٽ�(�
�{{[�=`O�L ����tIj����   0���$� �<60�ѳ9?i�2��첪��>y�MA��A=���L�&«*���ٮ��a"�JU6@   �Y₁B���m���, �^I�_���L�;��X�<���{[�=`O�L ����tIj����   F&������ �ڸ�<|�?��A1���0J�VA���>��A=����x���*��$��¶���JU6@   �Y₁B���m���, �I;E�� ۏ��[�%���D�{[�=`O�L ����tIj����   ���� �ͳ�<}�?�#�T��h<_A���>��A=���V����*��}��¸e��JU6@   �Y₁B���m���, ��_����^j�o�C.Bb j{[�=`O�L ����tIj����   w����'� �:��<~�?�1��R�/�gA���>��A=����#1��*�����§]�JU6@   �Y₁B���m���, ��X�ZF38��P8�ܵ1���{[�=`O�L ����tIj����   ܋��U7�> �ª�<�?G&���[��pA���>��A=����_��*��P���|?JU6@   �Y₁B���m���, ����2�T��[��Y�x�0����$P�����L��m�   V۰�@�q®*��        80?"�9?�*A��*>  �>R���!l�®*��Y"��?\\®*��   �Y₁B���m���, �&���2�T��[��Y�x�0����$P�����L��m�   wԮ��@$®*��        80?"�9?\F\A��*>  �>����?®*��g��^�®*��   �Y₁B���m���, �*���2�T��[��Y�x�0����$P�����L��m�   1���`���*��        80?"�9? �IA��*>  �>����aK���*���߫¿*g��*��   �Y₁B���m���, �0���2�T��[��Y�x�0����$P�����L��m�   Z���.-༮*��        80?"�9?��hA��*>  �>�t������*�����¶��@�*��   �Y₁B���m���, �4���f07L6���	��䬕��u	���B1������   �.���u|�u���        80?"�9?��@���=��@����tj��X���԰ºrc��  �Y₁B���m���, �6���f07L6���	��䬕��u	���B1������   "B�3�u���        80?"�9?��@���=��@߬��8�?�X���d׮��C&c��  �Y₁B���m���, �7���f07L6���	��䬕��u	���B1������   r���0.�u���        80?"�9?�(�@���=��@�����%�X���\��|�c��  �Y₁B���m���, �9���f07L6���	��䬕��u	���B1������   n��Zr��u���        80?"�9?���@���=��@�{�®D��X��������c��  �Y₁B���m���, �:���f07L6���	��䬕��u	���B1������   kh���u��u���        80?"�9?�@���=��@Ѭ�T��X�������6/g��c��  �Y₁B���m���, �<���f07L6���	��䬕��u	���B1������   g����`l�u���        80?"�9?���@���=��@Uj��E}��X���z~���丽�c��  �Y₁B���m���, �=���f07L6���	��䬕��u	���B1������   &/���j@u���        80?"�9?z��@���=��@�����	�=X����������@�c��  �Y₁B���m���, �A���f07L6���	��䬕��u	���B1������   =����f�u���        80?"�9?���@���=��@,����pq�X���MB��]]\c��  �Y₁B���m���, �B���f07L6���	����+�(������ְ�P��M�   ���hN�0���N?6�>�N?6����*>��*>���@s�¿�[ª p��f��f@�k���   �Y₁B���m���, �C���f07L6���	����+�(������ְ�P��M�   $��	j@2���N?6�>�N?6����*>��*>x��@E���\W�=� p����µ��@k���   �Y₁B���m���, �D���f07L6���	����+�(������ְ�P��M�   ����.�f�'���N?6�>�N?6����*>��*>���@���tq p�Y"��?\\�k���   �Y₁B���m���, �E���f07L6���	����+�(������ְ�P��M�   �������0���N?6�>�N?6����*>��*>���@'B���ª p��5��a���k���   �Y₁B���m���, �F$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3�-���N?6�>�N?6����*>��*>��@����?¥ p�o��½B&�k���   �Y₁B���m���, �G���f07L6���	����+�(������ְ�P��M�   ����2yA���N?6�>�N?6����*>��*>��o@y�·��@� p��0��2Ak���   �Y₁B���m���, �H���f07L6���	����+�(������ְ�P��M�   e���c�-�0���N?6�>�N?6����*>��*>���@�0�½�d�� p�;$�����k���   �Y₁B���m���, �I���f07L6���	����+�(������ְ�P��M�   �]��x��,���N?6�>�N?6����*>��*>
�@�۬��Z��O���߫¿*g���<   �Y₁B���m���, �J���f07L6���	����+�(������ְ�P��M�   �|��M/�2���N?6�>�N?6����*>��*>�(�@0��=�%�Y��g��^����<   �Y₁B���m���, �K���f07L6���	����+�(������ְ�P��M�   ��´rl�2���N?6�>�N?6����*>��*>���@�t�����Y���^��L�����<   �Y₁B���m���, �L���f07L6���	����+�(������ְ�P��M�   3$���v|�'���N?6�>�N?6����*>��*>��@S���!l� p���r�k���   �Y₁B���m���, �M$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t��,���N?6�>�N?6����*>��*>���@����`K��� p�����ʝ��k���   �Y₁B���m���, �N��6�l���c�r��f��r��+�(������ְ�P��M�   %Y��3AX���#�9?80?        ��*>��*>���>�0��92A�*��ר5A���
   �Y₁B���m���, �O-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A���#�9?80?        ��*>��*>�8@�����\2A���N,��D*5A�c��
�+�(������ְ�P��M�   �k����X���        #�9�80?��*>��*>���>ʘ��X��®*��?�©g�����
   �Y₁B���m���, �Q��6�l���c�r��f��r��+�(������ְ�P��M�   �k���㖿        #�9�80?��*>��*>�8@ʘ��X���?��?�©g��k���
   �Y₁B���m���, �R���f07L6���	����+�(������ְ�P��M�   �|��M/�����N?6�>�N?6����*>��*>�(�@0��=�%°*��g��^��X���   �Y₁B���m���, �S���f07L6���	����+�(������ְ�P��M�   3$���v|�����N?6�>�N?6����*>��*>��@S���!l��Z�����r����   �Y₁B���m���, �T���f07L6���	����+�(������ְ�P��M�   ��´rl�����N?6�>�N?6����*>��*>���@�t������*���^��L���X���   �Y₁B���m���, �U$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3�����N?6�>�N?6����*>��*>��@����?�Z���o��½B&����   �Y₁B���m���, �V���f07L6���	����+�(������ְ�P��M�   $��	j@����N?6�>�N?6����*>��*>x��@E���\W�=�*�����µ��@X���   �Y₁B���m���, �W���f07L6���	����+�(������ְ�P��M�   ����.�f�����N?6�>�N?6����*>��*>���@���tq�Z���Y"��?\\����   �Y₁B���m���, �X$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t������N?6�>�N?6����*>��*>���@����`K��Z�������ʝ�����   �Y₁B���m���, �Y���f07L6���	����+�(������ְ�P��M�   �]��x������N?6�>�N?6����*>��*>
�@�۬��Z���*���߫¿*g�X���   �Y₁B���m���, �Z��6�l���c�r��f��r��+�(������ְ�P��M�   sܰ���q�G��#�9?80?        ��*>��*>9�@K	�r®*������-kqc��
   �Y₁B���m���, �[-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �J��\����#�9?80?        ��*>��*>�8@�w��.e\�������ѱ[c��
   �Y₁B���m���, �]-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   &���R@����#�9?80?        ��*>��*>�8@���� o@����Ob�£�?c��
   �Y₁B���m���, �_��6�l���c�r��f��r��+�(������ְ�P��M�   �߮���%�G��#�9?80?        ��*>��*>9�@��¬K&®*������N�%c��
   �Y₁B���m���, �`-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ��l����#�9?80?        ��*>��*>�8@�F��M���������c��
   �Y₁B���m���, �b-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   5^���������#�9? 80?��0�e���*>��*>�8@�5��������&ܬ�aK���c��
   �Y₁B���m���, �d��6�l���c�r��f��r��+�(������ְ�P��M�   Y���J���G��#�9?80?        ��*>��*>9�@1�§����*�������H���c��
   �Y₁B���m���, �e��6�l���c�r��f��r��+�(������ְ�P��M�   .�¿�e�X���#�9?80?	802�9'���*>��*>���>5��yNg��*��W۫��d����
   �Y₁B���m���, �f-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   .�¿�e����#�9? 80?��0�e���*>��*>�8@�߫�4rg������¾�d��c��
   �Y₁B���m���, �i��6�l���c�r��f��r��+�(������ְ�P��M�   冪��H)�G��#�9?80?        ��*>��*>9�@����}�Ƚ�*��Z��J4�=�c��
   �Y₁B���m���, �j��6�l���c�r��f��r��+�(������ְ�P��M�   ©¶]�@X���#�9?80?        ��*>��*>���>���@��@�*��A���,+�@���
   �Y₁B���m���, �k-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ©¶]�@���#�9?80?        ��*>��*>�8@+���@���}���p��@�c��
�+�(������ְ�P��M�   %Y��3A�㖿#�9?80?        ��*>��*>�8@���¬�3A?��*��"6A\���
   �Y₁B���m���, �z-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �k���±�Y�        #�9�80?��*>��*>�8@ʘ��X��c��?�©g��?��
�+�(������ְ�P��M�   sܰ���q㖿#�9?80?        ��*>��*>�8@K	�r�?������-kq�\���
   �Y₁B���m���, �|0]�����!E�U�=7O(
�+�(������ְ�P��M�   �J��\㖿#�9? 80?,��08�e���*>��*>�8@Y"��n\�?���ȯ¿�[�|���
   �Y₁B���m���, �}0]�����!E�U�=7O(
�+�(������ְ�P��M�   &���R@㖿#�9?80?        ��*>��*>�8@���� o@�?��Ob�£�?�\���
   �Y₁B���m���, �~0]�����!E�U�=7O(
�+�(������ְ�P��M�   �߮���%㖿#�9?80?        ��*>��*>�8@��¬K&�?������N�%�\���
   �Y₁B���m���, �0]�����!E�U�=7O(
�+�(������ְ�P��M�   ��l㖿#�9?80?        ��*>��*>�8@�F��M��?�������\���
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   5^�������㖿#�9? 80?,��08�e���*>��*>�8@�5�����?��&ܬ�aK��|���
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   Y���J����㖿#�9?80?        ��*>��*>�8@l��Z��?������[��\���
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   .�¿�e��㖿#�9?80?        ��*>��*>�8@A7��W�h�?���ݫ���e�\���
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   �L�����㖿#�9? 80?,��08�e���*>��*>�8@;$���2��?���ʪ����|���
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   冪��H)��㖿#�9?80?        ��*>��*>�8@���¤z9�?��I\���û\���
   �Y₁B���m���, ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ©¶]�@�㖿#�9?80?        ��*>��*>�8@+���@?��}���p��@\���
   �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   �.���u|°�Y�        80?"�9?��@���=�8@����tj�c��԰ºr�>��  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   =����f°�Y�        80?"�9?���@���=�8@,����pqc��MB��]]\�>��  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   "B�3°�Y�        80?"�9?��@���=�8@߬��8�?c��d׮��C&�>��  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   r���0.°�Y�        80?"�9?�(�@���=�8@�����%c��\��|��>��  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   n��Zr����Y�        80?"�9?���@���=�8@�{�®D���c������>��  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   kh���u����Y�        80?"�9?�@���=�8@Ѭ�T���c������6/g�>��  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   g����`l���Y�        80?"�9?���@���=�8@Uj��E}���c��z~���丽>��  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   &/���j@��Y�        80?"�9?z��@���=�8@�����	�=�c���������@>��  �Y₁B���m���, ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A��Y�#�9?80?        ��*>��*>�8@�����\2A�c��N,��D*5A>��
�@����X���8���Eg����   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   *c���1�A���N?6�>�N?6�����=���<�(�@1Ȯ��%��8�#������   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �
�y|�A���N?6�>�N?6�����=���<��@TT��vk���8�����Qr��   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �y����f�A���N?6�>�N?6�����=���<���@�İ��rq��8�/���b\��   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y��A���N?6�>�N?6�����=���<���@�F�µH���8�����4������   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �
���i@A���N?6�>�N?6�����=���<x��@Fo����=�8�t�����@���   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3�A���N?6�>�N?6�����=���<��@�w��<�?��8�+Į�rI&��   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l�A���N?6�>�N?6�����=���<���@�4��a����8�@k�§Ľ���   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y���c���N?6�>�N?6�����=���<���@�F�µH��鸑�����4���<��   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3c���N?6�>�N?6�����=���<��@�w��<�?�鸑�+Į�rI&�<��   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �
���i@�c���N?6�>�N?6�����=���<x��@Fo����=鸑�t�����@<��   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l��c���N?6�>�N?6�����=���<���@�4��a���鸑�@k�§Ľ<��   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �y����fc���N?6�>�N?6�����=���<���@�İ��rq�踑�/���b\�<��   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   "D��t}���c���N?6�>�N?6�����=���<
�@����X��鸑���Eg�<��   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   *c���1c���N?6�>�N?6�����=���<�(�@1Ȯ��%�鸑�#�����<��   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �
�y|c���N?6�>�N?6�����=���<��@TT��vk��踑�����Qr�<��   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   꾫�!SM���i�        80?"�9?��:@��*=���@��¿�d��*��/��6�U p�   �Y₁B���m���, ��Vz��������A�����2��0����$P�����L��m�   -ޫ�@�_��*��        80?"�9?���= �>  @?)?����`��*��1}�$_�[Ut�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �U��r����i�        #�9�80?��:@��*=���@����&��*��;$�¨���U p�   �Y₁B���m���, ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   �6�¦4���*��        #�9�80?���= �>  @?a��������*��i���D���[Ut�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   ���S.���i�        80?"�9? �?���=���@˷��s
6��*��cr��3�%�U p�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   t��X�U°�i�        80?"�9?��:@��*=���@�����[®*��l���,P�U p�   �Y₁B���m���, ��Vz��������A�����2��0����$P�����L��m�   � ��`�Z®*��        80?"�9?���= �>  @?�����Z®*�����·ZZ�[Ut�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �Э�wG°�i�        80?"�9?��:@��*=���@���®*��z�����U p�   �Y₁B���m���, ��Vz��������A�����2��0����$P�����L��m�   ���~�®*��        80?"�9?���= �>  @?�P��&%®*��ʎ��ֻ�[Ut�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �g�D����i�        #�9�80?��:@��*=���@���������*��� ��>���U p�   �Y₁B���m���, ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   LH�����*��        #�9�80?���= �>  @?H����[���*��P��6���[Ut�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   ��������i�        80?"�9? �?���=���@dɭ����*������u���U p�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   ����,AF°�i�        #�9�80?��:@��*=���@��L®*��xQ�� o@�U p�   �Y₁B���m���, ��&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   >y��$�A®*��        #�9�80?���= �>  @?:گ���A®*��B��|cA�[Ut�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �ׯ¤N°�i�        80?"�9? �?���=���@U���,P®*���L�U p�   �Y₁B���m���, �����2�T��[��Y�x�}�9�H
1ћfb��   �x��x�
1ћfb��   =Q��i�+A��i�        80?"�9?VUU?���=���@�q��'%A�*���0�¬n2AU p�   �Y₁B���m���, ��v� TW�߂G��'�/
��{[�=`O�L ����tIj����   .9��r�L­jf�q�<��?� �2O���EA�U�>��A=����N������e�J�X�   �Y₁B���m���, ��Բ����	X0D�ٽ�(�
�{{[�=`O�L ����tIj����   0���$­jf�<60�ѳ9?x�2z�첫��>y�MA��A=���L�&�����ٮ��a"�X�   �Y₁B���m���, ��^I�_���L�;��X�<���{[�=`O�L ����tIj����   F&�������jf�ڸ�<|�?S�A1���0J�VA���>��A=����x�����$��¶���X�   �Y₁B���m���, ��I;E�� ۏ��[�%���D�{[�=`O�L ����tIj����   �����jf�ͳ�<}�?�#�}U��g<_A���>��A=���V������}��¸e��X�   �Y₁B���m���, �Ρ_����^j�o�C.Bb j{[�=`O�L ����tIj����   w����'��jf�:��<~�?�1��D�/�gA���>��A=����#1�������§]�X�   �Y₁B���m���, ���X�ZF38��P8�ܵ1���{[�=`O�L ����tIj����   ܋��U7�>�jf�ª�<�?B&���\��pA���>��A=����_����P���|?X�   �Y₁B���m���, �����2�T��[��Y�x�0����$P�����L��m�   V۰�@�q����        80?"�9?�*A��*>  �>R���!l�����Y"��?\\����   �Y₁B���m���, �����2�T��[��Y�x�0����$P�����L��m�   wԮ��@$����        80?"�9?\F\A��*>  �>����?����g��^�����   �Y₁B���m���, �����2�T��[��Y�x�0����$P�����L��m�   1���`�����        80?"�9? �IA��*>  �>����aK������߫¿*g����   �Y₁B���m���, �����2�T��[��Y�x�0����$P�����L��m�   Z���.-����        80?"�9?��hA��*>  �>�t�����������¶��@���   �Y₁B���m���, �琤�f07L6���	��䬕��u	���B1������   �.���u|�s���        80?"�9?��@���=��@����tj�«���԰ºr�:n��  �Y₁B���m���, �鐤�f07L6���	��䬕��u	���B1������   "B�3�s���        80?"�9?��@���=��@߬��8�?«���d׮��C&�:n��  �Y₁B���m���, �ꐤ�f07L6���	��䬕��u	���B1������   r���0.�s���        80?"�9?�(�@���=��@�����%«���\��|��:n��  �Y₁B���m���, �쐤�f07L6���	��䬕��u	���B1������   n��Zr��s���        80?"�9?���@���=��@�{�®D����������:n��  �Y₁B���m���, �퐤�f07L6���	��䬕��u	���B1������   kh���u��s���        80?"�9?�@���=��@Ѭ�T����������6/g�:n��  �Y₁B���m���, ��f07L6���	��䬕��u	���B1������   g����`l�s���        80?"�9?���@���=��@Uj��E}������z~���丽:n��  �Y₁B���m���, ���f07L6���	��䬕��u	���B1������   &/���j@s���        80?"�9?z��@���=��@�����	�=�����������@:n��  �Y₁B���m���, �����f07L6���	��䬕��u	���B1������   =����f�s���        80?"�9?���@���=��@,����pq«���MB��]]\�:n��  �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   ���hN�WG��N?6�>�N?6����*>��*>���@s�¿�[­jH��f��f@��E�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   $��	j@WG��N?6�>�N?6����*>��*>x��@E���\W�=�jH����µ��@�E�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   ����.�f�WG��N?6�>�N?6����*>��*>���@���tq­jH�Y"��?\\��E�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �������WG��N?6�>�N?6����*>��*>���@'B���­jH��5��a����E�   �Y₁B���m���, ��$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3�WG��N?6�>�N?6����*>��*>��@����?­jH�o��½B&��E�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   ����2yAWG��N?6�>�N?6����*>��*>��o@y�·��@�jH��0��2A�E�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   e���c�-�WG��N?6�>�N?6����*>��*>���@�0�½�d��jH�;$������E�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �]��x��WG��N?6�>�N?6����*>��*>
�@�۬��Z���jH��߫¿*g��E�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   �|��M/�WG��N?6�>�N?6����*>��*>�(�@0��=�%�XG�g��^�¬jD�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   ��´rl�WG��N?6�>�N?6����*>��*>���@�t�����XG��^��L����jD�   �Y₁B���m���, �����f07L6���	����+�(������ְ�P��M�   3$���v|�WG��N?6�>�N?6����*>��*>��@S���!l�­jH���r��E�   �Y₁B���m���, � $`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t��WG��N?6�>�N?6����*>��*>���@����`K���jH�����ʝ���E�   �Y₁B���m���, ���6�l���c�r��f��r��+�(������ְ�P��M�   %Y��3A����#�9?80?        ��*>��*>���>�����\2A���N,��D*5AV5��
   �Y₁B���m���, �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A�Q��#�9?80?        ��*>��*>�8@�.���3AV5���Ԩ�g[6A:n��
�+�(������ְ�P��M�   �k���«���        #�9�80?��*>��*>���>ʘ��X������?�©g��V5��
   �Y₁B���m���, ���6�l���c�r��f��r��+�(������ְ�P��M�   �k�����W�        #�9�80?��*>��*>�8@ʘ��X���:Ni�?�©g���E�
   �Y₁B���m���, ����f07L6���	����+�(������ְ�P��M�   �|��M/�V5���N?6�>�N?6����*>��*>�(�@0��=�%����g��^�«���   �Y₁B���m���, ����f07L6���	����+�(������ְ�P��M�   3$���v|�V5���N?6�>�N?6����*>��*>��@S���!l�¬�����r�V5��   �Y₁B���m���, ����f07L6���	����+�(������ְ�P��M�   ��´rl�V5���N?6�>�N?6����*>��*>���@�t���������^��L�������   �Y₁B���m���, �$`�x��6'	�����#�{^�+�(������ְ�P��M�   {7�§3�V5���N?6�>�N?6����*>��*>��@����?¬���o��½B&�V5��   �Y₁B���m���, �	���f07L6���	����+�(������ְ�P��M�   $��	j@V5���N?6�>�N?6����*>��*>x��@E���\W�=�������µ��@V5��   �Y₁B���m���, �
���f07L6���	����+�(������ְ�P��M�   ����.�f�V5���N?6�>�N?6����*>��*>���@���tq¬���Y"��?\\�V5��   �Y₁B���m���, �$`�x��6'	�����#�{^�+�(������ְ�P��M�   ��t��V5���N?6�>�N?6����*>��*>���@����`K����������ʝ��V5��   �Y₁B���m���, ����f07L6���	����+�(������ְ�P��M�   �]��x��V5���N?6�>�N?6����*>��*>
�@�۬��Z������߫¿*g�����   �Y₁B���m���, �
   �Y₁B���m���, �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �J��\��Q��#�9?80?        ��*>��*>�8@Y"��n\�V5���ȯ¿�[�:n��
   �Y₁B���m���, �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   &���R@��Q��#�9?80?        ��*>��*>�8@�f���w@�V5��
   �Y₁B���m���, ���6�l���c�r��f��r��+�(������ְ�P��M�   �߮���%����#�9?80?        ��*>��*>9�@��¬K&��������N�%�:n��
   �Y₁B���m���, �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ��l��Q��#�9?80?        ��*>��*>�8@g��;��V5��������:n��
   �Y₁B���m���, �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   5^�������Q��#�9? 80?��0�e���*>��*>�8@�5�����V5��&ܬ�aK��:n��
   �Y₁B���m���, ���6�l���c�r��f��r��+�(������ְ�P��M�   Y���J������#�9?80?        ��*>��*>9�@1�§�����������H��:n��
   �Y₁B���m���, ���6�l���c�r��f��r��+�(������ְ�P��M�   .�¿�e�����#�9?80?	802�9'���*>��*>���>A7��W�h�����ݫ���e�V5��
   �Y₁B���m���, �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   .�¿�e��Q��#�9? 80?��0�e���*>��*>�8@�߫�4rg�V5����¾�d�:n��
   �Y₁B���m���, ���6�l���c�r��f��r��+�(������ְ�P��M�   冪��H)����#�9?80?        ��*>��*>9�@����}�Ƚ���Z��J4�=:n��
   �Y₁B���m���, ���6�l���c�r��f��r��+�(������ְ�P��M�   ©¶]�@����#�9?80?        ��*>��*>���>+���@���}���p��@V5��
   �Y₁B���m���, �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ©¶]�@�Q��#�9?80?        ��*>��*>�8@���@��@V5��A���,+�@:n��
�+�(������ְ�P��M�   %Y��3A�W�#�9?80?        ��*>��*>�8@�����\2A:Ni�N,��D*5A�E�
   �Y₁B���m���, �--}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �k����W{�        #�9�80?��*>��*>�8@ʘ��X���:n��?�©g��:Ni�
�+�(������ְ�P��M�   sܰ���q��W�#�9?80?        ��*>��*>�8@����sr�:Ni�ر��e�q��E�
   �Y₁B���m���, �/0]�����!E�U�=7O(
�+�(������ְ�P��M�   �J��\��W�#�9? 80?,��08�e���*>��*>�8@Y"��n\�:Ni��ȯ¿�[��E�
   �Y₁B���m���, �00]�����!E�U�=7O(
�+�(������ְ�P��M�   &���R@��W�#�9?80?        ��*>��*>�8@9���8�@�:Ni��d���@��E�
   �Y₁B���m���, �10]�����!E�U�=7O(
�+�(������ְ�P��M�   �߮���%��W�#�9?80?        ��*>��*>�8@����&�:Ni�4���%��E�
   �Y₁B���m���, �20]�����!E�U�=7O(
�+�(������ְ�P��M�   ��l��W�#�9?80?        ��*>��*>�8@�H�	�:Ni�+��'h��E�
   �Y₁B���m���, �30]�����!E�U�=7O(
�+�(������ְ�P��M�   5^�������W�#�9? 80?,��08�e���*>��*>�8@�5�����:Ni�&ܬ�aK���E�
   �Y₁B���m���, �40]�����!E�U�=7O(
�+�(������ְ�P��M�   Y���J����W�#�9?80?        ��*>��*>�8@l��Z��:Ni�����[���E�
   �Y₁B���m���, �50]�����!E�U�=7O(
�+�(������ְ�P��M�   .�¿�e��W�#�9?80?        ��*>��*>�8@A7��W�h�:Ni��ݫ���e��E�
   �Y₁B���m���, �60]�����!E�U�=7O(
�+�(������ְ�P��M�   �L�����W�#�9? 80?,��08�e���*>��*>�8@;$���2��:Ni��ʪ�����E�
   �Y₁B���m���, �70]�����!E�U�=7O(
�+�(������ְ�P��M�   冪��H)��W�#�9?80?        ��*>��*>�8@���¤z9�:Ni�I\���û�E�
   �Y₁B���m���, �80]�����!E�U�=7O(
�+�(������ְ�P��M�   ©¶]�@�W�#�9?80?        ��*>��*>�8@+���@:Ni�}���p��@�E�
   �Y₁B���m���, �:���f07L6���	��䬕��u	���B1������   �.���u|�W{�        80?"�9?��@���=�8@����tj��:n��԰ºr�:Ni�  �Y₁B���m���, �;���f07L6���	��䬕��u	���B1������   =����f�W{�        80?"�9?���@���=�8@,����pq�:n��MB��]]\�:Ni�  �Y₁B���m���, �=���f07L6���	��䬕��u	���B1������   "B�3�W{�        80?"�9?��@���=�8@߬��8�?�:n��d׮��C&�:Ni�  �Y₁B���m���, �>���f07L6���	��䬕��u	���B1������   r���0.�W{�        80?"�9?�(�@���=�8@�����%�:n��\��|��:Ni�  �Y₁B���m���, �@���f07L6���	��䬕��u	���B1������   n��Zr��W{�        80?"�9?���@���=�8@�{�®D��:n������:Ni�  �Y₁B���m���, �A���f07L6���	��䬕��u	���B1������   kh���u��W{�        80?"�9?�@���=�8@Ѭ�T��:n������6/g�:Ni�  �Y₁B���m���, �C���f07L6���	��䬕��u	���B1������   g����`l�W{�        80?"�9?���@���=�8@Uj��E}��:n��z~���丽:Ni�  �Y₁B���m���, �D���f07L6���	��䬕��u	���B1������   &/���j@W{�        80?"�9?z��@���=�8@�����	�=:n���������@:Ni�  �Y₁B���m���, �F-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3AW{�#�9?80?        ��*>��*>�8@�����\2A:n��N,��D*5A:Ni�
�@����X����i���Eg���h�   �Y₁B���m���, �T���f07L6���	����+�(������ְ�P��M�   *c���1�;Ni��N?6�>�N?6�����=���<�(�@1Ȯ��%���i�#�����h�   �Y₁B���m���, �U���f07L6���	����+�(������ְ�P��M�   �
�y|�;Ni��N?6�>�N?6�����=���<��@TT��vk����i�����Qr�h�   �Y₁B���m���, �V���f07L6���	����+�(������ְ�P��M�   �y����f�;Ni��N?6�>�N?6�����=���<���@�İ��rq���i�/���b\�h�   �Y₁B���m���, �W$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y��;Ni��N?6�>�N?6�����=���<���@�F�µH����i�����4�����h�   �Y₁B���m���, �X���f07L6���	����+�(������ְ�P��M�   �
���i@;Ni��N?6�>�N?6�����=���<x��@Fo����=��i�t�����@��h�   �Y₁B���m���, �Y$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3�;Ni��N?6�>�N?6�����=���<��@�w��<�?���i�+Į�rI&�h�   �Y₁B���m���, �Z$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l�;Ni��N?6�>�N?6�����=���<���@�4��a�����i�@k�§Ľ��h�   �Y₁B���m���, �[$`�x��6'	�����#�{^�+�(������ְ�P��M�   %���y��:n���N?6�>�N?6�����=���<���@�F�µH���Æ�����4������   �Y₁B���m���, �\$`�x��6'	�����#�{^�+�(������ְ�P��M�   ���W3�:n���N?6�>�N?6�����=���<��@�w��<�?Æ�+Į�rI&����   �Y₁B���m���, �]���f07L6���	����+�(������ְ�P��M�   �
���i@:n���N?6�>�N?6�����=���<x��@Fo����=�Æ�t�����@���   �Y₁B���m���, �^$`�x��6'	�����#�{^�+�(������ְ�P��M�   Ъ°�l�:n���N?6�>�N?6�����=���<���@�4��a����Æ�@k�§Ľ���   �Y₁B���m���, �_���f07L6���	����+�(������ְ�P��M�   �y����f�:n���N?6�>�N?6�����=���<���@�İ��rqÆ�/���b\����   �Y₁B���m���, �`���f07L6���	����+�(������ְ�P��M�   "D��t}��:n���N?6�>�N?6�����=���<
�@����X���Æ���Eg����   �Y₁B���m���, �a���f07L6���	����+�(������ְ�P��M�   *c���1�:n���N?6�>�N?6�����=���<�(�@1Ȯ��%Æ�#��������   �Y₁B���m���, �b���f07L6���	����+�(������ְ�P��M�   �
�y|�:n���N?6�>�N?6�����=���<��@TT��vk�Æ�����Qr����   �Y₁B���m���, �d���2�T��[��Y�x�}�9�H
1ћfb��   꾫�!SM�W�        80?"�9?��:@��*=���@��¿�d����/��6��jH�   �Y₁B���m���, �dVz��������A�����2��0����$P�����L��m�   -ޫ�@�_����        80?"�9?���= �>  @?)?����`����1}�$_����   �Y₁B���m���, �f���2�T��[��Y�x�}�9�H
1ћfb��   �U��r��W�        #�9�80?��:@��*=���@����&����;$�¨����jH�   �Y₁B���m���, �f&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   �6�¦4�����        #�9�80?���= �>  @?a����������i���D������   �Y₁B���m���, �h���2�T��[��Y�x�}�9�H
1ћfb��   ���S.�W�        80?"�9? �?���=���@˷��s
6����cr��3�%��jH�   �Y₁B���m���, �k���2�T��[��Y�x�}�9�H
1ћfb��   t��X�U�W�        80?"�9?��:@��*=���@�����[����l���,P¬jH�   �Y₁B���m���, �kVz��������A�����2��0����$P�����L��m�   � ��`�Z����        80?"�9?���= �>  @?�����Z�������·ZZ����   �Y₁B���m���, �m���2�T��[��Y�x�}�9�H
1ћfb��   �Э�wG�W�        80?"�9?��:@��*=���@�������z������jH�   �Y₁B���m���, �mVz��������A�����2��0����$P�����L��m�   ���~�����        80?"�9?���= �>  @?t;��b'����|y�������   �Y₁B���m���, �o���2�T��[��Y�x�}�9�H
1ћfb��   �g�D��W�        #�9�80?��:@��*=���@������������ ��>����jH�   �Y₁B���m���, �o&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   LH�������        #�9�80?���= �>  @?H����[�����P��6������   �Y₁B���m���, �q���2�T��[��Y�x�}�9�H
1ћfb��   ������W�        80?"�9? �?���=���@dɭ����������u����jH�   �Y₁B���m���, �s���2�T��[��Y�x�}�9�H
1ћfb��   ����,AF�W�        #�9�80?��:@��*=���@��L����xQ�� o@¬jH�   �Y₁B���m���, �s&�Hb	�ͳ1�;��1zQ���0����$P�����L��m�   >y��$�A����        #�9�80?���= �>  @?�į��A������¸eA����   �Y₁B���m���, �u���2�T��[��Y�x�}�9�H
1ћfb��   �ׯ¤N�W�        80?"�9? �?���=���@U���,P�����L¬jH�   �Y₁B���m���, �w���2�T��[��Y�x�}�9�H
1ћfb��   �x��x�
1ћfb��   =Q��i�+AW�        80?"�9?VUU?���=���@�q��'%A����0�¬n2A�jH�   �[@.IБ�1��E@� ����k��vml9���+�����א�� �s�gtQ�#�e;$,�   ~}� G������1���1�;�5��5?���?�UPB(VA)��;� «:�J������
��   �[@.IБ�1��E@� ��]�?���7g� ݗ𹠨J{v�{[�=`O�L ����tIj����   }}� G�����p� �p� <| 5�| 5?���?$�PBR�aA)��;� «:�J������
��   �[@.IБ�1��E@� ��}����3-"it�Of�N�א�� �s�gtQ�#�e;$,�   5NY��3D����Y�[�        �?���?�B<YA��g��̃«:�J�;� ¬
��   �[@.IБ�1��E@� ��e]ߞp�Q]��J��9�uu�{[�=`O�L ����tIj����   5NY��3D����z<        ��?���?o�B�TA��g��̃«:�J�;� ¬
��   �_��B��nL��[ �0���_�݄i������K��Q�}$uJ�q�NeȊq�`�1��    ��܅� ��          �?v�&  �@��*>  �@�� ���5��� ��H   �_��B��nL��[ ����f07L6���	��䬕��u	���B1������    �5�� ��          �?v�&  �@���<  �@�A��� ������܅� �  �_��B��nL��[ �?���f07L6���	��䬣}$uJ�q�NeȊq�`�1��    �2��Ve�          �?v�&UU�@�2@XU�>�,���«: �Cנg�� ��   ����G ���
�?� ��f07L6���	��䬕��u	���B1������   �.���u|��A        80?"�9?��@���=9�@����tj��8��A԰ºr���A  ����G ���
�?� ��f07L6���	��䬕��u	���B1������   =����f��A        80?"�9?���@���=9�@,����pq�8��AMB��]]\���A  ����G ���
�?� ��f07L6���	��䬕��u	���B1������   "B�3��A        80?"�9?��@���=9�@߬��8�?�8��Ad׮��C&���A  ����G ���
�?� ����f07L6���	��䬕��u	���B1������   r���0.��A        80?"�9?�(�@���=9�@�����%�8��A\��|����A  ����G ���
�?� ����f07L6���	��䬕��u	���B1������   n��Zr���A        80?"�9?���@���=9�@�{�®D��8��A������A  ����G ���
�?� ����f07L6���	��䬕��u	���B1������   kh���u���A        80?"�9?�@���=9�@Ѭ�T��8��A����6/g���A  ����G ���
�?� ����f07L6���	��䬕��u	���B1������   g����`l��A        80?"�9?���@���=9�@Uj��E}��8��Az~���丽��A  ����G ���
�?� ����f07L6���	��䬕��u	���B1������   &/���j@�A        80?"�9?z��@���=9�@�����	�=8��A�������@��A  ����G ���
�?� �0]�����!E�U�=7O(
�+�(������ְ�P��M�   %Y��3AƑ�A#�9?80?        ��*>��*>�8@�����\2A8��AN,��D*5AUu�A
   ����G ���
�?� �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �k���ªʘA        #�9�80?��*>��*>�8@ʘ��X����A?�©g��8��A
�?� �0]�����!E�U�=7O(
�+�(������ְ�P��M�   sܰ���q�Ƒ�A#�9?80?        ��*>��*>�8@����sr�8��Aر��e�q�Uu�A
   ����G ���
�?� � 0]�����!E�U�=7O(
�+�(������ְ�P��M�   �J��\�Ƒ�A#�9?80?        ��*>��*>�8@�w��.e\�8��A���ѱ[�Uu�A
   ����G ���
�?� �!0]�����!E�U�=7O(
�+�(������ְ�P��M�   &���R@�Ƒ�A#�9?80?        ��*>��*>�8@���� o@�8��AOb�£�?�Uu�A
   ����G ���
�?� �"0]�����!E�U�=7O(
�+�(������ְ�P��M�   �߮���%�Ƒ�A#�9?80?        ��*>��*>�8@��¬K&�8��A����N�%�Uu�A
   ����G ���
�?� �#0]�����!E�U�=7O(
�+�(������ְ�P��M�   ��l�Ƒ�A#�9?80?        ��*>��*>�8@�F��M��8��A�����Uu�A
   ����G ���
�?� �$0]�����!E�U�=7O(
�+�(������ְ�P��M�   5^������Ƒ�A#�9?80?        ��*>��*>�8@���>���8��A]1�9��Uu�A
   ����G ���
�?� �%0]�����!E�U�=7O(
�+�(������ְ�P��M�   Y���J���Ƒ�A#�9?80?        ��*>��*>�8@1�§���8��A�����H��Uu�A
   ����G ���
�?� �&0]�����!E�U�=7O(
�+�(������ְ�P��M�   .�¿�e�Ƒ�A#�9? 80?��0�e���*>��*>�8@�߫�4rg�8��A��¾�d�Uu�A
   ����G ���
�?� �'0]�����!E�U�=7O(
�+�(������ְ�P��M�   �L����Ƒ�A#�9? 80?,��08�e���*>��*>�8@;$���2��8��A�ʪ����Uu�A
   ����G ���
�?� �(0]�����!E�U�=7O(
�+�(������ְ�P��M�   冪��H)�Ƒ�A#�9?80?        ��*>��*>�8@����}�Ƚ8��AZ��J4�=Uu�A
   ����G ���
�?� �)0]�����!E�U�=7O(
�+�(������ְ�P��M�   ©¶]�@Ƒ�A#�9?80?        ��*>��*>�8@���@��@8��AA���,+�@Uu�A
   ����G ���
�?� �]���f07L6���	��䬕��u	���B1������   �.���u|ªʘA        80?"�9?��@���=�8@����tj���A԰ºr�8��A  ����G ���
�?� �^���f07L6���	��䬕��u	���B1������   =����fªʘA        80?"�9?���@���=�8@,����pq��AMB��]]\�8��A  ����G ���
�?� �`���f07L6���	��䬕��u	���B1������   "B�3ªʘA        80?"�9?��@���=�8@߬��8�?��Ad׮��C&�8��A  ����G ���
�?� �a���f07L6���	��䬕��u	���B1������   r���0.ªʘA        80?"�9?�(�@���=�8@�����%��A\��|��8��A  ����G ���
�?� �c���f07L6���	��䬕��u	���B1������   n��Zr���ʘA        80?"�9?���@���=�8@�{�®D���A����8��A  ����G ���
�?� �d���f07L6���	��䬕��u	���B1������   kh���u���ʘA        80?"�9?�@���=�8@Ѭ�T���A����6/g�8��A  ����G ���
�?� �f���f07L6���	��䬕��u	���B1������   g����`l��ʘA        80?"�9?���@���=�8@Uj��E}���Az~���丽8��A  ����G ���
�?� �g���f07L6���	��䬕��u	���B1������   &/���j@�ʘA        80?"�9?z��@���=�8@�����	�=�A�������@8��A  ����G ���
�?� �q-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   %Y��3A�ʘA#�9?80?        ��*>��*>�8@�����\2A�AN,��D*5A8��A
�?� �r-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   sܰ���qªʘA#�9?80?        ��*>��*>�8@����sr��Aر��e�q�8��A
�?� �s-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �J��\ªʘA#�9?80?        ��*>��*>�8@�w��.e\��A���ѱ[�8��A
�?� �t-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   &���R@ªʘA#�9?80?        ��*>��*>�8@���� o@��AOb�£�?�8��A
�?� �u-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �߮���%ªʘA#�9?80?        ��*>��*>�8@��¬K&��A����N�%�8��A
�?� �v-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ��lªʘA#�9?80?        ��*>��*>�8@�F��M���A�����8��A
�?� �w-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   5^�������ʘA#�9?80?        ��*>��*>�8@���>����A]1�9��8��A
�?� �x-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   Y���J����ʘA#�9?80?        ��*>��*>�8@1�§����A�����H��8��A
�?� �y-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   .�¿�e��ʘA#�9?80?        ��*>��*>�8@5��yNg��AW۫��d�8��A
�?� �z-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �L�����ʘA#�9?80?        ��*>��*>�8@sy�����A��P��8��A
�?� �{-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   冪��H)��ʘA#�9?80?        ��*>��*>�8@����}�Ƚ�AZ��J4�=8��A
�?� �|-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ©¶]�@�ʘA#�9?80?        ��*>��*>�8@���@��@�AA���,+�@8��A
�?� �}-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �k����A        #�9�80?��*>��*>�8@ʘ��X����?|A?�©g���A
|iBV��              �?  �?��wAV�4A;(BL�JB p1�;(B�6�B�:�   �<�F�d�G��� -8��fd�#߅X�.=�!����{[�H�_����˖���dn`   �$������rA��N���Ƿ�={?	�D�VC�B_~C��?=����̃�R�nA��[�^c�B��vA*   �<�F�d�G��� -8�u��&�44su�!-0�)�i|�-�6�QBڍ��a�1t   ��p��0���vA        n81�#|?�g�Bs]C  �?=����̃ª�vA��[�^c�B��vA   �<�F�d�G��� -8��p�h�u�����Ep\;���!�
+a�d��n�Kn:��e7   (j�^����vA        �3~>��w?+��B���B  �?����ı"ª�vA��[��5A��vA   �Hi:�-K�s��:� ���&��&��P�A�g�٣}$uJ�q�NeȊq�`�1��    ����\A�ʱ�        �5?�5?���@��*>  @@=���;A�ʽ����}A�ʥ�0   �Hi:�-K�s��:� �ᐤ�f07L6���	��䬕��u	���B1������    ���\A�ʱ�        �5?�5?��w@���<  0@=���=A�ʼ�����{A�ʦ�  �Hi:�-K�s��:� ���&��&��P�A�g�٣}$uJ�q�NeȊq�`�1��    ������@�ʱ�        �5��5?���@��*>  @@=�����@�ʽ����A�ʥ�0   �Hi:�-K�s��:� �����f07L6���	��䬕��u	���B1������    �����@�ʱ�        �5��5?��w@���<  0@=�����@�ʼ�����A�ʦ�  ��@<D����C�E�; �����2�T��[��Y�x�0����$P�����L��m�   $}�A/NX©�xA          �?���  0@��*>  �>$}�A��X©�vA$}�A��W©�zA   ��@<D����C�E�; �����2�T��[��Y�x�}�9�H
1ћfb��   I�fA�#XªʖA          �?���UUU?���=���@�O`A/NX©�vA��mA��W���A   ��@<D����C�E�; �����2�T��[��Y�x�}�9�H
1ћfb��   $}�A/XªʖA          �?�����:@��*=���@��mA�#X©�vA�'�A��W���A   ��@<D����C�E�; ��Vz��������A�����2��0����$P�����L��m�   zҋA/X�Uu�A          �?������=  �>  @?K�A��X�Uu�A���A�#W�Uu�A   ��@<D����C�E�; �̐��f07L6���	��䬕��u	���B1������   $}�A�cX��X�A          �?���  0@���=��@$}�A/�X�T�}A$}�A�8X��A  ��@<D����C�E�; �А��f07L6���	��䬕��u	���B1������   $}�A�cX��A          �?���  0@���=9�@$}�A/�X�8��A$}�A�8X���A  ��@<D����C�E�; �Ԑ��f07L6���	��䬕��u	���B1������   $}�A�cXªʘA          �?���  0@���=�8@$}�A/�X��A$}�A�8X�8��A  ��@<D����C�E�; �א��f07L6���	����+�(������ְ�P��M�   $}�A�X�8��A�[�&�5��[�&�5?���=  �<��/@$}�AY#X��X�A$}�AYX�A   ��@<D����C�E�; �ؐ��f07L6���	����+�(������ְ�P��M�   $}�A�X��A�[�&�5��[�&�5?���=  �<��/@$}�AY#X�Ƒ�A$}�AYX�q<�A   ��@<D����C�E�; �ٲ�6�l���c�r��f��r��+�(������ְ�P��M�   I�fA/NXªʲA�5'�5��5'�5?��*>��*>TUU?�O`A��X���A��mA��W�Uu�A
   ��@<D����C�E�; ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   $}�A/NXªʲA�[q&�5��[q&�5?��*>��*>��:@��mA��X���A�'�A��W�Uu�A
   ��@<D����C�E�; �ې��f07L6���	����+�(������ְ�P��M�   $}�A/NXªʲA�[�&�5��[�&�5?��*>��*>��/@$}�A��X���A$}�A��W�Uu�A   ��@<D����C�E�; �ܲ�6�l���c�r��f��r��+�(������ְ�P��M�   zҎA/NX�T�yA���  �?        ��*>��*>���>�'�A��X©�vA$}�A��W��?|A
   ��@<D����C�E�; ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   zҎA/NX�A���  �?        ��*>��*>�8@�'�A��X��?|A$}�A��W��A
�+�(������ְ�P��M�   zҎA/NX�Ƒ�A���  �?        ��*>��*>�8@�'�A��X�8��A$}�A��W�Uu�A
   ��@<D����C�E�; ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   zҎA/NXªʘA���  �?        ��*>��*>�8@�'�A��X��A$}�A��W�8��A
�+�(������ְ�P��M�   I�^A/NX�Ƒ�A���  �?        ��*>��*>�8@��]A��X�8��A�O`A��W�Uu�A
   ��@<D����C�E�; ���6�l���c�r��f��r��+�(������ְ�P��M�   I�^A/NX�T�yA���  �?        ��*>��*>���>��]A��X©�vA�O`A��W��?|A
   ��@<D����C�E�; ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   I�^A/NXªʘA���  �?        ��*>��*>�8@��]A��X��A�O`A��W�8��A
   ��@<D����C�E�; ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   �'�A/NX�A              �?��*>��*>�8@�'�A��X��?|A$}�A��W��A
�+�(������ְ�P��M�   �'�A/NX�T�yA              �?��*>��*>���>$}�A��X©�vAzҦA��W��?|A
   �*C�%A����	:�P pv���;A���?j�f��??^��ɬ�@MQ��
x>�Pr$   �\�A(��� ��A        �0u���?c#A!�f?��,A�~�A�����vAI� B�r�����A   �*C�%A����	:�P p��w��*:�Q0�p�<:/`� �?^��ɬ�@MQ��
x>�Pr$   �v�AZB-� ��AWUٷ��:��?�u�a��>�}�@s-A���A�=^���vAJ]�AxF�����A   �*C�%A����	:�P p��b8
�K����%��nhr�6w?^��ɬ�@MQ��
x>�Pr$   &��Az˟� ��A�v���?������5+��>ӥ@`�,AޱA���vA<p�A������A2   �*C�%A����	:�P p�j�ܖ�Ū��]|j4��caN�1
x>�Pr$   ��As��� ��A7�q8�G|�(�?�u�3��> ��@|r-A_�AK�ª�vA��A6t�����A.   �*C�%A����	:�P p�j�ܖ�Ū��]|j4��caN�1
x>�Pr$   D_ B}��� ��A        ���;��?ʘ>��?��,A��Apn ª�vA�� B�������A   �*C�%A����	:�P qRCzZ*
x>�Pr$   �2B�.�� ��A        �t�:��?ܖ>[�_?��,AI� B� ���vA��B+�����A   �*C�%A����	:�P q�I ���s/�3�d��
��aN�1
� �˭~��P�nKVO��ǔЭ@��}$uJ�q�NeȊq�`�1��   ���|�V����1�2�f$�^�l?�þ��>UUA���@���&�«J��Gλ���m����  �B-��DT����
� ����7Q�
nI$8k��BP�N�^*������5/���&9����   �B��z�w���y���r�i?�,
£�tASu�A   Ý"ce6Hй{�ֺk� (v�U�a�Sy;�8��@��^O�t����JR� ��}��G   S�{ATu�A        ��[��?8%'AҌNA��A��DyH@��vA2����|ASu�A   Ý"ce6Hй{�ֺk� (x���5H9�u��QCr��3�dO�t����JR� ��}��G   ���/�ATu�A        _�̼��?g
Ý��k);[�_��{}?� �I�}$uJ�q�NeȊq�`�1��   ؁��/.A«	������>*�0�*�0? �*>,�IAũLA;P���A�V�_�@��@����   �.;|Gc���J��:f ���Cj΅���l�lq��f���{[�=`O�L ����tIj����   _�@�q�*�JU�?              �?�b�? �*>UňB��J���*«:�47�/*� PB   �.;|Gc���J��:f ��a���ƹ���h���C�!�{[�=`O�L ����tIj����   _�@��X-�JU�?              �?�b�? �*>UňB��J��-«:�47�p-� PB   �.;|Gc���J��:f � ���f07L6���	���{[�=`O�L ����tIj����   �l8���+�JU�?              �?��*>�j
?UňB��9�p-«:�47���*� PB   ōi
�D�;;�� �͆u��
�D�;;�� ��Q���lY�u�8�?�����{[�=`O�L ����tIj����   B/�A�PBUN��G���O�:�5�55?E�*?R�*A���B&��A��B p1�~vB-� BV�B�   ōi
�D�;;�� �ؾ�u&oo��ܶy,>�y�dQ{[�=`O�L ����tIj����   u��Ac�BV5 B��=���#�4���4?hv�>P�EA��<A&��A�B���AboB�lBV�B   ōi
�D�;;�� ��<��:��sѠ�M¡;��LsO�|P���=�����4�   ���AcB���A          �?��&  �@��*>  �@���A�B���A���A�lBU�B   ōi
�D�;;�� ��O�~i+@�N�m���<� �#�z���(L��X�?��'�l���   ���Ac�B���A          �?��&  �@UU?  �@���A�lB���A���A�BU�B8   ōi
�D�;;�� ��OD8���}PV�a_���G��{[�=`O�L ����tIj����   �E�@���A�: B        o�w�  �?+�Bt]�>��*A[7�4?�A���A���A���A �B   ōi
�D�;;�� ��x��]�2(��"���Z�#*�i{[�=`O�L ����tIj����   ��AM�B�: B�<��<���4?��4? U�>���A�I7A<���B���A{߯A�B �B$   ōi
�D�;;�� �ܐ��f07L6���	���sO�|P���=�����4�   ���AM*B���A              �?  @@��*>  �@���A��B���A���A�BU�B   ōi
�D�;;�� �� t��������6f�̳=�4^*������5/���&9����   ���AM�B���A              �?  `@UU�>  �@���A��B���A���A�BU�B   ōi
�D�;;�� �ܠ�%�~q���pZ9���;g|5�z���(L��X�?��'�l���   ���AM�B���A              �?  `@UU?  �@���A�B���A���A��BU�B8   ōi
�D�;;�� ����`U�G�$
�D�;;�� �����f07L6���	���sO�|P���=�����4�   �@#?M�B���A        �5��5?��?@��*>  �@r�
�D�;;�� �� t��������6f�̳=�4^*������5/���&9����   �@C?M�B���A        �5��5?��_@TU�>  �@r�
�D�;;�� ��[��\��K�;!��KȻ�z���(L��X�?��'�l���   �@C?M�B���A        �5��5?��_@TU?  �@:,�>M�B���A���?M�BU�B8   ōi
�D�;;�� ��<�b�ыd� ���XK0�{[�=`O�L ����tIj����   �W�A��A���A        �*�  �?*�+A�m�>  �@TZ�AD��A���At*B�T�AV�	B   ōi
�D�;;�� ��MY� j�^ۃ�{h�}���]{[�=`O�L ����tIj����   ��A���A���A���=        �o?@U�>q8�@2�ATZ�A���A���A���AD��AV�	B   ōi
�D�;;�� �㐤�f07L6���	���sO�|P���=�����4�   ��A��A���A        �5?�5?��?@��*>  �@SZ�A��A���A���A��AU�B   ōi
�D�;;�� �� t��������6f�̳=�4^*������5/���&9����   ��A��A���A        �5?�5?��_@TU�>  �@SZ�A��A���A���A��AU�B   ōi
�D�;;�� ��[��\��K�;!��KȻ�z���(L��X�?��'�l���   ��A��A���A        �5?�5?��_@TU?  �@���A��A���ASZ�A��AU�B8   ōi
�D�;;�� Ԍ���f07L6���	���{[�=`O�L ����tIj����   �4�A� B�: B              �?@U�> �P?��*A&��A�B���A{߯A�B �B   �!yk�A����1�}H� 9$`�x��6'	�����#�{^�}$uJ�q�NeȊq�`�1��    �jA0�©��A              �? ��<�.�@���?tejA:(�S��AɺjAE�����A   �}��BV��=Th3yl P�
���;����A        ��/=��?J�A��A   A�����>�UՅ@SF���|@��bAL   �}��BV��=Th3yl P�o$�\�R+�������o��A�O�t����JR� ��}��G   �,������A        O�{=A�?οRA�A   A������UՅ@
���������bAT   �}��BV��=Th3yl P�|���P���!d���<E��O�t����JR� ��}��G   t�P�+ٔ���A��������?(l=\�AɋA  A)��@�N�UՅ@�����p@��bA�   ǽ�.hH�UOI��e ʍ%���%����	=�5��}��`S��C\��/��Ȧ��'���R    6�:B�Y��$���C(�.�V�]�?�BH'   @s9@��A6�5B�W��V��6�?B\��V����   ǽ�.hH�UOI��e ʍ��v�� ����o T��%AO��}$uJ�q�NeȊq�`�1��    8�:B�
���P��*5���E<�?k)�	 `@&k@�q�A6�3B\�� p!�6�AB\��V���q  ǽ�.hH�UOI��e ʍ�2ʦgah�@Ƃ�u��P^*������5/���&9����    ��=B�ޅ�/����Z?�^?����� =�=@k@�z�A6�:B܈� p!��\IB\��V���   ǽ�.hH�UOI��e ˥%���%����	=�5��}��`S��C\��/��Ȧ��'���R    ���B�Y��$���C(�.�V�]�?�BH'   @s9@��A��B�W��V�µ�B\��V����   ǽ�.hH�UOI��e ˥��v�� ����o T��%AO��}$uJ�q�NeȊq�`�1��    ���B�
���P��*5���E<�?k)�	 `@&k@�q�A��B\�� p!µ�B\��V���q  ǽ�.hH�UOI��e ˥�2ʦgah�@Ƃ�u��P^*������5/���&9����    ��B�ޅ�/����Z?�^?����� =�=@k@�z�A���B܈� p!�
�B\��V���   �+�I4o@%���5��� �����2�T��[��Y�xհ�"�� �����i��Vil   w)A���«:�              �?ֻ2B  �?���@4NS�����VEH��A�w�� �+�   �+�I4o@%���5��� ����9���'Gm���@�RT<:�[Y�gb����ޕc�   �QA�w����<��<�:�5��5?  �??�3B�)A4NS��w�� �+���A�w�«:�   �+�I4o@%���5��� ��v�ּ�Wi=��k�ӂ�;�j�$lh�x�� ����N��,   �QA������4��4�:�5��5?  �?0�3B�)A4NS����� �+����A���«:�   �+�I4o@%���5��� ���9u!��la�C׺f����{[�=`O�L ����tIj����   �QA����4¹5?�5?����� �?:4B7R+A4NS����� �+���A�w�«:�0   �{�"z�K�������03 -��o$�\�R+�������o��A�O�t����JR� ��}��G   �,����Tu�A        O�{=A�?οRA�A��A��������vA
�������Su�AT   �{�"z�K�������03 -��_����^`�f��i�
O�t����JR� ��}��G   3��!���Tu�A        �x�<��?�j�A:7A��A	���T�����vA�<����Su�A    �{�"z�K�������03 -��.n��\��)n�`�0�rҧO�t����JR� ��}��G   8����[��Tu�A        �~O�۫?�A�A��A��A	���u�����vAhH���E�Su�A(   �{�"z�K�������03 -� ӽ�������پN
�ط�O�t����JR� ��}��G   �4�h��Tu�A        ��s���?b-NA�'bA��A�J�u�����vA0��8U�Su�A   �{�"z�K�������03 -�+4D��c�+��k��vK&yO�t����JR� ��}��G   s'f­��Tu�A        @Wp=�?�cMA3�aA��AY�|�u�����vA�O��8U�Su�A   �{�"z�K�������03 -���1��*�d��P.)�z�Y/O�t����JR� ��}��G   Y�3��q��Tu�A              �?TU5A  H@��A�J�������vA�L�����Su�A   �{�"z�K�������03 .H�.E�㌰H)|V
ϗ�_"O�t����JR� ��}��G   �Lf��q��Tu�A              �?TU5A  H@��AY�|�������vA�O�����Su�A   �{�"z�K�������03 .���>T��֛#O�(�a�W�NO�t����JR� ��}��G   �S)�$.�Tu�A              �?(:�@n<�@��AZw5�@�X���vA0�	p�Su�A   �{�"z�K�������03 .�9�
�͘�ɋV���O�O�t����JR� ��}��G   ~�p�$.�Tu�A              �?���@n<�@��AY�|�@�X���vA��d�	p�Su�A   �{�"z�K�������03 .�|�Fh o|nȦ<�f�����O�t����JR� ��}��G   �������Tu�A        ��5=m�?���A��A��A�����>���vASF���u@Su�AT   �{�"z�K�������03 .�=�U�-�{u�a���<~`���O�t����JR� ��}��G   �M<��Tu�A        1�Z=��?e��Ax �A��A)��@�N���vA��²�u@Su�Ad   �{�"z�K�������03 /�F�A8[���2�x�S�����O�t����JR� ��}��G   �;�@ ��Tu�A�8A3b>�2o�z?&%K>��;B��fB  A��J���*ª�vA+B1��@Su�A�  �{�"z�K�������03 /䕊4R��!��@"O���qx�O�t����JR� ��}��G   �|AiEA�Tu�A        �72<�?N�B�vFA��A��իXª�vA�� B��)�Su�Al   ��md�@T��e�(>� 
����er��ٕ;�i[$l���}$uJ�q�NeȊq�`�1��   ���A2dBU��A2��0�{߱�p���z?[g@�\@UU�?����2�]B�ʽA����jB��A�   �-ٸ��@B���m]:� ����3'��){�w�_�p�[<�F�Lt��չa/g�rj�   ��
����D�AΆW�X.�   �-ٸ��@B���m]:� ��P���k!,[O��5��X�){[�=`O�L ����tIj����   �|�A��Y���q�        ��h�`�?ό�@��;?��AD�A'2^�����A}�T�X.�   ˄�9.AM�3�? �"� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   �[�A�z*� �        �U��  �?	�?��*> `�Bl��A��*� p!��q BF%*� PB   ˄�9.AM�3�? �"� ��FIxڑ';�co2E�$�O�Y�d{[�=`O�L ����tIj����   �U�A�/-� �        �X��  �?/ȱ?��*> `�Bz��AF�-� p!��q B��,� PB   ˄�9.AM�3�? �"� ��.lz��?P�ǒ�?���E{[�=`O�L ����tIj����   �y�AF�+� �        ��;�?�4>}? `�Bk��A��,� p!��(�A��*� PB   ˄�9.AM�3�? �"� �Ő��f07L6���	���{[�=`O�L ����tIj����   � BF�+� �              �?��*>��? `�B���A��,� p!��q B��*� PB   ��8�JK�������^ �ݐ�fd�#߅X�.=�!����{[�H�_����˖���dn`   �$����}z����N���Ƿ�={?	�D�VC�B_~C��?=����̃�[�����[�^c�B�*��*   ��8�JK�������^ �ݰu��&�44su�!-0�)�i|�-�6�QBڍ��a�1t   ��p��0��*��        n81�#|?�g�Bs]C  �?=����̃«*����[�^c�B�*��   ��8�JK�������^ ����p�h�u�����Ep\;���!�
+a�d��n�Kn:��e7   (j�^���*��        �3~>��w?+��B���B  �?����ı"«*����[��5A�*��   ��8�JK�������^ ���AJ�u�
+a�d��n�Kn:��e7   R;¬�P��*��        �ҽK�~?H�_B��0B  �?)�������*���,F���u@�*��   ��8�JK�������^ �k�H=��V��=&T��h���[�H�_����˖���dn`   �g��������O���ŷI{? �C��P�BO�C^�?=����̃¬
����a�^��B���%   ��8�JK�������^ �k��)�~M�u9�6%�yB�l.�|�-�6�QBڍ��a�1t   q� �
+a�d��n�Kn:��e7   wkr�����        ǁ>�w?ƅBX�B  �?�����1$������a��/A���   ��8�JK�������^ �~�AJ�u�
���:�^�B���   ��8�JK�������^ �~�"D�B�g������9|�-�6�QBڍ��a�1t   �z�?�B���        �<��?��]B�v�B  �?)��@����:�^�B���   ��8�JK�������^ �~*zyآ+�;�$~>�_��!�
+a�d��n�Kn:��e7   R;¬�P����        �ҽK�~?H�_B��0B  �?)����������,F���u@���   �4i70�D���ٲ�9,A e���f07L6���	���{[�=`O�L ����tIj����   $�A� w@Uu�A          �?      @@Z��=  �@$�AJrs@��vA$�A��z@Uu�A   �4i70�D���ٲ�9,A e(>��������;�Ra�$��}$uJ�q�NeȊq�`�1��   $�A���@U��A          �?      P@  �?  �@$�A�G�>��vA$�A�G�>Uu�A   �4i70�D���ٲ�9,A e�f��V]�I���ʪ����0����$P�����L��m�   $�A�i@U��A    :8  �?      P@k) ?] �@$�A�Y@��vA$�A�y@Uu�A<   �X��(@@ʌNXT �� ��TP�hs�9ȹ��V�
��@���        �\"�  �?xO"A
��@���        �"�  �?xO"Ao�>  ,ABE�B��u@��1��B�=�@�1�   �{��}Oޕ��
ї) İ��*k�5��Hq�88�����א�� �s�gtQ�#�e;$,�   7��B愃�ZUz��<4��5?@��8�A¸C @?O�BD�B��A݄�V5��n�B�,���?cA�   �{��}Oޕ��
ї) İ/M�s�֛%�����Y�;���{[�=`O�L ����tIj����   7��B焃�]Uz�T<4�y�5?I�p;��n�@ @?~ʊB�B��A݄�V5��n�B�,���?cA~   �{��}Oޕ��
ї) İ�������,����-�ɭG�N&KQ�!��(�!D����;�   ��B��ZUz�        �*�;d�?��S<��??��B�B݄�V5��n�B]���?cA   �{��}Oޕ��
ї) ı�ע� �
ї) ı�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    ��B�P�������J��s�?��;TU7A�?�?QA�B9j�¦�����5B�7��WG�   �{��}Oޕ��
ї) ı
ї) ı�`�z�t>P-�fx��-�_D���u	���B1������    ��BL������        d�?�;��1A��*=UU�@��B~��«����5Bc�¬jX�$  �{��}Oޕ��
ї) Ĳ�ע� �
ї) Ĳ�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    C�VBu��������J��s�?��;TU7A�?�?QAg�?B���¦����mB7u��WG�   �{��}Oޕ��
ї) Ĳ
ї) Ĳ�`�z�t>P-�fx��-�_D���u	���B1������    X�VB�Ã����        d�?�;��1A��*=UU�@_]@B �«���P�lB���¬jX�$  �{��}Oޕ��
ї) ĳ�ע� �
ї) ĳ�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    Y��B'��������J��s�?��;TU7A�?�?QA�"�Bm�¦�����B���WG�   �{��}Oޕ��
ї) ĳ
ї) ĳ�`�z�t>P-�fx��-�_D���u	���B1������    㙜B�0�����        d�?�;��1A��*=UU�@�y�B�S�«���๧BN
ї) Ĵ�ע� �
ї) Ĵ�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    �B�8�������J��s�?��;TU7A�?�?QA��B	R�¦���`�B���WG�   �{��}Oޕ��
ї) Ĵ
ї) Ĵ�`�z�t>P-�fx��-�_D���u	���B1������    }��Bn�����        d�?�;��1A��*=UU�@�j�BO��«���y��B�J�¬jX�$  �{��}Oޕ��
ї) ĸ�ע� �
ї) ĸ�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    ��B�P��h`����J��s�?��;TU7A�?�?QA�B9j��M;(���5B�7�¹��   �{��}Oޕ��
ї) ĸ
ї) ĸ�`�z�t>P-�fx��-�_D���u	���B1������    ��BL������        d�?�;��1A��*=UU�@��B~���W ��5Bc�±�5�$  �{��}Oޕ��
ї) Ĺ�ע� �
ї) Ĺ�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    C�VBu���h`����J��s�?��;TU7A�?�?QAg�?B����M;(��mB7u�¹��   �{��}Oޕ��
ї) Ĺ
ї) Ĺ�`�z�t>P-�fx��-�_D���u	���B1������    X�VB�Ã����        d�?�;��1A��*=UU�@_]@B ��W �P�lB���±�5�$  �{��}Oޕ��
ї) ĺ�ע� �
ї) ĺ�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    Y��B'���h`����J��s�?��;TU7A�?�?QA�"�Bm��M;(���B��¹��   �{��}Oޕ��
ї) ĺ
ї) ĺ�`�z�t>P-�fx��-�_D���u	���B1������    㙜B�0�����        d�?�;��1A��*=UU�@�y�B�S��W �๧BN
ї) Ļ�ע� �
ї) Ļ�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    �B�8��h`����J��s�?��;TU7A�?�?QA��B	R��M;(�`�B��¹��   �{��}Oޕ��
ї) Ļ
ї) Ļ�`�z�t>P-�fx��-�_D���u	���B1������    }��Bn�����        d�?�;��1A��*=UU�@�j�BO���W �y��B�J�±�5�$  �{��}Oޕ��
ї) Ŀ�ע� �
ї) Ŀ�ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    ��B�P����{@��J��s�?��;TU7A�?�?QA�B9j��>⾸�5B�7��SA   �{��}Oޕ��
ї) Ŀ
ї) Ŀ�`�z�t>P-�fx��-�_D���u	���B1������    ��BL��¥�i@        d�?�;��1A��*=UU�@��B~����=�5Bc����@$  �{��}Oޕ��
ї) ���ע� �
ї) ���ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    C�VBu�����{@��J��s�?��;TU7A�?�?QAg�?B����>��mB7u��SA   �{��}Oޕ��
ї) ��
ї) ���`�z�t>P-�fx��-�_D���u	���B1������    X�VB�Ã¥�i@        d�?�;��1A��*=UU�@_]@B ���=P�lB������@$  �{��}Oޕ��
ї) ���ע� �
ї) ���ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    Y��B'�����{@��J��s�?��;TU7A�?�?QA�"�Bm��>���B���SA   �{��}Oޕ��
ї) ��
ї) ���`�z�t>P-�fx��-�_D���u	���B1������    㙜B�0�¥�i@        d�?�;��1A��*=UU�@�y�B�S���=๧BN
ї) ���ע� �
ї) ���ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    �B�8����{@��J��s�?��;TU7A�?�?QA��B	R��>�`�B���SA   �{��}Oޕ��
ї) ��
ї) ���`�z�t>P-�fx��-�_D���u	���B1������    }��Bn�¥�i@        d�?�;��1A��*=UU�@�j�BO����=y��B�J����@$  �{��}Oޕ��
ї) �Ơ���Y>\��5!��b����k�c�V�6p��u|    /�B��¥�i@S3�߲6?t�2��
ї) ���ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    v�B�ă���{@S�lI��s�?��;��A�?�?QA��wB�ք�>⾖$�B²��SA   �{��}Oޕ��
ї) �Ɛ��f07L6���	���א�� �s�gtQ�#�e;$,�    �B΄�¥�i@        d�?�;��*?��? �@%F�BD���p�ʽ���BX���S��@   �{��}Oޕ��
ї) ��
ї) �Ǡ���Y>\��5!��b����k�c�V�6p��u|    .�B������S3�߲6?t�2��
ї) ���ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    u�B�ă�h`��S�lI��s�?��;��A�?�?QA��wB�ք�M;(��$�B²�¹��   �{��}Oޕ��
ї) �ǐ��f07L6���	���א�� �s�gtQ�#�e;$,�    �B΄�����        d�?�;��*?��? �@%F�BD����"����BX��� +�   �{��}Oޕ��
ї) ��
ї) �Ƞ���Y>\��5!��b����k�c�V�6p��u|    ,�B������S3�߲6?t�2��
ї) ���ܦT���h�ǖ�tY1��	4
BB��8\Sۥ	um��    r�B�ă����S�lI��s�?��;��A�?�?QA��wB�ք¦����$�B²��WG�   �{��}Oޕ��
ї) �Ȑ��f07L6���	���א�� �s�gtQ�#�e;$,�     �B΄�����        d�?�;��*?��? �@"F�BD�����ݟ�BX����U�   �{��}Oޕ��
ї) ��
ї) �L9�"O�׃L߀����a�^א�� �s�gtQ�#�e;$,�    (�B܂������	���	��5?�5?  �?\��B>�A���A܂�V� ��[�B܂�V���.   �{��}Oޕ��
ї) �L��0� L
��>9�-�(�����Ҥ'+�6����ŨD���R   X&�B\��������;�5��5?  �?���B��A���A\��V� X�B\��V���.   �{��}Oޕ��
ї) �LU�<���ƅ�\T�s��{[�=`O�L ����tIj����    (�B�������5?�5���e9D�e�� @?�m�B�+�A���A\��V� ��[�B܂�V���R   �{��}Oޕ��
ї) �M�ݿ<�L������:EɌ�}�}$uJ�q�NeȊq�`�1��    x��B�s}�6�����?8)��l997h#���bA�<A�L�AG�kB�� p!�$�Bpc�V���U$  �{��}Oޕ��
ї) �MN�4����'O�w���B�1��^*������5/���&9����    qb~Ba~�µ?��731�8_3?�P�;�>�F@��APVBG�mB��� p)�$�B�ƃ¬jC�   �{��}Oޕ��
ї) �N٧�P�e�+���`�G)S�]��}$uJ�q�NeȊq�`�1��    ?�B������?k㒷~�i�+l3<��9A�{?&��@��B�Ǆ� p!��6B܂���U  �{��}Oޕ��
ї) �N���f07L6���	��䬕��u	���B1������    ?�B���V��          �?GH'U�1A���<  �@��B��V� ��5Be��VE�  �{��}Oޕ��
ї) �O٧�P�e�+���`�G)S�]��}$uJ�q�NeȊq�`�1��    -�VB������?k㒷~�i�+l3<��9A�{?&��@�`?B�Ǆ� p!���mB܂���U  �{��}Oޕ��
ї) �O���f07L6���	��䬕��u	���B1������    -�VB���V��          �?GH'U�1A���<  �@�`@B��V� ���lBe��VE�  �{��}Oޕ��
ї) �P٧�P�e�+���`�G)S�]��}$uJ�q�NeȊq�`�1��    F��B������?k㒷~�i�+l3<��9A�{?&��@���B�Ǆ� p!2�B܂���U  �{��}Oޕ��
ї) �P���f07L6���	��䬕��u	���B1������    F��B���V��          �?GH'U�1A���<  �@�{�B��V� ��Be��VE�  �{��}Oޕ��
ї) �Q٧�P�e�+���`�G)S�]��}$uJ�q�NeȊq�`�1��    #��B������?k㒷~�i�+l3<��9A�{?&��@��B�Ǆ� p!�y#�B܂���U  �{��}Oޕ��
ї) �Q���f07L6���	��䬕��u	���B1������    $��B���V��          �?GH'U�1A���<  �@�l�B��V� �y��Be��VE�  �{��}Oޕ��
ї) �R�s�^�7���Gq֮8�ċ��}$uJ�q�NeȊq�`�1��    @�B">��������?�)��C�:2�W��':AT�?נ-A��B�«��6B܂�V����  �{��}Oޕ��
ї) �R�i�߱�����1��,,kr<���u	���B1������    ?�B��«J��          �?GH'U�1A���<  A��B�«����5Be�«
��  �{��}Oޕ��
ї) �S�s�^�7���Gq֮8�ċ��}$uJ�q�NeȊq�`�1��    .�VB">��������?�)��C�:2�W��':AT�?נ-A�`?B�«���mB܂�V����  �{��}Oޕ��
ї) �S�i�߱�����1��,,kr<���u	���B1������    -�VB��«J��          �?GH'U�1A���<  A�`@B�«�����lBe�«
��  �{��}Oޕ��
ї) �T�s�^�7���Gq֮8�ċ��}$uJ�q�NeȊq�`�1��    F��B">��������?�)��C�:2�W��':AT�?נ-A���B�«2�B܂�V����  �{��}Oޕ��
ї) �T�i�߱�����1��,,kr<���u	���B1������    F��B��«J��          �?GH'U�1A���<  A�{�B�«������Be�«
��  �{��}Oޕ��
ї) �U�s�^�7���Gq֮8�ċ��}$uJ�q�NeȊq�`�1��    $��B">��������?�)��C�:2�W��':AT�?נ-A��B�«�y#�B܂�V����  �{��}Oޕ��
ї) �U�i�߱�����1��,,kr<���u	���B1������    $��B��«J��          �?GH'U�1A���<  A�l�B�«���y��Be�«
��  ̓[�uH�~$q�*H< P4��fܯ�|��#lMz��UiO�t����JR� ��}��G   ��_�ϻ����A��,.x�.�x?E}>�-�B�H>B   A<A��'�"�UՅ@��[��5A��bA^  ̓[�uH�~$q�*H< P6x詘��p@��բ���"�$O�t����JR� ��}��G   ?���Z[����A@��\%5��=��+?���A� [A  A5����a��UՅ@�S��I̥���bA�   ̓[�uH�~$q�*H< Pm��>��)���%q�^���O�t����JR� ��}��G   7:z¨/����A        �x�zK}?�9�@%z�@   A)�¼���UՅ@,�r�؎����bA,   ͪ����B|�n�iw�� ����f07L6���	��䬣}$uJ�q�NeȊq�`�1��    !'A������          �?���&UB�>r?XU�>���]��®*����A�̃�XՀ�   �&�s^�F/�#W��>F� &w2� xb�c
��;�^��`�?πY>�A!��@�B/;&���Al�Bz�� �B   �&�s^�F/�#W��>F� &$h��:�<jE��G��b�f>�}$uJ�q�NeȊq�`�1��    �B���� B��;�>�=�~?�[1;,��>LA�@�	B%������A�Bzũ��:B|   �&�s^�F/�#W��>F� &$|��+�~Bg�J�Ԃ^~U����u	���B1������    ��Bm����RBG��<���;����=�?πY>�A!��@:sB�s����A�WBy�� �B   �&�s^�F/�#W��>F� &-w2� xb�c
��;�^��`�?πY>�A!��@��B^v����AJ�B�A� �B   �&�s^�F/�#W��>F� &6h��:�<jE��G��b�f>�}$uJ�q�NeȊq�`�1��    ��BF.� B��;�>�=�~?�[1;,��>LA�@��B�0�����A��B[��?�:B|   �&�s^�F/�#W��>F� &6|��+�~Bg�J�Ԃ^~U����u	���B1������    ��Bg�.��RBG��<���;����=�?πY>�A!��@>B������Aw"Bo�? �B   �&�s^�F/�#W��>F� &?w2� xb�c
��;�^��`�?πY>�A!��@ȐB�&�@��A(uB�QA �B   �&�s^�F/�#W��>F� &Hh��:�<jE��G��b�f>�}$uJ�q�NeȊq�`�1��    s�B07�A B��;�>�=�~?�[1;,��>LA�@p�B�g|A���Aw�B�:�A�:B|   �&�s^�F/�#W��>F� &H|��+�~Bg�J�Ԃ^~U����u	���B1������    ��B�/�A�RBG��<���;����=�?πY>�A!��@�B:A��AU�B���A �B   �&�s^�F/�#W��>F� &Qw2� xb�c
��;�^��`�?πY>�A!��@kGBn��A��A�RBlnB �B   �&�s^�F/�#W��>F� &_w2� xb�c
��;�^��`�?πY>�A!��@20B�����A�B��_� �B   ����c~Fȍ�Ji�` (Y�qF��� 2������U����[�H�_����˖���dn`   �n�����DZS��ŷrK{?)mC�A��BKsCz�?=����̃� P���g�^�B�:�%   ����c~Fȍ�Ji�` (Y�\���Z�ɽT[�e�l��!�
+a�d��n�Kn:��e7   �ItZ��:�        ��C�JG{?� C�O�B  �?=����̃«:���g�^�B�:�   �M�)��EY�|�+���w �m-��Ά�9
Kݾ_Uo��$ȳoe���n[��]��0�    �LA ����ʛA��<�?6:9:�=�8L�?�ʰ@T��@ƎEA9����?xA��OA
Kݾ_Uo��$ȳoe���n[��]��0�    fA�����ʛAp&.?�;?�_�9M:J�?�ʰ@T��@�ʾ@m����?xA�a7A�M��Uu�A  �M�)��EY�|�+���w ��G|.�Riw����}��(^*������5/���&9����    WOA������vA        \�?Gq����@���>  �?�ʾ@Fw����vA�a7A�M����vA   �M�)��EY�|�+���w ��pI�!���-^ݯ�]�E
A�j��Uu�A  �M�)��EY�|�+���w ��S�IG�ّ��#�r
����^*������5/���&9����    ���@�3����vA        ��c?�;�>���@���>  �?W�@�V©�vA�(A������vA   �M�)��EY�|�+���w ��pI�!���-^ݯ�]�E
����^*������5/���&9����    c1dA�����vA        �?��F=���@���>  �?98Ao	����vA:)�AnǠ���vA   �M�)��EY�|�+���w ��pI�!���-^ݯ�]�E
���?��
����^*������5/���&9����    �GA��6���vA        ,�=?,?���@���>  �?|�AA��b���vA�NAh�
���vA   �M�)��EY�|�+���w ��pI�!���-^ݯ�]�E
,?���@Ņ�=UU�@��CA�
b��?xA�.LAΡ�Uu�A$  �tL�KqJ��ڿ��Fq � Y�ڊ�;�"�_a���3JC�{[�=`O�L ����tIj����   �"�A8-���A        H��<�?T�AD�@��+A��:A%�/�UՅ@4��A�*�R�nA   �tL�KqJ��ڿ��Fq �4���8	`�*!�$�}K	\�{[�=`O�L ����tIj����   ��FA��0©*�@        I�2���?Ml2A�I@���@��@Fp3�UՅ@�x�A2�-��?+A   �tL�KqJ��ڿ��Fq �Q���#�Ћ�\�vg~]��\{[�=`O�L ����tIj����   i��@/�L©*�@        ��y:��?>;�>��@���@�S�@�T�UՅ@��@I�D��?+A   �tL�KqJ��ڿ��Fq ���'�5w��U����z��6G�{[�=`O�L ����tIj����   U
+a�d��n�Kn:��e7   5�B# �� p1�        hM=��?�Y�B�0�B  �?�(B܂� p1��B��fA p1�   Ҡ�`�VEߴ�9��Ӿe 
�+�(������ְ�P��M�   ?a�l!YªʲA   ?   ?   ?   ���*>��*>TsU?��-�S�Z���A���vW�Uu�A
   ұ/`�C`�&R�;̣t ��6�l���c�r��f��r��+�(������ְ�P��M�   ?a�nPªʲA   ?   ?   ?   ���*>��*>
   ұ/`�C`�&R�;̣t 𿐤�f07L6���	����+�(������ְ�P��M�   ?a�d�.ªʲA   ?   ?   ?   ���*>��*> ��@��-�F;7���A����&�Uu�A   ұ/`�C`�&R�;̣t �����f07L6���	����+�(������ְ�P��M�   ?a�}P@ªʲA   ?   ?   ?   ���*>��*>˨�@��-�
�H���A����7�Uu�A   ұ/`�C`�&R�;̣t �Ȳ�6�l���c�r��f��r��+�(������ְ�P��M�   ?a��![�Ƒ�A        �5��5?��*>��*>�8@��-��v[�8��A��S�Z�Uu�A
   ұ/`�C`�&R�;̣t ��0]�����!E�U�=7O(
�+�(������ְ�P��M�   ?a��![�T�yA        �5��5?��*>��*>���>��-��v[©�vA��S�Z��?|A
   ұ/`�C`�&R�;̣t �β�6�l���c�r��f��r��+�(������ְ�P��M�   ?a�_I��X�A�5?�5?        ��*>��*>��@��-��eI�T�}A��
�H��A
   ұ/`�C`�&R�;̣t �ϐ��f07L6���	����+�(������ְ�P��M�   ?a�_I©�xA�5?�5?        ��*>��*>��>��-��eI©�vA��
�H©�zA   ұ/`�C`�&R�;̣t �ײ�6�l���c�r��f��r��+�(������ְ�P��M�   ?a���7�T�yA�5?�5?        ��*>��*>���>��-�F;8©�vA����7��?|A
   ұ/`�C`�&R�;̣t ��-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ?a���7�A�5?�5?        ��*>��*>�8@����7��?|A~°�F;7��A
   ұ/`�C`�&R�;̣t �K���f07L6���	��䬕��u	���B1������   ���}P@��A        �5?�5?ʨ�@���=9�@@a(�
�H�8��A����7���A  ұ/`�C`�&R�;̣t �L���f07L6���	��䬕��u	���B1������   ���d�.��A        �5?�5?��@���=9�@@a(�F;7�8��A����&���A  ұ/`�C`�&R�;̣t �[-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ?a��![ªʘA        �5��5?��*>��*>�8@��-��v[��A��S�Z�8��A
�+�(������ְ�P��M�   ?a�_I�Ƒ�A�5?�5?        ��*>��*>�8@���eI�8��A~°�
�H�Uu�A
   ұ/`�C`�&R�;̣t �]0]�����!E�U�=7O(
�+�(������ְ�P��M�   ?a���7�Ƒ�A�5?�5?        ��*>��*>�8@����7�8��A~°�F;7�Uu�A
   ұ/`�C`�&R�;̣t �^0]�����!E�U�=7O(
�+�(������ְ�P��M�   ?a�,f&�Ƒ�A�5?�5?        ��*>��*>�8@��,f&�8��A~°���%�Uu�A
   ұ/`�C`�&R�;̣t 񋐤�f07L6���	��䬕��u	���B1������   ���}P@ªʘA        �5?�5?ʨ�@���=�8@@a(�
�H��A����7�8��A  ұ/`�C`�&R�;̣t 񌐤�f07L6���	��䬕��u	���B1������   ���d�.ªʘA        �5?�5?��@���=�8@@a(�F;7��A����&�8��A  ұ/`�C`�&R�;̣t �-}Z�}Jj�(֦߄���7�1�+�(������ְ�P��M�   ?a�_IªʘA�5?�5?        ��*>��*>�8@���eI��A~°�
�H�8��A
�H��X�A�k	���7�A   ұ/`�C`�&R�;̣t �֐��f07L6���	����+�(������ְ�P��M�   ��d�.��A   ?   ?   ?   ����=  �< ��@�
�H�Ƒ�A�k	���7�q<�A   �;�L��
|B_�@��>�b�B͵bA�?"A   �;�L��
�2 	��%�Vc�k)z_K��a!><n�}$uJ�q�NeȊq�`�1��   	����jqvB �Ax�:w���5��5?���@4��>�J@z����SgB��vA%8��uǂB�ʔA<   ӤO&GpL؁$ṷ
�2 	�K}��b�o3M �RZ_?�D�1�}$uJ�q�NeȊq�`�1��   	���5)B��Ah�T:�5{9��?��R��>�
�2 	�a��7��q$��K͆Ayk���}$uJ�q�NeȊq�`�1��   	F����GB��A��T:ǉ}���? ��7���>Z��@G�J@�����8B��vA�g���:VB�ʔA<   ӤO&GpL؁$ṷ
�2 	�w�,ɪ(����%��0��W�}$uJ�q�NeȊq�`�1��   	e��¾@�A �Ax��w���5?�5?���@4��>�J@��¾�A��vA�g�¾{�A�ʔA<   ӤO&GpL؁$ṷ
�2 	���%�Vc�k)z_K��a!><n�}$uJ�q�NeȊq�`�1��   	e���B �Ax�:w���5��5?���@4��>�J@�����A��vA�g�"B�ʔA<   ӤO&GpL؁$ṷ
�2 	���%�Vc�k)z_K��a!><n�}$uJ�q�NeȊq�`�1��   	e���,zA �Ax�:w���5��5?���@4��>�J@���-�=A��vA�g��>�A�ʔA<   ӭ�Cr��_�͍4� t�#�[c;|�8�K6����9�	�ޞ�2��r`<\�{�E   ց����3¬
���A��A�>��{�?� >Psp?4-JA K���#4� ��5
�@��3�V5���  ӭ�Cr��_�͍4� ��#�[c;|�8�K6����9�	�ޞ�2��r`<\�{�E   ׁ���xT�`���A���@��'�?g�?� >Fsp?3-JA K��ٸT�V5��5
�@�8T¬����  �$"�uFA]���6# u���2�T��[��Y�x�0����$P�����L��m�   wԮ��@$©�xA        80?"�9?\F\A��*>  �>����?©�vAg��^�©�zA   �$"�uFA]���6# ul���2�T��[��Y�x�0����$P�����L��m�   1���`����xA        80?"�9? �IA��*>  �>����aK����vA�߫¿*g���zA   �$"�uFA]���6# u����2�T��[��Y�x�0����$P�����L��m�   Z���.-༩�xA        80?"�9?��hA��*>  �>�t�������vA���¶��@��zA   �)Bn�Li�sK�x텫 C(���2�T��[��Y�x{[�=`O�L ����tIj����   ��=�/`
���f07L6���	���r��(;�{p9DC}�\ə�   3ԔB�K��mUA�        d�?�;N�A���>  @?�R�BS��������U�BB���۪¾   ��r�WC������Y ����f07L6���	���r��(;�{p9DC}�\ə�   �hB�*��mUA�        d�?�;�.�A���>  @?Q�GB8��������T�B4���۪¾   ��r�WC������Y ����f07L6���	���r��(;�{p9DC}�\ə�   +�%B��mUA�        d�?�;�Z�A���>  @?�aB*���������GB�r��۪¾   ��r�WC������Y �
��۪¾   ��r�WC������Y ����f07L6���	���r��(;�{p9DC}�\ə�   �&Bɹ��mUA�        d�?�;�Z�A���>  @?~#B�������THB\i��۪¾   ��r�WC������Y ����f07L6���	���r��(;�{p9DC}�\ə�   �MuB�;�mUA�        �<4?�5?�,9A  ?  @?�tB��R·���̀vB}d$�۪¾   ��r�WC������Y ����f07L6���	���r��(;�{p9DC}�\ə�   �{�B#�;�mUA�        �<4?�5?�,9A  ?  @?.�B�S·���5�B��$�۪¾   �u�xu&D}�c�K�vu% ��#��������v��yvK��,\{[�=`O�L ����tIj����   �
��{[�=`O�L ����tIj����   ǻL¦�3@Uu�A        t��  �?��AE�*>���?
��{[�=`O�L ����tIj����   �kL�� ��Uu�A        ����  �?�-�AD�*>���?Y�|��� ���A���Dv�����A   �u�xu&D}�c�K�vu% ��v� TW�߂G��'�/
��{[�=`O�L ����tIj����   oL���
�Uu�A        ����  �?!�AR�*>���?Y�|�"7���A���w�	����A   �u�xu&D}�c�K�vu% ��t/���$0�x0"��Ht<Ys{[�=`O�L ����tIj����   ��L���zu�A�5?�5?�iL9��M9��*>e�Aj\�?Y�|.����A�E�Fٚ����A"   �u�xu&D}�c�K�vu% ��!�)�a����/|��Ss�{[�=`O�L ����tIj����   ��L,��Yu�A�5?�5?�]�8RW�8d�*>��AL9�?Y�|�Fס���A��������A    �u�xu&D}�c�K�vu% � @���E0��H��X�h;��{[�=`O�L ����tIj����   u�����Uu�A�5?�5�d֪���8��*>�O�A�f�?�.����A��Y�Fٚ����A$   �u�xu&D}�c�K�vu% �@���E0��H��X�h;��{[�=`O�L ����tIj����   ����,��Uu�A�5?�5�H������8��*>�O�A�f�?�#�Fס���A��Y������A$   �u�xu&D}�c�K�vu% �
��Y^u+>��'�x��mT{[�=`O�L ����tIj����   ����� ��Uu�A         �  �?��A��*>���?�
�Uu�A        L�  �? O�A��*>���?���"7���A1\X�w�	����A    �u�xu&D}�c�K�vu% ���Y^u+>��'�x��mT{[�=`O�L ����tIj����   0	����`@Uu�A        T'�  �?��A��*>���?`�¦�[@��A@�U�PLf@���A   �u�xu&D}�c�K�vu% ���Y^u+>��'�x��mT{[�=`O�L ����tIj����   �����3@Uu�A        +�  �?��A��*>���?���P\.@��A5�U��9@���A   �u�xu&D}�c�K�vu% �W��
)A���?Պ������A���P\.@���A   �`|�v~H'�F�Ӟ��f #�N��O�5P;_�4�R��&>`]O�t����JR� ��}��G   �Kq�r2�� p�        �6�_�{?��B=C   A�%�g�� p1#t�	^�B p	�   �`|�v~H'�F�Ӟ��f %�RѢF�n���m�4o��]��	O�t����JR� ��}��G   �A���A p�        )�9��?5RB+ԿB   A��N��� p1FA�	�B p	�    �`|�v~H'�F�Ӟ��f +̣h{��E�k�� �M��O�t����JR� ��}��G   �!�B���� p�        N�<��?PC�B룣B   A��B܂� p1�R��BM`A p	�(   �`|�v~H'�F�Ӟ��f +��a2'��=���n��&u����O�t����JR� ��}��G   �\B�!A p�        ��;��?�SqAt��@   A��=B3��@ p1*zBW,^A p	�   ��҄[N���P0e� ����tݖ���5�2��B�A{[�=`O�L ����tIj����   J^C��	XBUu�A        [�;d�?:0�>�`�@���?@)E���JB��AS�A�Z_eB���A   ��҄[N���P0e� ���H��H�"Un5�c�܊n�E#�{[�=`O�L ����tIj����   �FQ�i0BUu�A        J2�;d�?k\�>,z>A���?�mS�2AB��ABO���GB���A   ��҄[N���P0e� �NT��T��[�+����ӡ��{[�=`O�L ����tIj����   ��R���AUu�A        97�;d�?��>�*A���?�U����A��A�P�2�B���A   ��҄[N���P0e� �0+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   R�T��AUu�A        W7�;d�?o�>�)A���?ИV�MqA��A�wR����A���A   ��҄[N���P0e� �M+�u`�=&Q��0�B£�n<{[�=`O�L ����tIj����   sV�rAUu�A        �6�;d�?/�>�)A���?�-X�PLf@��A�T�QcA���A   ��҄[N���P0e� �nܾ����.*���/��!<�{[�=`O�L ����tIj����   ��W�H%�Uu�A        P7�;d�?���>A�)A���?@�Y�Dv����A�U�P\.@���A   ��҄[N���P0e� ���[�"���=n�sp`E�a��
�{[�=`O�L ����tIj����   GrZ���`�Uu�A7�;b�?�:ġ)6��*>/�)A�1�?|�\�Fٚ���AbX�"7����A   ��҄[N���P0e� ��`�����']��]Vs�oa�{[�=`O�L ����tIj����   �[�C	��Uu�A        h>�;d�?fb�>��A���?e�]�?;����A��Y�Fס����A   ��҄[N���P0e� ��;����� ���ކu�p�#a�4{[�=`O�L ����tIj����   ��}�=F%�Uu�A*)9          �? �*>]�)A��?
/�B���A   ��҄[N���P0e� �Ȃ�=O��X@L��cy�{[�=`O�L ����tIj����   [D���;BUu�A              �? �*>�R}A���?o�¯�B��A���U:[B���A   �E��E��b?`�{  
z��er��ٕ;�i[$l���}$uJ�q�NeȊq�`�1��   ����sv�B���A��p�}�ñd.@�U)?[g@�\@UU�?�D�� �|B�˽A.���e[�B@!�A�   ُS�?�K.��Π9� � O ��5-��+�c����d|6�O�t����JR� ��}��G   �������A��A              �?��$AXU�@   AI��$7�AUՅ@�S��=�B��bA   ُS�?�K.��Π9� � O^���k��?E�#��h�s�O�t����JR� ��}��G   �����pB��A              �?��$A   A   AI���pBUՅ@�S���p$B��bA   ُS�?�K.��Π9� � O������
0V�Xk)��&u���W�>O�t����JR� ��}��G   d��=�&B��A        �J�;�?n�A1��A   A�6��5BUՅ@�U5��4GB��bA    ُS�?�K.��Π9� � O��AEu����f�I��Q�O�t����JR� ��}��G   ӝ�A�A��A        '���f�?)c�@�+A   A���ANfv@UՅ@��Bq�gA��bA    ُS�?�K.��Π9� � OAB�
�ط�O�t����JR� ��}��G   �4�h����A        ��s���?b-NA�'bA   A�J�u���UՅ@0��8U���bA   ُS�?�K.��Π9� � Oo�qW�BL�U�fF���L�j�O�t����JR� ��}��G   �S)�$.���A              �?(:�@n<�@   AZw5�@�X�UՅ@0�	p���bA   ُS�?�K.��Π9� � O��1��*�d��P.)�z�Y/O�t����JR� ��}��G   Y�3��q����A              �?TU5A  H@   A�J�����UՅ@�L�������bA   ُS�?�K.��Π9� � OH�.E�㌰H)|V
ϗ�_"O�t����JR� ��}��G   �Lf��q����A              �?TU5A  H@   AY�|�����UՅ@�O�������bA   ُS�?�K.��Π9� � O +4D��c�+��k��vK&yO�t����JR� ��}��G   s'f­����A        @Wp=�?�cMA4�aA   AY�|�u���UՅ@�O��8U���bA   ُS�?�K.��Π9� � O"�9�
�͘�ɋV���O�O�t����JR� ��}��G   ~�p�$.���A              �?���@n<�@   AY�|�@�X�UՅ@��d�	p���bA   ���6%G{���~�U� 	i��	��|G���Q�
��bE�Ee>@r�
��
��
vyE�Ee>@r�
��   ���6%G{���~�U� 	j`N���b�j�#;��NMl�@��{[�=`O�L ����tIj����   ��%Aʨ��V�����<��?��U��'0�[�>�BUգA�fA��+� p!§�-A�?��
��   ���6%G{���~�U� 	j��I�M��h��9	x�K���E�Ee>@r�
��   ���6%G{���~�U� 	j�~�4��T�:�/5d�{���'v{[�=`O�L ����tIj����   ���A����h��K)D= *D���4�^�4?
��   ���6%G{���~�U� 	j�JN��[>g&�p�i���E�Ee>@r�
��   ���6%G{���~�U� 	jٝr����=F'*�
��   ���6%G{���~�U� 	kAF�Cؚ�p��T��tB���E�Ee>@r�
��   ���6%G{���~�U� 	kA<>N��L�%$$�{�_���{[�=`O�L ����tIj����   IVIA'��V���wI<��L�l�6��g3?�U�>n՞@>�A
��   ���6%G{���~�U� 	kW
��   ���6%G{���~�U� 	kW��[�M�� �rU���q!{[�=`O�L ����tIj����   E�DA1�V���        :�<��?�v@��?UգA=&A��� p!�M�cA�
��   ���6%G{���~�U� 	k���g?{�1����`����E�Ee>@r�
��   ���6%G{���~�U� 	k&V�R�
��<��l���5{[�=`O�L ����tIj����   `?kA�!��V�����
��C��vY�>lj�A<
�A�dA~��� p!£�qA�?��
��   ��o'A8��� YH� �␤�f07L6���	���r��(;�{p9DC}�\ə�   W���ͪnBOUR@�A�&�A�&�5?�5?�@A���>  @?Wz��ݎVBOU:@Wz��^c�BOUj@   ��o'A8��� YH� �㐤�f07L6���	���r��(;�{p9DC}�\ə�   W���2d;BOUR@�A���A�&�5��5?��?A���>  @?Wz��(�"BOU:@Wz��'�RBOUj@   ��o'A8��� YH� �䐤�f07L6���	���r��(;�{p9DC}�\ə�   W��®BOUR@�A���A�&�5��5?�nAA���>  @?Wz�©��AOU:@Wz�9 BOUj@   ��o'A8��� YH� �吤�f07L6���	���r��(;�{p9DC}�\ə�   W���w�AOUR@�A���A�&�5��5?pAA���>  @?Wz��5�qAOU:@Wz��Sf�AOUj@   ��o'A8��� YH� �搤�f07L6���	���r��(;�{p9DC}�\ə�   W�� 5AOUR@�A���A�&�5��5?ҡAA���>  @?Wz��ܒ
?ŧ��NB��@�/��4�[BPU:@   ��o'A8��� YH� ���C��1�5g]�W�FJ�=vKȀ���z�/[%�n��^��Mӆ    W�����!B��(@        �5��5?��^@��J?��
@5N