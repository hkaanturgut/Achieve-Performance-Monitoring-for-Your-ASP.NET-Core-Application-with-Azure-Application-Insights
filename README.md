# Achieve Performance Monitoring for Your ASP.NET Core Application with Azure Application Insights

![Azure Application Insights](https://img.shields.io/badge/Azure-Application%20Insights-blue)

## Overview

This repository contains a step-by-step guide to integrate Azure Application Insights into your ASP.NET Core application for tracking and monitoring its performance. Azure Application Insights is a powerful Application Performance Management (APM) service within Azure Monitor, provided by Microsoft Azure. It enables you to monitor live application performance and gain valuable insights into your app's behavior.

## Getting Started

To get started with integrating Azure Application Insights into your ASP.NET Core application, follow these 5 simple steps:

### Step 1: Creating a New Application Insights Instance in Azure Portal

1. Access the [Azure Portal](https://portal.azure.com/) and search for "Application Insights."
2. Once on the Application Insights page, click on "Create" and fill in the required details in the form.
3. Click "Review + Create," and in a few minutes, your Application Insights instance will be created.
4. You can choose the region closest to your web app-hosted location and create a new resource group if needed.

![Screenshot 2023-07-31 at 6 18 19 AM](https://github.com/hkaanturgut/Achieve-Performance-Monitoring-for-Your-ASP.NET-Core-Application-with-Azure-Application-Insights/assets/113396342/d00a3cbf-1898-401b-9124-79bd947d7b5c)


### Step 2: Setting up Your ASP.NET Core MVC Application for Monitoring

1. Open your ASP.NET Core project in Visual Studio.
2. Search for the "Microsoft.ApplicationInsights.AspNetCore" Nugget Package and install it.

![Screenshot 2023-07-31 at 5 52 40 AM](https://github.com/hkaanturgut/Achieve-Performance-Monitoring-for-Your-ASP.NET-Core-Application-with-Azure-Application-Insights/assets/113396342/bd5b6e36-a388-44e7-b6ec-21b76ab64757)

3. Ensure you have the following prerequisites:
   - A functioning ASP.NET Core application (if you don't have one, you can create one using the ASP.NET Core tutorial).
   - A reference to a supported version of the Application Insights NuGet package.
   - A valid Application Insights connection string to send telemetry data to Application Insights. If you don't have one, you can create a new Application Insights resource to obtain the connection string.
  
![Screenshot 2023-07-31 at 6 22 05 AM](https://github.com/hkaanturgut/Achieve-Performance-Monitoring-for-Your-ASP.NET-Core-Application-with-Azure-Application-Insights/assets/113396342/8f74fb8b-cf94-4450-80e9-24abba5486f7)


### Step 3: Enable Application Insights Server-Side Telemetry

#### Using Visual Studio:
1. Open your project in Visual Studio.
2. Go to "Project" > "Add Application Insights Telemetry."
3. Select "Azure Application Insights" > "Next."
4. Choose your subscription and existing Application Insights instance or create a new one using "Create new."
5. Add or confirm your Application Insights connection string and select "Finish."
6. After adding Application Insights to your project, ensure you are using the latest stable release of the SDK by going to "Project" > "Manage NuGet Packages" > "Microsoft.ApplicationInsights.AspNetCore." Update it if needed.

#### Without Visual Studio:
1. Install the Application Insights SDK NuGet package for ASP.NET Core. Use the latest stable version for optimal performance.
2. In your project's .csproj file, add the following code under `<ItemGroup>`:

```XML
<PackageReference Include="Microsoft.ApplicationInsights.AspNetCore" Version="2.21.0" />

`````
1. In your startup.cs or program.cs class, add the following line to enable telemetry collection:
For ASP.NET Core 6 and later:

```
var builder = WebApplication.CreateBuilder(args);
builder.Services.AddApplicationInsightsTelemetry();
builder.Services.AddMvc();
var app = builder.Build();
```

![Screenshot 2023-07-31 at 6 17 08 AM](https://github.com/hkaanturgut/Achieve-Performance-Monitoring-for-Your-ASP.NET-Core-Application-with-Azure-Application-Insights/assets/113396342/39126967-bc57-45b8-9a23-c2d16ecccf78)

#### Step 4: Set Up the Connection String
You have two options to specify the connection string:

**Option 1:** Specify the connection string in the "appsettings.json" configuration file:

```
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",
  "ApplicationInsights": {
    "ConnectionString": "Copy connection string from Application Insights Resource Overview"
  }
}
```
![Screenshot 2023-07-31 at 6 21 53 AM](https://github.com/hkaanturgut/Achieve-Performance-Monitoring-for-Your-ASP.NET-Core-Application-with-Azure-Application-Insights/assets/113396342/00370217-2d3d-44d7-aa6a-6fbb329242aa)

**Option 2:** Specify the connection string in the

"APPLICATIONINSIGHTS_CONNECTION_STRING" environment variable or 

"ApplicationInsights:ConnectionString" in the JSON configuration file.

#### Step 5: Complete the Setup
With the connection string in place, your setup is complete! Now you can run your application and explore logs and live metrics in the Azure Portal.

### Monitoring Your Application
In the Azure Portal, you can take advantage of features like live tracking and performance monitoring to gain insights into your application's behavior. Watch your app perform like a pro!

**Live Metrics**

![Screenshot 2023-07-31 at 6 24 50 AM](https://github.com/hkaanturgut/Achieve-Performance-Monitoring-for-Your-ASP.NET-Core-Application-with-Azure-Application-Insights/assets/113396342/85085acb-98c9-4469-85b1-cf4e90c52d9a)

**Performance**

![Screenshot 2023-07-31 at 6 28 15 AM](https://github.com/hkaanturgut/Achieve-Performance-Monitoring-for-Your-ASP.NET-Core-Application-with-Azure-Application-Insights/assets/113396342/320635d8-a7e5-4477-adc3-c29d136841e6)


### Additional Resources
For more detailed information and advanced configurations, check out the <a href="https://learn.microsoft.com/en-us/azure/azure-monitor/app/asp-net-core?tabs=netcorenew%2Cnetcore6" target="_blank">official Microsoft documentation.</a> 

Enjoy the journey of monitoring and optimizing your ASP.NET Core application with Azure Application Insights! If you encounter any issues or have questions, feel free to raise an issue in this repository.

Let the magic of Azure Application Insights be your guiding light 🌟 and may your ASP.NET Core app thrive like never before! 🚀 Happy coding! 😄


