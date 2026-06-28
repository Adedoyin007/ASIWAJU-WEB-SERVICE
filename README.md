# ASIWAJU-WEB-SERVICE
ASIWAJU-WEB-SERVICE

Azure App Service Web App Deployment

Overview

This project demonstrates the deployment of a web application using Microsoft Azure App Service (PaaS). The goal is to showcase cloud deployment, CI/CD integration, and application configuration.

The application is deployed using GitHub Actions and hosted on Azure App Service.

⸻

Architecture

* Platform: Azure App Service (PaaS)
* CI/CD: GitHub Actions
* Runtime: PHP 8.5
* Region: France Central
* Pricing Tier: F1 (Free Tier)

⸻

Deployment Steps

1. Create App Service Plan

* Tier: F1 (Free)
* Region: France Central

2. Create Web App

* Runtime: PHP 8.5
* OS: Linux
* Unique app name configured

3. Deploy Application

* Code pushed to GitHub repository
* GitHub Actions used for deployment
* Application successfully deployed to Azure

⸻

CI/CD Pipeline (GitHub Actions)

Workflow:

* Trigger: Push to main branch
* Steps:
    * Checkout repository
    * Deploy to Azure Web App

Benefits:

* Automated deployment
* Reduced manual errors
* Continuous delivery

⸻

Application Configuration

Application settings configured in Azure:

* ENVIRONMENT = production
* WEBSITE_RUN_FROM_PACKAGE = 1
* APP_NAME = asiwaju-app

Purpose:

* Separate config from code
* Enable flexibility across environments
* Improve maintainability

⸻

Monitoring and Diagnostics

Tools Used:

* Log Stream for real-time logs
* Application Insights (optional)

Benefits:

* Faster debugging
* Performance monitoring

⸻

Scaling Strategy

Current Tier:

* F1 (Free Tier)
    * Limited resources
    * No autoscaling

Future Plan:

* Scale up to B1 for better performance
* Scale out with multiple instances if needed

⸻

Live Application

🔗 URL:
https://asiwaju-app-asf4e7a2a9wb0aq.francecentral-01.azurewebsites.net

The application successfully displays a custom HTML page (“I really love coffee”), confirming successful deployment instead of the default Azure page.

⸻

Challenges and Solutions

Issue: Default Azure Page

* Cause: Incorrect file placement
* Fix: Ensured index.html is in root directory

Issue: Deployment Errors

* Cause: CI/CD misconfiguration
* Fix: Corrected GitHub Actions workflow

⸻

Key Learnings

* Cloud deployment using Azure App Service
* CI/CD with GitHub Actions
* Environment-based configuration
* Monitoring and debugging in Azure
* Basic scaling strategies

⸻

Conclusion

This project demonstrates a working cloud deployment using Azure App Service with CI/CD integration. It follows best practices for configuration, deployment, and scalability.
