---
title: Creating an OData Service with Create Operation and XSJS Exit
description: Creating an OData Service with Create Operation and XSJS Exit
primary_tag: products>sap-hana
tags: [  tutorial>intermediate, topic>odata, products>sap-hana, products>sap-hana\,-express-edition  ]
---
## Prerequisites  
- **Proficiency:** Intermediate
- **Tutorials:** [Creating an OData Service with an Entity Relationship](http://www.sap.com/developer/tutorials/xsa-xsodata-entity.html)

## Next Steps
- [Tutorial Catalog](http://www.sap.com/developer/tutorial-navigator.html)

## Details
### You will learn  
Now to expand your code to include an XSJS exit.

**Please note - This tutorial is based on SPS11**

### Time to Complete
**10 Min**.

---


[ACCORDION-BEGIN [Step 1: ](Create new OData service)]

Create another OData service named `user2.xsodata` for `dev602.data::User.Details`. This time, also link the create operation to the Server Side JavaScript  Library (XSJSLIB) `xsjs::usersCreateMethod.xsjslib` and the function `usersCreate`. This will be the exit code that performs validation before the insert of the new record. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex3_12`

```
service namespace "dev602.services"{
```

[DONE]
[ACCORDION-END]  

[ACCORDION-BEGIN [Step 2: ](Create first XSJS library)]

In the `xsjs` folder create the file `usersCreateMethod.xsjslib`.  Here is the code for this file. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex3_13`

```
$.import("xsjs", "session");
```

[DONE]
[ACCORDION-END]  

[ACCORDION-BEGIN [Step 3: ](Create second XSJS library)]

Create another file in the `xsjs` folder named `session.xsjslib`. Here is the code for this file. Note: if you don't want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex3_14`

```
/**  
```

[DONE]
[ACCORDION-END]  

[ACCORDION-BEGIN [Step 3: ](Save and run)]

Save and run the Node.js and then the web module. Change the URL to `/xsodata/user2.xsodata` Unfortunately its much more complicated to test Create/Update/Delete methods from the browser as they create other HTTP verbs. Later we will build a user interface which can call this service in order to fully test it.

![Results](4.png)
[DONE]
[ACCORDION-END]  


## Next Steps
- [Tutorial Catalog](http://www.sap.com/developer/tutorial-navigator.html)