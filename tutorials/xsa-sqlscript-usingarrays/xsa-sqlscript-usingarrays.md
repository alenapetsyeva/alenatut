---
title: Using Arrays
description: Leveraging SQLScript in Stored Procedures & User Defined Functions
primary_tag: products>sap-hana
tags: [  tutorial>intermediate, topic>sql, products>sap-hana, products>sap-hana\,-express-edition  ]
---
## Prerequisites  
- **Proficiency:** Intermediate
- **Tutorials:** [Using Cursors](http://www.sap.com/developer/tutorials/xsa-sqlscript-usingarrays.html)

## Next Steps
- [Using Index-based Cell Access](http://www.sap.com/developer/tutorials/xsa-sqlscript-usingindexbased.html)

## Details
### You will learn  
This solution shows how to use Arrays data iteration as well as the result creation.
**Please note - This tutorial is based on SPS11**

### Time to Complete
**15 Min**.

---

[ACCORDION-BEGIN [Step 1: ](Edit previous procedure)]

Return to the procedure called `calculate_cumulative_sum_of_delivered_products`.

![prcoedure editor](1.png)

Delete all of the logic in the body of the procedure

![delete logic](2.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Add DECLARE statements)]

Enter the following DECLARE statements. Notice here you are declaring 4 arrays.

![declare statements](3.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Add column to array)]

Next, use the `ARRAY_AGG` statement to extract a column of the table into an array

![aaray_agg statement](4.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Insert values into array)]

Use a FOR loop to perform the calculation and insert the value into the array

![for loop](5.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Add UNNEST)]

Finally, use the UNNEST statement to render the arrays into the output table parameter.

![unnest statement](6.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 6: ](Check completed code)]

The completed code should look like the following. If you do not wish to type this code, you can reference the solution web page at `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex2_22`

```
PROCEDURE "dev602.procedures::calculate_cumulative_sum_of_delivered_products" (
```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 7: ](Save and build)]

8. Click **Save**.

![save](8.png)

9. Use what you have learned already and perform a build on your `hdb` module.

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 8: ](Run the call statement)]


Return to the HRTT page and run the call statement again.

![HRTT](9.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 8: ](Check results)]

Check the results.

![results](10.png)

Notice the execution time is a little bit less than when doing the calculation using SQL, and a lot less than when doing the calculation using cursors.

![execution time](11.png)

[DONE]
[ACCORDION-END]




## Next Steps
- [Using Index-based Cell Access](http://www.sap.com/developer/tutorials/xsa-sqlscript-usingindexbased.html)