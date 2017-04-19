---
title: SAPUI5 - Add a list to the view
description: Add a list view to a UI5 page
primary_tag: topic>sapui5
tags: [ tutorial>beginner, topic>html5, topic>sapui5, products>sap-cloud-platform ]
---
## Prerequisites  
- **Proficiency:** Beginner
- **How-To** [Start this tutorial series](https://www.sap.com/developer/tutorials/sapui5-webide-open-webide.html)
- **Tutorials:** This tutorial is part of a series.  The previous tutorial is part 3: [Set up the data source in the Application](https://www.sap.com/developer/tutorials/sapui5-webide-setup-datasource.html)

## Next Steps
- The next tutorial in the series is Part 5: [Enable Routing](https://www.sap.com/developer/tutorials/sapui5-webide-enable-routing.html)

## Details
### You will learn  
Add a list to first XML view (`View1.xml`). The list will display data from the data model, that got filled with data from the Northwind data service. Every list element will represent a product entity in the data model. Thanks to the data binding, SAPUI5 takes the path of the aggregation and automatically creates as many list items as the aggregation includes (all the product entities).

### Time to Complete
**15 Minutes**.

---
>  **Web IDE** If you don't have the Web IDE open, follow these steps: [Enable and open the SAP Cloud Platform Web IDE](https://www.sap.com/developer/tutorials/sapui5-webide-open-webide.html)


1.  Open the file `webapp/view/View1.view.xml` in your editor.  

    You will add a new `<List>` element, and define how every item will be displayed.

    ```XML
    <List items="{/Products}" >
		      press="handleListItemPress"
	```

    ![View1.view.xml file](1.png)


3.  Open the `webapp/controller/View1.controller.js` file.  You will add an event handler function for the press event.

    ```JavaScript
    return Controller.extend("HelloWorld.controller.View1", {
			sap.m.MessageBox.show(
				"You pressed item: " + evt.getSource().getBindingContext(), {
					icon: sap.m.MessageBox.Icon.INFORMATION,
					title: "It works!",
					actions: [sap.m.MessageBox.Action.OK]
				}
			);
	```

    ![style.css file](3.png)

    > **NOTE**:  See that alert box, red with the X?  That is a warning, and not an error.  The editor has detected that you are using Windows, and has noticed that the linefeed characters are not what it expected.  You can ignore this.

4.  Now **RUN** your application.  

    ![Running application with list view](4.png)

5.  Click on an item in your application, and a pop-up will appear.  

	 Notice that the pop-up displays the number of the item pressed, in parenthesis (in the image below: `Products(6)`).

    ![Alert pop-up](5.png)

## Next Steps
 - The next tutorial in the series is Part 5: [Enable Routing](https://www.sap.com/developer/tutorials/sapui5-webide-enable-routing.html)


## Additional Reading
- [Data Binding](https://sapui5.netweaver.ondemand.com/#docs/guide/68b9644a253741e8a4b9e4279a35c247.html)
- [`sap.m.MessageBox`](https://sapui5.netweaver.ondemand.com/sdk/#docs/api/symbols/sap.m.MessageBox.html)