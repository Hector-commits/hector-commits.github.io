# CF-300 LS Central for retail Part I

## Structure

LS Central solution is built on top of Microsoft Dynamics 365 Business Central to cater to the needs of Retail & Hospitality businesses. LS Central is a one-stop solution for Retailers, as it provides the benefits of an ERP and a Dynamic Retail Solution.

**Head Office (HO)** The Head Office is the first entity we need to set up. System setups and configurations take place in HO. It is the hearth of operations where decisions related to finance, operations and other departments take place.

**Back Office (BO)** In the store **Back Office**, we define and carry out Store, POS, and Cash management (retail stores or outlets).

**Customer Facing** This could be a web store, integrated eCommerce portal or ScanPayGo terminal.

**Front End** Can be a store, outlet, or any other place where the customer is interacting with store staff and concluding the retail transaction.
Each retail store can have multiple POS options.

**Standar POS** A stationary point of sale, where the customer settles the retail transactions. 

**Mobile POS** Store staff can operate with a mobile POS and help customers to conclude the transaction on the move.

**Call Center** A help desk or call center can be a part of the retail store/location.

### Head office

Here, you can centrally manage the important LS Retail functionality on top of standard Business Central. We will dig deeper into those functionalities later on.

If we section the solution by work locations, we first have the head office functionality designed to fulfill the needs and requirements of central operations.

The following are part of the head office: 

- Product Management 
- Price & Offer Management 
- Member Management
- Replenishment
- Franchise Management 
- Staff Commission
- Customer Orders
- Click and Collect
- Inventory Optimization
- Campaign Management
- Analytics for LS Central
- Loss Prevention

### Back office

Store back office is managed with the following operational features in LS Central.

This part of the setup gives you the power to run essential store operations like General store management, POS, and Inventory management, as well as tasks like EOD.  Setup, view, and maintaining items, price, and promotions on the store level are important to many retailers and here you can do that. In typical retail, this is basically where you run your company on a daily basis.

Store back office functionality is designed for simplicity and process control. 

When staff enters the system, they will only see products and documents that are relevant for their role/store to guarantee correct and productive process execution. 

Mobile devices are supported for all store processes to give mobility, simplicity, and process-led work.

The following are part of back office:

- Store Management
- Cash Management
- POS Management
- Inventory Management

### Front office

POS Terminal can be operated with the following available Apps & Clients.

This is where you touch base directly with the customer, so a very vital part of Retail operations is handled and maintained through this part. We offer with our Omni Channel solution different points of shopping and interaction with the customer. A web store today is just another Store in your setup, a Mobile POS today is just another POS, but every customer is unique and a happy customer will return. The customer management is handled with our Mobile Loyalty and we will look at that closer in the coming slides. 

Front office processes are performed out on the floor by the staff, servicing customers.

These processes need to be simple, straight to the point, and should only require a short amount of training time.

The following are part of front office:

- LS Central POS
- Mobile POS
- Mobile Inventory
- Business Central Phone and Tablet App

### Customer facing

To interact with retailers, the following apps are available to customers and are part of customer facing:

- Web store
- Mobile loyalty
- Loyalty portal

## Retail Setup

Retail Setup is a company-wide setup to define default values including the local store, number series, posting configurations, and sales history setup.

With the help of Retail Setup, you can activate LS Central features and functionalities in the LS Central solution. In addition, you can set up certain default values in the company.

### Retail Setup functions

- Default Logo: Upload Company logo from this action.
- Insert Default Data: Use this function to insert default LS Central data into the Company.
- LS Central in Use: Enable LS Central in Use to activate the retail functionality.
- Local Store No.: Define Local store here. For an example; HO in head-office database & store ID S0001 for Retail Store.
- Store No. Nos.: Select value for Sotre Number Series, if stores are numbered automatically.
- Create Items No. Series: Select value for Item Number Series, if items are numbered automatically.

![LocalStoreNo](/images/202411/LocalStoreNo.jpg)

## Store 

In LS Central, the Retail store is identified with the help of the Store entity. All active Retail outlets and Web stores are created in the LS Central database.

The Retail store represents Retail outlet or Web store where all store-specific configurations and transactions take place.

**Store Type**: Store, Head Office, Call Center, Warehouse and Other.

## Head Office

Head office store is the store at the hearth of the operation. It represents the central database, where all business central ledgers reside and it is used to create and disribute master data. All master data should be created here before being distributed.

![HeadOfficeStoreCard](/images/202411/HeadOfficeStoreCard.png)

#### Store Card sections: 

**Address**: Define Store Address.
**POS**: Define Store Profiles.
**Inventory Lookup**: To enable inventory lookup functionality for store.
**Location Code**: Link Inventory location with Store.

#### Store Card Tabs:
##### Numbering
Store as a head office creates masters with the help of the defined number series. Those masters will then be distributed to all the recipients, POS systems, and Store databases. Define Number series to create Master data like Terminals, Staff, Promotions, Coupons etc. 

## Store - Retail outlet

The Retail store represents Retail outlet or Web store, where all store-specific configurations and transactions take place. An inventory location must be assigned to each store to manage inventory. A new location must be configured in the Inventory posting setup.

- Head office: Head office store is the store at the heart of the operation where Business Central ledgers reside.  We can connect all types of retail stores with multiple POS interfaces that fit each type of retail. 
- Small supermarket: This could be a small supermarket with another pricing than the big one. 
- Day opening: This group of stores has regular opening and a different price group.
- Web store: Then we have the web store and we can have another price group there.
- Super markets, long opening: This could be a group of super market that has longer opening and then a different price group.

![StoreCardDetails](/images/202411/StoreCardDetails.jpg)

Store Actions (Store actions Tab features):

**Store Price Groups**: Retail Price group helps store to get sales price. Multiple Retails Price groups can be linked with Store and priority could be managed with "Priority" field value. 

**Receipt Printing**: Define Receipt Printing for store which includes General, Top, Bottom & Gift Receipt Bottom sections. 

**Store Locations**: Multiple locations can be linked with Retail Store including Layaway, Damage & Claim locations. Only one Sales location should be linked.

More often than not, there is no Business Central customer linked to a sale. The store must act as a substitute for the customer.

Number series for statement and posted statement should be declared and a statement is set up individually for each store.

![StoreCardFeatures0](/images/202411/StoreCardFeatures.jpg)

Store Card specifics:
**Statement Nos.**: Number series to create Statement for store.
**Posted Statement Nos.**: Number series to post Statement for store.
**Store VAT Bus. Post. Grp.**: Define default VBPG for Retail walk-in customers.
**Store Gen. Bus. Post. Grp.**: Define default GBPG for Retail walk-in customers.

## POS terminal

### POS terminal

POS terminal stands for point of sale terminal. It can be a mobile terminal, tablet terminal, call center terminal, or traditional POS terminal. **At least one terminal needs to be linked to the Store**. Store may have multiple terminals.

Here you see how terminals are linked to Stores:

- Head office as Store: Head office as Store is the heart of the operations where Business Central ledgers reside. 
- Web store: Web store is one of the options. 
- Retail store: This could be like a regular supermarket with terminals by the entrance, cashiers and self service. 
- Retail store: This store can be set up with multiple  functions, help desk, salesperson on the floor with mobile POS and regular cashier by the entrance POS. 
- Small retail store: We can also have a small retail with only one terminal.
- Small retail store: We can also have one mobile POS for the retail store.

![POSTerminal](/images/202411/POSterminal.jpg)

Store may have multiple terminals with the following Terminal types: POS, Mobile, and Call Center terminals. 

### Get familiar with POS terminal

Terminal type indicates whether the terminal is being used as a standard POS terminal, a mobile POS, or for orders in the call center. The options are:

* POS Terminal
* Mobile POS
* Used by Call Center

Some fields on the POS Terminal card:

**Printing**: Perform printing related setups
**erminal type**: Choose the terminal type for POS. Three options are available: POS Terminal, Mobile POS, Used by Call Center.
**Manager Key on Return**: To force POS to ask for Manager login in case of Return transaction.
**Return in transaction**: Set whether Return in  a sales transaction is allowed. Applicable in exchange transactions.
**Show Item Image**: Retail image will be displayed for an item in an active transaction. Item images can be enabled if images are available and linked to retail items.
**Show Item Html**: It can display detailed description of an item at Clienteling or Web POS, if defined for retail item.

### POS terminal - Receipt printing

Terminal receipt printing can be defined with this setup. In a POS Terminal selected, you can create a specific printing setup for the General, Top, and Bottom areas of the receipt. If the printer supports back-side printing, this can also be included for the receipt. You can define the store policy in terms of return and exchange on gifts under the Gift receipt bottom section. The receipt header and footer may be specified separately for each terminal.

![POSTerminalPrinting](/images/202411/PosterminalPrinting.jpg)

Tabs on POS Terminal Receipt Printing:

**General**: General settings related to Receipt.
**Top Section**: Setup Top part of POS Receipt.
**Bottom Section**: Setup bottom part of POS Receipt.
**Back Section**: Setup Back part of POS Receipt if supported by the POS printer.
**Gift Receipt Bottom**: This section will be used to define Gift Receipt bottom text, applicable for Gift receipt printouts only.

### POS terminal - Receipt barcode

By enabling the Receipt Barcode function, the receipt should have a barcode printed on it. This function is very useful during return transactions. The barcode type can be selected and this function also supports QR code.

The Sales Slip function provides various options to print sales receipts or email sales receipts to the retail customer.

![ReceiptBarcode](/images/202411/ReceiptBarcode.png)

### POS terminal - Display and dual display


A POS pole display may be attached to a terminal. Configure Pole/Line display settings.

![PoleDisplay](/images/202411/PoleDisplay.jpg)

The LS Central dual display is a customer-facing display that can show information on, for example, what is being sold in a transaction or some selected offers in the store.

The dual display is configured in the LS Central back office and must be enabled in the POS terminal card to run. The dual display starts by default on a secondary screen when the POS is run.

If the POS is run from within the LS Central app (in Windows AppShell), the dual display starts in full-screen mode.

The dual display has its own panels and uses controls and menus from the POS profiles.

![DualDisplayExample](/images/202411/DualDisplayExample.jpg)

Configure customer facing display where store can run graphics, images, and videos to influence customers buying behavior.

|Field|Description|
|------|------|
| Dual Disp. Interface Profile | Select this field for terminals that have Dual Display.|
| Dual Disp. Interface Profile | Primary Interface Profile for the Dual Display program.|
| Dual Disp. Menu Profile| Primary Menu Profile for the Dual Display program.|
| Dual Disp. Style Profile| Primary Style Profile for the Dual Display program.|
| Dual Disp. Slideshow| This field is for the Media Playlist Number. The Media Playlist entered here is what the Dual Display will run after it gets a connection with the POS client and the cashier is not logged into the POS.|
| Dual Disp. Screen | This field is set to 0 by default and does not need to be changed unless you have more than two screens in your setup and want to run the Dual Display on a device other than the secondary screen. For example, if you want to set the Dual Display to your third screen, enter 3 in this field.<br/>The Dual Display cannot be run alongside the POS on the primary screen. |

## Store tender

### Store tender

Store tender contains the payment methods available within the store. Common retail payment tenders are:

- Cash
- Currency
- Debit/Credit card
- Coupon
- Gift card
- Loyalty points
- Customer account
  
The Tender Type table contains all the information about the tender types in a Store. For each tender type, such as cash, accounts, and credit cards, you need to define how it handles the amount, change, checks, authorization, and so on in order to ensure it's used correctly on the POS terminals.

### Tender types

All acceptable payment methods are linked with the Retail store from Store card. Before you can post a statement with transactions sales and payments for each tender type, you must set up a G/L account or bank account for each tender type. You will also need to create a G/L account into which you will post the difference between the payment amount and the counted amount for each tender type.

You can assign a infocode to a tender type. Infocodes contain additional information about the Transaction header created at the POS terminals.

When you select the tender type's Function, the system automatically assigns properties for the tender type from the Tender type setup table. The Tender type setup table contains a setup for each tender type in the system, with default functionality for each tender type setup.

**Edit Tender Type**: Use this page to add, edit and delete Tender Types.
**Default Function:**: The field Default Function defines and controls the behaviour of the POS toward a particular tender.

![TenderTypeSetupList](/images/202411/TenderTypeSetupList.jpg)

**Tender types**

All acceptable payment methods are linked with Retail store from Store card.

![TenderTypesStoreCard](/images/202411/TenderTypesStoreCard.jpg)

| Function| Description|
|-----|-----|
| Normal | Function set to normal is used for cash, currency, vouchers, gift cards, and coupons.|
| Card | Function set to card is used for both debit and credit cards. |
| Check | Function set to check is used for checks.|
| Customer| Function set to customer is used for customer accounts.|
| Tender remove/Float | Function set to Tender remove/Float is used for tender remove and tender float.|

### Tender type - Cash

**Function**: Should be set to Normal.

**Amount**: Common Cash tender behaviour should be enabled as shown in picture.

- Overtender
- Undertender
- Return/Minus
- Keyboard Entry

**May Be Used**: The function May Be Used should be enabled for Cash to activate the tender in the store.

**Drawer Opens**: The drawer needs to open automatically and should be enabled for Cash.

**Rounding**: Rounding type & Rounding can be defined.

**Posting**: Cash may be posted to either a G/L or a Bank account. Difference A/C is required to capture overs and unders. Cash posting setup including G/L or Bank Account & difference account should be defined.

**Change Tend. Code**: Define tender code to issue change back to retail customer after Cash transaction.

### Tender type - Card

Cards using different payment methods may have different posting setups. To use cards, the function should be set to Card.

**Card Setup (Action to link)**: Different Card types can be defined with their specific G/L account numbers.

**Card/Account No.**: Should be enabled for Card.

**May Be Used**: Should be enabled for Card.

**Change to Account No.**: Define Income account in case surcharge is applicable. 

**Charge %:** Define surcharge percentage if income account for surcharge is defined.

### Tender type - Customer


Tender type customer is used to:

• Allow credit to the customer.

• Create a Customer ledger entry upon posting a statement.

**Card/Account No.**: Should be enabled for Customer. This function is used to post a credit sale in a customer's account.

**May Be Used**: Should be enabled for Customer.

**Other tender in finalizing**: If a credit sale is disallowed, then the function “Other Tender in Finalizing” on the **Retail customer card** must be enabled to let the customer settle the payment with a different tender such as cash.

### Tender type - Tender remove/Float

**Tender remove/Float**: When using a Store with Safe management, the Tender remove/Float (virtual tender) identifies the cash inside a Safe.

![TenderRemoveFloat](/images/202411/TenderRemoveFloat.jpg)

## Store Income/Expense account

### Income/Expense account

Income/Expense account is used to record a monetary transaction that does not involve the sale of an item.

These accounts are very useful entities to record income or expense transactions within the store (example of a taxi fare, bithday celebration, etc.). These accounts should be configured and linked to the Retail store.

Store Card -> (Actions) -> Related -> Store -> Cash & Safe Management ->Income/Expense Accounts

Note: there is a function to copy the expense accounts from store to store (with an extra function to override).

![IncomeExpense](/images/202411/IncomeExpense.jpg)

**Define account type**: Income account is used to record a deposit/liability such as the payment against a gift card.

Four options are available:

- Income: Register income
- Expense: Register expense
- Suspense: For later processing
- Refund: To issue customer refunds
- 
![ExpenseExample](/images/202411/ExpenseExample.jpg)

### LS Central store setup

Store setups can be copied from one store to another using Copy functions.

![CopyStoreSetup](/images/202411/CopyStoreSetup.jpg)

## Staff

### Staff

The Staff Card contains information about each staff member, such as name, address, and phone number. In addition, it contains information on what actions the staff member is authorized to perform at the POS terminal, for example, voiding transactions, giving discounts, and performing tender declarations.

Each staff member must have a number for identification purposes, both in the Store back office and on the POS terminals.

Staff can be classified as Cashier or Salesperson on the Staff Card.

Store List -> Store Card -> Factbox "Store General Information" -> Number of Staff (XX) <- can navigate from here --> Staff Card

#### Staff Card

![StaffCard](/images/202411/StaffCard.jpg)

**Employment type**: Cashier, Sales Person (can be linked with a salesperson in BC), Both.
**Permission Group**: CASHIER, etc.. **(Staff Permission Group)**
**Personal (tab)**: including pasword.
**Store Link Lines**: here we can link the staff with different stores. If we have a stores managers we can leave the **Store No.** blank on the General Tab on Staff Card (and also on the lines), with this setup store manager can operate in all stores.
**Staff Permissions**: Manager Privileges, Add Payment, Price Override, Open Drw. without..., Void Transaction, Void Line, Return in Transaction, Suspend Transaction...
**MSR Card**: Related -> Staf -> Link MSR Card. *Note*: Login via a barcoded staff card or an MSR card needs to be enabled in the active “Functionality Profile”, as shown in the graphics below and available in the POS functionality profile card.

![MSRCard](/images/202411/MSRCard.jpg)

Three login methods: 
* Staff ID and password
* MSR (Magnetic strip card)
* Barcode (using the Barcode mask setup)

![AllowMSRCard](/images/202411/AllowMSRCard.jpg)

![BarcodeLogon](/images/202411/BarcodeLogon.jpg)

### Staff permission group

It is very convenient to be able to create many staff permission groups, where each group has very strictly defined privileges according to the level of responsibility. This table contains all the factors that can be used when defining permission groups, such as the privilege to void transactions, declare tender, override price, and suspend transactions.

![PermissionGroupOnStaffCard](/images/202411/PermissionGroupOnStaffCard.jpg)

Permission group is used to control sensitive activities on the POS.

Must be assigned to each staff member to provide appropriate access.

![ManagerPrivileges](/images/202411/ManagerPrivileges.jpg)

Manager privileges may be set to:

* **Yes**, if a staff member is granted **all permissions**.
* **No**, if a staff member’s activities are **restricted**.

# CF-300 LS Central for retail Part II

## Item hierarchy

### Item hierarchy

A hierarchy is a multi-level tree structure with Nodes and Links, where the Links can be added to the Nodes. To create this hierarchy, you will need to add Item links. LS Central has a five-level static item hierarchy:

* **Item Divisions** - Contains Item Categories
* **Item Categories** - Contains Product Groups
* **Product Groups** - Contains Retail Items
* **Retail Item** - Standard Business Central item with additional features
* **Variants** - stock-keeping units

![ItemHierarchy](/images/202411/ItemHierarchy.png)

Example:
* **Item to sell**: We have a medium size of Sunny Soda to register. Let's enter the item, we need to decide Item division. In our example, we have two options, Nonfood items and Food items. 
* **Division-NonFood**: The Soda is an food item so we will not select this division. 
* **Division-Food**:We select Food division. 
* **Item Catagory-Beverages**: Categories can be for example Beverages, bread, meat etc. We would select Beverages. 
* **Product group-Soda**: We could create a group that define Soda drinks. Our drink falls under Soda drinks.
* **Retail item-Sunny Soda**: Here we would register our item. 
* **Variants**: Our item could have different options based upon size, color, flavor etc. For example, if this Soda bottle comes in different flavors,  then each different flavor could be represented with the variant.

Each item belongs to only one **Division**, one **Item Category**, and one **Product Group**.

### Item divisions

Item Divisions hierarchy is used for Open-To-Buy, reports/analysis, and retail item search. The uso of Item Divisions is not mandatory and can be left blank.

#### To set up Item Divisions:

1. Seach for the Divisions page
2. Click New action to enter a new Item Division
3. Fill in the Code and Description fields

![ItemDivisions](/images/202411/Item%20Divisions%201-10.jpg)

* **Item Division** is the Top node in the hierarchy.
* May be **left blank** if not required.
* May be used for **Retail Item Search**.

### Item Categories

In the static item hierarchy, the next two levels of item grouping in LS Central are:

* **Item Categories (2nd level):** Each Item Category contains a number of Retail Product Groups.
* **Retail Product Groups (3rd level):** Each Retail Product Group contains a number of retail items.

It is important to have a well-defined **Item Category structure** before you start to set up Item Categories. Before setting up Item Categories, you should define how detailed the Item Category structure needs to be in order to best serve the requirements of your business. Once you have defined the Item Category structure, you create Item Categories and assign closely related Retail Product Groups to the same Item Category.

To ensure the correct handling of retail items, you need to set up Item Categories. You can use Item Categores to:

* Group Retail Product Groups.
* Define default Posting Groups.
* Base POS cost calculation on Item Categories.
* Create and view statistics on an Item Category level.
* Set up an Open Item category sale.

#### Retail Item Category details

* **Code**: This code just defines the Item Category Code. Note that if Division is not being used, item category may act as the top node in the hierarchy.
* **Division Code**: This Link Division code with Item Category.
* **Item Template Code**: An Item Template Code may be created specifying defaults for certain standard Business Central item parameters and assigned to a category.
* **POS Inventory Lookup**: (boolean) Enable POS Inventory lookup if you want all items belonging to this category to participate in Inventory Lookup process.

![RetailItemCategory](/images/202411/RetailItemCategory.png)

### Product Groups

**Retail Product Groups** provide a convenient way of handling **barcode generation**, as well as supporting default variants for the retail items included in the group.

When you select a **Retail Product Group** for a retail item, the Item Category, the posting groups, the section and shelf location, the bar code mask, and the variant groups of the Retail Product Group will all be automatically assigned to the item. When you make changes to these features after you have assigned items to a group, you can use a function to copy these features specifically to the items.

#### Product Groups

* May be used to specify defaults for certain **Retail Item** parameters
* May be used for **POS Inventory Lookup**

##### Retail Product Group Card

![RetailProductGroupCard](/images/202411/RetailProductGroupCard.jpg)

* **Item Category Code:** Link Item Category code for your Product group.
* **Division Code:** Displays Division code linked to Product Group.
* **POS Inventory Lookup:** Enable POS Inventory lookup if you want all items belonging to this product group to participate in Inventory Lookup process.

### Open item category/Product sale

**Business Central** does not allow a sale on **open item groups**. Only sales on items are possible. Nevertheless, you can set up an open **item category sale** or **open product group sale**; meaning that when you have an item that **does not have a registered item number**, you can sell the item as part of a specific **Item Category** or **Product Group**.

#### Retail Item Card detail

![RetailItemCardDetail](/images/202411/RetailItemCardDetail.png)

* **Description:** You can create an item card for all non standard items.
* **Item Category Code:** Miscellaneous category can be created and then linked with random item codes if you don't want to mix sales of these items with your regular items.
* **Retail Product Code:** Open product group can be created and then linked with random item codes if you don't want to mix sales of these items with your regular items.
* **Keying in Price:** If price is not defined for these kind of items, **'Keying in Price'** action can be set on item card which will get triggered at POS when this item comes to POS journal.

## Retail Item

### Retail item

**Retail items** are created and maintained in LS Central primarily to represent Inventory items. It is also possible to create non-inventory and service items in LS Central.

**Retail Items** are:

* a **standard Business Central** item with extensions for the **retail industry**
* having extensions that control how the **POS** reacts to **items** with certain properties.

#### Mandatory fields on the Retail Item Card

* Base Unit of Measure
* Costing methods
* Inventory Posting Group
* Gen. Prod. Posting Group
* VAT Prod. Posting Group
* Unit Price

![RetailItemCardFields](/images/202411/RetailItemCardFields.png)

Extra Tabs: Pricing, Distribution. 
We have an Item HTML with preview.
Variants have a barcode.

## Item unit of Measure

### Retail item - Unit of Measure

Before you start creating **retail items**, you should set up **units of measure codes**, which you then **assign to retail items**. You can set up all required units of measure codes in LS Central.

* **Base Unit of Measure**: Base Unit Of Measure is the unit used by the system to record inventory in the Item Ledger Entry.
* **Sales Unit of Measure**: Sales order will get created with this unit of measure. Relation between Sales unit of measure and Base unit of measure should be defined if both are not same.
* **Purch. Unit of Measure**: Purchase order will get created with this unit of measure. Relation between Purchase unit of measure and Base unit of measure should be defined if both are not same.

The **Purchase Unit of Measure** field defines the unit of measure used to purchase an **item**. This is important in cases where an **item is purchased** in a unit that is **different** from the **base unit of measure**. For example, the base unit of measure for sodas is 'bottle', but the sodas are ordered and purchased in cartons. Therefore, the Purchase Unit of Measure for the sodas should be set to 'carton'.

## Item barcode

### Retail item - Barcode

**Item Barcode** may be defined manually, by obtaining it from the vendor/manufacturer, or it can be generated using the Barcode Mask.

**Multiple Barcodes** may be defined for an item however, only one barcode will be visible on the Retail Item Card.

![ItemBarcode](/images/202411/ItemBarcode.jpg)

### Barcode Mask

LS Central supports barcodes for several entities. You can set up barcode masks to create barcodes for **items, customers, staff, coupons, and data entries**.

In the **Barcode Mask** table, you set up barcode masks for your retail system. Since creating barcodes manually is prone to error, using barcode masks to create the barcodes is a simple, error-free way to create and check barcodes.

The system supports the creation of standard barcodes and in-house barcodes. In-house barcodes are barcodes created and used in your company only.

**Barcode masks** may be required to generate barcodes for different entities:

* Item
* Employee
* Coupon
* Data Entry
* Member Card

**Standard Barcode Masks**

**Standard Barcode Masks** must follow a globally recognized **barcoding standard**. Barcodes often have a fixed structure, for example, EAN standard barcodes. If you are using EAN standard barcodes, with modulus check digit as the last digit, the system can automatically check the validity of the barcode input, and if necessary, calculate the check digit and convert the input into a standard EAN barcode.

#### The LS Retail system supports eight barcode creation and checking standards:
(don't know why we have some repeated)
* EAN8
* EAN13
* UPCE
* UPCA
* EAN8
* EAN13
* UPCE
* UPCA
* QR Code

* **Other Barcode Mask Setup Card** fields:
* **Prefix**: Prefix value can be defined to construct Barcode Mask.
* **Number Series**: You must define Number Series code in case any of segment is using Type 'Number Series'.
* **Segments**: The Barcode Mask Segment table contains the setup of the Masks that are assigned to the barcode mask segment. For each barcode mask, you must create a barcode mask segment with one or more segment lines.

![BarcodeMaskSetupCard](/images/202411/BarcodeMaskSetupCard.png)

**Certain prefixes** Certain prefixes (viz. 02 and 20-29) are normally used by retailers globally to identify variable measure retail items.

**Prefix**: This field contains the first characters used in the barcode mask. You must fill in this field when creating a barcode mask.

**Total length of the barcode mask** =  Total length of segments + Number of characters in the prefix.

![BarcodeMaskSetupList](/images/202411/BarcodeMaskSetupList.png)

**In-house Barcode Masks**

We recommend using a fixed structure for in-house barcodes by using a specific barcode mask, and a check digit. Whether a fixed structure is needed for in-house barcodes depends on the scanner settings on the POS terminals. Some scanners only validate barcodes with a specific format and check digits. The LS Central system supports input from scanners that read the entire barcode number and check the barcode's check digit. When setting up barcodes and barcode masks, you should be aware of the scanner settings the system will be using.

If you choose to use a **barcode mask** for items with **variants**, you can let the program generate the barcodes necessary to represent each **size**, **color**, and **style combination**.

## Retail Item - POS tab

* **Behavior of Retail Item** at POS is controlled using the settings defined under the **POS tab** of Retail Item Card.

* Fields like **Scale Item, UOM Pop-up on POS, Keying in Price, and Keying in Quantity** can be set according to retailer needs.

If **Scale Item** is enabled, one unit of measure has to be enabled as **Weight unit of measure** (a boolean on the Item unit of measure table).
**Scale Item** must be disabled if a barcode exists.
**UOM Pop-up on POS** Must be disabled if a barcode exists.

## Retail item - Sales price

### Retail item - Sales price

Sales price on a **Retail Item Card** can be defined with the help of the following entities:

* **Sales Codes**: A Sales Code of a Retail Price Group is required to price an item. Sales code can be used to set prices for single store or group of stores.
* **Dates**: Date based Retail prices can be set for an item.
* **UOMs**: Multiple prices can be set for different Unit of Measures Codes.
* **Variants**
* **Currencies**

## Actual Inventory

Actual Inventory is calculated by subtracting unposted sales quantities from the total sales quantities (**Actual Inventory** =**Inventory** - **Qty. Sold not Posted** of the POS transactions). Quantities on purchase orders and sales orders are not considered in this calculation.
The Actual Inventory field is available under the Item Inventory Factbox on the Retail Item card. It is a very useful field for finding out the live inventory of any item, at any moment, from the head office (HO) database.

## Variant framework setup

### Retail Item - Variant

**Item Variant** usually applies to items in **fashion retail, accessories retail, electronics, etc.**

Each variant represents an **Item with a unique option value**. Variants represent different available options with respect to an item. These options can be based upon color, size, style, etc.

Variants let you handle retail items that have up to **six different variant dimensions**. By assigning a unique barcode for each variant combination, you can scan the barcode at the POS terminal and let the program find which variant of the item is being sold. You can, therefore, collect and view statistics on variant sales.

On the **Retail Item Card** a **Variant Framework Code** (for example WOMEN) comprising the variants needs can be assigned to the item.

### Variant Framework Base Values

On the Variant Framework Base Values card there's an action to call the combinations. It has some posibilities for automatic selection (to suggest automatically the combinations to create as item variants).
This table is used to **control** which **values** are incorporated into a **combination (framework)** of base values when variants are created.
If a combination uses **'Color'**, for example, this table contains the setup for color options: **black, blue, white**, and so on.
The **'value'** field can be selected from available **'base'** values for this **'Color'**. Only values that have already been pre-defined in base values can be entered.
When creating a **framework (combination of variant dimensions)**, you can set up which **values (colors, sizes, etc.)** are available to the user when variants are created for the item.
The **Value Type field** controls if and when a **value** is part of the variant option for an item:

![VariantFrameworkBaseValues](/images/202411/VariantFrameworkBaseValues.png)

### Variant Framework Codes setup

* **Combinations**: (Action) Defines a framework to combine variant base (usually two or more).
* **Framework Code**: Defines framework code.
* **Registration Type**: Depending on Registration Type the combinations may need to be reconfirmed at the time of creating the variants.
* **Variant suffix/sequence**: Used to define the naming style of a variant record.
* **Barcode Mask**: A barcode mask may be defined to generate barcodes automatically when the variants are created.

![Variant%20framework%20codes%20setup](/images/202411/Variant%20framework%20codes%20setup.jpg)

### Retail Item - Variant Creation

An existing variant set may be appended with unused combinations or create unused variants. If a framework is already in use, you can't introduce a new base or new values for an existing base.

![RetailItemVariant](/images/202411/RetailItemVariant.jpg)

## Item Attributes

### Attributes

Attributes can be **used for filtering** (e.g. in search functinos) and for statistical analysis. Attributes are linked to certain tables and records in those tables are given an attribute value.

* **Hard atribute**: Each category on the filtering list is an Attribute Card.
* **Retail item attribute**: Each option is first set as option value on the Attribute card then attribute is selected on the Retail Item.
* **Filtering**: When we have set attributes to Retail Item we can use it for filtering either in POS or in Web store (example Ironing Yes/No).

### Attribute Card

You give attributes to an Item, Variant, Store, Deal, or other items by using an Attribute Card. Start by adding General information to the Attribute Card

* **Attribute Card**: Example, attribute card for `FABRIC`.
* **Code and Description**: Code is the name of Attribute and and description is shown on filtering options (example `Fabric type`)
* **Attribute type ID**: Here we can define and link Attribute types like Retail, Dining, Clienteling etc.
* **Options - Option Value**: If Value Type is selected as Option Value, then you should provide all possible options under 'option value'. Possible value types: `Text, Numérice, Amount, Date, File, Option Value, Table Link, Weighted Option`.

Once General information has been inputted, you can then add options and types of linking.

* **Assignments** (Action) You can view Assignments list, that will display all items that have this attributes attached.
* **Options** (SubPage List on Attributes card) Here we add line for each options that will be optional on the Retail Item that this Attribute will display on. 
* **Linking** (SubPage List on Attributes card) May be linked individually to an item or to any of the hierarchies.

### Hard Attributes

#### Hard attributes on items and Stores/Restaurants:

When a hard attribute is added to items or stores, a new field is added to the Retail Item Card, the Store, or Restaurant Card. Up to five hard attributes can be added to items and stores.

**Hard attributes** are attributes that are stored as fields in linked tables. The following tables can have hard attributes:

* Item
* Store
* Extended Variant Dimensions

**Item Hard Attributes**: These attributes are set in the Attribute Setup page. Any five attributes may be defined as Hard Attributes which are fields hosted in the Item table. New attribute is created if it does not already exist.

### Attribute on Retail Item Card

The caption of a hard attribute field is updated based on the **Attribute Code** and can be viewed on the Retail item card under the Attributes tab.

Attributes act as useful filters both on POS and in web commerce to narrow down a search.

![RetailItemCardAttributes](/images/202411/RetailItemCardAttributes.png)

**Attribute values** can be set on the **Item / Store / Restaurant** cards on the **Attributes FastTab**. **Attribute values** are stored in the tables so that, for example, items can be **filtered to specific attribute values**. **Values for hard and soft attributes** can be edited in the Attributes Value page and the Attribute Assignments page. The item and store tables are updated accordingly.

## Item Finder

### Item finder - Using item attribute

You can use item attributes to **search** for items on the **POS** with the help of **Item Finder**.

* Items can have multiple attributes
* Items can have soft and hard attributes
* Item attributes can be shown on the POS

You can use item attributes to select items into POS Dynamic Menus. POS Dynamic Menus use attributes for sorting. You can assign sorting attributes to items for this purpose.

A query tool using item attributes as a parameter/filter can be used to find an item on the POS. No Pre Value is set for the Attribute filter so that the POS user can query on any value available for that attribute.

![ItemFinderSetup](/images/202411/ItemFinderSetup.png)

![ItemFinderOnPOS](/images/202411/ItemFinderOnPOS.jpg)

## Special groups

**A retail item can be a part of Special Groups**. They are used for additional grouping outside of the static item hierarchy. Special Groups can be used in LS Central for the Retail Item, such as Search, Reports, Statistics, in Periodic Offers, etc. You can link a special group to an Item Hierarchy. This gives the option of seeing the special groups in the Sales History. (Actions) Related Data > Groups and Links > Special Groups.

* Customizable groups.
* May host items from different Product Groups
* May be used in certain discount offers
* An item may belong to multiple special groups.
* Only one special group code is visible on the item card.

![SpecialGroups](/images/202411/SpecialGroups.jpg)

![SpecialGroupsOnItemCard](/images/202411/SpecialGroupsOnItemCard.jpg)

# CF-300 LS Central for retail Part III

## Price management general

### LS Central includes several tools for sales and price management.

The **pricing mechanism** in LS Central is built on the price structure in Dynamics Business Central. Items can have multiple prices that are valid at different dates/times or based on different tender types. Different stores and/or customers can enjoy different prices and these are just a few of the avialable options.

Promotions appear as a temporary price change, whereas discount offers are used to provide a periodic discount. Offers can be defined by a specific store or group of stores, date period, time period and/or specific weekdays, customer and/or Member Schemes and/or Member Attributes. Offers can also be triggered by coupons.

The system will calculate a specific customer price and retail price,  which are then compared to give the customer the lowest price.

| Category | Pricing Options |
|----------|----------------|
| In LS Central, it is possible to set prices for: |POS terminal defined prices and discounts: |
| <ul><li>Customers</li><li>Stores</li><li>Promotions</li><li>Periodic Offers</li></ul>| <ul><li>Line Discount</li><li>Total Discount</li><li>Price Change</li><li>Keying in Price</li></ul>|

## Retail Price Groups

Retail Price Group is based on the standard Customer Price Group table plus any LS Central additions, for example, the Store Group to which the item should belong. Retail Price Group is used for the Replication distribution of an item.

Retail Price Groups are assigned to Stores, where the default priority can be changed. The ihgher the number is, the higher the priority is. This is the rule when working with Retail Price Groups.

![RetailPriceGroups](/images/202411/RetailPriceGroups.jpg)

### Store Price Groups

This field contains the code of the Distribution Location that the price group is valid in.
The program fills in this field automatically.

![StorePriceGroups](/images/202411/StorePriceGroups.jpg)

### Item Prices can be set per:

* Store
* Unit of Measure
* Currency
* Variant
* Date range

![ItemPrices](/images/202411/ItemPrices.jpg)

## Promotions

### Promotions

LS Centra provides various possibilities for adjusting the sales price of the POS, for example, by using promotions and offers. You will learn more about the different offer types in the coming sections.

Promotionsis an automated way to set a sales price for an item or group of items. **Promotional Price** doesn't show a discount in POS journal nor does it print on the POS receipt.

1. Open the Promotion List
2. Click on New
3. This will create a new Promotion that can be defined according to Lines, Triggers, Benefits, and Settings

![PromotionList](/images/202411/PromotionList.png)

Promotion is an automated price change, not a discount. It does not generate Trans. Discount Entry.

![PromotionCard_Enabled](/images/202411/PromotionCard_Enabled.jpg)

## Price Group

* **Price Group**: Brings base prices to an active Promotion.
* **New line/item**: Selecting the appropriate type (**Item, Product Group, Item Category, All and Special Group**) and No.
* **Unit of Measure**: Define unit of measure for which promotional price should trigger.
* **Validation Period ID**: this is the period when the promotion is available.

![SoftDrinkPromotion](/images/202411/SoftDrinkPromotion.jpg)

![PromotionTriggers](/images/202411/PromotionTriggers.jpg)

* **Currency Code**: I fStore has specific Currency Code.
* **Customer Discount Group**: Select if Promotion is only active for specific Customer Group.
* **Coupon Code**: Use if Promotion is only active for specific Coupon.
* **Coupons Qty. Needed**: Number of Coupons needed to trigger the promotion.
* **Member Management**: Culb or Scheme, Member attributes.

### Benefits

![PromotionBenefitsTab](/images/202411/PromotionBenefitsTab.jpg)

* **Discount**: Discount percentage applicable oto Promotion lines.
* **Discount Amount**: Discount Amount applicable to Promotion lines.
* **Rounding Method**: Rounding method for promotion discount.

### Settings

About the settings tab:
* All types of active periodic discount involving an item on promotion may be blocked.
* Changing the price of an item on promotion may be blocked.

![PromotionSettingsTab](/images/202411/PromotionSettingsTab.jpg)

## Validation Periods

**Note**: Validation periods are not mandatory.

LS Central provides various possibilities for adjusting the sales price on the POS, for example, by using promotions and offers. You will learn more about the different offer types in the coming sections.

A validation period can be set on all offer types. If no validation period is selected, the offer is not restricted by a time period.

The **validation period** is used to set up different **groups** of **validation periods** that can be used to define when certain **discount types** are **valid**. You can set a **start** and **end date**, a **valid time** for each **weekday**, and select whether the dates and times are **valid within** or **outside** the time bound set for that period.

You can use **discount validation periods** when you want to set limits on the **validation period** for **Periodic Discount groups**, **Offer**, and **Mix & Match Line Groups**.

To view the Validation Period, go to the **Validation Period Setup List**.

* **Validation Period Setup Card**

* **Description**: This field contains a description of the Validation Period. Required to define the period in which a promotion or an offer is active.
* **Start Date and Ending Date**: The **Starting Date** and **Ending Date** fields act as the primary validation. You can not add a validation time for each day if the time is set here. You can either select a time that applies to all days or select a time for each day.
* **Time within Bounds**: A checkmark in this field indicates that the validation period is valid within the Starting Date and Ending Date. If **this field is not marked**, then Starting Time and Ending Time represent the period during which the period is not valid. If Starting Time and Ending Time fields are not filled in, a checkmark in this field indicates that weekedys with no time restrictions are valid for this validation period. If this field is not marked, the weekdays with no time restrictions are not valid for this validation period.
* **Starting Time**: This field contains the time when the validation period starts.
* **Ending Time**: This field contains the time when the validation period ends.
* **Days Valid**: Here you can see what days are valid. To set activation to days of the week you need to fill out below for each day.
* **Time Restrictions**: This is an overview of what days of the week have time restrictions. In this overview there are no time restrictions so none of the days are active (Time Bound on Monday, Tuesday...).

![ValidationPeriodSetupCardDetail](/images/202411/ValidationPeriodSetupCardDetail.png)

* **Timeless offer**: For a timeless offer, the date fields are left blank.

![TimeLessOffer](/images/202411/TimeLessOffer.jpg)

* **Time-Bound Validation Period**: An offer may be time-bound or active only during certain hours of a day. An offer may be active during different hours depending on the day of the week.

![TimeBoundOffer](/images/202411/TimeBoundOffer.png)

* **Offer Beyond Midnight**: If the Ending Time is lower than the Starting Time, then the offer runs beyond midnight. Useful for retail business which operates round the clock.

![OfferBeyondMidnight](/images/202411/OfferBeyondMidnight.jpg)

### Discount offers

A Discount Offer gives a discount from the regular price and is the most basic form of automated discounting. A Trans. Discount Entry record is created upon posting of Store Statement.

Discount the promotion price if an item is featured in both a promotion and a discount offer at the same time. Once triggered, Discount Offer displays discount in POS journal and can be printed on POS receipt. 

![DiscountOfferCardDetail](/images/202411/DiscountOfferCardDetail.jpg)

**Discount Offer Card details**

* **Price Group**: Select Price Group from where Discount offer will take Standard prices.
* **Priority**: Default priority appears, can be changed.
* **Discount tracking**: Slect, in case this discount offer is used to track Staff discount allowances.
* **Validation Pediod ID**: Select Validation Period.
* **Information Tab**: You can always click in information sign to expand and collapse overview information section.
* **Type**: This field specifies the type of the discount offer line. The options are:
    - **Item** - The offer line includes an Item.
    - **Product Group** - The offer line includes a Product Group.
    - **Item Category** - The offer line includes an Item Category.
    - **All** - The offer line includes all Items.
    - **Special Group** - Offer line is based on Special group.
* **Variant Type**: An offer may be restricted to a specific variant of an item, choowse ariant Type from available options: Variant and Dimension 1.
* **Variant Code**: If an Item with variants is selected for the discount offer line, you can use this field to select rrom the available Variant Codes.
* **Exclude**: If true, excludes an ite, an Item Category or a Product Group from an offer depending on the Type used in the offer line.
* **Unit Of Measure**: This field contains the unit of mesasre used for the discount offer in question. If empty, the sales Unit of Measure is used. An offer may be restricted by the Unit Of Measure of an item when the item has multiple Sales UOM.

### Amount to Trigger

**To activate an offer using 'Amount to Trigger'**:

* The transaction must include at least one item which is part of the offer.
* The transaction total should be greater than or equal to the trigger amount specified.

![AmountToTrigger](/images/202411/AmountToTrigger.png)

## Discount offers - Additional benefits

### Additional benefits

Optional benefits that a customer can get from an offer include: 

* Gift Items
* Buying an Item for a specific amount
* Return Coupons
* Extra Loyalty Points

**Discount Offer Benefits**:

* **To edit Discount Offer**: To edit a discount offer, the offern needs to be **Disabled**.
* **Type - Item List**: List of gift items can be dispalyed with the type Item-list. Infocode with Usage Category = "Optional Benefits" and Value Type and Value = Blnak.
* **Coupon**: The Coupon is printed with the receipt at the end of the sale.
* **Member Points**: Value Type = Points -> Value = Number of additional points earned. Value Type = Factor -> Value = Multiply Factor with normally earned points.
* **Value Type**: Value Type = Amount (applicable for Items), Value Type = Points (Extra Points earned), Value Type = Factor (Multiple of normal points earned).
* **Value**: Value should be empty for gift/fee items. Reduced value for an item can be set here.

### Additional benefits at the POS

![AdditionalBenefitsPOS](/images/202411/AdditionalBenefitsPOS.jpg)

* When benefits are items and Total is pressed, a pop up will appear with the selections .
* A coupon is automatically printed before the receipt.
* Member Points are automatically added to the sale.

## Multibuy discount

### Multibuy discount

With **multibuy discount**, it is possible to give different levels of discount based on the quantity sold. To view Multibuy Discount, go to **Multibuy Discount List**.

Multibuy Discount encourages customers to buy more, which, in turn, provides a greater discount.

![MultibuyDiscount](/images/202411/MultibuyDiscount.jpg)

* **Discount Type**: Discount Type can be Deal Price, Discount % or Discount Amount.
* **Discount Lines**: Discount Lines are set of discounts with an increasing number of items. The Multibuy Discount Line table contains the minimum quantity and the discount price of percentage set for a Mix & Match Line Groups.
* **Min. Quantity, Multibuy Discount Line**: This field contains the mimnmum quantity sold of the retail item for the multibuy discount in the line to take effect.

## Mix & Match Discount

### Mix & Match

The **Mix & Match Offer** uses line groups to create a mixing of one or multiple offer lines. It uses the field **'No. of items needed'** to define the fixed quantity for every offer line in the mix. With the help of **Mix & Match Offer** and line groups, we can create various permutations and combinations to provide benefits to customers.

### Mix & Match Lines

![MixAndMatchCardDetails](/images/202411/MixAndMatchCardDetails.jpg)

* **Priority**: Default Priority, could be changed.
* **Type**: The Mix & Match Lines can have the following type: **Item, Product Group, Item Category, Special Group.**
* **No. of Items needed**: If No. of Items Needed is a variable quantity, then it is defined as a Range in Mix & Match Line Groups.
* **Line Group**: Uses the function, Mix & Match Line Groups to create a mix with one offer or multiple offer lines.
* **Validation Period ID**: Specify Validation period.

### Mix & Match benefits 

* **Discount Type**: options -> Deal Price, Discount %, Discount Amount, Least Expensive, Line Spec.
* **Discount % Value**: Percentage of the discount.
* **Same/Diff. M&M Lines**: * Mixing of items may be restrictive, * Often used to clear out slow moving items.
* **No. of Times Applicable**: Offer may be set to trigger `X` time(s) per transaction.

### Mix & Match configuration templates

#### **Least expensive free**
* The customer needs to buy 3 items to get the least expensive item for free.
* All items are in the same line group, so any 3 items or combination of items can trigger the discount.
* The discount is automatically entered for all M&M lines, proportionally distributed among the items.

![LeastExpensiveFree](/images/202411/LeastExpensiveFree.jpg)

#### **Buy two, get one free**

The same setup as for least expensive free except now there is only one item line

![BuyTwoGetOne](/images/202411/BuyTwoGetOne.png)


#### **Buy 5, get 2 free**

![Buy5Get2](/images/202411/Buy5Get2.jpg)

#### **Buy 2, get line specific discounts**

![Buy2GetLineSpecificDiscounts](/images/202411/Buy2GetLineSpecificDiscounts.jpg)

#### **Deal Price *

Buy one item from group A and any item from group B for a total price of 99.00. 

![DealPrice](/images/202411/DealPrice.jpg)

#### **Buy two items in the same Product Group, get a 15% discount**

![Buy2GetLineSpecificDiscounts](/images/202411/Buy2GetLineSpecificDiscounts.jpg)

#### **Buy Item A and 2 – 4 items B, get 30% discount**

![BuyItemAGet30Discount](/images/202411/BuyItemAGet30Discount.jpg)

#### **Pop up Mix & Match options on POS**

Buy item A and one item in Line Group B and get 10% off.

![PopUpOption](/images/202411/PopUpOption.png)

Here you can see what the pop up looks like when the Mix & Max offer is triggered

![PopUpOnPOS](/images/202411/PopUpOnPOS.jpg)

## Total discount offer

### Total discount offers

**Total Discount Offer** is created to encourage customers to spend more and provide invoice amount-based benefits. The more the customer spends, the better the benefit they will be offered with the help of this discount offer.

The triggering of **Total Discount Offers** is the same as for other offers with one exception, the **Step Amount selection** of the Total Discount Offer and Benefits. The Step Amount is triggered against the total amount of the transaction. The discount and the distribution of the offer discount are triggered against the item lines defined in the offer. The total amount of the transaction activates the highest possible Step Amount. This means that the steps are not accumulative. 

As defined on the Benefits FastTab, a Total Discount Offer can have many **types of benefits** such as giving Discounts, Items, a selection from an Item-List, Member Points, and Coupons. Each Step Amount can have a benefit defined under the Type field and if the Step Amount triggers an offer, the customer is entitled to get the defined benefit. **Discounts, Points, and Coupons are awarded automatically** but gift items have to be selected by the customer. The Total button on the POS will open a pop-up for the customer to select gift items from all available gifts on the Item list.

**All valid Total Discount Offers are activated on the POS when the Total button is pressed.**

### **Total discount benefits**: 
Different benefits may be set for different totals as displayed under the Benefits tab. Total must contain at least one item which is part of the offer.

In this example, we have step amounts of 50, 100 and 200 and the Value type is %, % and Amount, with the values 5, 10 and 50 (meaning for amounts > 50 -> 5%, amounts > 100 -> 10% and finally Amounts > 200 -> 50 of discount amount - not percentage)

![DiscountOfferBenefits](/images/202411/DiscountOfferBenefits.png)

**Total discount benefits**: Different benefits may be set for different totals as displayed under the Benefits tab. Total must contain at least one item which is part of the offer.

![TotalDiscountOffer](/images/202411/TotalDiscountOffer.png)

* **Type**: Appropriate type can be chosen from Type field: **Item, Product Group, Item Category, All and Special Group** are the options.
* **Excluding Item**: Item, Product Group, Item Category or Special Group can be excluded from Offer with the help of Exclude field.
* **Type of benefits**: Benefit types available under this field: **Discount, Item, Item-List, Coupon, Loyalty Points**.
* **Discount Value**: Veaue Types Aavilable in this field: **(blank), %, Amount, Points, Factor**.

## Line discount offer

### Line discount offer

**Line Discount Offer** is an offer type that functions similarly to other Discount Offers. It can be triggered either automatically or manually according to setup. **This offer type gives the retailer the ability to control and define the discounts that are allowed**.

A typical way to use a **Line Discount Offer** is to use it to control **how much of a discount to give** when the item is damaged in some way. By creating a Discount group and setting up discounts in the group to cover all possible and acceptable discounts for damaged items, it is possible to have a **range of offers covering each category** of the operation or even one offer covering everything. After creating and setting up the offer, the only thing needed is to **define a button on the POS to activate the selection of the best offer** within a given Line Discount Group. 

To view Line Discount Offer, go to **Line Discount Offer List**.

![LineDiscountOfferCard](/images/202411/LineDiscountOfferCard.png)

* **Type**: When a new line is created you can select from all to a specific item. Here you add what should be included or excluded in the Line Discount Offer. Values: **Item, Product Group, Item Category, All, Special Group**.
* **Line Discount group code**: Primarily used to replace the manual line disocunt scenarios.
* **Line Discount Execution**: Three options are available to choose from: "Manual-Line, Manual-Trans. and Automatic".
* **Customer Disc.**: To trigger this offer for specific Customer Group.
* **Coupon Code**: To trigger this offer for specific Coupon.
* **Coupon Qty. Needed**: Define Coupon quantity required to trigger, Coupon code column should be filled.
* **Member type**: Here you can select between Scheme or Club. Then member Value varies based on this selection.
* **Member value**: This drop down menu varies from the selection above. You remember the difference between Scheme and Club in member management.
* **Member attributes**: Here you can trigger the Line Discount offer by member attributes. Member attributes value is then based on selection in field.
* **Member Attribute Value**: Select Attribute value for Member Attribute selected above.
* **Sales Type Filter**: Select Sales Type if this Discount Offer is specific to selected sales type.
* **Price Group Validation**: Select Price Group if Offer requires validation with specific Price Group.
* **Discount Value**(Benefits tab): Here you select if the benefit should be disount % or Amount.

## Tender type offer

### Tender type offers

**Tender Typer offer** is used to provide associated benefits if the customer is paying with a specific payment mode like currency, specific credit card, etc.

The activation of **Tender Typer Offers** is the same as for other offers with **one exception - the Tender Type Triggers filtering**. Tender Type offers are always calculated last as part of the calculation sequence, **wihic cannot be defined for other types of offers**.

Another extension to Tender Type Offer is the ability to define a pop-up for all available offers when the Total button is pressed on the POS. Offers that do not pop up when the Total button is pressed will pop up when the corresponding tender type is selected as payment. This is done in order to ask if the cusomer is willing to finalize the transaction with the tender because **Tender Type Offers are limited to finalizing a transaction with one tender**. The transaction, therefore, can only be fully paid with the tender type of the offer.

To view Tender Type Offers, go to the **Tender Type Offer List**.

![TenderTypeOfferCard](/images/202411/TenderTypeOfferCard.png)

* **Type**: Here you can select the item or Group for which customer gets discount. Available options are: **Item, Product Group, Item Category, All, Special Group**.
* **Tender Type Code**: Triggered wihil choosing the payment tender.
* **Tender Type Value**: This field varies depending on what option you choose in the Tender Type Code.
* **Other triggers**: They have the same values and actions as in Discount Line Offer.
* **Benefits**: Either **Tender Offer % or Tender Offer Amount** can be epecified.

## Discount offers - Priority

![DiscountOfferList](/images/202411/DiscountOfferList.jpg)

**Discount offer list**: Priority

It is a field used to prioritize overlapping offers
* Shared by all types of discount offers
* **LOWER** value has a **HIGHER** priority
* Works based upon priority sequence

Priority values of active offers containing the same item(s) may be swapped using the function **Change Priority**.

![DiscountOfferPriorities](/images/202411/DiscountOfferPriorities.jpg)

From **Discount Offer** card we can navigate to the Periodic Discount Priority card, this card show us different views of overlapping offers. The different options for the overlapping list are: **Show all offers, Show offers overlapping Item/Variant, Show offers overlapping Product Group, Show offers overlapping Item Category, Show offers overlapping Item Special Group and Show overlapping offers**. There's an action on this page to **Change Priority** that helps us to change the priority order.

## Rules of prioriy in price calculation

1. Retail Price, defined for the store, is fetched; if the item is on a Promotion then the Promotion price is used.
2. If any Discount Offer is triggered, the  the discount is either calculated on the base price or on the promotion price.
3. If the sale is linked with a customer, then the customer price is compared with the discounted price; the better price is chosen.
4. If a Deal is available, then all above calculations are ignored.
5. Any manual discounting is applied after all the automated price calculations are done.

### Price Priority

**Active price** is the **best price** from:

![ActivePrice](/images/202411/ActivePrice.png)

* Promotion
* Sales Price
* Customer Price

### Active Price

**Active Price** is the price the discount is given on.

![ActivePriceDiscount](/images/202411/ActivePriceDiscount.png)

If the **Active Price** is a **Promotion Price** and the **Promotion** is marked to **disable periodic discounts**, the **periodic discounts** will not affect the Price.

For **Mix & Match**, **Discount Offers**, and **Multibuy** you can set up priority for overlapping discounts.

## Archived offers

**Offers** can be archived by a scheduled job or manually by using the **Archive action** in the **offer card pages**. Offers stored in the **Discount Offer table** (99001453) can be archived. When an offer is archived, the offer data is **copied** to archived tables and **deleted** from the working tables. This makes all processing with offers **faster**, especially **priority changes** and **POS operations**.

There's an Action to **Restore Offer** on the **Archived Offer Card**.

## Coupons - Manufacturer

### Manufacturer coupon

**Manufacturaercoupons** are issued by the manufacturer of a product in order to **increase sales** and **product awareness**. These coupons are commonly printed on the **product's packaging**, in **newspaper, or in magazines**. Once accepted, the manufacturer owes the store the coupon amount. Thus, these coupons **do not affect** the **profit** on the **sold item**.

### Default type

**Default Handling, Default Price Group, and Default Type**: These are settings that are **copied** to a **coupon** when it is **created** for the issuer.

Coupons must be issued by the **Manufacturer** or the **Retailer**. Select from the **Default Type** field.

The **Coupon Issuer Card** is used for setting up the registration of coupon issuers. When you register these, you can trace from whoim you accept coupons.

You can use the **information** in this table for **invoicing coupon issuers**, and, if needed, **block coupons** from a specific issuer.

![CouponIssuerCard](/images/202411/CouponIssuerCard.jpg)

### Discount or tender

The handling of the discount is defined in the **Handling** field under 'Fast tab' "Use" and there are **two options**:

* **Tender** - If you want to handle the coupon as a tender, it **will not affect the profit** on the item sold. 
* **Discount** - May **directly or indirectly trigger a discount** through an offer. Store coupons are usually handled as a discount, which will affect the profit. 
 
**Calculation Type** - This field can be set to Discount or Triggers Offer.

**Discount Type** - This field can be set to Discount % or Discount Amount.

**Barcode Mask** - This field contains the barcode mask used to generate the barcode for the issued coupon.

**Extra Print Setup** - This field contains the print setup used for printing the coupon.

**Rounding Method** - This field contains the rounding method used when calculating the issued coupon value.

![StoreCoupon](/images/202411/StoreCoupon.jpg)

### Use restriction

Coupons must have **Use Restriction** defined if not used as a **trigger** in a **discount offer**. 

You can **define information** about which **item** or **item groups** the **coupon applies to** in the **Use Restriction tab**.

![UseRestriction](/images/202411/UseRestriction.jpg)

### To identify coupons on the POS

To be able to identify **coupons** on the **POS**, you need to set up a **Barcode Mask** for the coupons.

The Barcode Mask is a combination of a **prefix**, the Coupon Issuer’s **EAN number**, the **Coupon Reference No**, price or a discount, and a check digit.

* **Barcode Mask** - This field contains the barcode mask used to generate the barcode for the issued coupon.

You must use a **Barcode Mask** while defining each **element** of the **mask**. 

The system will find the coupon setup by looking it up using the **Barcode Mask**.

![StoreCoupon](/images/202411/StoreCoupon.jpg)

## Coupons - Store

### Store coupons

**Store coupons** are issued by the store itself. The **difference** from a **manufacturer coupon** is in the **handling of the coupon**. The store coupon is **handled** as **discount** and **does affect the store profit**.

### Store cupons as discount or tenders

* ***Store Coupon - General**: With the **Store Coupon**, the coupon issuer is the store itself and handling is set as **Discount** rather than **Tender**, as with a manufacturer coupon. General Tab Fields:

**Coupon Issuer**: Coupon issuer can be selected on the Store coupon.
**Use Restriction**: Use restrictions with applicable type and values can be defined as lines.
**Price Group**: You can select the Price Group where this coupon should be applicable.

![StoreCouponDetail](/images/202411/StoreCouponDetail.jpg)

* **Store Coupon - Issue** Issue Tab Fields:

**Calculation Type**: Select Calculation Type from **Discount or Triggers Offer**.
**Discount Type**: Select Discount Type from **Discount Amount or Discount %**.
**Barcode Mask**: Link Barcode Mask to read barcoded coupons.
**Barcode Element**: Define barcode elements to read from barcode (Prefix, Coupon Reference No., Discount %, Check Digit...).

* **Store Coupon - Use**: Under the Use tab, various validations, along with criteria to use Store coupons, are defined. Store Coupon Use Tab Fields:

**Handling**: Define Handling of coupon from: **Tender or Discount**.
**Affects**: Select how scanning of coupon Affects at POS: 

- Any Item Line - You can scan the coupon any time after you have scanned the item that triggers the disount.
- Last Item Line - You need to scan the coupon directly after you scanned the item that triggers the discount.
- Next Item Line - You need to scan the coupon before you scan the item that triggers the discount.

**Member Type**: Select Member Type from **Scheme or Club**.

![StoreCouponUse](/images/202411/StoreCouponUse.png)

## Coupons - Return

### Return coupons

This is a coupon that is issued at the POS in order to encourage the customer to return to the store. The coupon is usually in the form of some sort of discount or payment.

These coupons can only be issued at the end of the sale and the coupon gets printed along with the Sales receipt.

Return Coupon will affect any item defined under Use restrictions when scanned at the POS.

* **Return Coupon**

- Used as a tender
- Triggers a discount
- Issue and Use restrictions applicable
- Printed along with the sales receipt

![ReturnCoupon](/images/202411/ReturnCoupon.png)

![ReturnCouponUse](/images/202411/ReturnCouponUse.jpg)



