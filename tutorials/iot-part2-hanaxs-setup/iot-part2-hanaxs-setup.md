---
title: Internet of Things (IoT) Setup SAP HANA XS (On-premise or stand-alone server)
description: Part 2 of 10, Setup and configure your initial SAP HANA XS application for use with your IoT Data
primary_tag: topic>internet-of-things
tags: [products>sap-hana, topic>big-data, topic>internet-of-things, tutorial>beginner ]

---

## Prerequisites  
- **Proficiency:** Beginner
- **Tutorials:** [Internet of Things (IoT) Setup the Tessel](http://www.sap.com/developer/how-tos/2016/09/iot-tessel.html)


## Next Steps
- [Internet of Things (IoT) Posting data with a REST Client](http://www.sap.com/developer/tutorials/iot-part3-posting-data-hana.html)

## Details
### You will learn  

You are now going to build a simple and quick SAP HANA XS application, if you already have experience doing this feel free to jump ahead as you feel fit.


### Time to Complete
**< 5 Min**.





![Repository View](p2_2.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Create application)]

Now you will need to right-click on your `myiot` package and choose **Create Application**.

![Package Creation](p2_4.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Accept defaults)]

Accept the default values, and an empty application with the basic `.xsapp` and `.xsaccess` files you need will be created.



>Be sure to use all capital letters for the schema filename

>Ensure you use all capital letters for the schema name

schema_name="JOHNDOE";
```


![Data definition](p2_8.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 9: ](Add content)]

Enter the following content in your `mydata.hdbdd` file, and replace instances of `johndoe` and `JOHNDOE` with the name you used.

```

@Schema: 'JOHNDOE'
context mydata {
type SDate : UTCTimestamp;
type tt_error {
 HTTP_STATUS_CODE: Integer;
 ERROR_MESSAGE: String(100);
 DETAIL: String(200);
};
type tt_details {
 ID: Integer;
TIMESTAMP: SDate;
TEMPERATURE: Decimal(9,5);
HUMIDITY: Double;
BRIGHTNESS: Double;
};

@Catalog.tableType : #COLUMN
Entity Data {
key ID: Integer;
TIMESTAMP: SDate;
TEMPERATURE: Decimal(9,5);
HUMIDITY: Double;
BRIGHTNESS: Double;
};

};  
```


```

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 14: ](Enter content)]

Enter the following content in your `.hdbprocedure` file, and replace instances of `johndoe` and `JOHNDOE` with the name you used.

```
IN row JOHNDOE."CODEJAMMER.johndoe.myiot::mydata.tt_details",
OUT error JOHNDOE."CODEJAMMER.johndoe.myiot::mydata.tt_error" )  
LANGUAGE SQLSCRIPT
SQL SECURITY INVOKER
DEFAULT SCHEMA JOHNDOE
AS
BEGIN
/*****************************
Write your procedure logic
*****************************/

declare lv_temperature string;
declare lv_humidity string;
declare lv_bright string;
select TEMPERATURE, HUMIDITY, BRIGHTNESS into lv_temperature, lv_humidity, lv_bright  from :row;

if :lv_temperature = ' ' then
error = select 400 as http_status_code,
'invalid date' as error_message,
  'Invalid response from sensor' as detail from dummy;
else
insert into "CODEJAMMER.johndoe.myiot::mydata.Data" values ("CODEJAMMER.johndoe.myiot::johndoe_id_seq".NEXTVAL, now(), CAST(lv_temperature AS decimal(9,5)), CAST(lv_humidity AS double), CAST(lv_bright AS double) );

end if;

END;

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 16: ](Add content)]

Enter the following content in your `.xsodata` file, and make the appropriate name changes. This file will provide us the ability to read data but also insert data into our table.

```
"JOHNDOE"."CODEJAMMER.johndoe.myiot::mydata.Data" as "HISTORY";
"JOHNDOE"."CODEJAMMER.johndoe.myiot::mydata.Data" as "DATA"
create using "CODEJAMMER.johndoe.myiot::newdata";
}
```

![New role](p2_11a.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 18: ](Add your name)]

Once created, click on **Object Privileges**, then the **+** sign. Enter your name (**JOHNDOE** used here) and a schema and sequence Object Type should appear in the Matching Items list.

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 19: ](Add the role)]

Select the schema item then click OK to add it to the role.

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 20: ](Select all privileges)]

Once the schema is added, select all the checkboxes under **Privileges** (on the right hand side).

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 21: ](Enter your name)]

Click the **+** sign again, enter your name again, select the sequence item and click **OK**. Once added, mark the SELECT checkbox under **Privileges**.

You will need to add your schema, table, sequence and procedure to this and then save.

![Sequence](p2_11c.png)

![Table](p2_11d.png)

![Procedure](p2_11e.png)


![User selection](p2_12.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 23: ](Select your role)]

Click the **+** symbol under the **Granted Roles** tab and search for the role you created (e.g. `johndoe`). Select your role, click **OK** and **Save**.
![Assign Role](p2_13.png)


[DONE]
[ACCORDION-END]



## Next Steps
- [Internet of Things (IoT) Posting data with a REST Client](http://www.sap.com/developer/tutorials/iot-part3-posting-data-hana.html)