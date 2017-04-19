---
title: Run and Test a Project in SAP HANA Smart Data Streaming
description: Part 7 of 9. Run and test the streaming project using Stream View, Manual Input, and Event Tracer tools.
primary_tag: products>sap-hana-smart-data-streaming
tags: [ tutorial>beginner, products>sap-hana-smart-data-streaming, products>sap-hana-studio ]
---
## Prerequisites  
 - **Proficiency:** Beginner
 - **Tutorials:** [Generating Alerts Using a Derived Window in SAP HANA Smart Data Streaming](http://www.sap.com/developer/tutorials/sds-part6-alerts.html)
 - **Files:** Download the [**`machinedata.csv`**](machinedata.csv) file, which will be use later for playback during testing.

## Next Steps
Either of the following tutorials may be done next:
 - **Tutorials:** [Watch for Patterns of Events and Use the CCL Editor in SAP HANA Smart Data Streaming](http://www.sap.com/developer/tutorials/sds-part8-patterns.html)
 - **Tutorials:** [Custom Flex Operators with Advanced CCL in SAP HANA Smart Data Streaming](http://www.sap.com/developer/tutorials/sds-part9-flex-operators.html)

## Details
### You will learn  
 - Running the project that you built in the previous exercises.
 - Using the Playback tool to simulate a live source and stream in data from a file at a controlled rate.
 - Using the Stream Viewer to view the output from each stream/window in your project.
 - Using the Manual Input tool to manually generate test events and send them into your project one at a time.
 - Using the Event Tracer tool to see how an event flows through the directed graph within the project.

### Time to Complete
**15 Min**.

---

#### Run the Project, Play Some Data and View Results

1. Go to **SAP HANA Streaming Development** perspective. Click the drop down arrow next to the **Run** button and select the streaming server to run this project. You will be switched into the **SAP HANA Streaming Run-Test** perspective after you have deployed and ran the project.

    ![run the project](runandplay/1-runtheproject.png)

2. Double-click on **`MACHINEDATA`** to open it in the **Stream View**.

    Note: You won't see any data, because we haven't loaded any data yet.

    ![go to stream view](runandplay/2-gotostreamview.png)

3. Now double-click on each of the other streams/windows to open them in the **Stream View** tool.

    ![open all tables](runandplay/3-openalltables.png)

4. Click the **Playback** tab.

    ![playback](runandplay/4-playback.png)

5. Click Select Project icon in the top right corner of the **Playback** window to connect the playback tool to the current project (if you had multiple projects running it would ask you to choose).

    ![select project](runandplay/5-selectproject.png)

6. Click Select Playback File icon shown below to select the data file to use.

    ![select playback file](runandplay/6-selectplaybackfile.png)

7. If you have not downloaded the playback data already, please download the **`machinedata.csv`** file included in the prerequisites. In the Open dialogue window, change the file type to **`.csv`**. Choose **`machinedata.csv`** included in this tutorial and then click **Open**. You can also press **Alt+o**.

    ![open file](runandplay/7-openfile.png)

8.  Click **rec/ms**. You want to control the playback speed so that you can watch things happen at a reasonable pace. Once it's running you can speed it up or slow it down using the slider tool. Enter `0.005` in the **rec/ms** box.

    ![rec per sec](runandplay/8-recpersec.png)

9. Then click the Start Playback button with icon shown below.

    ![play](runandplay/9-play.png)

10. Click each viewer tab to view the output from each stream/window.

    ![switch tabs](runandplay/10-switchtabs.png)

#### Use manual input and event tracer tools

1. Click the **Event Tracer** tab to select it. Click on the Select Running Project button to connect to a running project. if you have multiple projects running, it would prompt you to choose one.

    ![open event tracer](manualinput/1-openeventtracer.png)

2. Click the **Manual Input** tab.

    ![click manual input](manualinput/2-clickmanualinput.png)

3. Click **Select Stream** to connect the manual input tool to the project.

    ![select project](manualinput/3-selectproject.png)

4. Click on **MACHINEDATA** and then click **OK**.

    ![choose project](manualinput/4-chooseproject.png)

5. Fill out input fields as shown in the picture. Use one of the following as the **`MACHINEID`** since these are the existing values in the `"MACHINE_REF"` table that you are using: `2DDDBW3TP`, `EKM49RTXK`, `RB82KMY3S`, `4CBH7792RN`, `JMD51RTKK`, `GGR23RTXK`, or `8HRT4WX2`. You can alter the other values. Then click Publish button to send the event.

    ![fill info](manualinput/5-fillinfo.png)

6. The colors in the **Event Tracer** (at the top  of studio) diagram shows how each stream/window in the project is affected by the event you just sent. Double-click on each node to view the output generated by that node in response to the event in the Console.

    ![event tracer](manualinput/6-eventtracer.png)

7. Click the **Stream View** tab.

    ![stream view](manualinput/7-streamview.png)

8. Find the entry that you submitted through Manual Input.

    ![find the event](manualinput/8-findtheevent.png)


## Next Steps
Either of the following tutorials may be done next:
 - **Tutorials:** [Watch for Patterns of Events and Use the CCL Editor in SAP HANA Smart Data Streaming](http://www.sap.com/developer/tutorials/sds-part8-patterns.html)
 - **Tutorials:** [Custom Flex Operators with Advanced CCL in SAP HANA Smart Data Streaming](http://www.sap.com/developer/tutorials/sds-part9-flex-operators.html)