# ASIWAJU-WEB-SERVICE
ASIWAJU-WEB-SERVICE

Azure App Service Web App Deployment

Overview

This project demonstrates the deployment of a web application using Microsoft Azure App Service (Platform as a Service - PaaS). It showcases cloud deployment, CI/CD automation, application configuration, and basic scalability planning.

The application is deployed via GitHub Actions and hosted on Azure App Service, eliminating the need to manage underlying infrastructure.

⸻

Architecture

* Cloud Platform: Azure App Service (PaaS)
* CI/CD Tool: GitHub Actions
* Runtime Environment: PHP 8.5
* Operating System: Linux
* Region: France Central
* Pricing Tier: F1 (Free Tier)

⸻

Deployment Process

1. App Service Plan

* Created using the F1 (Free Tier)
* Selected France Central region
* Suitable for development and testing purposes

2. Web App Creation

* Configured with PHP 8.5 runtime
* Deployed on Linux OS
* Unique app name assigned

3. Application Deployment

* Source code hosted on GitHub
* Automatic deployment configured via GitHub Actions
* Successful deployment verified through browser access

⸻

CI/CD Pipeline (GitHub Actions)

Workflow Summary

* Trigger: Push to main branch
* Process:
    1. Checkout repository code
    2. Deploy application to Azure Web App

GitHub Actions Workflow

name: Deploy to Azure Web App
on:
  push:
    branches:
      - main
jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3
      - name: Deploy to Azure Web App
        uses: azure/webapps-deploy@v2
        with:
          app-name: asiwaju-app
          publish-profile: ${{ secrets.AZURE_WEBAPP_PUBLISH_PROFILE }}
          package: .

Explanation of Steps

* Checkout code: Retrieves repository files
* Deploy step: Publishes application to Azure using secure credentials

⸻

Application Configuration

Application settings were configured in Azure to separate environment-specific values from the source code.

Configured Variables

* ENVIRONMENT = production
* WEBSITE_RUN_FROM_PACKAGE = 1
* APP_NAME = asiwaju-app

Purpose

* Improves maintainability
* Supports environment-based behavior
* Enhances security by avoiding hardcoded values

⸻

Monitoring and Diagnostics

Tools Used

* Log Stream: Real-time application logs
* Application Insights (optional): Performance monitoring and telemetry

Benefits

* Enables quick debugging
* Provides visibility into application behavior

⸻

Scaling Strategy

Current Setup

* Tier: F1 (Free Tier)
* Limitations:
    * Shared infrastructure
    * No autoscaling support

Future Improvements

* Scale Up: Upgrade to B1 for dedicated resources
* Scale Out: Add multiple instances under higher load

Example Plan

* Low traffic → F1
* Medium traffic → B1 (single instance)
* High traffic → Premium tier with autoscaling

⸻

Live Application

URL:
https://asiwaju-app-asf4e7a2a9wb0aq.francecentral-01.azurewebsites.net

The application successfully displays a custom HTML page (“I really love coffee”), confirming that deployment is working correctly and not showing the default Azure placeholder page.

⸻

Challenges and Solutions

Default Azure Page Displayed

* Cause: Application files not in correct root directory
* Solution: Ensured index.html is deployed to the root (wwwroot)

Deployment Failures

* Cause: Incorrect GitHub Actions configuration
* Solution: Fixed workflow file and verified successful pipeline execution

⸻

Key Learnings

* Understanding of PaaS vs traditional hosting
* Practical experience with Azure App Service
* CI/CD pipeline implementation using GitHub Actions
* Use of environment variables for configuration
* Basics of monitoring and scaling cloud applications

⸻

Conclusion

This project demonstrates a complete cloud deployment workflow using Azure App Service and GitHub Actions. It follows best practices for automation, configuration management, and scalability planning.

The deployed solution is functional, maintainable, and aligned with modern DevOps principles.
