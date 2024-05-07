---
title: Publish Angular App in Azure
date: 2024-03-13 22:00:00 000
categories: [Angular]
tags: [Angular, Azure]
published: false
---
# First Step is to Sign in to Azure from VS Code
![Sign in to Azure](/images/202403/2024-03-13_21-46-13.jpg)
# Next Step is to Create the Web App in Azure
![Create Web App in Azure](/images/202403/2024-03-14_9-18-30.jpg)
# Create the build in Angular
![Create the build in Angular](/images/202403/2024-03-14_9-22-19.jpg)
# Last deploy the Web App
![Deploy the Web App](/images/202403/2024-03-13_21-49-51.jpg)

Here you'll need to browse the whatever it's inside the /dist folder for the build
# Remember to address the CORS issue if you are going to receive incoming API calls
![Sign in to Azure](/images/202403/2024-03-14_17-48-50.jpg)
Also if it's sending outgoing API calls CORS will need to be checked on the receiver (it might be another Azure Web App or Azure function).