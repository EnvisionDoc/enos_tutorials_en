# Module 5: Writing a Java program to call the EnOS™ API

This session of the experiment aims to enable you to gain experience in
interacting with the platform using the EnOS™ APIs, e.g., logging in and querying
the device properties, real-time and historical data and device alerts, etc.

Compared with the previous session of the experiment, the difference of this
session lies in the fact that you are required to write Java codes using the
Java SDK of the EnOS™ APIs to achieve the calling of the APIs.

## Preparation of the experimental environment

### SDK downloading

1.  JDK: jdk 1.8.0;

2.  The relevant SDK of the EnOS™ API;

The platform SDK that this experiment relies on can be downloaded from the SDK
of the EnOS™ Portal at the following [address](https://dev.envisioncn.com/devportal/index.html#/168/57baab5ed3eb4806104b045d/consoleMenu1):


![](media/module_5_SDK.png)

Two SDKs are required in this experiment: EnOS API V0.1.47” and " Log SDK V1.1",
which can be downloaded at the above-mentioned address and added to your own
java project.

### Development environment

In this experiment, the IntelliJ IDEA integration development environment is
recommended for the Maven Project.

## Operational instructions

### Creating a new Maven project

Select **File\>New\>Project**, check **Create from archetype**, select the
*org.apache.maven.archetypes:maven-archetype-quickstart* template, and then
click **Next**, as described below:

![](media/module_5_Create_from_archetype.png)

GroupId and ArtifactId are used to uniquely identify a project, the GroupId is
filled in with the reversed domain name, and for the ArtifactId, the project
name will do. The following is an example, which may be adjusted according to
your specific conditions. Click **Next** , as described below:

![](media/module_5_GroupId_ArtifactId.png)

The default settings may be used for User setting file, then click **Next** , as
described below:

![](media/module_5_setting_files.png)

The default settings may be used for the project name, then click **Finish**, as
described below:

![](media/module_5_finish.png)

### Configuring Project DependencIES

1.  Right click your Project, select Open Module Settings, as described below:

    ![](media/module_5_open_module_settings.png)

2.  Select **Dependencies** , click       ![](media/module_5_addbutton.png), and add the sdks related to the EnOS API here:

    The sdks related to EnOS™ required for this experiment include:

    `eeop-0.1.45.jar;`

    `logsdk-logger-1.2-SNAPSHOT.jar`

    ![](media/module_5_logsdk-logger-1.2-SNAPSHOT.png)

    ![](media/module_5_logsdk-logger-1.2-SNAPSHOT_2.png)

3.  Add the following dependencies to the POM files for your project:
    ```
        \<dependency\>

          \<groupId\>org.slf4j\</groupId\>

          \<artifactId\>slf4j-api\</artifactId\>

          \<version\>1.7.9\</version\>

          \</dependency\>
    ```  

    ![](media/module_5_logsdk-logger-1.2-SNAPSHOT_3.png)

### Writing the Java codes

You are required to achieve the following functions:

1.  Logging in;

2.  Acquiring the list of sites/devices with permissions under the developer's
    account;

3.  Acquiring the main data of the specified mdmid devices;

4.  Acquiring the real-time data of the specified mdmid devices;

5.  Acquiring the historical data of the specified mdmid devices.

The corresponding results are only required to be printed onto the console.



You may use our example codes for reference:

![](media/module_5_logsdk-logger-1.2-SNAPSHOT_4.png)
