---
title: Consume a Basic OData Service
description: Consume a Basic OData Service within UI5 binding the service to a Table
primary_tag: products>sap-hana
tags: [  tutorial>intermediate, topic>html5, topic>odata, topic>sapui5, products>sap-hana, products>sap-hana\,-express-edition  ]
---
## Prerequisites  
- **Proficiency:** Intermediate
- **Tutorials:** [SAPUI5 User Interface](http://www.sap.com/developer/tutorials/xsa-sapui5.html)

## Next Steps
- [Use OData Metadata to dynamically create the columns](http://www.sap.com/developer/tutorials/xsa-sapui5-metadata.html)

## Details
### You will learn  
Consume a Basic OData Service within UI5 binding the service to a Table.

**Please note - This tutorial is based on SPS11**

### Time to Complete
**15 Min**.

---


[ACCORDION-BEGIN [Step 1: ](Create new folder)]

Create a folder named `odataBasic` within the `web/resources` folder

![new folder](1.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Create required files)]

Within this folder, create two files – one named `Component.js` and one named `index.html`.  Also create a sub-folder named view.

![new files](2.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Create controller and view)]

Within the view folder you just created, please now create two files – `App.controller.js` and `App.view.js`

![new files](3.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Create index.html)]

To avoid having to do too much typing, we have prepared some template code for you.  In the `index.html` we need to insert the basic UI5 `bootstrap` and initialization code. This page will create a single html content item and then start the `Component.js` file which contains the rest of the true application startup logic. We recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex4_10`

```
<!DOCTYPE html>
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Create the Component JavaScript file)]

In the `Component.js` file you initialize the application and set the base UI elements for the page. We recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex4_11` You should notice that there are commented `To-Do` sections in this code which you just copied into the file. These are the most important parts and will be completed in the next few steps.

```
jQuery.sap.declare("sap.shineNext.odataBasic.Component");
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 6: ](Create empty controller)]

Since this is a simple example application we won't need any controller logic. Just insert this empty controller logic.

```
sap.ui.controller("sap.shineNext.odataBasic.view.App",{
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 7: ](Create view definition)]

For the view definition to avoid having to do too much typing, we have prepared some template code for you which already has the definition of the table UI element and the table columns, but none of the logic to consume the OData service. You can cut and paste this template code from this address into the `odataBasic.view.js` file: Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex4_12` You should notice that there are commented To-Do sections in this code which you just copied into the file. These are the most important parts and will be completed in the next few steps.

```
sap.ui.jsview("sap.shineNext.odataBasic.view.App", {
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 8: ](Create model)]

In the first `To-Do` location in the `Component.js` file, you should add the code to create a model object named `oModel` of type `sap.ui.model.odata.ODataModel`. Use the provided service `/sap/hana/democontent/epmNext/services/businessPartners.xsodata/`.

![model object](8.png)

```
var oModel = new sap.ui.model.odata.ODataModel("/xsodata/businessPartners.xsodata/", true);
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 9: ](Connect model to controller)]

In the second To-Do location in the `App.view.js` file, you should set the model named `bpModel` to the table control named `oTable`. Create a sorter (type `sap.ui.model.Sorter`) which uses the column `PartnerId`. Bind the table to the entity `BusinessPartners` and add the sorter object to the binding.

![table object](9.png)

```
var sort1 = new sap.ui.model.Sorter("PARTNERID");
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 10: ](Save and run the HTML5 module)]

That's all that is necessary to connect the Table UI element to the OData service.  We get built-in table sorting and filtering, as well as server-side scrolling via the various built-in parameters of the OData service framework. Save your files, run the HTML5 (`web`) module.

![run module](10.png)

Adjust the run URL to `/odataBasic/`.   

![run](11.png)
[DONE]
[ACCORDION-END]



## Next Steps
- [Use OData Metadata to dynamically create the columns](http://www.sap.com/developer/tutorials/xsa-sapui5-metadata.html)