---
title: Personal Notes on Expense Management Functionality
date: 2024-11-12 16:00:00 000
categories: [Business Central, Continia]
tags: [Business Central, Continia]
published: false
---
# Benefits

* Much of the daily routines go through a dedicated Mobile App
* Minimizes Business Central subscriptions (as there're dedicated web portals)
* Cool feature for the rides integrated with Google Maps
* Rapid setup and comprehensive overview
* Product in constant development
 
# Main Features

<iframe width="560" height="315" src="https://www.youtube.com/embed/3REgOXlJoyE" title="Certificaciones de Continia para Business Central" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<!-- Not required... it displays fine
Si tienes problemas para visualizar el video, [haz clic aquí para verlo en YouTube](https://www.youtube.com/watch?v=3REgOXlJoyE).
-->

[![Link for Google Play Application](https://play.google.com/intl/en_us/badges/static/images/badges/es_badge_web_generic.png)](https://play.google.com/store/apps/details?id=continiaexpensemanagement2.droid&hl=es)

[Continia Expense Management Application on Microsoft AppSource](https://appsource.microsoft.com/en-US/product/dynamics-365-business-central/PUBID.continia365%7CAID.8d4eab29-8c7f-4b6c-be9a-b7fdfb9da196%7CPAPPID.8d4eab29-8c7f-4b6c-be9a-b7fdfb9da196)

[Access the Continia Expense Portal](https://cem.continiaonline.com/Account/Login)

## Expense Roles

The extension includes these two Roles:

* Continia Expense Management
* Continia Expense Management limited

Standard roles extended: Accountant, Business Manager and Business Manager Evaluation.

## The 4 expense document types

* Expenses, general expenses, public transport, meals, etc.
* Mileages, for vehicle usage.
* Per diems, a fixed allowance per day.
* Expense reports, these collect a number of various types of expenses.

## Daily Administration Tasks

Managing the day-to-day operations of Expense Management involves a variety of essential tasks for administrators and accountants, including:

- Managing and Editing Approval Flows.
- Posting Approved Submissions
- Sending Reminder Emails.
- Automating Recurring Tasks.
- Processing Reimbursements.
- Adjusting Available Fields on the Mobile App.


## **Importing Credit Card Transactions**

Automatically importing credit card transactions into Expense Management significantly enhances processes for users, approvers, and administrators by:

- Configuring Available Payment Types.
- Setting Up Automatic or Manual Imports.
- Creating Templates for Manual Imports.
- Linking Specific Credit Cards to Users.
- Mapping Currency and Region Codes.

# Set up user permissions

* System administrators should be configured with SUPER permission.
* These are the two main module permissions, note that they are complementary, only one should be assigned:
  
| **Permission Set** | **Description** 
|---|---|
| **CSC BASIC**| Grants access to all Continia Core features and allows tracking of Expense Management activation status. **All Expense Management users must have both CSC BASIC and CEM-ALL** permission sets to ensure full functionality of standard features.|
| **CSC APP SETUP**| Enables activation of Continia products, including Continia Core. Primarily used for product installation and managing subscription agreements in Business Central Online, such as selecting or deselecting subscribed modules. **Essential for online deployments**.|

[More about Permissions](http://go.continia.com/docs/en-us/em/linkid=em-62)

|Function|Example|Minimum BC license requirement|Set up on Continia User Setup|
|---|---|---|---|
|**Expense user**|User of the Expense Mobile App to submit expenses|No license required|Create as **Expense User** (dedicated boolean on *Continia User Setup Card*)|
|**Approver**|Oversees a number of employees|Team Member license|Indicate Unlimited approval limit or a specific amount|
|**Admin**|Accountant or HR manager|Essentials license|Create as **Approval Administrator**.|

At least one of the users should have the **Aproval Limit** set to **Unlimited**.
From the list with **Export Users** will send a welcome e-mail to the users with all the detail about how to log into the Application and the Web Portal.

We can link the **Continia User Setup** to a Vendor No. (this is recommended setup), but we can link it as well to a Employee No. If both are selected Employee takes prevalence and Employee Ledger Entries will be created.

# Delegate expense users
The Expense User delegation works similarly to Document Capture. It also can be easily set up on the Mobile App.

# Set up general features for expenses

There are three check to have in mind on the **Expense Management Setup**:
* **Auto submit for approval**: Set the expenses to go directly to the appover, otherwise they need to be supervised by the admin first.
* **Post in Expense Currency**: Specifies is expenses should be posted in the expense currency and not in the company currency. This is overruled if the bank account has a currency specified.
* **Copy Description from Transaction**: Specifies if the description should be automatically copied from the bank transaction.

# Set up Expense Types

Expense types is a open list 