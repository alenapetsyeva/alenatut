---
title: SAPUI5 User Interface
description: Creating a SAPUI5 user interface in XSA
primary_tag: products>sap-hana
tags: [  tutorial>intermediate, topic>html5, topic>odata, topic>sapui5, products>sap-hana, products>sap-hana\,-express-edition  ]
---
## Prerequisites  
- **Proficiency:** Intermediate
- **Tutorials:** [Creating an OData Service with Create Operation and XSJS Exit](http://www.sap.com/developer/tutorials/xsa-xsodata-create.html)

## Next Steps
- [Consume a Basic OData Service](http://www.sap.com/developer/tutorials/xsa-sapui5-odata.html)

## Details
### You will learn  
Now we want to build a proper SAPUI5 interface that will consume our XSJS and XSODATA services.

**Please note - This tutorial is based on SPS11**

### Time to Complete
**15 Min**.

---

[ACCORDION-BEGIN [Step 1: ](Create new HTML file)]

Return to your `web` module and create a new html file in the resources folder called `odataTest.html`

![new file](1.png)

Here is the complete coding of the `odataTest.html` page. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_1` You are loading the SAPUI5 `bootstap` and then initializing the Fiori shell.

```
<!DOCTYPE html>
```
[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Create `csrf.js`)]

There are two utility JavaScript libraries you reference in this html page &#151; `common/csrf.js` for the handling of CSRF tokens and `common/error.js` for producing error messages. Create a common folder in resources and add these two files.

![new files](3.png)

4. Here is the coding of `csrf.js` Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_2`

```
$.ajaxSetup({
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Create `error.js`)]


5. Here is the coding of `error.js` Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_3`

```
function onErrorCall(jqXHR, textStatus, errorThrown){
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Create optional images folder)]

You also reference some images in this HTML page. They aren't critical, but if you want you can create an images folder inside resources and then upload these images from our GIT repository.

![new images](6.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Create `Component.js`)]

Next you need to create your `Component.js` file. Here is the coding of this file. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_4` Here you initialize the SAPUI5 component and in doing so you create an instance of the JSON configuration model. You also load your first view which you will create in the next step. Finally you see that you make a call to `xsjs/exercisesMaster.xsjs` to fill the page header with the current user id.

```
jQuery.sap.declare("dev602.odataTest.Component");
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 6: ](Create `App.view.xml`)]

Create a folder called `odataView` inside resources. This is where you will hold all of your views and controllers. Create the root view named `App.view.xml`.

![new folder](8.png)

Here is the complete coding of the `App.view.xml` file. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_5` It creates the shell control and the overall flow of your page, but then defers the design of the header and table areas to an XML fragment we will create next.

```
<core:View controllerName="odataView.App" xmlns="sap.m"
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 7: ](Create `MRead.fragment.xml`)]

10. Create a file named `MRead.fragment.xml`. Here is the complete coding of this file. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_6` Here you build a panel with your input fields. These fields will allow you to control settings for calling your XSODATA service. You then will have a table control for your purchase order header and another for your purchase order item.  The rendering of these two sections are further separated out into two JavaScript based fragments.

```
<core:FragmentDefinition xmlns:core="sap.ui.core" xmlns="sap.m">
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 8: ](Create `MTableHead.fragment.js`)]

Create the `MTableHead.fragment.js` file. Here is the complete coding for this file. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_7` You are creating a table control to display our Purchase Order Header data which will be returned by the XSODATA service.

```
sap.ui.jsfragment("odataView.MTableHead", {
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 9: ](Create `MTableItem.fragment.js`)]

Repeat the process for the PO Item table. Filename `MTableItem.fragment.js`. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_8`

```
sap.ui.jsfragment("odataView.MTableItem", {
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 10: ](Create `App.controller.js`)]

The final piece of our UI is the view controller named `App.controller.js`. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602 &sub=ex4_9`

//To use a javascript controller its name must end with .controller.js


![run module](14.png)

In the running tab, you should see the `index.html` from earlier. Change this to `odataTest.html` to test the new UI you have created.

![results](15.png)

[DONE]
[ACCORDION-END]



## Next Steps
- [Consume a Basic OData Service](http://www.sap.com/developer/tutorials/xsa-sapui5-odata.html)