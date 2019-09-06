# Module 1: Logging in and Browsing through the EnOS Console

This module aims to give you an overview of the EnOS™ Console.

## Log in to the EnOS™ Console

Visit the EnOS Console through: <https://dev.envisioncn.com/devportal/>

.. note:: If you don't have an EnOS username yet, request your username and password from the training teacher.

.. image:: media/module_1_EnOS_Portal.png

## Browse the menus of the EnOS™ Console

The following table walks you through the menus in the EnOS™ Console and their major functions. The modules to use and the access rights required in this experiment are indicated in the last column.

The letters **R**, **W** and **N** used for marking herein refer to **Read**, **Write** or **Not Required** respectively.

.. list-table::
   :widths: auto

   * - Menu
     - Submenu
     - Main functions
     - This experiment
   * - Asset Management
     - \
     - \
     - \
   * - \
     - Sites and Devices
     - Creating and managing the assets and devices
     - R
   * - \
     - Asset tree
     - Configuring the hierarchy of assets
     - R
   * - --
     - Device Connections
     - Configuring device connections through MQTT
     - N
   * - --
     - Edge Connections
     - Configuring debugging the Edge connection
     - N
   * - --
     - Templates
     - Configuring device connections through Edge
     - N
   * - \
     - Device monitoring
     - Monitoring the data access by roll back the uploaded device data
     - R
   * - \
     - Data Preview
     - Device data accessed to the organization can be viewed
     - R
   * - \
     - Device simulator
     - Simulating the status of the accessed devices
     - N
   * - Protocol Center
     - None
     - Managing the communication protocols on the platform
     - N
   * - Model Center
     - \
     - \
     - \
   * - \
     - Viewing the configuration of models
     - Showing the definitions of all models
     - N
   * - \
     - Device Model Center
     - Creating and Managing device models
     - R
   * - Event Management
     - \
     - \
     - \
   * - \
     - Triggering Rules
     - Configuring event triggering rules f
     - R/W
   * - \
     - Event Groups
     - Configuring event groups
     - R/W
   * - \
     - Event Contents
     - Configuring the contents to display in the alerts
     - R/W
   * - Stream Service
     - None
     - Uploading the stream computing packages
     - N
   * - Applicaitons Managment
     - None
     - Creating App records
     - R
   * - API Service
     - \
     - \
     - \
   * - \
     - EnOS™ API
     - EnOS™ API References
     - R
   * - \
     - Public APIs
     - 3rd-party public APIs
     - N
   * - \
     - My API
     - The custom APIs of my organization
     - N
   * - \
     - API Test
     - Testing API invocation and showing the results
     - R/W
   * - BI & Reports
     - \
     - \
     - \
   * - \
     - Getting Started
     - Displaying the reports and statistics of my organization
     - R
   * - \
     - Data
     - Creating datasets from data sources to be used for the reports
     - R/W
   * - \
     - Reports
     - Creating and managing the BI reports
     - R/W
   * - Data Explorer
     - None
     - An online notebook for writing the scripts to interact with the relational databases of the hive and BI reports on the platform, and for adding, deleting, modifying and querying the data
     - R/W
   * - Data Integration
     - None
     - mporting the data from an external source into the platform
     - N
   * - Data IDE
     - \
     - \
     - \
   * - \
     - Task Designer
     - Developing batch processing workflows
     - R/W
   * - \
     - Resource Management
     - Centralize the --management of the resources that are used for batch processing
     - R/W
   * - Data Operation and Maintenance
     - None
     - Showing the status and logs of batch data processing workflows
     - R/W
   * - Data Source
     - None
     - Configuring connections to external data sources
     - N

Among them, you can access the data of the 3 electrical meters collected from
the simulators, through **Asset Management > Data Viewing Tools** as shown in
the following figure. The subsequent experiments will center on these data.

.. image:: media/module_1_Realtime_data_of_Analog_Device_Meter01.png
   :alt: Fig. Real-time Data of Analog Device Meter01

.. image:: media/module_1_Visualizing_business_statistical_indicators.png
   :alt: Fig. One-day Historical Data Trend of the Current Point EMT. Ia of Analog Device
   Meter01

<!--end-->
