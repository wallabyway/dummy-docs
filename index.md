---
title: Overview
has_children: false
nav_order: 1
---

![Tandem API](./img/TandemLogo.png)

# Overview

Tandem digital twins represent a hub of information about your facility and they establish the existence and location of assets within that facility. That foundation is critical, but any good digital twin will include integrations with other systems and will support programmatic management of the asset data. Therefore, API access to the Tandem data model is essential.  Over time, we plan to offer comprehensive APIs in several contexts to help developers customize and extend the foundational capabilities that the Tandem product provides.

## Tandem APIs

![API Contexts](./img/API_contexts.png)

All sample code, API documentation and example data, can be found on our Github repo, here:

Github: [Tandem APIs & Samples](https://github.com/autodesk-tandem)

_NOTE: Currently, these samples are marked "Private". To gain access, [email us](Support.md) with your GitHub username, and we will add you to this repository._

The main read/write functions will not be very interesting until you learn how to setup a Facility, create user-defined Parameters, and map those parameters to assets using Classifications in a Facility Template.  To learn how to do that and to get started with the product, visit: [intandem.autodesk.com](https://intandem.autodesk.com/)

### REST API

The REST API is a thin layer over the underlying Tandem database.
A Postman collection is provided to allow interactive testing of the REST APIs.

To learn more, click [here](./restAPI/intro.md)

### Javascript SDK

The Javascript SDK allows you to interact with the Tandem database via Javascript and in "Embedded Viewer" scenarios, similar to how developers use the Forge Viewer.

To learn more, click [here](./SDK Samples/intro.md)


### Tandem Plug-ins

Direct plug-ins to the Tandem product itself are envisioned for the future, but are not yet supported. There have been some experiments with lightweight integrations via a Crome browser plug-in.  A sample project has been included here: [Chrome Plugin Sample](https://github.com/autodesk-tandem/tandem-sample-chrome-ext).

Autodesk does not support Tandem plug-ins at this time, however, so this sample is only provided as-is, with no support or guarantees.
