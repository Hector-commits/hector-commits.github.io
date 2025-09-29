---
title: Personal Notes on LS Central
date: 2024-11-29 16:00:00 000
categories: [Business Central, Continia]
tags: [Business Central, Continia]
published: false
---

# LS CENTRAL INTRODUCTION
## LS Central Back Office

### Stores

There's a Store List. Every POS belongs to a certain Store.
Store Management > General > Stores (alternatively lookup for Store List). Another option to open the Store List is to go to the Back Office tab → Store Management → General → Stores. 
#### Store Card
The Store Card keeps all information about a store, including name, code, address, opening hours, tender types, and etc.
Every Store has a No. and a descriptive Name. The Store Card has some data that defines the Store. There's some additional information, like the Phone No. of the Store and the Address as well. LS Central POS does not use that kind of information, but the e-Commerce does. In e-Commerce you need to know where the Store is located.
To display the Latitude and Longitude we press "Show more" on the General tab.
There's as well a "Retail Calendar" tab. This is as well for e-Commerce, and it gives information about the opening hours and the opening days. This is also helpful for hospitality and other kind of commerce businesses.
We also have images on the page, like the "Store Logo" and "QR Code for Direction". This can be managed from Related > Store > Images. The "Link Type" field has the following options: "Image", "Logo" and "QR Code". "Image" would be the Store itself so people can recognize the Store itself.
#### Cash Management
"Cash Management" Action: we have different "Tender Types" with the different options available for the Store. Every "Tender Type" has a "Code" and a "Description", also a link "May Be Used". With this check we can setup if the Cash is going to be used for this Store. Another interesting option is "Overtender Allowed", also a boolean. This is for giving cashback, which makes sense for Cash tender types, but not for payments with card, in which case, this option should be disabled. We, as well have the option "Overtender Max. Amt.", aslo the option "Return/Minus Allowed" if the Tender Type is allowed for returns. There also Rounding options.

### POS Terminals

Each store has one or many cash registers or tills, but we refer to them as the POS. Each POS station is setup as a terminal in the Back Office. 
In the setup, it is necessary to create each and every terminal. You do this by selecting POS Terminals in the Store Card.

Is in every terminal where we define the "POS Terminals" of tills. These can be accessed from the FactBox on the Store Card "Store General Information" where we have a "POS Terminals" indicator which displays the number of Terminal for the Store.
Every Store has a minimun of one POS Terminal. The No. identifies the POS Terminal for the Store. Every terminal belongs to one store. It's very important to remark that you can never change the POS Terminal to be located in a different Store than the one that was located in originally, not after starting using it. But this is something that actually may occur. If that happens, i.e. the device needs to be relocated, this device will get a new No. for the different Store.
In the POS Terminal the profiles are defined, remember the different POS styles (like Leo, Supermarket, etc.). 
Interesting options: "Exit After Each Trans.": with this option, staff does not have to log off after each sale (this will be helpful for cosmetic stores, but not for a Supermarket). We also have the "AutoLogoff After (Min.)" which states the number of minutes the POS Terminal stays active before the auto-log off.

#### POS Terminal Printing Options

In every terminal we have "Receipt Printing" and "Dispense Printing Setup". Under the "Receipt Printing" for the specific POS Terminal we have "POS Terminal Receipt Text Top" and "POS Term. Receipt Text Bottom". This kind of setup can be done at the level of the Store, but as well at the level of the POS Terminal. POS Terminal will override Store level setup.
Notice that in the Receipt No. on the POS Terminal, part of the No. of the receipt is the POS Terminal No.

### Staff List Overview

The Staff List is where you register the POS users. The most important thing here is to insert staff members into the correct permission group. The permission group decides what actions in the POS staff members are allowed to do.

The Staff List is a complete overview of all employees who have access to your POS. Let's open the Staff List in the Back Office the same way we opened the Store List.

#### Staff Card

The Staff Card consists of all the information related to store staff using the POS. Here we define the ID for the staff person, their name, name for receipt, and more. But one of the most important things here is the Permission Group the staff member belongs to.

The Permission Group defines the operations the POS staff are allowed to do. For example, void line, void sale, refund, max manual discount, etc.

Overview on the fields:

* **"ID and Name":** Each ID is unique and also acts as the login number for each employee. You can add a full name and select a name that should be displayed on the receipt ("Name on Receipt").
*  **Store No.:** Keep the Store No. field for the employee empty if this employee works in more than one store and then fill out the Store Link Lines at the bottom of the Staff Card. If the employee only works in one store, fill out the store number.
*  **Employment Type:** This field specifies the type of employment that the staff member is currently assigned to. The options are: Cashier, Sales Person, Both.
* **Language:** If an employee prefers another language rather than the default language in the POS, you can select it here.
* **Blocked:** If for some reason anb employee should not have access to the POS you can block the access. You can schedule when the action should take place.
* **Personal Tab:** Here you can add personal information about the employee, such as address and phone number.
* **Store Link Lines Tab:** Here you can add multilabel stores with a different permission group for this employee. We can use this instead of Store No. field for multiple Stores.
* **Permission:** This is the most important field. Here you define an employee's permission within the POS.
* **POS Profiles:** In advanced use of the system you can adjust POS profiles for each employee. Profiles are usuarlly set up for stores and terminals, but additionally it is possible to configure them as well for the staff.

### Manager Login options in the POS

The Permission Group for the POS staff defines what an employee can or cannot do in the POS.

Let's imagine a situation in a store when an employee without Manager Permission needs to do something that is not allowed by their designated permission group, such as add an extra discount or void a line (for instance, an item that is defected or a customer that changed their mind about an item).

For situations like this, you can use the Manager Login option. (The Permission Group for the employee displais on the status bar, for example saying "Mgr. = Yes").
There is a "Staff Permission Group Card" completely independent of the Business Central permissions. Here we have permissions like "Vode Transaction", "Void Line", etc. Manager group has "Manager Privileges" = Yes, that means that everything is at maximum level.
For example, the Permission Group "CASHIER" looks very different, it has "Manager Privileges" = No and has differente options for transactions and so on.
Being a cashier, we can call the manager and there's an option "Manager Login" on the POS that allows the manager to Login with the same session, therefore the status bar "Mgr" changes to Yes but the member of the staff that it's logged was the same cashier. When we click on "Manager Login" again, the Manager logges off.

### Retail Users


The Retail User is where you define which terminals and stores the user is connected to. For example, in the VM there is a user called SUPER. When SUPER starts the POS, the setup in retail users dictates which terminal SUPER can open. 

Each POS user has to be registered in Retail Users and connected to the terminal they're supposed to use.
Each button has a setting behind it where it's possible to see the user behind the button. To do that, just right click on the button you want to see the settings for and select Edit.

![RetailUsers](/images/202411/RetailUsers.png)

![RetailUserOnPOS](/images/202411/RetailUserOnPOS.png)

## Retail Items

In the LS Central Demo Data company, you can find the Retail Item List. Here, you'll find all the items in the system. Each item has its own Retail Item Card which contains detailed information about the product, how it's sold, and how it's categorized for reporting, monitoring, and displaying.

### Retail Item Card

On the Retail Item Card, you register all the information about the item, including description, name, division, category, retail product group, and much more.

**Item grouping:** Item grouping is a hierarchy that helps you organize products. It is used in different operations and is helpful for reporting and analysis. Interesting features are: **Division Code** and **Item Price Overview** which helps lookup different prices for different Customer groups (that may be different Stores).

#### POS Tab on Retail Item Card

* **Scale Item:** For putting bananas on a scale (item that we need to weight).
* **UOM Pop-up on POS:** Ability to sell coffes in different UOMs.
* **Keying in Price:** Options: Not Mandatory, Must Key in New Price, Must Key in Higher/Equal Price, Must Key in Lower/Equal Price, Must not Key in Price. 
* **Zero Price Valid:** For items that can be sell at Zero price.
* **Qty. Becomes Negative:** Quantity can become negative for this item when enabled.

### Setting up different prices for the same item

When we sell the same item but in different places, we may want to set a different price for it. For example, a beverage is sold in a grocery store, but is also sold in a restaurant or a coffee shop where the price happens to be higher.

How do we do that? By using Prices & Discounts and Sales Prices. (this seems to be the exact standar Business Central prices feature "Sales Prices" -> "Price List Lines" and different "Assign-to" - note: I believe these "Assign-to" codes are linked to the different Stores we have).

#### Retail Items - images and extra descriptions

When you are in the POS, it's easy to display the extra description and item HTML for the item the same way for eCommerce. The additional information for the item, like the HTML information (Retail Item Card -> Related -> Master Data -> Item HTML (with input screen and preview options)), has the option to have one or many lines. Remember that the item's description is limited to 100 characters, so it's good to have the item HTML option to add more detailed information about the item. 
To see the extra description in the POS, you put the item into the sale and double click on the line. Note: if an item does not have the item HTML data, then nothing will happen.

For the same item we may have several images, this could be because we want to show them on eCommerce. The different images can be linked to the item similarly as what we did before with the Store images. Go to Related -> Images -> and then link the images we want on the "Retail Image Link List".

#### Different variations of the same Item

In the fashion industry, items are sold in different sizes and colors, where each variation has its own barcodes. These barcodes include the size and color of the individual items.

Usually items in retail are sold by barcodes, but standard items such as bags may not have variants. But for items  sold in variants, like different colors and sizes, the barcode will include the variant option. If you do not have a barcode for the item, then the POS then will ask which variant you are selling when you enter an item.

![SellingVariants](/images/202411/SellingVariants.png)

#### Items Unit of Measure

When selling an item in different units, like coffee, you don't need to create a Retail Item for each unit type. Instead, you use the Unit of Measure option in the Retail Item Card to set different units, including a conversion for the base unit of measures. 
As an example we have **Base Unit of Measure** -> CUP, but then on the FactBox "Item Price Overview" we can see the different prices we have per each different Unit of Measure). We use for coffee the option "UOM Pop-up on POS" which is the trigger that fires the next screen with the different Units of Measure we have. We have to have "POS Selection" = Allowed in the Items Unit of Measure. We also need to have the lines configured for the "Price List Lines".

You then use two other setup options; one to trigger the unit of measure option to pop up in the sale and the other to set the prices per unit of measurement.

## POS Operations

### Menu and Button Properties

Only POS users with the SUPER User authorization ("POS Super User" = True on "Retail Users") can change the look and layout of the POS with the open button or Menu Properties directly in the POS. Note: Standard POS users in a store never have the POS Super User enabled. Only those that are part of the implementation team have this option enabled.

A menu comprises one or more buttons. Each menu is part of the POS Menu Profile and is easy to work with in the POS. It's easy to add a button, change a button, or change the number of buttons in a menu.

![ButtonSetup](/images/202411/ButtonSetup.png)

#### Menu Properties

If there are no empty buttons in the the area of the POS where you would like to have a new button, you need to add more columns or rows for that menu by using the Menu Properties. 

You can add as many new columns and rows as you want (even 10x6 = 60 buttons!!)- just make sure it makes sense in the space where the menu is displayed!

![MenuProperties](/images/202411/MenuProperties.png)

#### Button Properties

To change the setup for a button, you need to open Button Properties or edit the button line for the menu.  It's optional to put images on buttons, but it's an easy task to do.

Each button has a POS Command behind it to trigger a specific operation.

![ButtonProperties](/images/202411/ButtonProperties.png)

### Item Inventory in the POS

Another functionality available in the POS is to see how many items are left in the store stock. For example, a customer is interested in an item and would like to know where it's available. This information can easily be found through the POS.
We can look for the Description by clicking on the Description column and then starting to type.

![LookupInventory](/images/202411/LookupInventory.png)

We need to run a Job so the inventory gets updated:
"Retail Product Groups" -> Edit -> Process -> Update POS Inventory Lookup.
Simpler way: Scheduler Job List -> INVLOOKUP -> Run Now

### More Commands behind buttons

Each button has a "Command", like PLU_K, LOGOFF, VOID_L etc. There're like 800 different commands. The easiest way to discover what it's the command behind a button is to right click on it and then go into "Button Properties". Under "Menu Properties" we can see all the buttons Commands for the buttons in that menu.

### Return and Refund

It's easy to refund/return items in the POS. The POS offers different options for refunding/returning items.

Note: Some countries do not allow  to return and sell in the same sale. This can also be accomplished in the setup.

* **Option 1: Return in a sale:** The first option is to return an item during a sale. To do that, you need to put negative quantity (for example -1) in the line for the item you need to return.
* **Option 2: Refund mode:** This option refunds all items in a sale. At the start of the sale, use the refund button before adding items to put the POS into Refund Mode. Next, enter the items you want to return and all the lines will appear in a red color on the POS (colors are set in the POS Style Profile) which signals the items are being returned. Note: When you are in Refund Mode, you cannot enter any sale item into the sale. You must finish the sale first as any other sales transaction. Make sure you select the payment type that the retailer allows for refunds. The payment type is usually a voucher, but any tender type can be used as long as it is marked as allowed for return in the setup. On this mode all items that are inserted to the sale will be refund items.
* **Option 3: Refund by transaction:** Some retailers only allow customers to refund items if they bring the original receipts with them. This is to ensure that the refund will be done with the same prices and discounts as when the item was first sold. The staff then scans in the receipts or finds them using the Transactions operation. The system keeps track of the transaction and ensures that the same items from the same receipt can never be refunded again. You go to **Transactions List, Print, Return** and select on the list of transactions. To be able to find needed transaction you need to know the receipt number.

![TransactionListButton](/images/202411/TransactionListButton.png)

### Menu Status Bar

The Status Bar (Menu ID = #STATUSBAR) can be in different places on the POS. For Aries, it's at the bottom.

The Status Bar is a menu with a few menu lines that display information, such as state mode, receipt number, staff ID, manager mode (Mgr), date, and time. 

![StatusBar](/images/202411/StatusBar.png)

![StatusBarExample](/images/202411/StatusBarExample.png)

### POS Dynamic Menu

POS Dynamic Menus makes working with the POS much easier. They can appear as pop-up menus or in the main menu, and additional menu, sections on the POS.

![DYNMENUUsage](/images/202411/DYNMENU_Usage.png)

![DYNMENU](/images/202411/DYNMENU.png)

The POS Command DYNMENU needs a parameter where the parameter points to a specific setup defined in the LS Central Back Office or in the dynamic menus. 

![DYNMENUUsage](/images/202411/DYNMENU_Setup.png)

When you use a button in the dynamic menu, the system builds the menu in the POS based on the selection and sorting criteria that goes with it each time it is used. The benefit with the dynamic menus is that you do not have to create a fixed menu; the POS Command takes care of all the items according to the criteria when the button is used. This can change depending on the data when the command is executed. For the dynamic menus we have the **Selection Type** with the following options: Attribute, Product Group, Item Category, Special Group, Item and Deal.

### Transaction Register

Transaction Register is a list of all transactions that have been done in the POS with detailed information. You can find it in the Back Office by typing in "Transaction Register" in the search feature.

Each transaction can only be vieweb - not edited or ddeleted. In the Transaction Register, the system stores all information about the sale, such as the receipt number, store number, terminal number, staff ID, date, time, discounts, an more.
Additionally on the factbox it's possible to see details of the transaction: what items were sold, what payment method ws used, etc.

![TransactionRegister](/images/202411/TransactionRegister.png)

If we have a look into the Transaction Card there are two tabs with details: "Sales Entries" with the detail of the items sold on the transaction, and "Payment Entries" with the detail of the payments applied to the ticked, including "Tender Type" which is the code that specifies if the transaction was made in cash, credit card, currency, etc.

If we activate the training mode, (with supervisor access), the Transaction is posted in the system with the flag "Training Mode" = true.

## Offers in LS Central

### Discounts in LS Central

Discounts in the POS can either be **manual or automatic.**
Automatic discounts are different that manual ones, they are triggered automatically in the POS transaction.
LS Central has several offer types. 

#### Discount Offer Setup in the Back Office

There are multiple options available for the Discount Offer setup. In the setup, you decide the Price Group that the offer is assigned to, and the period for which the offer will be valid, including the times and days of the week. Most importantly, you define the item and/or item groups, such as the categories, retail product groups, and special groups, that will be a part of the offer. Note: The las thing you do for the offer is enable it so it's valid in the POS. If you forget it, it won't work.

##### Discount Offer Card

* **Price Group:** Here you can choose which Price Group the promotion will be used for. It can be all groups or just some specific groups.
* **Additional Benefits:** Here it's possible to set up optional benefits that a customer can get from the offer.
* **Validation Period ID:** Here a validation period can be set on all offer types. This can include specific days, periods, or times. For example, happy hour deals in the hospitality business. If no validation period is selected, the offer will not be restricted by a specific period.
* **Lines:** Under this tab, you select items that are included in the offer. The options are single items, product groups, item categories, or all. It is also possible to select a special group. Note: it is also possible to exclude items by selecting the check box in the "exclude"column.
* **Triggers:** Triggers limit the group of customers that can benefit from an offer. For example, we can create an offer which will be valid only for members of the loyalty club (you can set it up in Member Management). Another example is when the user needs to bring a coupon to activate an offer. Several other activities or attributes can trigger an offer. The Member Management module and the Coupon functionality are closely tied to this functionality. If no fields are filled out the offer is valid for all customers.
* **Benefitx:** In this tab, you define what benefits/discounts the offer has.
  
![DiscountOfferCard](/images/202411/DiscountOfferCard.png)

To exclude one item from a category, we enter a line with the Category and then another line with the Item but we mark the boolean "Exclude".

![ValidationPeriodSetupCard](/images/202411/ValidationPeriodSetupCard.png)

### Promotions

Promotions are a specific type of offer that changes the price of an item for a given period. The printed receipt will show the new price instead of a discount, so the buyer does not know that there is a change to the retail price.

#### Promotion Setup in the Back Office

The setup for Promotions is very similar as the Discount Offer. The only difference between the setup for these two is that there is no tab for Additional Benefits (but there are Benefits).

![PromotionCard](/images/202411/PromotionCard.png)

### Mix and Match Offers

Mix and Match offers in LS Centrar are very flexible and practical for the retailer. With a Mix and Match offer, you can combine different items into one offer. In other words, the offer can include different items from different item groups and have a specific quantity of items specified. It is very important for those working with the system to understand the Mix and Match offers setup and its capabilities.

* **Examples of Mix and Match offers:**
* 
1. Buying one soda drink and two chocolate bar triggers a five percent discount only for the items that are part of the offer, such as particular brands.
2. Buying three different children's clothing items and getting the cheapest one for free.
3. Buying a printer and a cable together. The printer gets a five percent discount and the cable gets twenty percent - so a different discount fore each item in the offer.
4. Buying two specific items that are worth $120, but getting them for the price of $99.

The Mix and Match offer set up has so many more capabilities than the Discount Offer. Mix and Match offers have five different "sub-types".

![MixAndMatchPopUp](/images/202411/MixAndMatchPopUp.png)

#### Mix and Match Setup in the Back Office

The setup in the Back Office for this type of offer is a bit different compared to what we have seen previously, but it is very flexible.

![MixAndMatchCard](/images/202411/MixAndMatchCard.png)

**Line Group:** With the line group option, you decide how many items are needed to trigger the offer.
**Trigger Pop-up on POS:** In this column you can choose which item of the offer will trigger the pop-up window in the POS.
**Benefits:** This section is the most important for the Mix and Match offer as you must select the Discount Type which are: "Deal Price", "Discount %", "Discount Amount", "Least Expensive" and "Line spec.".

## POS Look and Layout

There are different POS layouts in LS Central demo. Menus are just one part of the POS screens; there are also other parts such as journal, images - and even blank areas. All this is defined within the system and there are tools in LS Central that can help you set up the POS look.

Menus are easy to understand and control A menu consists of 1-2 or more buttons. Buttons can have different colors and fonts. This setup is done directly in the Back Office or can be changed straight at the POS.

For begginers, it's easiest to change the POS menus directly from the POS, but always remember to have a copy of your menus and profiles before you do this.

**Remember you can only do changes in POS if you have SUPER User access set up in Retail Users.

An easy way to change a color for a button is to open the button's properties, which you may already be familiar with, and adjust the Skin and Font fields with a different value. When you're at the POS and changing the skin or font of a button or menu, it will be updated immediately once you close the option.

![ButtonProperties_1](/images/202411/ButtonProperties_1.png)

All the menus in the system belong to a POS Menu Profile. The menu profile is set on the store, terminal or staff user, depending how you want to use them. It is important to remember if the menu profile for the store and the terminal is different, then the system will use the menu profile from the terminal setup. Then a setting for the menu profile of a staff user will overwrite the terminal. This is the rule we have: the "narrower" the setting is, the more priority it has.

There is a different menu profile for the Aries POS than the Supermarket one. Some menus are used in both. Menus that are exactly the same for all setups are kept in the shared menu profile called Default or ##DEFAULT.

![MenuProfileDefault](/images/202411/MenuProfileDefault.png)

Store > POS > Staff (the narrower one takes priority)

## POS Tags

Tags are fixed information that are entered into the Menu line. The system has many different tags that can be used in the system depending on the nature of the information.

The menu lines include the Tag ID. When the POS is running, the Tag ID is replaced with its information. The information can be taken from the current POS transaction or from another table taht can be referenced from the current transaction.

![POSTags](/images/202411/POSTags.png)

![ButtonOverriding](/images/202411/ButtonOverriding.png)

## POS Style Profile

POS Style Profile defines the colors and fonts used on the POS. This includes the look of the buttons, the font and the color used for all the different controls, ant the space between buttons.

There is a functionality to **Copy to Current Style** and it's easy to use (similar to copy a Item or copy a document).

Each POS Style Profile has three main parts:

**Skin Lines**
POS Skin Lines define the color and shape of many of the POS areas including the buttons and journal:

![SkinLines](/images/202411/SkinLines.png)

**Font Lines**
POS Font Lines define text styles in the different areas including buttons.

![FontLines](/images/202411/FontLines.png)

**Color Lines**
POS Color Lines define the color for different parts of the POS. This can, for example, be the bacground color for some parts, the area between buttons, and the grid line color.

![ColorLines](/images/202411/ColorLines.png)

## POS Panels

The POS is based on many panels. Every window that appears in the POS is a panel.

A panel is like a puzzle; it consists of many parts that cannot and may not overlap each other. The panel's parts are rectangles that can be of different sizes, lengths, and widths. Each panel covers at least one column and one row. It is possible to configure each part so that it covers more than one column or row, by using the span feature in the panel lines.

(right click -> Panel properties)
**POS Panel Row/Column List**
**POS Panel Control Lines**

![POSPanel](/images/202411/POSPanel.png)

## Hierarchy

Hierarchy is a multi-level structure with Nodes and Links used for replenishment, clienteling, and eCommerce. It is flexible and easy to setup.

As you may remember, at the beginning of our course we looked at the Clienteling POS. The item hierarchy in the Clienteling mode is set up in the Back Office. Here the items are not menus with buttons as we are used to having, but instead they have a web template behind them. The web template uses a hierarchy for all the items it's displaying. We have full control of the hierarchy, and can crate and edit it in the Back Office.

![WebTemplate](/images/202411/WebTemplate.png)

**Note:** The items here are not ina a menu. It's the web template that uses the hierarchy here.

![HierarchyNodes](/images/202411/HierarchyNodes.png)

To add items into the hierarchy, we need to work in the Back Office via the Hierarchy option and use the action edit hierarchy.

In this example, we use Hierarchy Nodes to define the structure, and then items are added into the Hierarchy Nodes Links section.

Fashion -> Hierarchy Nodes -> (similar to standard categories)

# CF-100 Introduction to LS Central Part II
# Member Management

## About Member Management

Member Management in LS Central (sometimes referred to as loyalty management) allows members to collect points and use them as payment or get special benefits in the different POS offers.

Member Management offers the possibility to handle multiple **Member Clubs** in a company with different rules and setups. For example, ther can be one club for members and another one for the retailer's staff members.

Each club has its own **Member Schemes**, such as Bronze, Silver, and Gold (we will go through that later in the course). Members are registered to the clubs, either directly in the Back Office system, at the POS, or in systems connected with LS Central via Commerce Service.

Member Management is fundamental for eCommerce and loyalty apps because users there also become member contacts in LS Central.

You can add a loyalty member into a sale manually by:

1. Searching directly for the member or their card number in the input field.
2. Using the Member Card option to enter their card number.
3. Using the Member Contact option to find the member.

![AddLoyaltyMember](/images/202411/AddLoyaltyMember.png)

**Member Information** When a member has been added, you will see the information here (left-top).
**Member Card** In the member card you can add the member of the loyalty club by entering the member's card number (real life scenarios would be by swiping or scanning the card).
**Member Contact** To search here for an existing member, you can enter any information such as name, phone, etc.

## Earning points

It is easy for members to earn points in the POS. Simply add the member at any point of the sale - beginning, middle, or before you proceed to the payment.

There are few ways to add a member into the sale. In real life scenarios, customer have a card that can be swiped or scanned or a QR code to show, but the POS user can also enter the member manually into the sale.

For this training, we are going to add members manually into the sale since we do not have the physical card ready or a card reader.

## Member Management in the Back Office

Member clubs are created in the Back Office where you can add basic information about the program. In Member Schemes, you can create how members level-up.

As a retailer, you can create as many member clubs as you want, but before deciding on your usage of clubs, it's important to understand the possibilities.

There are options to differentiate club members without the need to create new clubs.

Member clubs can be used both for the retailer's customers and for the staff.

So why would you want to have a member club for the retailer's staff? Member information can be used with all the different offers in the system. This means you can create a discount offer that is only valid for staff members and another offer that is only valid for the customers, for example. And you can go even further. For example, you can have an offer that's only valid for a specific club or group of members within a club. By using member management with different offers, retailers can more easily control discounts in their stores and monitor all sales to their staff.

To understand the capabilities of member management, we need to understand the basics and how it's used with LS Central.



