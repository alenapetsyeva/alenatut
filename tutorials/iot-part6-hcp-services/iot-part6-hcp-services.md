---
title: Internet of Things (IoT) Explore the SAP Cloud Platform IoT Services
description: Part 6 of 10, Setup and configure the use of the IoT Services with SAP Cloud Platform
primary_tag: topic>internet-of-things
tags: [products>sap-hana, products>sap-cloud-platform, topic>big-data, topic>internet-of-things, tutorial>beginner ]

---

## Prerequisites  
- **Proficiency:** Beginner
- **Tutorials:** [Internet of Things (IoT) Setup the Tessel](http://www.sap.com/developer/how-tos/2016/09/iot-tessel.html)


## Next Steps
- [Internet of Things (IoT) Adding a new device to the IoT Services](http://www.sap.com/developer/tutorials/iot-part7-add-device.html)

## Details
### You will learn  

This tutorial will detail the steps needed to simply the process of connecting your hardware device to SAP. As you saw in the previous section connecting our device directly to an SAP HANA server left plenty of room for errors as well as a number of security holes.


This procedure assumes you are using the trial edition of the SAP Cloud Platform, but you can use a production account if you have one.  

### Time to Complete
**15 Min**.

---


[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Open Internet of Things Services)] ￼

One you log in, click on **Services** in the left-hand navigation bar, scroll down to find **Internet of Things Services** and click on that tile.

![Services](p6_2.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Enable IoT the service)] ￼

Click on the **Enable** button. After a few seconds the page will update and show **Enabled**.

![Enable Service](p6_3a.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Open the service)] ￼

Once the service is enabled click the **Go to Service** link and a new browser tab will open.

![Access Service](p6_4.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Configure Message Management Service)] ￼

With IoT services enabled, you can begin the steps necessary to connect your device and enable message communication. The first step will be to configure and deploy the Message Management Service (MMS). Click on the **Deploy Message Management Service** tile.

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 6: ](Enter ID and user name)] ￼

Enter in your information in the fields, where your account ID is your p-number (or s-number if you are SAP's customer or partner, or i-/d-number if you are SAP employee) with the world "trial" (no space between the p-number and trial) and your user name is just your p-number.
![Deploy Service](p6_6a.png)

![Deployed application](p6_7.png)

![Authorizations](p6_8.png)


Then under **Individual Users**, click **Assign** and enter your SAP Cloud Platform user ID (e.g. your p-number without the word "trial" on the end).
- [Internet of Things (IoT) Adding a new device to the IoT Services](http://www.sap.com/developer/tutorials/iot-part7-add-device.html)