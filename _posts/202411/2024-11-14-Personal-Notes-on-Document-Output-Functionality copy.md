---
title: Personal Notes on Document Output Functionality
date: 2024-11-14 16:00:00 000
categories: [Business Central, Continia]
tags: [Business Central, Continia]
published: false
---
# Benefits

This extension uses email templates for most document types.

Features:
* Applying customized styles to email text and attachments
* Differentiating emails for language and other variables
* Responding to customer and vendor communication requirements
* Sending documents in a combination of formats, including print, e-document and email
* Creating an audit trail of communication
* Automating document generation and email dispatch
* Adding security features such as passwords and authentication certificates

# Extra Cue Groups

* **Unhandled document cues**: documents ready to dispatch, dedicated for **Sales, Posted Sales, Posted Service, Finance and Purchase**.
* **Document queue and print queue**: to manage the dispatch process in BC.

# Email templates

Document Output comes with email templates ready to use.
* **Email HTML template**
* **PDF attachment options**
* **Email template lines**

# Options for recipients and delivery

* **Recipient setup** allows you to fine-tune exactly where each email template searches for recipients, and prioritize this list if this information could be found in multiple places.
* **Email recipients** settings from inside the customer or vendor card are where you set up options for meeting customer and vendor requirements, such as special email addresses to be used for some document types.
* **Output profiles** for you to manage your customers and vendors preferences for specific delivery methods, for example sending sales invoices as e-documents but everything else by email.
* **Document Output** log lets you quickly find an audit trail of sent documents when customers and vendors ask questions.

# Send automatically and add security

* **Document queue** is a powerful feature that collects and dispatches documents in the background of Business Central, saving you time while you to get on with other tasks.
* **Email jobs** can save you even more time by creating automated email jobs to transfer documents for you to the document queue as soon as your set up condition is met. For example, as soon as a sales invoice is posted, you can automatically transfer a shipment notice to the document queue.
* **Statement and reminder** documents types can be automated, and you can control how often to send, what to include in the email, and when to skip or pause sending these.
* **PDF passwords and authentication** certificates give your customers and vendors peace of mind that emails from your company are genuine.

# Send emails and attached documents

# Unhandled documents lists

Each unhandled document cue opens the associated document list. This list shows documents which are ready to send with an email template in Document Output. Just like other lists in BC, filters can be applied and they can be viewed by clicking on the No. column.

# View and edit generated emails

The E-Mail page looks much like any other email client program, such as Microsoft Outlook, where you can view and edit:

- From and to email addresses, including CC and BC addresses
- Subject text
- Email body text content and style
- Signatures
- Attachments

# Adjust email message contents

At the center of each email template in Document Output is a Business Central document such as a purchase order, statement or shipment notice. Email templates accompany these documents with email messages, extra file attachments and options for applying style and formatting. This unit focuses on the contents of the email message itself, and the following unit focuses on options for file attachments.

You set up the contents and format of email messages in the HTML email templates, which are a combination of fixed text parts and merge fields that link to sources within Business Central, such as:

* customer and vendor cards
* company information
* users' contact information
* template email signatures
* template tables of merge fields

# View an HTMS email template

From the menu for Document Output > Setup > Template Setup > Email Templates.

Choose the E-Mail Template Card for the associated Business Central document.

Then, in the E-Mail Template Lines section, in the E-Mail Template action menu, select Edit HTML Template.

e example image of an HTML email template for sales shipments includes a range of merge fields. Three of these merge fields are labeled in the image:
- A merge field in the subject line for the document number, labeled A.
- A merge field in the salutation at the beginning of the email body text, labeled B.
- A merge field for the default signature at the end of the email body text, labeled C.

# Add merge fields into an HTML email template

To add a merge field into the subject line or email body text, type the percent sign (%), and then select from the list of available merge fields shown in the Merge Fields FactBox. In the email body text, you can also use the Insert merge item tool, which will open the list of merge fields, tables and signatures to select from.

# Add or change email signatures

Document Output is set up with two template email signatures:

- The **default signature**, which includes many standard signature elements such as name, role, and contact details.
- The **advertise signature**, which is intended for temporary messages and banners.
An HTML email template typically includes both signatures, which are included in the email body as the merge fields. You can view and adjust the content of email signatures from the Signatures FactBox.

You can also access the E-Mail Signatures setup page through the Document Output > Setup menu, where you can add more email signatures to suit the needs of your business.

# Default signature

The content of the default signature is almost entirely merge fields that link to your own company information and the contact information of related users, such as salespeople. These merge fields allow you to ensure a shared signature style, even when Document Output sends emails on behalf of different users in different locations.

From the E-Mail Signature Card, you can look up current and available merge fields in the Merge Fields FactBox.

Use the Insert merge item action, or begin typing with the percent sign (%) to insert one of the available merge fields.

# Advertise signature

The advertise signature is useful as a banner for promotional or seasonal events. The Start Date and End Date options allow you to create multiple advertise signatures and schedule these for a later start date and transition between different versions.

If you set up a default advertise signature template without dates specified, you can display a banner during periods when no special events need to be promoted. Alternatively, you can leave this default advertise signature template without content, so that no banner appears in emails outside of the start and end dates of the other advertise signatures.

# Make additional merge fields available

Document Output includes the most commonly used merge fields for each document type. However, sometimes companies need additional merge fields to be available for inclusion in email templates. You can make additional merge fields available, including text, hyperlinks, links to email address or images that are already somewhere on Business Central.

In the email template card, the **General** FastTab has an option to open the list of merge fields by selecting the number at No. of Merge Fields.

In the E-Mail Template Merge Field list, the option at Get Field From allows you to link from Business Central tables, contacts, code units, and many other sources. When these sources are updated in their original location, the merge fields automatically generate the updated information in the email templates.

