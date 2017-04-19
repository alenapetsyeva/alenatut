---
title: Enable SAP Cloud Platform mobile services for development and operations
description: Enable and configure the mobile services for development and operations in SAP Cloud Platform
primary_tag: topic>mobile
tags: [products>sap-cloud-platform, topic>cloud, topic>mobile, tutorial>intermediate ]
---
## Prerequisites  
- **Proficiency:** Intermediate

## Next Steps
- [Create an app in SAP Cloud Platform mobile services](http://www.sap.com/developer/tutorials/hcpms-create-hybrid-app.html)

## Details
### You will learn  
In this tutorial, you will enable and configure SAP Cloud Platform mobile services for development and operations in your trial account.  Once configured, you can use mobile services to run hybrid and native apps on SAP Cloud Platform

### Time to Complete
**5 Min**.

---

[ACCORDION-BEGIN [Step 1: ](Log into SAP Cloud Platform Cockpit)]

Go to your [SAP Cloud Platform Cockpit](https://account.hanatrial.ondemand.com) and log on.

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Enable Development & Operations)]

From the SAP Cloud Platform Cockpit page, click **Services** in the navigation bar, scroll down until you see the Mobile Services group then click on the **Development & Operations** tile.

![Subscriptions tab](mg5-1-02.png)

If Development & Operations is not enabled, click on the blue **Enable** button and wait a few seconds until the green **Enabled** badge appears. Return to the cockpit by clicking on your User ID "breadcrumb" link near the top left of the browser window.

![Enable HCPms](mg5-1-03.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Add admin role)]

You will need to add an `Admin` role to Development & Operations. To do so, click on the **Configure Development & Operations** link.

![Configure Development & Operations](mg5-1-04.png)

Then, click on the **Roles** tab, select **Administrator** under **New Role** then click on **Assign** next to **Individual Users**.

![Role configuration](mg5-1-05.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Assign the role)]

Enter your User ID (e.g. `p12345678`) then click **Assign**. Notice that the dialog box shows the role name you are assigning.

![Role assignment](mg5-1-06.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Check roles page)]

Your Roles page should look similar to this now:

![Role assigned](mg5-1-07.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 6: ](Create destinations)]

The next step is to create two SAP Cloud Platform Destinations. To display the navigation bar, click on your **User ID** link again (near the top left of the window), click on the **Destinations** tab, then click on **New Destination**.

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 7: ](Populate first destination)]

For the first Destination, complete the form with the info below, and click Save.

Field Name                | Value
:------------------------ | :-------------
Name                      | `HMAdminJaxrs`
Type                      | `HTTP`
Description               |`<you can leave this blank>`
URL                       | `https://hcpms-trial.hanatrial.ondemand.com/Admin/`
Proxy Type                | `Internet`
Authentication            | `AppToAppSSO`

Make sure the "Use default JDK truststore is checked.

![Destination 1](mg5-1-10.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 8: ](Populate second destination)]

For the second Destination, complete the form with the info below, and click Save.

Field Name                | Value
:------------------------ | :-------------
Name                      | `HMAdminHandlers`
Type                      | `HTTP`
Description               |`<you can leave this blank>`
URL                       | `https://hcpms-trial.hanatrial.ondemand.com/Admin/AdminData`
Proxy Type                | `Internet`
Authentication            | `AppToAppSSO`

Make sure the "Use default JDK truststore is checked.

![Destination 2](mg5-1-11.png)

[DONE]
[ACCORDION-END]


## Next Steps
- [Create an app in SAP Cloud Platform mobile services](http://www.sap.com/developer/tutorials/hcpms-create-hybrid-app.html)
