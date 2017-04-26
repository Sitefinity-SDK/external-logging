External logging
============================

### This repository is not automatically upgraded to latest Sitefintiy version. The repository is monitored for pull requests and fixes. The latest official version of Sitefinity that supports this sample is 9.1. Be aware that using a higher version could cause unexpected behavior. If you successfully upgrade the example to a greater version, please share your work with the community by submitting your changes via pull request.

[![Build Status](http://sdk-jenkins-ci.cloudapp.net/buildStatus/icon?job=Telerik.Sitefinity.Samples.ExternalLogging.CI)](http://sdk-jenkins-ci.cloudapp.net/job/Telerik.Sitefinity.Samples.ExternalLogging.CI/)

As of Sitefinity CMS version 7.1, developers can implement their own custom error logger. This sample demonstrates error logging to an external application, which in this case is [Raygun.io](https://raygun.io/).

### Requirements 

* Sitefinity CMS license
* .NET Framework 4
* Visual Studio 2012
* Microsoft SQL Server 2008R2 or later versions
* Windows Identity Foundation
   NOTE: Depending on the Microsoft OS version you are using, the method for downloading and installing or enabling the identity framework differs:

  * **Windows 7** - download from [Windows Identity Foundation](http://www.microsoft.com/en-us/download/details.aspx?id=17331)
  * **Windows 8** - in the Control Panel, turn on the relevant Windows feature Windows Identity Foundation 3.5* Windows Identity Foundation

### Prerequisites

Clear the NuGet cache files. To do this:

1. In Windows Explorer, open the **%localappdata%\NuGet\Cache** folder.
2. Select all files and delete them.

You need a Raygun API key, in order to run this sample. To acquire a Raygun API key register in [Raugun.io](https://raygun.io/) and create a new application on your Raygun.io dashboard.

### Nuget package restoration
The solution in this repository relies on NuGet packages with automatic package restore while the build procedure takes place.   
For a full list of the referenced packages and their versions see the [packages.config](https://github.com/Sitefinity-SDK/external-logging/blob/master/ExternalLogging/packages.config) file.    
For a history and additional information related to package versions on different releases of this repository, see the [Releases page](https://github.com/Sitefinity-SDK/external-logging/releases).    


### Installation instructions

1. Clone the sample repository
2. Open your Sitefinity CMS application in Visual Studio.
3. From the context menu of the solution, select *Add* » *Existing project…*
4. Browse to the folder of the custom error trace listener
5. Select the ExternalLogging.csproj file
6. From the context menu of the *Reference* folder in your project, select *Add* » *References…*
7. Select the newly added **ExternalLogging** project
8. Open the **web.config** file of your Sitefinity CMS application and configure Raygun:
  * Add the following section to configSections: 
   ```<section name="RaygunSettings" type="Mindscape.Raygun4Net.RaygunSettings, Mindscape.Raygun4Net"/>```
  * Add the Raygun settings configuration block: 
   ```<RaygunSettings apikey="YOUR_APP_API_KEY" />```
  * **NOTE**: You can check the [Raygun GitHub readme](https://github.com/MindscapeHQ/raygun4net/blob/master/README.md) for additional information on how to configure your application's **web.config** file.
9. Build your solution

### Additional resources

#### Youtube video demo:

[![Tooltip](https://raw.githubusercontent.com/Sitefinity-SDK/external-logging/master/externalLogging.png)](http://youtu.be/-L_99f7UjZ8)

#### Progress Sitefinity CMS Documentation
[Tutorial: Create and enable a custom trace listener](http://docs.sitefinity.com/tutorial-create-and-enable-a-custom-trace-listener)
