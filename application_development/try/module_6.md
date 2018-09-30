# Module 6: Creating a form and development of offline workflows

## Creating new Hive tables with Data Explorer

This job aims to create the hive forms used to store the data of the meters and
sites, as described below:

1.  Enter the **Data Explorer** module and create a new hive worksheet:

    ![](media/module_6_Create_a_new_worksheet_in_the_Data_Explorer.png)

    *Fig. Create a new worksheet in the Data Explorer*

2.  Enter the worksheet and create a new dw_meter_1h form

-   The statements for constructing the new form are described as follows as an
    example( If this form is used, please change the name *dw_meter_1h_demo*，which shall be different from that of the example):
    ```
    %hive
    DROP TABLE IF EXISTS dw_meter_1h_demo;
    CREATE TABLE dw_meter_1h_demo(
       device_id string,
       site_id string,
       ts timestamp,
       hour int,
       energy double,
       max_power double)
    PARTITIONED BY (
       yyyymmdd string)
    ROW FORMAT DELIMITED
       FIELDS TERMINATED BY '\\t'
    STORED AS ORC
    ```
    After completion of constructing the form, queries shall be made to make sure if it is successful, as described as below:

    ![](media/module_6_queries_successful.png)

    <body>
    <table border="1" cellspacing="0" cellpadding="0" width="692">
      <tr>
        <td width="692" nowrap colspan="7" valign="top"><strong>hive: dw_meter_1h Sample   Data </strong></td>
      </tr>
      <tr>
        <td width="132" nowrap valign="top"><strong>device_id </strong></td>
        <td width="132" nowrap valign="top"><strong>site_id </strong></td>
        <td width="144" nowrap valign="top"><strong>ts </strong></td>
        <td width="53" nowrap valign="top"><strong>hour </strong></td>
        <td width="58" nowrap valign="top"><strong>energy </strong></td>
        <td width="88" nowrap valign="top"><strong>max_power </strong></td>
        <td width="84" nowrap valign="top"><strong>yyyymmdd </strong></td>
      </tr>
      <tr>
        <td width="132" nowrap valign="top">1c7cd59561002000</td>
        <td width="132" nowrap valign="top">1c7cd5955e000000</td>
        <td width="144" nowrap valign="top">2018-08-10 00:00:00.0</td>
        <td width="53" nowrap valign="top">0</td>
        <td width="58" nowrap valign="top">75.8</td>
        <td width="88" nowrap valign="top">81</td>
        <td width="84" nowrap valign="top">20180810</td>
      </tr>
    </table>
    </body>


3.  Creating new dw_site_1h forms

-   The statements for constructing the new form are described as follows as an
    example( If this form is used, please change the name dw_meter_1h_demo，which shall be different from that of the example):
    ```
    DROP TABLE IF EXISTS dw_site_1h_demo;
    CREATE TABLE dw_site_1h_demo(
       site_id string,
       ts timestamp,
       hour int,
       energy double,
       max_power double)
    PARTITIONED BY (
       yyyymmdd string)
    ROW FORMAT DELIMITED
       FIELDS TERMINATED BY '\\t'
    STORED AS ORC
    ```

    <body>
    <table border="1" cellspacing="0" cellpadding="0" width="692">
      <tr>
        <td width="692" nowrap colspan="6" valign="top"><p><strong>hive:   dw_site_1h Sample Data </strong></p></td>
      </tr>
      <tr>
        <td width="161" nowrap valign="top"><p><strong>site_id </strong></p></td>
        <td width="170" nowrap valign="top"><p><strong>ts </strong></p></td>
        <td width="66" nowrap valign="top"><p><strong>hour </strong></p></td>
        <td width="64" nowrap valign="top"><p><strong>energy </strong></p></td>
        <td width="97" nowrap valign="top"><p><strong>max_power </strong></p></td>
        <td width="135" nowrap valign="top"><p><strong>yyyymmdd </strong></p></td>
      </tr>
      <tr>
        <td width="161" nowrap valign="top"><p>1c7cd5955e000000</p></td>
        <td width="170" nowrap valign="top"><p>2018-08-10 00:00:00.0</p></td>
        <td width="66" nowrap valign="top"><p>0</p></td>
        <td width="64" nowrap valign="top"><p>638.23</p></td>
        <td width="97" nowrap valign="top"><p>678</p></td>
        <td width="135" nowrap valign="top"><p>20180810</p></td>
      </tr>
    </table>
    </body>

## Synchronizing the main data and creating forms with "Job Development"

The job aims to synchronize the main data of the meters to the hive and create
the corresponding hive form so as to obtain the descriptions of the electrical
meters (Name), as described as below:

1.  Enter **Data Development Suite \> Job Development**, double click "Main Data
    Synchronization V0.1.2", where the roles and application of the SDK are
    detailed, as described below:

    ![](media/module_6_Instructions_on_the_SDK_for_Main_Data_Synchronization.png)

    *Fig. Instructions on the SDK for Main Data Synchronization*

2.  Click **Apply this method**, input the name of your program (the suffix "demo"
    may be changed to your program name, which shall not be identical with that
    of other programs), select **/Workflow/Practice**, as described below:

    ![](media/module_6_select_WorkflowPractice.png)

3.  The job parameters are configured as described below:

    ![](media/module_6_job_parameters.png)

    The parameters are as follows:
    ```
    mdmID=1c750ed055000000
    path=/user/db_owner_enos_training/cim
    domain=198
    overwrite=true
    ```

4.  Publish and pre-run the job.

## Synchronize the form structures with "Job Development"

The job aims to synchronize the form structures in the hive automatically to the
relational databases for reports using the sdk on the platform for the purpose
of creating new forms, which may avoid creating new forms by writing SQL
statements on your own.

The forms required to be synchronized to the report databases include:

-   dw_meter_1h(data sheets for the electrical meters);

-   dw_site_1h ( Site data sheets);

-   icat_c6_meter (Main data sheets for the electrical meters);

-   icat_c6_site (Site main data sheets);

1.  Enter **Data Development Suite \> Job Development**, double click "Report
    Database Synchronization V0.1.1", where the roles and application of the SDK
    are detailed, as described below:

    ![](media/module_6_Synchronization_of_report_database_structures.png)

    *Fig. Synchronization of report database structures*

2.  Click **Apply this method**, input the name of your program (the suffix "demo"
    may be changed to your program name, which shall not be identical with that
    of other programs), select **/Workflow/Practice**, as described below:

    ![](media/module_6_select_WorkflowPracticeapplymethod.png)

3.  Configure the parameters

    ![](media/module_6_confi_gramm.png)

    The parameters are as follows:

    tablename= dw_meter_1h_demo( *Note: Please do fill in your form name here.*). In this
example, synchronization of 4 forms are required, one form each time:

    dw_meter_1h_demo ( Data sheets for the electrical meters);

    dw_site_1h_demo(Site data sheets;

    icat_c6_meter_demo (Main data sheets for the electrical meters);

    icat_c6_site_demo(Site main data sheets).

4.  Publish and pre-run the job.

    Please do repeat the above-mentioned operations and synchronize all the form structures required.

## Adding main keys for the report databases with Data Explorer

This job aims to add the main keys for the report databases to avoid repeated
records arising from regular synchronization.

1.  Enter the **Data Explorer** module, create a worksheet of mysql_report type,
    as described below:

    ![](media/module_6_Creating_a_new_mysql_report_type_worksheet.png)

    *Fig. Creating a new mysql_report type worksheet*

2.  The main keys are added to the 4 forms respectively, among which:

    · device_id and ts are used as the main keys for the form dw_meter_1h_demo;

    · site_id and ts are used as the main keys for the form dw_site_1h_demo;

    · \_objectid is used as the main key for the form icat_c6_meter_demo;

    · \_objectid is used as the main key for the form icat_c6_site_demo;

    Take the main key codes for the form dw_meter_1h_demo as an example described below:

    ```
    ALTER TABLE dw_meter_1h_demo ADD PRIMARY KEY (device_id,ts)
    ```

    Upon completion, view the descriptions of the form for confirmation, the code example of which are described as follows:
    ```
    desc dw_meter_1h_demo
    ```
    ![](media/module_6_Adding_main_keys_to_the_form_dw_meter_1h_demo.png)

    *Fig. Adding main keys to the form dw_meter_1h_demo*
