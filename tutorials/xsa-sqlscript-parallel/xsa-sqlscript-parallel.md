---
title: Parallel Processing and Parameters
description: Leveraging SQLScript in Stored Procedures & User Defined Functions
primary_tag: products>sap-hana
tags: [  tutorial>intermediate, topic>sql, products>sap-hana, products>sap-hana\,-express-edition  ]
---
## Prerequisites  
- **Proficiency:** Intermediate
- **Tutorials:** [Creating Stored Procedures](http://www.sap.com/developer/tutorials/xsa-sqlscript-stored-proc.html)

## Next Steps
- [Intermediate Table Variables](http://www.sap.com/developer/tutorials/xsa-sqlscript-table-var.html)

## Details
### You will learn  
In this exercise we will modify the code of procedure `get_po_header_data`  so that it takes full advantage of the parallel processing within HANA by using table variables.
**Please note - This tutorial is based on SPS11**

### Time to Complete
**15 Min**.

---


[ACCORDION-BEGIN [Step 1: ](Edit previous procedure)]

Return to your procedure called `get_po_header_data`.

![Existing Procedure](1.png)

Define two tabular output parameters which will be used to explicitly pass the results of the SELECT statements to the caller.

![Define output](2.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Assign SELECT statements)]

Next, assign SELECT statements to the output parameters as shown here.

![assign select](3.png)

The completed code should be similar to this. If you do not wish to type this code, you can reference the solution web page at `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex2_11`

```
PROCEDURE "dev602.procedures::get_po_header_data" (
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Save and build)]

Save the procedure.

![Save Procedure](5.png)

Perform a build on the `hdb` module.

![Build Module](6.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Invoke the procedure again)]

Return to the HRTT page and invoke the procedure again.

![HRTT](7.png)

The CALL statement will be inserted into a new "SQL" tab

![Call statement](8.png)

Click the **Run** button

![Run](9.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Check execution time)]

Check the execution time again, you may notice that it is a bit faster this time. The reason is that these SQL statements are now executed in parallel.

![Check execution time](10.png)

[DONE]
[ACCORDION-END]




## Next Steps
- [Intermediate Table Variables](http://www.sap.com/developer/tutorials/xsa-sqlscript-table-var.html)