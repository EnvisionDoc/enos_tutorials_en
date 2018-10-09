# Module 4: Querying device data with the API testing tool

This learning module aims to help you learn how to interact with your data in the EnOS™ Cloud using the EnOS APIs, such as logging in and querying the device properties, real-time and historical data and device alerts.

It doesn't matter even if you are unfamiliar with programming, as you can send requests to the platform automatically through the GUI-based API testing tool and obtain the desired results.

## EnOS™ API

The instructions for the open APIs of EnOS are listed under **API Service > EnOS APIs**, click **API Groups** to expand the APIs in the group, and then click **View details** to view the instructions on a specific API.

On the API details page, you can browse the use scenarios, input and output parameters, example of returned results, and sample java code for the API.

![](media/module_4_List_of_APIs.png)

*Figure 1. List of APIs*

![](media/module_4_Example_of_API_details.png)

*Figure 2. Example of API details*

## Using API testing tools

Under **API Service > API Test**, you can select the desired API and enter the parameters that are required for invoking this API, click  **Submit Test** and then the results of the API invocation is returned and shown on the right panel.

![](media/module_4_Example_of_API_testing.png)

*Figure 3. Example of API testing*

In this experiment, we will learn to call the following most frequently used APIs:

1.  The `login` API under the `UserService` category (logging in)
2.  The `getObjectAttributes` API under the `MdmServicecategory` (Querying the properties of a specific device)
3.  The `getmdmidspoints` interface under the `DomainService` category (Querying the latest real-time data of a specific device)
4.  The `detailsv2` interface under the `DomainService` category (Querying the historical data of a specific device during a specified period of time)
5.  The `getAlarmings` interface under the `EventService` category (Querying the events generated on a specific device)

Instructions on input of the parameters:

- **appKey**: Select **EnOS_Lab_Domain—enos_demo_app**，as described below:

    ![](media/module_4_select_EnOS_Lab_Domain.png)

    *Figure 4. Select EnOS_Lab_Domain—enos_demo_app as the appKey*

2.  **username** and **password**: enter your EnOS™ Console account name and the password.

3.  The **mdmid** of the device: you can find the **mdmid** of a device by accessing the **Asset Management > Data Preview** menu, clicking the device from the asset tree, and locating the **objectID** as shown in the following figure:

    ![](media/module_4_Query_the_device_mdmid_in_the_data_preview_tools.png)

    *Figure 5. Query the device mdmid in the data preview tool*
