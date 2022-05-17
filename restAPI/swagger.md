
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



```
none
```


***Status Code:*** 200

<br>



### 5. /modeldata/:modelID/history


Returns history of all changes for a given model.

The request payload consists of an array of specific "timestamps" to look for. If no specific timestamps are listed, then you can specify a range via the "min" and "max" fields.

If the "includeChanges" flag is set to true it will return extra information about the nature of the change, a possible description, and the identifier of the element changed.

Timestamps are specified using: milliseconds since the UNIX epoch.

*NOTE: there are no shortcuts for specifying the min/max values. For instance, you cannot omit the max value to get the current time. You must pass in valid timestamps for both min and max.*


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{TandemBaseURL}}/modeldata/:modelID/history
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) ID of the twin |



***Body:***

```js        
{
    "timestamps": [1642622292740, 1642622224147],
    "includeChanges": true
}
```



***More example Requests/Responses:***


#### I. Example Request: OK - 30 days, includeChanges=true


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) ID of the twin |



***Body:***

```js        
{
    "timestamps": [],
    "min": 1639987200000,
    "max": 1642665599999,
    "includeChanges": true
}
```



#### I. Example Response: OK - 30 days, includeChanges=true
```js
[
    {
        "t": 1642622292740,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "eSelem67SMmRIHH6JgautgAD7RM"
        ]
    },
    {
        "t": 1642622224147,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642622021073,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642621942845,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "eSelem67SMmRIHH6JgautgAD7RM"
        ]
    },
    {
        "t": 1642621815827,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642621773777,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642620798449,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642620729258,
        "c": "qGQp6HR6IRjSTPebAPYSC9DSzne8NEYS",
        "n": "James Awe",
        "o": "mutate",
        "d": "WO_Tandem App Update",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642620480389,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642620315244,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642620221681,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    },
    {
        "t": 1642619960300,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    }
]
```


***Status Code:*** 200

<br>



#### II. Example Request: OK - 30 days, includeChanges=false


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) ID of the twin |



***Body:***

```js        
{
    "timestamps": [],
    "min": 1639987200000,
    "max": 1642665599999,
    "includeChanges": false
}
```



#### II. Example Response: OK - 30 days, includeChanges=false
```js
[
    {
        "t": 1642622292740,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642622224147,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642622021073,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642621942845,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642621815827,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642621773777,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642620798449,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642620729258,
        "c": "qGQp6HR6IRjSTPebAPYSC9DSzne8NEYS",
        "n": "James Awe"
    },
    {
        "t": 1642620480389,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642620315244,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642620221681,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    },
    {
        "t": 1642619960300,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe"
    }
]
```


***Status Code:*** 200

<br>



#### III. Example Request: OK - with specific timestamps


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) ID of the twin |



***Body:***

```js        
{
    "timestamps": [1642622292740, 1642622224147],
    "includeChanges": true
}
```



#### III. Example Response: OK - with specific timestamps
```js
[
    {
        "t": 1642622292740,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "eSelem67SMmRIHH6JgautgAD7RM"
        ]
    },
    {
        "t": 1642622224147,
        "c": "G74mtwnvTkdyksNUqHTyCEefXORn1Lnh",
        "n": "James Awe",
        "o": "mutate",
        "d": "",
        "k": [
            "ricOExIyRIyTke1_49OlKgAD-WQ"
        ]
    }
]
```


***Status Code:*** 200

<br>



### 6. /modeldata/:modelID/model


Returns Forge Viewer-related information such as the camera definitions, reference point transformations, bounding box, north and up vectors, etc.

This information is used by the Forge Viewer to render the 3D geometry and is not very useful in the pure REST context.


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/modeldata/:modelID/model
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
    "cameras": [
        {
            "aspect": 1.0785232782363892,
            "fov": 0,
            "isPerspective": false,
            "orthoScale": 308.75335693359375,
            "position": {
                "x": 177.00845336914062,
                "y": -176.81759643554688,
                "z": 218.61822509765625
            },
            "target": {
                "x": -1.2503929138183594,
                "y": 1.4412460327148438,
                "z": 40.359375
            },
            "up": {
                "x": -0.408248290463863,
                "y": 0.408248290463863,
                "z": 0.816496580927726
            }
        }
    ],
    "custom values": {
        "angleToTrueNorth": 0,
        "refPointTransform": [
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
    "default camera": {
        "index": 0
    },
    "distance unit": {
        "value": "foot"
    },
    "double sided geometry": {
        "value": false
    },
    "fragmentTransformsOffset": {
        "x": -1.2503947132524118,
        "y": 3.9348150233566628,
        "z": 40.359376430511475
    },
    "georeference": {
        "positionLL84": [
            -71.033,
            42.213,
            0
        ]
    },
    "name": "OTG Model Root",
    "navigation hint": {
        "value": "Turntable"
    },
    "stats": {
        "num_fragments": 8314,
        "num_geoms": 1210,
        "num_materials": 68,
        "num_polys": 3132543,
        "num_textures": 0
    },
    "version": 1,
    "view to model transform": {
        "type": 4
    },
    "world bounding box": {
        "maxXYZ": [
            101.66738831495942,
            76.03270351107649,
            90.42708587646484
        ],
        "minXYZ": [
            -104.16817774146425,
            -68.16307346436317,
            -9.708333015441895
        ]
    },
    "world front vector": {
        "XYZ": [
            0,
            -1,
            0
        ]
    },
    "world north vector": {
        "XYZ": [
            0,
            1,
            0
        ]
    },
    "world up vector": {
        "XYZ": [
            0,
            0,
            1
        ]
    }
}
```


***Status Code:*** 200

<br>



### 7. /modeldata/:modelID/mutate


The /mutate endpoint is used to update property values in the Tandem database. It is currently designed to be efficient for bulk updates from the Tandem client app and is therefore somewhat cryptic. It takes several arguments of arrays that are expected to match in length:

*   "keys:" is an array of element IDs to change.
*   "muts:" is an array of matching mutations for each of the elements listed in "keys:". each entry in the "muts:" array has the following:
    *   operation: "i" indicates that this is an insert/update operation on the database, or "d" indicates that this is a delete operation on the database.
    *   column family: "z" indicates that this is a user-defined property (Column Family)
    *   column name: "xyz" is the identifier for that user-defined property
    *   value: "new value" is the new value for this property
*   "desc": is an optional string that can be used to tell the Change History mechanism where/why these changes were made. In our examples, we will use "Updated from Postman" to show that it was not the Tandem product that updated the value.
    

NOTE: there are other Column Family specifiers that can be used, but most are read-only properties and are reserved for internal use. API users will probably ONLY use "i" and "z" for the first two arguments of the "muts" array.

*NOTE: /mutate works on a per-model basis, so if you have 3 models loaded and have elements from each model you want to change properties for, you need to call it 3 separate times.*

See the examples of POST /mutate to see how the body of the request changes under these various conditions.

For more examples of the /mutate endpoint, see these notes: [https://autodesk-tandem.github.io/API_mutate.html](https://autodesk-tandem.github.io/API_mutate.html)


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{TandemBaseURL}}/modeldata/:modelID/mutate
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AQAAAHknpXpuu0jJkSBx-iYGrrYAA-0T"
    ],
    "muts": [
        [
            "i",
            "n",
            "!n",
            "Type prop change 99"
        ]
    ]
}
```



***More example Requests/Responses:***


#### I. Example Request: OK - Update "Common | Name" property to new value


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AAAAAK4nDhMSMkSMk5Htf-PTpSoAA_lk"
    ],
    "muts": [
        [
            "i",
            "n",
            "!n",
            "RandomName_112"
        ]
    ],
    "desc": "Updated from Postman"
}
```



#### I. Example Response: OK - Update "Common | Name" property to new value
```js
{
    "timestamp": 1644883459264
}
```


***Status Code:*** 200

<br>



#### II. Example Request: OK - Update user-defined property to new value


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AAAAAK4nDhMSMkSMk5Htf-PTpSoAA_lk"
    ],
    "muts": [
        [
            "i",
            "z",
            "zAc",
            "value XYZ"
        ]
    ],
    "desc": "Updated from Postman"
}
```



#### II. Example Response: OK - Update user-defined property to new value
```js
{
    "timestamp": 1644883682673
}
```


***Status Code:*** 200

<br>



#### III. Example Request: OK - Update single property, multiple elements


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AAAAAATEUWm2ZEeev3txuY9_YQsAA_sz",
        "AAAAAK4nDhMSMkSMk5Htf-PTpSoAA_lk"
    ],
    "muts": [
        [
            "i",
            "z",
            "zAc",
            "New string value A"
        ],
        [
            "i",
            "z",
            "zAc",
            "New string value B"
        ]
    ],
    "desc": "Updated from Postman"
}
```



#### III. Example Response: OK - Update single property, multiple elements
```js
{
    "timestamp": 1644884236216
}
```


***Status Code:*** 200

<br>



#### IV. Example Request: OK - Update different properties, different elements


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AAAAAATEUWm2ZEeev3txuY9_YQsAA_sz",
        "AAAAAK4nDhMSMkSMk5Htf-PTpSoAA_lk"
    ],
    "muts": [
        [
            "i",
            "z",
            "zAc",
            "New string value A"
        ],
        [
            "i",
            "z",
            "zQc",
            9876.99
        ]
    ],
    "desc": "Updated from Postman"
}
```



#### IV. Example Response: OK - Update different properties, different elements
```js
{
    "timestamp": 1644884422960
}
```


***Status Code:*** 200

<br>



#### V. Example Request: OK - Delete a property from a given element


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AAAAACSELi_hCUJBrw7O42GpkVgABEnp"
    ],
    "muts": [
        [
            "d",
            "z",
            "zQc"
        ]
    ],
    "desc": "Updated from Postman"
}
```



#### V. Example Response: OK - Delete a property from a given element
```js
{
    "timestamp": 1644974202579
}
```


***Status Code:*** 200

<br>



#### VI. Example Request: OK - Add Classification to an element


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AAAAAKljBWwVbUezt0cIIJETKaAAA9pl"
    ],
    "muts": [
        [
            "i",
            "n",
            "!v",
            "03 00 00"
        ]
    ]
}
```



#### VI. Example Response: OK - Add Classification to an element
```js
{
    "timestamp": 1645552120743
}
```


***Status Code:*** 200

<br>



#### VII. Example Request: OK - Update multiple properties, same element


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AAAAAK4nDhMSMkSMk5Htf-PTpSoAA_lk",
        "AAAAAK4nDhMSMkSMk5Htf-PTpSoAA_lk"
    ],
    "muts": [
        [
            "i",
            "z",
            "zAc",
            "New string value A"
        ],
        [
            "i",
            "z",
            "zQc",
            9876.99
        ]
    ],
    "desc": "Updated from Postman"
}
```



#### VII. Example Response: OK - Update multiple properties, same element
```js
{
    "timestamp": 1645554126017
}
```


***Status Code:*** 200

<br>



#### VIII. Example Request: OK - Delete multiple properties, same entity


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) Model URN you want to update elements for |



***Body:***

```js        
{
    "keys": [
        "AAAAACSELi_hCUJBrw7O42GpkVgABEnp",
        "AAAAACSELi_hCUJBrw7O42GpkVgABEnp"
    ],
    "muts": [
        [
            "d",
            "z",
            "zAc"
        ],
        [
            "d",
            "z",
            "zQc"
        ]
    ],
    "desc": "Updated from Postman"
}
```



#### VIII. Example Response: OK - Delete multiple properties, same entity
```js
{
    "timestamp": 1645570707722
}
```


***Status Code:*** 200

<br>



### 8. /modeldata/:modelID/props/:elementID



***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/modeldata/:modelID/props/:elementID
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} |  |
| elementID | AAAAAK4nDhMSMkSMk5Htf-PTpSoAA_lk |  |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} |  |
| elementID | AAAAAK4nDhMSMkSMk5Htf-PTpSoAA_lk |  |



***Body: None***



#### I. Example Response: OK
```js
{
    "key": "ricOExIyRIyTke1_49OlKgAD-WQ",
    "data": [
        {
            "c": "r:-AI",
            "v": "BLDG 4 - EastWall - Ground to Roof",
            "t": 0
        },
        {
            "c": "r:-AQ",
            "v": 0,
            "t": 0
        },
        {
            "c": "r:0AI",
            "v": "",
            "t": 0
        },
        {
            "c": "r:0AY",
            "v": 4145.164591038102,
            "t": 0
        },
        {
            "c": "r:2wY",
            "v": "Up to level: T.O. ROOF BLDG 4",
            "t": 0
        },
        {
            "c": "r:3wI",
            "v": "Vertical",
            "t": 0
        },
        {
            "c": "r:4gI",
            "v": 3454.3038258651127,
            "t": 0
        },
        {
            "c": "r:7wM",
            "v": "Bearing",
            "t": 0
        },
        {
            "c": "r:8QQ",
            "v": "All-Ground Level",
            "t": 0
        },
        {
            "c": "r:8gI",
            "v": "New Construction",
            "t": 0
        },
        {
            "c": "r:8gU",
            "v": "Revit Walls",
            "t": 0
        },
        {
            "c": "r:LQ",
            "v": "",
            "t": 0
        },
        {
            "c": "r:Rg",
            "v": "",
            "t": 0
        },
        {
            "c": "r:ZQ",
            "v": 0,
            "t": 0
        },
        {
            "c": "r:_gE",
            "v": 0,
            "t": 0
        },
        {
            "c": "r:jQM",
            "v": 0,
            "t": 0
        },
        {
            "c": "r:jwE",
            "v": 0,
            "t": 0
        },
        {
            "c": "r:kwI",
            "v": "260452",
            "t": 0
        },
        {
            "c": "r:lgE",
            "v": 51.583333333333336,
            "t": 0
        },
        {
            "c": "r:lwY",
            "v": 0,
            "t": 0
        },
        {
            "c": "r:mgE",
            "v": "Finish Face: Exterior",
            "t": 0
        },
        {
            "c": "r:mwE",
            "v": 0,
            "t": 0
        },
        {
            "c": "r:pAE",
            "v": "Rebar Cover 1 <0' - 1\">",
            "t": 0
        },
        {
            "c": "r:pgU",
            "v": 1,
            "t": 0
        },
        {
            "c": "r:pwU",
            "v": "Rebar Cover 1 <0' - 1\">",
            "t": 0
        },
        {
            "c": "r:rgI",
            "v": "",
            "t": 0
        },
        {
            "c": "r:rwc",
            "v": "Rebar Cover 1 <0' - 1\">",
            "t": 0
        },
        {
            "c": "r:tgM",
            "v": "None",
            "t": 0
        },
        {
            "c": "r:wAI",
            "v": 80.31693606751301,
            "t": 0
        },
        {
            "c": "r:xwQ",
            "v": 1,
            "t": 0
        },
        {
            "c": "r:zgM",
            "v": 1,
            "t": 0
        },
        {
            "c": "z:zAc",
            "v": "value 4",
            "t": 0
        },
        {
            "c": "z:zQc",
            "v": 1234.99,
            "t": 0
        },
        {
            "c": "z:0Ac",
            "v": "https://www.apple.com",
            "t": 0
        },
        {
            "c": "z:0Qc",
            "v": "urn:adsk.dtd:Baz3jf5WTA-MX3EOSg6rmw",
            "t": 0
        }
    ]
}
```


***Status Code:*** 200

<br>



### 9. /modeldata/:modelID/schema


The /attrs and /schema endpoints are used to retrieve information about the properties that are available within Tandem. Some properties are read-only and come from the design source files (e.g. Revit, IFC). Other properties are defined in Tandem by the user and are read/write.  
When reading property values via /scan or writing property values via /mutate, it is necessary to know information about the property definition. For instance, both endpoints expect properties to be referenced by their internal "fully qualified" names (e.g., "z:zAc" instead of the human-readable display name "Concrete | Param A").

The /schema endpoint returns the list of properties in an easy to read JSON format, but is not the most efficient way to retrieve these names. The Tandem client application calls /attrs and builds a mapping table to go back and forth between DisplayName and internal "fully qualified" names.

See these notes for more information: [https://autodesk-tandem.github.io/API_attrs.html](https://autodesk-tandem.github.io/API_attrs.html)


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/modeldata/:modelID/schema
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) ID of the model to get |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| modelID | {{TandemSampleModelURN}} | (Required) ID of the model to get |



***Body: None***



#### I. Example Response: OK
```js
{
    "version": "v1",
    "attributes": [
        {
            "id": "n:n",
            "fam": "n",
            "col": "n",
            "name": "Name",
            "category": "Standard",
            "dataType": 20
        },
        {
            "id": "n:!n",
            "fam": "n",
            "col": "!n",
            "name": "OName",
            "category": "Standard",
            "dataType": 20
        },
        {
            "id": "n:u",
            "fam": "n",
            "col": "u",
            "name": "Uniformat Class",
            "category": "Standard",
            "dataType": 20
        },
        {
            "id": "n:!u",
            "fam": "n",
            "col": "!u",
            "name": "Uniformat Class Override",
            "category": "Standard",
            "dataType": 20
        },
        {
            "id": "n:v",
            "fam": "n",
            "col": "v",
            "name": "Classification",
            "category": "Standard",
            "dataType": 20
        },
        {
            "id": "n:!v",
            "fam": "n",
            "col": "!v",
            "name": "Classification Override",
            "category": "Standard",
            "dataType": 20
        },
        {
            "id": "n:c",
            "fam": "n",
            "col": "c",
            "name": "Category ID",
            "category": "Standard",
            "dataType": 2
        },
        {
            "id": "n:f",
            "fam": "n",
            "col": "f",
            "name": "Family Path",
            "category": "Standard",
            "dataType": 20
        },
        {
            "id": "n:a",
            "fam": "n",
            "col": "a",
            "name": "Element Flags",
            "category": "Standard",
            "dataType": 2
        },
        {
            "id": "l:l",
            "fam": "l",
            "col": "l",
            "name": "Level",
            "category": "Standard",
            "dataType": 10
        },
        {
            "id": "l:!l",
            "fam": "l",
            "col": "!l",
            "name": "Level Override",
            "category": "Standard",
            "dataType": 10
        },
        {
            "id": "l:m",
            "fam": "l",
            "col": "m",
            "name": "Top Level",
            "category": "Standard",
            "dataType": 10
        },
        {
            "id": "l:p",
            "fam": "l",
            "col": "p",
            "name": "Parent",
            "category": "Standard",
            "dataType": 10
        },
        {
            "id": "l:s",
            "fam": "l",
            "col": "s",
            "name": "Subfamily",
            "category": "Standard",
            "dataType": 10
        },
        {
            "id": "l:t",
            "fam": "l",
            "col": "t",
            "name": "Family Type",
            "category": "Standard",
            "dataType": 10
        },
        {
            "id": "r:-AE",
            "fam": "r",
            "col": "-AE",
            "name": "Horizontal Void/Chase Area Threshold",
            "category": "Energy Analytical Model",
            "dataType": 3,
            "dataTypeContext": "autodesk.unit.unit:squareFeet-1.0.1",
            "displayName": "Horizontal Void/Chase Area Threshold",
            "forgeUnit": "squareFeet"
        },
        {
            "id": "r:-AI",
            "fam": "r",
            "col": "-AI",
            "name": "Type Name",
            "category": "Identity Data",
            "dataType": 20,
            "displayName": "Type Name",
            "flags": 8
        },
        {
            "id": "r:-AM",
            "fam": "r",
            "col": "-AM",
            "name": "name",
            "category": "__name__",
            "dataType": 20
        },
        {
            "id": "r:-AQ",
            "fam": "r",
            "col": "-AQ",
            "name": "Top Offset",
            "category": "Constraints",
            "dataType": 3,
            "dataTypeContext": "autodesk.unit.unit:feetFractionalInches-1.0.0",
            "displayName": "Top Offset",
            "flags": 8,
            "forgeUnit": "feetFractionalInches"
        },
        {
            "id": "r:-AU",
            "fam": "r",
            "col": "-AU",
            "name": "K1",
            "category": "Materials and Finishes",
            "dataType": 20
        },
        {
            "id": "r:-AY",
            "fam": "r",
            "col": "-AY",
            "name": "Bending",
            "category": "Materials and Finishes",
            "dataType": 3,
            "dataTypeContext": "autodesk.unit.unit:kipsPerSquareInch-1.0.1",
            "displayName": "Bending",
            "forgeUnit": "kipsPerSquareInch"
        },
        {
            "id": "r:-QE",
            "fam": "r",
            "col": "-QE",
            "name": "Frame",
            "category": "Materials and Finishes",
            "dataType": 20
        },
        {
            "id": "r:-QI",
            "fam": "r",
            "col": "-QI",
            "name": "Shear modulus",
            "category": "Materials and Finishes",
            "dataType": 3,
            "dataTypeContext": "autodesk.unit.unit:kipsPerSquareInch-1.0.1",
            "displayName": "Shear modulus",
            "forgeUnit": "kipsPerSquareInch"
        },
        {
            "id": "r:-QM",
            "fam": "r",
            "col": "-QM",
            "name": "Guide Grid",
            "category": "Other",
            "dataType": 20,
            "displayName": "Guide Grid"
        },
        {
            "id": "r:-QQ",
            "fam": "r",
            "col": "-QQ",
            "name": "Length",
            "category": "Analytical Properties",
            "dataType": 3,
            "dataTypeContext": "autodesk.unit.unit:feetFractionalInches-1.0.0",
            "displayName": "Length",
            "flags": 8,
            "forgeUnit": "feetFractionalInches"
        },
        {
            "id": "r:-QU",
            "fam": "r",
            "col": "-QU",
            "name": "glass inset",
            "category": "Dimensions",
            "dataType": 3,
            "dataTypeContext": "autodesk.unit.unit:feetFractionalInches-1.0.0",
            "forgeUnit": "feetFractionalInches"
        },
        {
            "id": "r:-QY",
            "fam": "r",
            "col": "-QY",
            "name": "Assembly Description",
            "category": "Identity Data",
            "dataType": 20,
            "displayName": "Assembly Description",
            "flags": 8
        },
        {
            "id": "z:zAc",
            "fam": "z",
            "col": "zAc",
            "name": "Param A",
            "category": "Test 2 - Concrete",
            "dataType": 20,
            "flags": 16,
            "context": "e"
        },
        {
            "id": "z:zQc",
            "fam": "z",
            "col": "zQc",
            "name": "Param B",
            "category": "Test 2 - Concrete",
            "dataType": 3,
            "flags": 16,
            "context": "e"
        },
        {
            "id": "z:zgc",
            "fam": "z",
            "col": "zgc",
            "name": "Param Alpha",
            "category": "Test 3 - Masonry",
            "dataType": 20,
            "flags": 16,
            "context": "e"
        },
        {
            "id": "z:zwc",
            "fam": "z",
            "col": "zwc",
            "name": "Param Beta",
            "category": "Test 3 - Masonry",
            "dataType": 3,
            "flags": 16,
            "context": "e"
        },
        {
            "id": "z:0Ac",
            "fam": "z",
            "col": "0Ac",
            "name": "Param C",
            "category": "Test 2 - Concrete",
            "dataType": 25,
            "flags": 16,
            "context": "e"
        },
        {
            "id": "z:0Qc",
            "fam": "z",
            "col": "0Qc",
            "name": "Param D",
            "category": "Test 2 - Concrete",
            "dataType": 25,
            "flags": 16,
            "context": "e"
        },
        {
            "id": "z:0gc",
            "fam": "z",
            "col": "0gc",
            "name": "Param 1",
            "category": "Architecture",
            "dataType": 20,
            "flags": 16,
            "context": "e"
        },
        {
            "id": "z:0wc",
            "fam": "z",
            "col": "0wc",
            "name": "Param 2",
            "category": "Electrical",
            "dataType": 3,
            "flags": 16,
            "forgeUnit": "watts",
            "forgeSymbol": "watt",
            "forgeSpec": "electrical.apparentPower",
            "context": "e"
        },
        {
            "id": "z:1Ac",
            "fam": "z",
            "col": "1Ac",
            "name": "Param 3",
            "category": "General",
            "dataType": 20,
            "flags": 16,
            "context": "e"
        }
    ]
}
```


***Status Code:*** 200

<br>



## models/{model ID}



### 1. streams/{element ID}



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 2. /models/:modelID/props


Return model properties, such as data source definition and model state


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/models/:modelID/props
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
    "dataSources": {
        "schemaVersion": 1,
        "forgeUrn": "dXJuOmFkc2sub2JqZWN0czpvcy5vYmplY3Q6ZHR3LXRtcC1zdG9yYWdlLXRlc3QvdXJuOmFkc2suZHR0OmIzVmpiZ1dqVFlTQUR4ejhxQnNTMHclMkYxNjI3NDIwMTAxNzg5JTJGUjIxJTIwTWlsbCUyMEJ1aWxkaW5nJTIwLSUyMEFyY2gucnZ0",
        "documentId": "mwlSTzukR2uVre2WRvQT1g",
        "fileName": "R21 Mill Building - Arch.rvt",
        "lastUpdated": "2021-07-27T21:14:15Z",
        "phaseNames": [
            "new construction"
        ]
    },
    "settings": null,
    "state": {
        "state": "r"
    }
}
```


***Status Code:*** 200

<br>



## twins/{twin ID}



### 1. classification (DEPRECATED/LEGACY)



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 2. documents



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 3. model



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 4. psets (DEPRECATED/LEGACY)



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 5. template



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 6. thumbnail



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 7. users/{user ID}



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 8. /twins/:twinID


Hard delete of the Twin including all related data.

NOTE: as of now, no notifications go out to any clients that may have this Twin loaded. So, it is possible to delete it out from underneath them. Those clients will have degraded performance.


***Endpoint:***

```bash
Method: DELETE
Type: 
URL: {{TandemBaseURL}}/twins/:twinID
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | urn:adsk.dtt:7Fely1WMS1ObWG5Pswwnhw | (Required) ID of the twin |



***More example Requests/Responses:***


#### I. Example Request: OK (204 - No Content)



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | urn:adsk.dtt:7Fely1WMS1ObWG5Pswwnhw | (Required) ID of the twin |



***Body: None***



***Status Code:*** 204

<br>



### 9. /twins/:twinID


Returns metadata about the Twin (imported models, documents, identity data, etc). Call this to inspect the current state or to prepare for a PUT call, which requires you to get the current state before making any changes.


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/twins/:twinID
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) ID of the twin |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) ID of the twin |



***Body: None***



#### I. Example Response: OK
```js
{
    "links": [
        {
            "disciplines": null,
            "label": "Arch",
            "main": true,
            "modelId": "urn:adsk.dtm:SgmBAad2QWCAN4asbyn6GA",
            "on": true,
            "accessLevel": "Owner"
        },
        {
            "disciplines": null,
            "label": "MECH",
            "main": false,
            "modelId": "urn:adsk.dtm:lfx8qZIwR1qR-HYhGpZKLQ",
            "on": true,
            "accessLevel": "Owner"
        },
        {
            "disciplines": null,
            "label": "ELEC",
            "main": false,
            "modelId": "urn:adsk.dtm:xUXZHzRPSk-yzSKznv-JMA",
            "on": true,
            "accessLevel": "Owner"
        }
    ],
    "docs": [
        {
            "id": "urn:adsk.dtd:Baz3jf5WTA-MX3EOSg6rmw",
            "contentType": "application/pdf",
            "s3Path": "b3VjbgWjTYSADxz8qBsS0w/05acf78d-fe56-4c0f-8c5f-710e4a0eab9b/v0",
            "lastUpdated": "2021-11-01T21:26:28Z",
            "signedLink": "https://tandem-stg.autodesk.com/api/v1/twins/urn:adsk.dtt:b3VjbgWjTYSADxz8qBsS0w/documents/urn:adsk.dtd:Baz3jf5WTA-MX3EOSg6rmw/content?lastupdated=1635801988",
            "name": "A100 SERIES.pdf",
            "accPath": "/file/path/in/acc",
            "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
            "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
            "accLineage": "urn:adsk.wipstg:dm.lineage:CPnmL9HfTQ6iqU8LBceHjA",
            "accVersion": "urn:adsk.wipstg:fs.file:vf.CPnmL9HfTQ6iqU8LBceHjA?version=1"
        },
        {
            "id": "urn:adsk.dtd:SqzGFsAfS3CcknEqlON_gA",
            "contentType": "application/pdf",
            "s3Path": "b3VjbgWjTYSADxz8qBsS0w/4aacc616-c01f-4b70-9c92-712a94e37f80/v0",
            "lastUpdated": "2021-11-09T15:54:50Z",
            "signedLink": "https://tandem-stg.autodesk.com/api/v1/twins/urn:adsk.dtt:b3VjbgWjTYSADxz8qBsS0w/documents/urn:adsk.dtd:SqzGFsAfS3CcknEqlON_gA/content?lastupdated=1636473290",
            "name": "A300 SERIES.pdf",
            "accPath": "/file/path/in/acc",
            "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
            "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
            "accLineage": "urn:adsk.wipstg:dm.lineage:y6dpA9_XSLm2LdMMmWmCrw",
            "accVersion": "urn:adsk.wipstg:fs.file:vf.y6dpA9_XSLm2LdMMmWmCrw?version=1"
        },
        {
            "id": "urn:adsk.dtd:RXM1NYTXThmrup6H8N31iQ",
            "contentType": "application/pdf",
            "s3Path": "b3VjbgWjTYSADxz8qBsS0w/45733535-84d7-4e19-abba-9e87f0ddf589/v0",
            "lastUpdated": "2021-11-09T16:10:39Z",
            "signedLink": "https://tandem-stg.autodesk.com/api/v1/twins/urn:adsk.dtt:b3VjbgWjTYSADxz8qBsS0w/documents/urn:adsk.dtd:RXM1NYTXThmrup6H8N31iQ/content?lastupdated=1636474239",
            "name": "SCHEMATIC DESIGN SUBMISSION VOLUME 1.pdf",
            "accPath": "/file/path/in/acc",
            "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
            "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
            "accLineage": "urn:adsk.wipstg:dm.lineage:XDI_Q-aNSnmhGqViMCXCmg",
            "accVersion": "urn:adsk.wipstg:fs.file:vf.XDI_Q-aNSnmhGqViMCXCmg?version=1"
        }
    ],
    "props": {
        "Identity Data": {
            "Address": "1 Market St., Suite #500, San Francisco CA 94105",
            "Building Name": "One Market",
            "Owner": "Autodesk, Inc",
            "Project Name": "Autodesk HQ (actually King St)"
        },
        "Other": {
            "Project Number": ""
        }
    },
    "dateCreated": "2021-07-27T21:07:58Z",
    "template": {
        "uuid": "WUVNJPtnTM26OrgOSm7L0g",
        "name": "CityWorks",
        "description": "CityWorks test with WO mapping",
        "classificationId": "masterformat",
        "psetIds": [
            "U2qVqS3RSO-GYITwQfzSGg",
            "tyFDfH8PRAGPNHoGbwlGng",
            "nGs9n4WISzCjDeDVUWTmqA",
            "IApO4oiHTt-Z39RH9ynniw"
        ]
    },
    "accessLevel": "Owner",
    "accountGroup": "urn:adsk.dtg:iCGGqdNMS4-9o-iVOs86Tw",
    "dateModified": "2022-01-19T22:14:03Z",
    "etag": "1642630443294"
}
```


***Status Code:*** 200

<br>



### 10. /twins/:twinID


Commonly used to check that a given token has access to the given Twin. Response will contain a header, indicating actual access level.


***Endpoint:***

```bash
Method: HEAD
Type: 
URL: {{TandemBaseURL}}/twins/:twinID
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}}  | (Required) ID of the twin |



### 11. /twins/:twinID


Update the Twin according to new/changed information in the JSON metadata object.

This endpoint expects you to be careful with the JSON object and know what can and cannot be changed. As an example, the property `links.on` could be set to false to turn of default visibility for that particular model. However, you cannot delete a model by simply removing it from the JSON object.

The correct procedure to update is:

1.  call GET baseURL/twins/:twinID to get the current state of the JSON object
2.  modify the appropriate data only
3.  grab the eTag that was returned in step 1
4.  use the eTag as a parameter in the request header
    

The eTag is "proof" that you got the current state first before modifying it.


***Endpoint:***

```bash
Method: PUT
Type: RAW
URL: {{TandemBaseURL}}/twins/:twinID
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |
| etag | 1642117507831 |  |



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) ID of the twin |



***Body:***

```js        
{
    "links": [
        {
            "disciplines": null,
            "label": "Arch",
            "main": true,
            "modelId": "urn:adsk.dtm:SgmBAad2QWCAN4asbyn6GA",
            "on": true,
            "accessLevel": "Owner"
        },
        {
            "disciplines": null,
            "label": "MECH",
            "main": false,
            "modelId": "urn:adsk.dtm:lfx8qZIwR1qR-HYhGpZKLQ",
            "on": false,
            "accessLevel": "Owner"
        },
        {
            "disciplines": null,
            "label": "ELEC",
            "main": false,
            "modelId": "urn:adsk.dtm:xUXZHzRPSk-yzSKznv-JMA",
            "on": false,
            "accessLevel": "Owner"
        }
    ],
    "docs": [
        {
            "id": "urn:adsk.dtd:Baz3jf5WTA-MX3EOSg6rmw",
            "contentType": "application/pdf",
            "s3Path": "b3VjbgWjTYSADxz8qBsS0w/05acf78d-fe56-4c0f-8c5f-710e4a0eab9b/v0",
            "lastUpdated": "2021-11-01T21:26:28Z",
            "signedLink": "https://tandem-stg.autodesk.com/api/v1/twins/urn:adsk.dtt:b3VjbgWjTYSADxz8qBsS0w/documents/urn:adsk.dtd:Baz3jf5WTA-MX3EOSg6rmw/content?lastupdated=1635801988",
            "name": "A100 SERIES.pdf",
            "accPath": "/file/path/in/acc",
            "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
            "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
            "accLineage": "urn:adsk.wipstg:dm.lineage:CPnmL9HfTQ6iqU8LBceHjA",
            "accVersion": "urn:adsk.wipstg:fs.file:vf.CPnmL9HfTQ6iqU8LBceHjA?version=1"
        },
        {
            "id": "urn:adsk.dtd:SqzGFsAfS3CcknEqlON_gA",
            "contentType": "application/pdf",
            "s3Path": "b3VjbgWjTYSADxz8qBsS0w/4aacc616-c01f-4b70-9c92-712a94e37f80/v0",
            "lastUpdated": "2021-11-09T15:54:50Z",
            "signedLink": "https://tandem-stg.autodesk.com/api/v1/twins/urn:adsk.dtt:b3VjbgWjTYSADxz8qBsS0w/documents/urn:adsk.dtd:SqzGFsAfS3CcknEqlON_gA/content?lastupdated=1636473290",
            "name": "A300 SERIES.pdf",
            "accPath": "/file/path/in/acc",
            "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
            "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
            "accLineage": "urn:adsk.wipstg:dm.lineage:y6dpA9_XSLm2LdMMmWmCrw",
            "accVersion": "urn:adsk.wipstg:fs.file:vf.y6dpA9_XSLm2LdMMmWmCrw?version=1"
        },
        {
            "id": "urn:adsk.dtd:RXM1NYTXThmrup6H8N31iQ",
            "contentType": "application/pdf",
            "s3Path": "b3VjbgWjTYSADxz8qBsS0w/45733535-84d7-4e19-abba-9e87f0ddf589/v0",
            "lastUpdated": "2021-11-09T16:10:39Z",
            "signedLink": "https://tandem-stg.autodesk.com/api/v1/twins/urn:adsk.dtt:b3VjbgWjTYSADxz8qBsS0w/documents/urn:adsk.dtd:RXM1NYTXThmrup6H8N31iQ/content?lastupdated=1636474239",
            "name": "SCHEMATIC DESIGN SUBMISSION VOLUME 1.pdf",
            "accPath": "/file/path/in/acc",
            "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
            "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
            "accLineage": "urn:adsk.wipstg:dm.lineage:XDI_Q-aNSnmhGqViMCXCmg",
            "accVersion": "urn:adsk.wipstg:fs.file:vf.XDI_Q-aNSnmhGqViMCXCmg?version=1"
        }
    ],
    "dateCreated": "2021-07-27T21:07:58Z",
    "template": {
        "uuid": "WUVNJPtnTM26OrgOSm7L0g",
        "name": "CityWorks",
        "description": "CityWorks test with WO mapping",
        "classificationId": "masterformat",
        "psetIds": [
            "U2qVqS3RSO-GYITwQfzSGg",
            "tyFDfH8PRAGPNHoGbwlGng",
            "nGs9n4WISzCjDeDVUWTmqA",
            "IApO4oiHTt-Z39RH9ynniw"
        ]
    },
    "accessLevel": "Owner",
    "accountGroup": "urn:adsk.dtg:iCGGqdNMS4-9o-iVOs86Tw",
    "dateModified": "2022-01-13T23:45:07Z",
    "etag": "1642117507831"
}
```



### 12. /twins/:twinID/cleanup


Dispatches a cleanup task for the given Twin. Cleanup involves removing certain properties from assets.

  
Example: removing properties from a parameter set that was deleted


***Endpoint:***

```bash
Method: POST
Type: 
URL: {{TandemBaseURL}}/twins/:twinID/cleanup
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***Body: None***



***Status Code:*** 202

<br>



### 13. /twins/:twinID/confirmupload


Confirm that data uploading to OSS has finished - using direct s3 access


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{TandemBaseURL}}/twins/:twinID/confirmupload
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***Body:***

```js        
{
    "fileName": "officia aliqua incididunt",
    "key": "labore dolore dolore",
    "name": "laboris anim adipisicing",
    "url": "minim incididunt",
    "urn": "sit in cillum"
}
```



### 14. /twins/:twinID/documentsbulk


Create a Tandem document from an ACC file (will copy file content to the Tandem managed storage system).

The payload in the request is an array of document specifiers. The information in each specification is expected to come from the ACC Documents API.

For more information on the Documents endpoints, please visit: [https://autodesk-tandem.github.io/API_docs.html](https://autodesk-tandem.github.io/API_docs.html)


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{TandemBaseURL}}/twins/:twinID/documentsbulk
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***Body:***

```js        
[
    {
        "name": "A600 SERIES.pdf",
        "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
        "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
        "accLineage": "urn:adsk.wipstg:dm.lineage:oJGDdicDTWy8UucCU14pNg",
        "accVersion": "urn:adsk.wipstg:fs.file:vf.oJGDdicDTWy8UucCU14pNg?version=1"
    }
]
```



***More example Requests/Responses:***


#### I. Example Request: OK - add PDF file from ACC Docs repository


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***Body:***

```js        
[
    {
        "name": "A600 SERIES.pdf",
        "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
        "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
        "accLineage": "urn:adsk.wipstg:dm.lineage:oJGDdicDTWy8UucCU14pNg",
        "accVersion": "urn:adsk.wipstg:fs.file:vf.oJGDdicDTWy8UucCU14pNg?version=1"
    }
]
```



#### I. Example Response: OK - add PDF file from ACC Docs repository
```js
{
    "status": "succeeded",
    "data": [
        {
            "id": "urn:adsk.dtd:Q8inOVzhRviEoJRBbWvwtw",
            "contentType": "application/pdf",
            "s3Path": "b3VjbgWjTYSADxz8qBsS0w/43c8a739-5ce1-46f8-84a0-94416d6bf0b7/v0",
            "lastUpdated": "2022-03-08T00:14:05Z",
            "name": "A600 SERIES.pdf",
            "accProjectId": "b.a1a5a4c3-18d3-4557-bf56-bf45d8cab93d",
            "accAccountId": "b.a263f880-9604-4f48-a270-6ccf92dc6370",
            "accLineage": "urn:adsk.wipstg:dm.lineage:oJGDdicDTWy8UucCU14pNg",
            "accVersion": "urn:adsk.wipstg:fs.file:vf.oJGDdicDTWy8UucCU14pNg?version=1"
        }
    ]
}
```


***Status Code:*** 200

<br>



### 15. /twins/:twinID/import


Trigger a model import job for the given model.  
This is an async API - you will get notified via a realtime event when using the SDK. Otherwise, you can poll for the result.


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{TandemBaseURL}}/twins/:twinID/import
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***Body:***

```js        
{
    "modelId": "voluptate nulla qui sunt id",
    "phaseNames": [
        "sed mollit anim",
        "do velit"
    ],
    "realFilename": "cupidatat Ut sed pariatur enim",
    "roomAssignment": true,
    "urn": "ut eu magna"
}
```



### 16. /twins/:twinID/inlinetemplate


Get the Template associated with this Twin (including classification information)


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/twins/:twinID/inlinetemplate
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) TwinID |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***Body: None***



#### I. Example Response: OK
```js
{
    "uuid": "WUVNJPtnTM26OrgOSm7L0g",
    "name": "CityWorks",
    "description": "CityWorks test with WO mapping",
    "classification": {
        "uuid": "masterformat",
        "name": "Masterformat",
        "rows": [
            [
                "01 00 00",
                "General Requirements",
                1
            ],
            [
                "01 30 00",
                "Administrative Requirements",
                2
            ],
            [
                "01 31 00",
                "Project Management and Coordination",
                2
            ],
            [
                "01 31 13",
                "Project Coordination",
                3
            ],
            [
                "46 73 26",
                "Egg-shaped Digesters",
                3
            ],
            [
                "46 73 31",
                "External Draft Tube Digester Mixing System",
                3
            ],
            [
                "46 73 32",
                "Internal Draft Tube Digester Mixing System",
                3
            ],
            [
                "46 73 33",
                "Confined Gas Mixing System ",
                3
            ],
            [
                "46 73 34",
                "Unconfined Gas Mixing System",
                3
            ],
            [
                "46 73 41",
                "Digester Heating Equipment",
                3
            ],
            [
                "46 73 63",
                "Residuals Pasteurization Equipment",
                3
            ],
            [
                "46 76 00",
                "Residuals Dewatering Equipment",
                2
            ],
            [
                "46 76 13",
                "Vacuum Filters",
                3
            ],
            [
                "46 76 21",
                "Belt Filter Presses",
                3
            ],
            [
                "46 76 23",
                "Plate-and-Frame Filter Presses",
                3
            ],
            [
                "46 76 26",
                "Rotary Presses",
                3
            ],
            [
                "46 76 27",
                "Screw Presses",
                3
            ],
            [
                "46 76 33",
                "Dewatering Centrifuges",
                3
            ],
            [
                "46 76 53",
                "Belt Dryers",
                3
            ],
            [
                "46 76 60",
                "Direct-heat Residuals Drying Equipment",
                3
            ],
            [
                "46 76 70",
                "Indirect-heat Residuals Drying Equipment",
                3
            ],
            [
                "46 78 00",
                "Thermal Treatment of Residuals",
                2
            ],
            [
                "46 78 13",
                "Multiple-hearth Sludge Incinerators",
                3
            ],
            [
                "46 78 23",
                "Fluidized-bed Sludge Incinerators",
                3
            ],
            [
                "46 78 33",
                "Ash Handling Equipment ",
                3
            ]
        ]
    },
    "classificationId": "masterformat",
    "psets": [
        {
            "version": 1,
            "name": "CW Connection",
            "uuid": "U2qVqS3RSO-GYITwQfzSGg",
            "owner": "",
            "applicationFilters": {
                "masterFormat": [
                    "01 00 00"
                ]
            },
            "parameters": [
                {
                    "name": "WO Id",
                    "dataType": 20,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "04fa96d8-e47b-4af9-b8c4-4d4b0664a6d4",
                    "context": "e"
                }
            ],
            "hidden": false
        },
        {
            "version": 4,
            "name": "Test 1 - General",
            "uuid": "tyFDfH8PRAGPNHoGbwlGng",
            "owner": "",
            "applicationFilters": {
                "masterFormat": [
                    "01 00 00"
                ]
            },
            "parameters": [
                {
                    "name": "Param 1",
                    "dataType": 20,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "3c40403b-a927-4b71-965c-4872f9451194",
                    "context": "e"
                },
                {
                    "name": "Param 2",
                    "dataType": 1,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "3c007b67-dcc6-4103-9a85-81d5f133de2b",
                    "context": "e"
                },
                {
                    "name": "Param 3",
                    "dataType": 2,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "32950857-3f12-45ce-b059-a6f288195777",
                    "context": "e"
                },
                {
                    "name": "Param 4",
                    "dataType": 20,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "defd6a7c-1ede-4fcb-9a91-921812e26bd9",
                    "context": "e"
                }
            ],
            "hidden": false
        },
        {
            "version": 5,
            "name": "Test 2 - Concrete",
            "uuid": "nGs9n4WISzCjDeDVUWTmqA",
            "owner": "",
            "applicationFilters": {
                "masterFormat": [
                    "03 00 00"
                ]
            },
            "parameters": [
                {
                    "name": "Param A",
                    "dataType": 20,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "2662c68e-4585-4416-9a45-287350d21b87",
                    "context": "e"
                },
                {
                    "name": "Param B",
                    "dataType": 3,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "a32db3d9-4d79-4f47-afad-9e0164f12633",
                    "context": "e"
                },
                {
                    "name": "Param C",
                    "dataType": 25,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "967d561d-c5d5-479e-b0b1-d77117847cb4",
                    "context": "e"
                },
                {
                    "name": "Param D",
                    "dataType": 25,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "1c77dc41-2d21-4d10-b609-69efd9c65e3a",
                    "context": "e"
                }
            ],
            "hidden": false
        },
        {
            "version": 1,
            "name": "Test 3 - Masonry",
            "uuid": "IApO4oiHTt-Z39RH9ynniw",
            "owner": "",
            "applicationFilters": {
                "masterFormat": [
                    "04 00 00"
                ]
            },
            "parameters": [
                {
                    "name": "Param Alpha",
                    "dataType": 20,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "b4bb3c9a-9d43-4a23-8766-d98a80203bdf",
                    "context": "e"
                },
                {
                    "name": "Param Beta",
                    "dataType": 3,
                    "forgeUnit": "",
                    "forgeSymbol": "",
                    "forgeSpec": "",
                    "precision": 0,
                    "description": "",
                    "uuid": "a70c83b5-c225-4728-9313-f5ef3ade6a89",
                    "context": "e"
                }
            ],
            "hidden": false
        }
    ]
}
```


***Status Code:*** 200

<br>



### 17. /twins/:twinID/subjects


Returns Groups and Users having access to the given Twin.


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/twins/:twinID/subjects
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***More example Requests/Responses:***


#### I. Example Request: OK



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***Body: None***



#### I. Example Response: OK
```js
{
    "urn:adsk.dtg:iCGGqdNMS4-9o-iVOs86Tw": {
        "name": "James Awe's Account",
        "accessLevel": "Owner"
    },
    "urn:adsk.dtu:N8UCJ7VRWGPF": {
        "name": "Traian Stanev",
        "accessLevel": "Manage"
    }
}
```


***Status Code:*** 200

<br>



### 18. /twins/:twinID/uploadlink


Creates a signed link to upload file(e.g. revit model) to OSS - using direct s3 access


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{TandemBaseURL}}/twins/:twinID/uploadlink
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| twinID | {{TandemSampleFacilityURN}} | (Required) Twin ID |



***Body:***

```js        
{
    "realFileName": "eu pariatur"
}
```



## Ungrouped



### 1. /users/:userID/twins


Returns a collection of Twins the UserID has direct access to. This does not include Twins whiich are part of a Group the UserID has access to anyway (i.e. the "Shared With Me" tab in the Tandem client application).

See "GET baseURL/groups/:groupID/twins" for how to get Twins that are part of a Group.

UserID is the AutodeskID that looks like: "Q7W5J5WV3AEJ", or it can be "@me" to use the current User's ID.


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/users/:userID/twins
```



***URL variables:***

| Key | Value | Description |
| --- | ------|-------------|
| userID | {{TandemSampleUserId}} | (Required) User ID - supports @me |



***More example Requests/Responses:***


#### I. Example Request: OK - userID



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| userID | {{TandemSampleUserId}} | (Required) User ID - supports @me |



***Body: None***



#### I. Example Response: OK - userID
```js
{
    "urn:adsk.dtt:7xafc_StQ9etrHD0FJjpMQ": {
        "links": [
            {
                "disciplines": null,
                "label": "Technical_school-current_m.rvt",
                "main": true,
                "modelId": "urn:adsk.dtm:KzUQ8SgZSfutapjylcgIIA",
                "on": true,
                "accessLevel": "Manage"
            }
        ],
        "docs": null,
        "props": {
            "Identity Data": {
                "Address": "",
                "Building Name": "[test - do not delete] app server e2e test facility",
                "Owner": "https://git.autodesk.com/constructwin/dt-client/tree/master/tests",
                "Project Name": ""
            },
            "Other": {
                "Project Number": ""
            }
        },
        "dateCreated": "2020-11-20T09:35:45Z",
        "template": {
            "uuid": "",
            "name": "",
            "description": "",
            "classificationId": "",
            "psetIds": []
        },
        "accessLevel": "Manage",
        "accountGroup": "urn:adsk.dtg:eNhZdIizSKKhEdC-KjWVQg",
        "dateModified": "2020-11-25T09:45:36Z",
        "etag": "1606297536753"
    },
    "urn:adsk.dtt:l1Fm_m4ARGegnSH9UKbddg": {
        "links": [
            {
                "disciplines": [],
                "label": "Archy",
                "main": true,
                "modelId": "urn:adsk.dtm:Yt-UJ1JHT8OxV2T3Q03SXA",
                "on": true,
                "accessLevel": "ReadWrite"
            }
        ],
        "docs": null,
        "props": {
            "Identity Data": {
                "Address": "Takkatukka Land",
                "Building Name": "Räuberhöhle",
                "Owner": "Hotzenplotz",
                "Project Name": "Fette Beute"
            },
            "Other": {
                "Project Number": ""
            }
        },
        "dateCreated": "",
        "template": null,
        "accessLevel": "ReadWrite",
        "accountGroup": "urn:adsk.dtg:WgHMoyALRnGz4d0jHjpEDg",
        "dateModified": "2020-09-07T09:17:38Z",
        "etag": "1599470258624"
    }
}
```


***Status Code:*** 200

<br>



#### II. Example Request: OK - @me



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| userID | @me | (Required) User ID - supports @me |



***Body: None***



#### II. Example Response: OK - @me
```js
{
    "urn:adsk.dtt:7xafc_StQ9etrHD0FJjpMQ": {
        "links": [
            {
                "disciplines": null,
                "label": "Technical_school-current_m.rvt",
                "main": true,
                "modelId": "urn:adsk.dtm:KzUQ8SgZSfutapjylcgIIA",
                "on": true,
                "accessLevel": "Manage"
            }
        ],
        "docs": null,
        "props": {
            "Identity Data": {
                "Address": "",
                "Building Name": "[test - do not delete] app server e2e test facility",
                "Owner": "https://git.autodesk.com/constructwin/dt-client/tree/master/tests",
                "Project Name": ""
            },
            "Other": {
                "Project Number": ""
            }
        },
        "dateCreated": "2020-11-20T09:35:45Z",
        "template": {
            "uuid": "",
            "name": "",
            "description": "",
            "classificationId": "",
            "psetIds": []
        },
        "accessLevel": "Manage",
        "accountGroup": "urn:adsk.dtg:eNhZdIizSKKhEdC-KjWVQg",
        "dateModified": "2020-11-25T09:45:36Z",
        "etag": "1606297536753"
    },
    "urn:adsk.dtt:l1Fm_m4ARGegnSH9UKbddg": {
        "links": [
            {
                "disciplines": [],
                "label": "Archy",
                "main": true,
                "modelId": "urn:adsk.dtm:Yt-UJ1JHT8OxV2T3Q03SXA",
                "on": true,
                "accessLevel": "ReadWrite"
            }
        ],
        "docs": null,
        "props": {
            "Identity Data": {
                "Address": "Takkatukka Land",
                "Building Name": "Räuberhöhle",
                "Owner": "Hotzenplotz",
                "Project Name": "Fette Beute"
            },
            "Other": {
                "Project Number": ""
            }
        },
        "dateCreated": "",
        "template": null,
        "accessLevel": "ReadWrite",
        "accountGroup": "urn:adsk.dtg:WgHMoyALRnGz4d0jHjpEDg",
        "dateModified": "2020-09-07T09:17:38Z",
        "etag": "1599470258624"
    }
}
```


***Status Code:*** 200

<br>



### 2. /health


Returns a JSON object with information about server health. A "verbose=true" parameter will include websocket statistics.


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{TandemBaseURL}}/health
```



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| verbose | true | adds more verbose output: e.g. websocket stats |



***More example Requests/Responses:***


#### I. Example Request: OK - verbose=false



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| verbose | false | adds more verbose output: e.g. websocket stats |



***Body: None***



#### I. Example Response: OK - verbose=false
```js
{
    "env": "stg",
    "version": "9efb4745-v"
}
```


***Status Code:*** 200

<br>



#### II. Example Request: OK - verbose=true



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| verbose | true | adds more verbose output: e.g. websocket stats |



***Body: None***



#### II. Example Response: OK - verbose=true
```js
{
    "env": "stg",
    "version": "9efb4745-v",
    "msghub": {
        "connectedEntities": 6,
        "subscriptions": 6,
        "connectedClients": 2
    }
}
```


***Status Code:*** 200

<br>



### 3. /admin/modelscheck


Checks whether given URNs exist somewhere globally in the Tandem platform


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{TandemBaseURL}}/admin/modelscheck
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |



***Body:***

```js        
{
    "urns": [
        "urn:adsk.dtm:SgmBAad2QWCAN4asbyn6GA",
        "urn:adsk.dtm:lfx8qZIwR1qR-HYhGpZKLQ"
    ]
}
```



---
[Back to top](#autodesk-tandem-model-service-beta)

>Generated at 2022-05-16 20:52:42 by [docgen](https://github.com/thedevsaddam/docgen)
