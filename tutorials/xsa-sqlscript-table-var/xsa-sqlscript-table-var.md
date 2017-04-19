---
title: Intermediate Table Variables
description: Leveraging SQLScript in Stored Procedures & User Defined Functions
primary_tag: products>sap-hana
tags: [  tutorial>intermediate, topic>sql, products>sap-hana, products>sap-hana\,-express-edition  ]
---
## Prerequisites  
- **Proficiency:** Intermediate
- **Tutorials:** [Parallel Processing and Parameters](http://www.sap.com/developer/tutorials/xsa-sqlscript-parallel.html)

## Next Steps
- [Creating Scalar User Defined Functions](http://www.sap.com/developer/tutorials/xsa-sqlscript-scalar.html)

## Details
### You will learn  
In this exercise you will modify the code of procedure `get_po_header_data` again to use a single tabular output. Existing queries will be reused based on intermediate table variables.
**Please note - This tutorial is based on SPS11**

### Time to Complete
**15 Min**.

---


[ACCORDION-BEGIN [Step 1: ](Edit previous procedure)]

Return to your procedure called `get_po_header_data`.

![Existing Procedure](1.png)

Delete the output parameters which you defined in the last section.

![Define output](2.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Define new output parameter)]

Define a new output parameter as shown

![New output](3.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Rename variables)]

Rename `EX_PO_CREATE_CNT` to `PO_CREATE_CNT`. Also rename `EX_PO_CHANGE_CNT` to `PO_CHANGE_CNT`

![change name](4.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Edit SELECT statements)]

Modify the two SELECT statements and add `AS EID` after the `EMPLOYEEID` field.

![modify select](5.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Add SELECT statement)]

Next, add another SELECT statement after the 2 previous SELECT statements as shown. This statement uses the previously defined table variables.

![add another select](6.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 6: ](Check complete code)]

The completed code should be very similar to this. If you do not wish to type this code, you can reference the solution web page at `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex2_12`

```
PROCEDURE "dev602.procedures::get_po_header_data" (

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 7: ](Save and build)]

Save the procedure

![save Procedure](7.png)

Use what you have learned already and perform a build on your `hdb` module.



[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 8: ](Run and view results)]

Return to the HRTT page and invoke the procedure.

![HRTT](8.png)

Click **Run**.

![Run](9.png)

The results are then shown.

![Results](10.png)

[DONE]
[ACCORDION-END]



## Next Steps
- [Creating Scalar User Defined Functions](http://www.sap.com/developer/tutorials/xsa-sqlscript-scalar.html)