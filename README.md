# Achieve-Performance-Monitoring-for-Your-ASP.NET-Core-Application-with-Azure-Application-Insights

# ASP.NET Core Application with Azure Application Insights Integration

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

### Step 2: Setting up Your ASP.NET Core MVC Application for Monitoring

1. Open your ASP.NET Core project in Visual Studio.
2. Search for the "Microsoft.ApplicationInsights.AspNetCore" Nugget Package and install it.
3. Ensure you have the following prerequisites:
   - A functioning ASP.NET Core application (if you don't have one, you can create one using the ASP.NET Core tutorial).
   - A reference to a supported version of the Application Insights NuGet package.
   - A valid Application Insights connection string to send telemetry data to Application Insights. If you don't have one, you can create a new Application Insights resource to obtain the connection string.

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



