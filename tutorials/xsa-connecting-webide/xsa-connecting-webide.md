---
title: SAP HANA XS Advanced, Connecting to the WebIDE and cloning a Git Repository to begin development
description: Part 1 of 3, Connect to Web IDE and Clone a Git Repository to begin development
primary_tag: products>sap-hana
tags: [  tutorial>beginner, topic>html5, products>sap-hana, products>sap-web-ide ]
---

## Prerequisites  
 - [How to create an SAP HANA Developer Edition in the Cloud](http://www.sap.com/developer/tutorials/hana-setup-cloud.html)

## Details
SAP HANA XS Advanced is the new development paradigm from SAP based around the Cloud Foundry concepts and architectures. To begin with you will need see how to connect to the SAP Web IDE for SAP HANA and clone a Git Repository.

As of SPS12, all design-time artifacts are stored in Git instead of the HANA database. We need to setup the repository so development can be collaborative.

### Time to Complete
**20 Min**

---

[ACCORDION-BEGIN [Step 1: ](Launch SAP Web IDE for SAP HANA)]

Launch the SAP Web IDE for SAP HANA at the following URL in your web browser. The `hostname` of course is the hostname of the SAP HANA Developer Edition that you created in the previous tutorial. Remember for XSA you will need to use the hostname and not the IP address of the server, instructions are found on the server landing page itself.

`http://<hostname>:53075/`

User: `WORKSHOP_01`
Password: `HanaRocks2016` or what you changed it to

or you can use

User: `CODEJAMMER`
Password: `CodeJam2016` or what you changed it to

For HANA Express Edition, if you have not setup an additional user, use `XSA_DEV` with the master password you entered during setup.

![Log in to SAP Web IDE for SAP HANA](1.png)

[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 2: ](Sign in to your Git account)]

From a separate tab in the web browser, log into [GitHub](https://GitHub.com). If you do not have an account, proceed to create one by following the instructions to create and activate your account in the **sign up** button.

![Sign in or sign up to your GitHub account](1_git.png)

> If you are setting up the repository for use beyond this tutorial, you may want to create an organization and invite other users to join your repository. Further information on GitHub can be found [on GitHub](https://help.github.com/articles/creating-a-new-repository/)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Create a GitHub repository)]

Whether you have just activated a newly-created account or have been using GitHub disconnected from a HANA workspace, you may wish to create a new repository for this tutorial. If you already have a  GitHub repository you would like to use, continue to Step 3.

Follow the instructions in the **New Repository** option from the **+** menu in the upper right corner on `GitHub.com`

![New Repository](2.png)

Complete the form, adding a name and description and click on **Create Repository**.
![New Repository](3.png)

[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 4: ](Clone the Repository into the Workspace)]

Form the GitHub page, copy the URL of the repository from the **Clone or Download** menu
![Use the Clone or Download button from the right corner](3_1.png)

Return to the SAP Web IDE for SAP HANA. Right click on the Workspace and choose **Clone Repository** from the Git menu.
![Clone Repository in Web IDE](4.png)

SAP Web IDE for SAP HANA will request all the necessary information to access the Git repository:
![Repository Cloning parameters](4_2.png)

URL: Paste the URL you copied from the GitHub page

Host and Repository Path will populate automatically by breaking down the URL.

Connection:
- Protocol: https
- Port: 443

Authentication:
- User:  `<Your GitHub User ID>`
- Password:  `<You've guessed: Your GitHub password!>`

Tick the **Remember me** box.

If successful, you will see the repository folder in your workspace, which is now connected to the git repository.
![Git is cloned into SAP HANA Web IDE](4_3.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Configure the Space for the repository)]

Last, you need to configure the space for the repository you have just linked.

>Introduced in SPS12, spaces enable applications to access shared resources that can be used to develop, deploy, and maintain applications.

Right-click on the folder for the repository and select **Project Settings**

![Project Settings for Git repository](5.png)

Select DEV - or development for HANA Express -  from the list of available spaces, or use the space setup by the System Administrator:

![Select DEV space](6.png)

Click **Save**.

[DONE]
[ACCORDION-END]


## Next Steps
 - [SAP HANA XS Advanced Creating an HTML5 Module](http://www.sap.com/developer/tutorials/xsa-html5-module.html)