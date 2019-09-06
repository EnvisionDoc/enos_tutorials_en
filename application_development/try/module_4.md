# Module 4: Calling EnOS API

This learning module aims to help you learn how to interact with your data in the EnOS™ Cloud by calling EnOS API, such as logging in and querying the device properties, real-time and historical data and device alerts. With EnOS API, you can develop your own applications that consume your resources in the EnOS Cloud.

The sections below describe the major steps that you can follow to calll EnOS API:

1. Creating an application in EnOS Developer Center

2. Reading EnOS API documentation

3. Calling EnOS API

4. Testing and deploying the application

## Creating an application

Before calling EnOS API, you need to create an application in EnOS Developer Center. The application can be recognized as your identity as a developer. Log in EnOS Developer Center and go to the **Console** > **Application Management** page to create an application. After the application is created, an APP Key and APP Secret will be assigned to your application, which will be used for authorization and signature check when calling EnOS APIs.

## Reading EnOS API documentation

The documentation for each API can be found under **API Service** > > **EnOS APIs**. Expand **API Groups** to view APIs in each group, and then click **View details** to view details about an API, including API function, calling method, requesting URL, parameter description, calling sample, and response sample.

.. image:: media/module_4_List_of_APIs.png
   :alat: List of APIs

.. image:: media/module_4_Example_of_API_details.png
   :alt: Example of API documentation

## Calling EnOS API

EnOS API service provides an API testing tool for you to test calling APIs and debug errors. On the **API Service** > **API Test** page, select the API group, API name, and calling method, enter the parameters that are required for invoking the API, and click **Submit Test**. The result of the API invocation is returned in JSON format and shown on the right panel.

.. image:: media/module_4_Example_of_API_testing.png
   :alt: Example of API testing

When developing your application, you can either use the official SDK provided by EnOS or assemble HTTP requests manually to call EnOS API.

- **Use EnOS API SDK**: Official SDK provided by EnOS, supporting request URL assembling, signature generation, response parsing, and APP performance optimization. You are recommended to use EnOS API SDK. For detailed instructions, see [Using Java SDK to call EnOS API](/docs/enos-tutorials/en/latest/application_development/try/module_5.html).     

- **Assemble HTTP requests manually**: Wrap up API service URL, parameters, and signatures manually to assemble HTTP requests to call an API. For detailed instructions, see [EnOS REST API reference](/docs/enos/en/latest/rest_api_reference.html).

## Testing and deploying the application

EnOS provides a log tool to help you monitor the running status of your application. You can search for historical API calling requests by request ID, API name, or other keywords. When the application development and test is completed, you can deploy it online.
