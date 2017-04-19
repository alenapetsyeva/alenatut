---
title: Text Bundles within Node.js SAP HANA applications
description: Working with text bundles in Node.js
primary_tag: products>sap-hana
tags: [  tutorial>intermediate, products>sap-hana, products>sap-hana\,-express-edition  ]
---
## Prerequisites  
- **Proficiency:** Intermediate
- **Tutorials:** [Asynchronous Non-Blocking I/O](http://www.sap.com/developer/tutorials/xsa-node-async.html)

## Next Steps
- [Web Sockets](http://www.sap.com/developer/tutorials/xsa-node-websockets.html)

## Details
### You will learn  
Working with text bundles in Node.js

**Please note - This tutorial is based on SPS11**

### Time to Complete
**15 Min**.

---

[ACCORDION-BEGIN [Step 1: ](Add new module requirements)]

Return to the Node.js module and the `server.js` source file.

Begin by adding a new Node.js module requirements toward the beginning of the file. For a Node.js module named `./textBundle` which we will create in a moment.

```
"use strict";
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Add new route)]

Add a route for this module that corresponds to `/node/textBundle`

```
//Create base Express Server App
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Create `textBundle.js`)]

Create a new file in your `js` folder called `textBundle.js`.

![new file](4.png)

Add the following code to your `textBundle.js` file. It has implemented an HTTP handler for the root URL using express. In the processing of this handler use the `TextBundle` library. When creating a new `TextBundle` instance the input are path (value messages to point to your `message.properties` file) and locale which should call `getLocale` passing in the `req` object. Then write into the `res` object with the `TextBundle` `getText` function (passing in the text ID of greeting and two parameters of `os.hostname()` and `os.type()`.

```
"use strict";
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Import `i18n.zip`)]

Look at the `package.json` file in the editor. You will see the dependencies section which lists all required libraries and their versions. You manually added the `sap-textbundle` and `accept-language-parser` modules to the dependencies section.

```
"dependencies": {
```

You need a few text files to test with. Right mouse click on the `js` folder and choose `Import-> From` File System.  Choose the file `i18n.zip` from the Git repo. Keep all other settings at their default values.  Choose **OK**.

![import](7.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Run the `js` module)]

We can now run the `js` module.

![run](8.png)

You should see that the build and deploy was successful.

![success](9.png)

However if you go to the tab where the service run was started, you will see an 11. Unauthorized message just as in previous sections. This is as intended.

![unauthoirzed](10.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 6: ](Run the web module)]

So now run the `web` module.

![web module](11.png)

In the running tab, you should see the `index.html` from earlier.  

![running tab](12.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 7: ](Test the module)]

Now change the path in the browser to `/node/textBundle`.  You should see the English message output from your text file in the `i18n` folder.

![new path](13.png)

In order to test the translated strings, go into the browser Settings. Search for Lang and then choose the Language and input settings button.

![broswer settings](14.png)

Drag and drop to raise German to the top of the list

![drag drop](15.png)

Refresh the web browser and you should now see the German text.

![refresh](16.png)

Repeat the process raising Japanese `[ja]` to the top of the list and refresh the web page

![new language](17.png)

[DONE]
[ACCORDION-END]


## Next Steps
- [Web Sockets](http://www.sap.com/developer/tutorials/xsa-node-websockets.html)