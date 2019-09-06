# EnOS device access method summary

## Connection methods


As shown below, generally the real-time device data can be connected to the EnOS™
platform in three ways:

- **To be connected via EnOS™ IoT Hub under MQTT protocol (cloud access service).**

  This requires the device end to support MQTT protocol and is applicable to most new devices of Internet of Things;

- **To be connected via EnOS™ Edge (Edge can be deployed locally or on the cloud).**

  This applies to access of most traditional devices and systems;

- **To be connected via EnOS™ Cloud Edge clusters (cloud access service).**

  This requires the device to be connected to bear a unique ID and uploading under communication protocol. This method is frequently used for photovoltaic device access;

- **Method 3: Connect through EnOS Cloud Edge clusters (cloud access service).**  

  This requires that the device to be connected has a unique ID and can upload data through supported communication protocols. This method is frequently used for photovoltaic device connection.

.. image:: media/device_connection_methods.png

## Matrix of scenarios applicable to different access methods

**Matrix of access scenarios:**

.. image:: media/Method_summary_Matrix_of_access_scenarios.png

**Description of various Edges:**

.. image:: media/Method_summary_Description_of_various_Edges.png

**List of Edge technical parameters:**

.. image:: media/Method_summary_List_of_Edge_technical_parameters.png

## EnOS™ device access solution example

### Scenario 1: photovoltaic monitoring application (the device is connected to the cloud via local Edge)

#### 1. Business background

An application developer plans to build a cloud-based distributed photovoltaic
monitoring application to realize central real-time monitoring of operation
conditions of different site photovoltaic devices at the cloud. The application
will also provide alarm and analysis services to facilitate effective management
and optimization of photovoltaic power generation assets.

This application developer, as a third party operator, is unable to modify the
inverter to be connected, and needs to adapt to various inverters in the market.

#### 2. MVP business analysis

Assumptions:

1. Two types of devices need to be connected: converter and electric meter. But
the brand and model of inverters and electric meters vary in different projects;

2. There is no third party system in the site, and the device data need to be
collected directly from EnOS™ cloud;

3. The total number of devices to be connected to a site does not exceed 20, and
each device collects data from 20 points on average, with an average sampling
cycle of 1 minute;

4. Both inverters and electric meters support standard Modbus-RTU protocols;

5. Wired network is available in the site for connection to the public network;

Analysis:

Due to the presence of multiple third-party devices, the communication system
can’t be varied. Therefore, data acquisition needs to be completed with Edge.

#### 3. MVP business construction

[Targeted at applications. All projects reuse this model.]

1. Device modeling (on EnOS™ cloud platform):

   Creation of photovoltaic domain – creation of photovoltaic site model – creation of inverter model, electric meter model;

   [Targeted at projects. Configuration is based on project conditions.]

2. Select an appropriate local Edge and install the software:

   Since each site has limited number of sampling points and limited sampling frequency, Edge hardware with a low configuration will be OK;

   Moreover, as the inverters and electric meters are connected via RS485 bus, a serial port server is required to achieve conversion from serial port to network port;

   Purchase an Edge based on the recommended list and install the Edge software;

3. Create a device template (on EnOS™ cloud platform):

   .. note:: Assume that there are 20 inverters of the same brand and the same model in the site, and there is a measurement electric meter, a device template for this inverter model and a device template for the electric meter should be created.

4. Connect the cloud (on EnOS™ cloud platform): Create cloud assets (model instantiation), Edge, connection configurations;

5. On-site wiring: 485 bus is used in the site to connect all inverters and electric meters serially in a daisy chain, and then connect to a serial port server;
   Connect the serial port server to Edge via wired network, and complete relevant configurations;

   Connect Edge to the wired network in the site, and ensure that Edge can be connected to the public network;

6. Communication test:

   Publish the cloud configuration to Edge and check communication to ensure all
device data have been correctly collected by the cloud.

   So far, the device data have been collected by the cloud. The next steps will be data acquisition, processing, and analysis via EnOS™ API with developed photovoltaic applications.

### Scenario 2: Home energy storage battery monitoring application (device connected directly to the cloud via MQTT protocol)

#### 1. Business background

A foreign home energy storage battery operator plans to build a cloud-based
battery monitoring system in order to realize central real-time monitoring of
operation conditions of different home energy storage batteries at the cloud.
The application will also provide alarm and analysis services.

The operator has its own energy storage batteries, and is able to develop and
modify batteries.

#### 2. MVP business analysis

Assumptions:

1. The battery has its own communication system, and the operator has the R&D
capability to modify external communication system of the batteries;

2. There is no third party system in the site, and the battery device is
connected directly to EnOS™ cloud platform;

3. There is a local wired network with access to public network connected to the
battery communication system;

Analysis:

As the operator has the capability and right to modify the device, it can
develop device self-registration service in the devices, and realize data
interaction through connection with cloud IoT Hub via MQTT protocol. As the
devices are standard, all devices have the same template. Therefore, the mapping
relationship can be directly fixed in the device configuration file. There is no
need to create a device template at the cloud.

#### 3. MVP business construction

1. Device modeling (on EnOS™ cloud platform):

   Create a home energy storage domain – create a home site model – create a
battery model;

2. Modify the device, develop self-registration services and integrate MQTT
Client:

   Modify the battery device, develop device self-registration service in PLC
(calling EnOS™ API via Web Service protocol), and integrate MQTT Client.
Determine MQTT parameters and relevant message structure based on platform MQTT
access standards. Download the license, device id, and key that have been
applied at the platform to the device as firmware. This will allow automatic
connection of the device to EnOS™ cloud platform on power-up.

3. After the battery is powered on and connected to the grid, it will be
automatically connect to EnOS™ cloud platform for device registration and asset
creation, and transmit the data already mapped to the model point to the cloud.

   So far the automatic connection and registration of the device have been
completed. The next steps will be data acquisition, processing, and analysis via
EnOS™ API with developed energy storage applications.

.. image:: media/Summary_of_device_access_home_page.png


<!--end-->
