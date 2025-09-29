# CF-300 LS Central for retail Part IV (`second part`)

## Gift card

### Gift card

#### Customer scenario

A customer wants a gift card (of any denomination) to be issued and redeemed at the POS. In other words, a gift card can be sold as an item as well as accepted as a mode of payment.

When processing a return, instead of refunding the customer in cash, **the customer wants to be issued a voucher**, which can also be used as a form of payment at the POS. 

A **gift card** can be used as a form of payment at the checkout when making a purchase. 

* Either a paper-based or preprinted plastic card can be used as a gift card.
* When printed it uses a template and the gift card will be printed along with the sales receipt.
* The amount on the card may be redeemed over multiple transactions.

#### Gift card - Components

To be able to create and use a gift card, we need following components:

* **A Data Entry Type**
* **Two Infocodes linked with the Data Entry Type**: One to sell the gift card and One to redeem the gift card.
* **An Income Account or an item linked with the infocode used for selling.**
* **A Tender Type linked with the infocode used for redeeming.
* **Two POS Buttons (Commands): Income Account /Item and Tender Type.

#### Data entry type - Gift card

While being redeemed, the gift card goes through validations. It must use certain validation routines during redemption. Examples of validation include,
- that the card is registered
- the outstanding amount is available

Go to POS Data Entry Type in your VM and view the GIFTCARDNO

![GiftCardDetail](/images/202411/GiftCardDetail.jpg)

* **Check Amount**: Validates Gift Card balance.
* **Numbering**: Must be numbered, either automatically or a number series (Options= No. series, Automatic, None).
* **Barcode mask**: Link Barcode Mask if you like Gift Card to be barcoded.
* **No. of open entries**: It displays Gift Cards with open balances.
* **Use Full Remaining Balance**: You can force customer to use entire balance while redeeming Gift Card.
* **One Time Redemption**: You can force customer to do Gift Card redemption in single transaction.
* **Refill**: Enable if you want top-up facility with your plastic Gift Card. If Refill is enabled, then Expiration Policy cannot be set.
* **Expiration Policy**: If enabled, need to define Expiration Formula for Gift Card validity from purchase date.
* **Print Remaining Balance**: If enabled, on customer enquiry, you can print gift Card Balance from receipt printer and handover to customer.
* **Expiration Formula**: Gift card may have an expiration. The Expiration Policy check box is selected, enter the Expiration Policy here. For example, 1Y.

#### Infocode - Create data entry

**Go to the Infocodes in your VM and search for the GIFTCARDNO to view.**

![Infocodes](/images/202411/Infocodes.png)

#### Infocode - Apply to entry

**Go to the Infocodes list in your VM and search for the GIFTCARDIN to view.**

![Infocodes2](/images/202411/Infocodes2.png)

#### Income account

**Go to Store list in your VM and select store S0001 and navigate to the Income/Expense Accounts as shown in the image below.**

![IncomeExpenseAccounts](/images/202411/IncomeExpenseAccounts.jpg)

![IncomeExpenseAccountCard](/images/202411/IncomeExpenseAccountCard.png)

* **Infocodes**: Income Expense is linked to the Infocodes through actions.
* **More options**: with the option to Print Setup Card.
* **Description & Account Type**: While being sold the Gift Card generates a liability income.
* **POS VAT Code**: Usually an income like this does have a tas elemento to it.

#### Tender type in Store

![TenderTypesInStore](/images/202411/TenderTypesInStore.jpg)

![TenderTypeCardGiftCard](/images/202411/TenderTypeCardGiftCard.jpg)

* **Infocodes**: Here we use the Infocode GiftCardIn
* **May be Used**: Must be enabled
* **Amount**: Both overtender and undertender may be allowed. Refund to the card not applicable.

#### POS button - Income account

![POSButtonIncomeAccount](/images/202411/POSButtonIncomeAccount.jpg)

* **Command**: Select Command **INCEPX**
* **Parameter**: Select Income account as parameter
* **Gift card sale**: Give the button name shown in the POS.
* **Right click on button**: When you right click on button, select Button Properties.

#### POS button - Tender type

![POSButtonTenderType](/images/202411/POSButtonTenderType.jpg)

* **Command**: Select Command **TENDER_K**

## Return voucher

### What is a return voucher?

A **return voucher** is a liability document issued by a retailer to a customer against the value of returned goods or services. **A return voucher is issued during a sales refund and printed along with the sales receipt**. The amount on the voucher may be redeemed over multiple transactions.

### Voucher - Components

- [ ] A Data Entry Type
- [ ] Two Infocodes linked with the Data Entry Type: One to issue the voucher. One to redeem the voucher.
- [ ] A Tender Type linked with both infocodes
- [ ] A POS button (command): Tender Type

### Data Entry Type - Voucher

While being redeemed, the **voucher** goes through validations. It must use certain **validation routines** during redemption. Examples of validation include,
- that the voucher is registered
- the outstanding amount is available

**Go to POS Data Entry Type in your VM and the VOUCHER**

![VoucherPOSDataEntryTypeCard](/images/202411/VoucherPOSDataEntryTypeCard.jpg)

* **Numbering**: Must be numbered, either automatically or with number series.
* **Barcode**: To generated barcoded **Return Voucher**, link Barcode Mask.
* **Expiration**: Set expiry date formula by enabling **Expiration Policy**.

### Infocode - Create Data Entry

**Go to the Infocodes list in your VM and search for the VOUCHER to view.**

![InfocodeCardVoucher](/images/202411/InfocodeCardVoucher.jpg)

* **Type & Data Entry Type**: - Specal Type used for Vourcher. - Linked with the Data Entry Type. **Create Data Entry** is isued to issue Return Voucher.
* **Input Required**: Input Required could be **enabled**.

### Infocode - Apply to Entry

**Go to the Infocodes list in your VM and search for the VOUCHERIN to view.**

![InfocodeCardVoucherIn](/images/202411/InfocodeCardVoucherIn.png)

* **Type & Data Entry Type**: - Specal Type used for Vourcher redemption. - Linked with the Data Entry Type. **Apply To Entry** is isued to redeem Return Voucher.
* **Input Required**: Input Required must be **enabled**.

### Tender Type

Store Card has an Action on the Action tabs called **Cash Management**

![TenderTypeCardVoucher](/images/202411/TenderTypeCardVoucher.png)

* **General**: While being both, issued & redeemed, the voucher is a payment tender.
* **Must be linked with both infocodes**: When Required must be set to: - Negative for Create Data Entry. - Positive for Apply to entry.
* **May be Used**: Should be enabled.

### Tender type - Extra print setup

![ExtraPrintSetup](/images/202411/ExtraPrintSetup.jpg)

**There are two templates used to print:**
•The voucher while being issued
•The voucher endorsement while being redeemed

**'When Required' must be set to the following:**
•'Voucher Re-Issue' for Create Data Entry
•'Positive' for Apply To Entry

### POS button - Tender type

•A button in the payment menu
•Points to the Tender Type defined for the voucher

As shown in the image below:

![POSButtonVoucher](/images/202411/POSButtonVoucher.jpg)

## Infocodes

### Infocodes

**Infocodes** are used to add extra information to the POS sales. Here are some examples of the type of extra information you might want to add.

Reasons why the:
* customer is returning an item.
* cashier is giving a discount.
* cashier is Voiding a Transaction.

Additional information or survey like:
* Postcode
* Age
* Gender

Infocodes Data Entry Types: (blank), Selection, Date Input, Numeric Imput, Item Input, Customer Input, Staff Input, Create Data Entry, Apply To Entry, Text Input, Group.

Information can be viewed and used for reports, analysis, statistical purposes, and other operational controls.

## Infocodes assignment - Command and post command

### Infocode setup

#### Infocode types

* Infocodes can have different info types
* The type defines the kind of input required
* Type selection requires the set up of Selection Subcodes

![InfocodeTypes](/images/202411/InfocodeTypes.jpg)

### Input Infocodes

If the **Infocode type** requires input, the **POS terminal** validates the input keyed in or the code selected and checks its value according to the type.

|||
|---|---|
|Date:|The input must be in a valid date format with respect to the system date format.|
|Numeric:|The input must be numeric.|
|Customer:|The input must be a customer on file at the POS terminal.|
|Staff:|The input must be a valid Staff ID.|
|Text:|The input must be text.|

### Input Infocodes - Text

Example Post Code Survey:

![InfocodePostCodeSurvey](/images/202411/InfocodePostCodeSurvey.png)

* **Type**: Text input
* **Display Option**: Alphabetic Pad
* **Once per Transaction**: Set these kind of Infocodes **Once Per Transaction** marked
* **Random Factor**: Random Factor % can be **defined**

The command on POS would be **INFO_K**

![POSCommandPostCode](/images/202411/POSCommandPostCode.jpg)

**Note**: This command INFO_K is used to manually associate an Infocode with a sales line or transaction through a menu.

## Infocodes assignment - POS actions

### Infocodes - Type selection

1. Type selection Infocodes use a number of predefined inputs -The predefined inputs are set up on fast tab Selection Subcodes.
2. The user only needs to select the appropriate code as a response to the Infocode query. 
3. The Type is Selection.
4. Display Option can either be Pop-up or Lookup.
5. If the Input is Required, it is mandatory for the cashier to select a code.

![InfocodeSelection](/images/202411/InfocodeSelection.png)

### Assigning Infocode to a POS action

* POS Actions allow the POS to run some “actions” based on typical POS events.
* You can, for example, assign an Infocode to the Action Trigger “Refund Sales”.

![InfocodePOSAction](/images/202411/InfocodePOSAction.png)

## Infocodes linked

### Infocode linking

You can link one Infocode with another Infocode. Linked Infocode under the General tab field is used to link one infocode with another infocode.

![LinkedInfocode](/images/202411/LinkedInfocode.png)

### Linking Infocode to a selection

You can also link another Infocode to type selection Infocodes.
**Example**:  If the cashier is giving a Customer a discount at the POS and the reason is not listed under selection values, the cashier can select “Other”. We can link another Infocode which opens a keyboard where the cashier must type in the reason for the discount manually.

![OtherReasonInfocode](/images/202411/OtherReasonInfocode.jpg)

## Infocodes entries

### Infocode entries

Transaction Infocode entries

* Can be viewed from the Infocode card itself under factbox and also from Infocode usage under Infocode fast tab
* Can be viewed by running an Infocode report

![OtherReasonInfocode](/images/202411/OtherReasonInfocode.jpg)

## Infocodes with trigger functions

### Infocodes with trigger functions

- [ ] **Item** - Create an 
- [ ] **Discount group** - Add an Infocode discount group to the Item line.
- [ ] **VAT business posting group** - Change VAT business posting group on the line.
- [ ] **Run Business Central objects** - Report, Page, etc. 
- [ ] **Tax Area Code** - Select the tax area code.

### Trigger function example - Item

**Necklace**: When we sell a necklace 100160-Necklace to a customer, the customer should be able to choose the length of the chain.
The **Unit of measurement** of the chain is 1 centimeter and the price is 10.00.

![RetailItemChainSilver](/images/202411/RetailItemChainSilver.png)

**The Infocode, CHAIN-Silver Chain, has three selections for the same item**:

* The three Subcodes have the Trigger Function listed as Item
* Each line has its own chain length under the Qty. per Unit of Measure column (with different Qty. per Unit of Measure)

![InfocodeChainSilver](/images/202411/InfocodeChainSilver.png)

We link the Infocode to the Retail item, 100170-Necklace (Actions > Related > POS > Infocodes)

![NecklaceCard](/images/202411/NecklaceCard.jpg)

![InfocodeLinkToNecklace](/images/202411/InfocodeLinkToNecklace.jpg)

Now, we can sell the necklace on the POS

When we sell the necklace, the Infocode will pop up on the POS. After we have selected the chain length, the chain item is added to the POS Journal. 

![POSNecklaceDetail](/images/202411/POSNecklaceDetail.jpg)

## Cross-selling

With the help of cross-selling, the retailer provides an option to customers to get all those related items/accessories at the POS.

### Cross-selling

* Cross-selling uses Infocodes

* Cross-selling groups may also be created to group together relevant Cross-selling Infocodes

* Cross-selling selections are displayed via a pop-up on the POS

![CrossSellingCard](/images/202411/CrossSellingCard.png)

**Infocode linked with the item**: Retail Item Card > Actions > Retail/POS > Cross-selling

![CrossSellingInfocodes](/images/202411/CrossSellingInfocodes.jpg)

**Depending on the settings**, one or multiple items can be selected from the Pop-Up triggered upon selecting the relevant item.

![CrossSellingOnPOS](/images/202411/CrossSellingOnPOS.jpg)

## Retail users

### Retail users

The **Retail Users** table contains control information for back-office users. This record is also used to define a default main menu such as LS POS, which is run automatically when the **LS POS** is started. The **InStore menu** and most of the **Inventory Management** functionality uses the Store No. field in the Retail User record to restrict the user activities and to control automatic data entry. 

**Note**: `POS Super User` allows the user to change the setup

Before the POS Client is loaded, the user must be set up in Retail Users.

![RetailUsersList](/images/202411/RetailUsersList.jpg)

### User setup

The Retail User connects to the Business Central user as shown below (linked with the BC Users):

![BCUsersAndLSUsers](/images/202411/BCUsersAndLSUsers.png)

## POS Login Methods

### POS login

When you open a POS, the first menu you see will be to
* log in to the POS
* log off from the POS

Logon is used to log into the POS

* enter the staff ID and password

Methods to log in (three login methods):
* use the keyboard to enter staff ID and password
* use the touchscreen to enter staff ID and password
* scan in the staff barcode
* swipe an MSR card

![Logon](/images/202411/Logon.jpg)

### Client requirements

The client wants a staff member to be able to **log in to the POS** by using an **MSR card** or by using their **staff ID** and **password**. The password is defined on the Personal tab on the Staff Card and by using the keyboard icon on the Numpad, the virtual keyboard will open for input.

The POS for this client has a touch screen but not a physical keyboard.

Login - Staff ID and password:

![LoginPassword](/images/202411/LoginPassword.png)

### POS functionality profile card & Barcode mask setup card

**POS Functionality Profile Card**

* Allows MSR card and staff barcode login 
* On the Functionality Profile, we check the fields 'Allow MSR Cards' under the General tab and 'Staff Barcode Logon' under the 'Staff & Logon' tab

![AllowMSRCardCheck](/images/202411/AllowMSRCardCheck.jpg)

**Barcode Mask Setup Card**

In the Barcode Mask Setup Card, we need to create a Barcode Mask of the Type: Employee. 

![BarcodeMaskEmployee](/images/202411/BarcodeMaskEmployee.png)

### MSR card login

Then, we need to create a **MSR Card** for the staff.

![CreateMSRCard](/images/202411/CreateMSRCard.jpg)

## POS Training Mode

### Training mode

When **users are learning** how  to use  the POS terminal, it can be useful to have the **POS in training mode**

**To turn training mode on / off**:
• In the POS, select **Supervisor menu**
• Select **Training** to turn on and off the training mode

**Training mode**:
• Training can be displayed in the Status bar
• Training is printed in the journal part
• Receipts are marked as ** **TRAINING** **
• Transactions in Transactions Register are marked as Training

![POSInTrainingMode](/images/202411/POSInTrainingMode.jpg)

# CF-300 LS Central for retail Part V

## Profiles general and assignment

### Profiles

LS Central has five types of profiles: **Interface, Menu, Functionality, Style, and Hardware**. Profiles are linked to Stores, POS Terminals, and/or Staff. In the fact box pane of the store list, you can see what profile is linked to each store.

![StoreList](/images/202411/StoreList.jpg)

**Note**: It is possible to have many profiles of each type.
Each profile has a ##DEFAULT profile - used for shared data.

## Functionality profile

You will use the **POS Functionality Profile Card** to set up various functionalities of the POS terminals in the Store. In the card, you select default settings for VAT, Infocode with store actions, rounding of numbers, whether returns require price confirmation, and so on.
When you have set up a POS Functionality Profile, you must assign it to the relevant store(s) to be able to run the POS terminals in the store.

### POS Functionality Profile Card sections

Here are the different settings for POS functionality.

**General**

Features can be enabled or disabled in this section. Several features are available, including Allow MSR, Number pad in Tender, mapping of cash customer, and Z report auto print.

![POSFunctionalityProfile](/images/202411/POSFunctionalityProfile.png)

**Amount**

In this section, you can define if VAT needs to be printed on the receipt, the Currency Symbol to be used, the Placement of currency on the receipt, amount roundings, etc.

![POSFunctionalityAmount](/images/202411/POSFunctionalityAmount.jpg)

**Transaction Server and Web Services**

Transaction Server and Web Services allow the POS to access a remote HO database in order to retrieve or update information. This gives the POS the resilience of the standalone mode as well as the data availability of the online mode. Here you can decide which options to activate.

![FuncProfileTransactionServerAndWebService](/images/202411/FuncProfileTransactionServerAndWebService.jpg)

**Transaction Server and Web Services Settings, Data Director**

Here we define web services to run in the background, check missing transactions while posting statements, etc.

![FuncProfileTransactionServerAndWebServiceDataDirector](/images/202411/FuncProfileTransactionServerAndWebServiceDataDirector.jpg)

**Windows Printing, Staff & Logon**

Windows printing can be used as an alternative to OPOS printing. In such cases, report IDs need to be defined here. 

In the Staff & Logon tab, the Logoff Function can be set, Staff Barcode Logon can be enabled, log in and log out time can be registered, and so on.

![FuncProfileWindowsPrinting](/images/202411/FuncProfileWindowsPrinting.jpg)

**Prepayment and LS Omni Server**

In the Prepayment tab, you can disable the prepayment functionality for customers and items.

In LS Omni Server tab, define the Service URI for making use of customer order functionality. 

![FuncProfilePrepaymentAndLSOmniServer](/images/202411/FuncProfilePrepaymentAndLSOmniServer.jpg)

## Hardware profile

The **POS Hardware Profile Card** contains basic information for the setup of hardware for the POS terminals. It is used to set preferences and properties for the POS terminal and peripherals of the POS terminal, such as the display and the printer.

You can have several POS hardware profiles for your business. You can select which profile to run on specific POS terminals in the hardware profile in the POS terminal table.

### Hardware profile sections

**General, LS Hardware Station, and Error/Alert tone**

In the General tab, you define the unique Profile ID and Description.

In the LS Hardware Station tab, you define the hardware station configurations.

In the Error/Alert tone tab, you can configure an error tone or alert sound. For example, when you are scanning a barcode that does not exist.

![POSHardwareProfileCard](/images/202411/POSHardwareProfileCard.jpg)

**EFT and POS Printers**

An EFT device is connected to the LS Central POS through the LS Hardware Station, hence an EFT device needs to be configured here. 

A POS Printers device can either be an OPOS device or a Windows printer, which can be a normal printer or a label printer.

![EFTAndPOSPrinters](/images/202411/EFTAndPOSPrinters.jpg)

**POS Drawers & POS Displays**

POS Drawers devices are handled and created as an OPOS device. Cash drawers are very often connected through an OPOS printer in a retail setup, but they still need to be created as a separate device in the LS Hardware Station.

![POSDrawersAndPOSDisplays](/images/202411/POSDrawersAndPOSDisplays.jpg)

**POS Displays is an OPOS device that is the customer-facing display** that shows information about **each item that is scanned**, the price, and the total balance to pay. These displays generally have two lines where information can be displayed to the customer. A Dual Display can also be used as a customer facing display.

## Menu profile

### Menu profile list

Menu profiles contain some of the setup data that includes the menus used by the POS. Menu profiles have settings for which menus become active for the POS depending on the mode the POS is active in. 

Finally, the Menu profiles include settings where it is possible to set different menus for different staff permission groups.

The Menu profile works very closely with the data setup in the Interface profile. The button pad controls, defined in the Interface profile, are linked to menus in the Menu profiles. 

![POSMenuProfileList](/images/202411/POSMenuProfileList.jpg)

**Sales mode menu fields**

The following fields define the active menu for the #MAIN button pad control in the POS. When the POS is in this mode, the fields available are **Start Menu, Sales Menu, Payment Menu, Refund Payment Menu, Tender Op. Menu, Phys. Inv. Menu, and Quick Cash Menu.**

![SalesModeMenuFields](/images/202411/SalesModeMenuFields.jpg)

**Additional menus fields**

The system has three possible controls for the additional menus to the #POS panel:

#ADDMENU 1 – **Additional Menu 1**
#ADDMENU 2 – **Additional Menu 2**
#ADDMENU 3 – **Additional Menu 3**

Sample image of the menu for #FASHION2:

![Fashion2](/images/202411/Fashion2.png)

### Interface profile

The interface of the POS consists of panels and numerous controls that define and control the sections of the POS. Some of the Interface profile’s controls become active or appear when different POS commands are used.  Each POS section consists of a POS panel made up of interface controls. 

**Interface Profile**

* defines the layout of the POS
* works with the Menu Profile
* includes the Panel, Lookup list, and Controls
* connects the Data Table for the POS Journal

![POSInterfaceProfileCard](/images/202411/POSInterfaceProfileCard.jpg)

### Style profile

With the **POS Style Profile Card, the look of all buttons and fields for the POS is defined**. This includes the button look, the font, the color used for all the different controls, and the space between buttons. **The Style profile's main purpose is to make the setup easier and quicker**; that is, the button look is defined with the Style profile and not individually for each menu line. 

![POSStyleProfileCard](/images/202411/POSStyleProfileCard.png)

**Skin Lines**: Skin Lines which define the color, shape, curvature, gradient mode, and transparency of the POS buttons and other areas.
**Font Lines**: Font Lines which define the font name, size, and attributes for POS buttons and other areas.
**Color Lines**: Color Lines of different parts of the POS. This can, for example, be the background color for different parts, color area between buttons and the grid line color.

### Assigning POS profile

**All profiles can be assigned in**:

* Store Card
* Terminal Card

**Interface, Menu and Style profile can also be assigned in**:

* Staff Card
* Staff Store Link Lines

### Active POS profile

The POS finds its active profile by this rule

Store Link > Staff > Terminal > Store > ##DEFAULT

When no profile is found: ##DEFAULT profile is automatically the active profile

### POS: Active profile

**How do I see which profile is active in the POS?**

* Menu SYSINFO displays active profiles
* In Hyper POS
  - Use: Start
  - Button: System Information

![ShowActiveProfile](/images/202411/ShowActiveProfile.jpg)

## Menu profile - Menus

### Menu profile - Menus

The **POS Menu Profile Card** contains basic information for the setup of the visual appearance of the POS terminals. You use it to select menus that appear on the POS terminal screen, as well as to define colors and bars visible.

You can have several POS Menu Profiles in your business. You can select which profile to run on specific POS Terminals in the Menu Profile field in the POS Terminal table.

![POSMenuProfileCard](/images/202411/POSMenuProfileCard.jpg)

### POS function menu

From the POS Menu profile Card, you get a **list of all the menus that are linked to the Menu Profile Card**. 

Let's take a look at a POS Function Menu.

![HyperMarket](/images/202411/HyperMarket.jpg)

**Menu Attributes**

Menu Attributes is used to define the number of columns & rows for the menu. Here you can also define the Button Spacing, Menu Color, Skin, Font, etc.

![POSMenuMenuAttributes](/images/202411/POSMenuMenuAttributes.jpg)

**Lines**

* Each Menu Line equals one button
* Each Menu Line has a POS Command
* It is possible to open a menu in a Menu Line
* Optional fields, such as Disable, Hidden, Span, Skin, and Font

![POSMenuLines](/images/202411/POSMenuLines.jpg)

### Working with a menu

**Different ways to open Menu List**

From Menu Profile use Menu List => opens menus in the selected profile

![POSMenuProfileCardMenuList](/images/202411/POSMenuProfileCardMenuList.jpg)

From Point of Sale (Windows POS only) - Design open Menus => menus in all profiles.

![Interface_MenuProfiles](/images/202411/Interface_MenuProfiles.jpg)

In POS, when in the menu, right-click the mouse and select Menu Properties

![POSMenuProperties](/images/202411/POSMenuProperties.jpg)

## Menu profile - ##Default profile

### ##DEFAULT profile

**##DEFAULT profile has two main purposes**

Each Profile Type has a ##DEFAULT profile:
1. When no profile value is found, the ##DEFAULT Profile automatically becomes the active profile 
2 Reusing data: When the POS does not find data in the active profile, the POS automatically looks for it in the ##DEFAULT profile

![DefaultProfile](/images/202411/DefaultProfile.jpg)

## Reusing menus

**The POS uses menus that are located in**:

- Active Menu Profile
- The Store's Menu Profile
- ##DEFAULT Menu Profile

**Note**: Menus in Menu Profile ##DEFAULT are automatically shared for all Profiles

![DefaultMenuProfile](/images/202411/DefaultMenuProfile.jpg)

Menu #NUMPAD1 is an example of a menu that exists only in the Menu Profile ##DEFAULT but is used by all setups.

![Numpad1](/images/202411/Numpad1.jpg)

![Numpad1Detail](/images/202411/Numpad1Detail.png)

## Menu profile - Dynamic menus

POS Dynamic Menus appear on the POS, similar to POS Menus, and consist of items and deals. Instead of adding the exact items or deals into the menu, as you do with POS menus, you can add to a dynamic menu a selection of product groups, item categories, and special groups along with items or deals with certain attributes. You can select how the system sorts the items and deals included in the selection. 

Dynamic menus

* Appear on the POS like POS Menus
* Consist of items and deals
* No static content
* Filter a selection of product groups, item categories, and special groups along with items or deals with certain attributes
* Customized sorting

![DynamicMenus](/images/202411/DynamicMenus.jpg)

### Dynamic menus

The menu can be displayed in different ways. Display types:

* On Top of Menu
* Replace Menu 
* Pop-up 

![POSDynamicMenuCard](/images/202411/POSDynamicMenuCard.png)

* Display Type: Options: **On Top of Menu, Replace Menu, Pop-up**.
* Display Section: Options: **Main Menu, Additional Menu 1, Additional Menu 2, Additional Menu 3**.
* Button Display: It's possible to add text to the button, such as the price.
* Menu Exit: Options: **None, Exit First Button, Exit Last Button, Exit First and Last Button, Exit after Selection**.
* Base POS Menu: A Base POS Menu is used to configure common POS Menu controls such as button spacing, sliding and scrolling.
* Glyphs Tab
  * Selection Type: Items can be selected by Product Group, Item Category, Special Group, Attribute or Item No.
  * Filter Value: (based on the previous **Selection Type**, the Special Group, Attribute, etc.).
  * Validation Period ID: It is possible to add a Validation Period to each selection line.
  * Exclude: A selection line can also be used to exclude items or deals.

Items can be **sorted by** Product Group, Item Category, Division, Attribute, Description, or Search Description. Deals can be sorted by description or a sorting attribute. The sorting is done in the same order as the order of the sorting lines. The order of **sorting lines can be changed** by using the Up and Down actions.

![POSDynamicMenuSorting](/images/202411/POSDynamicMenuSorting.png)

### Dynamic menus preview

**Preview in POS Dynamic Menu Card**

You can Preview and Test the Dynamic Menu for each store since Dynamic Menus only include items and deals that have distribution in the active store.

![POSDynamicMenuPreview](/images/202411/POSDynamicMenuPreview.jpg)

(On the preview it shows the list of items)

## Menu profile - Tags

### Tags

Tags are fixed information that is entered into the Menu line.

The system has many different tags that can be used in the system and they are of different types depending on the nature of the information.

The Menu lines include the Tags ID. When the POS is running, the Tag ID is replaced with its information. The information can be from the current POS transaction or from another table that can be referenced from the current transaction.

|Type|Description|
|---|---|
|System|For system information, for example, a date.|
|Transaction|For information from the current transaction, for example, the receipt number. Can also be sent to the KDS System.|
|Session|For information in the session, for example, the active profile name.|
|Multiple Use|Used to get information from transactions outside the sales POS.|

## Interface profile

### Interface profile

The interface of the POS consists of **panels** and **numerous controls** that define and control the sections of the POS. Some of the Interface profile’s controls become active or appear when different POS commands are used. Each POS section consists of a POS panel made up of interface controls.

**Below are the various options that can be assigned to an Interface Profile**:

* Panel
* Button Pad Control
* Data Grid Control
* Input Control
* Record Zoom Control
* Lookup

![InterfaceProfileOptions](/images/202411/InterfaceProfileOptions.png)

**Note**: Interface Profile parts are shared data, as the menus are for the Menu Profile.
Interface Profile ##DEFAULT should include all the base data.
The Journal Data Table ID is set up in the Interface Profile Setup.

## Interface Profile - Panel

### Panel

**The POS is based on many panels**. Every window which appears in the POS is a panel. A panel is a fixed area in the POS. A Panel is like a puzzle in that it consists of **many parts which cannot overlap each other**. The panel’s parts are rectangles which can be of different sizes, lengths, and widths.  Each panel covers at least one column and one row. It is possible to configure each part so that it covers more space by using the span feature for the columns and rows. 

The POS main window is one panel. All  POS windows are set up as panels and a panel can include another panel. **Panel parts can not overlap each other**.

**A panel can have one or many controls**

Control Types are:

* Button Pad Control
* Data Grid Control
* Media Control
* Input Control
* Record Zoom Control
* Browser Control

![POSPanelDetail](/images/202411/POSPanelDetail.jpg)

![POSPanelDetail1](/images/202411/POSPanelDetail1.jpg)

### To create a panel

1. Define the number of Columns and Rows
2. Define the panel‘s size:
0 = window‘s full size
3. Create the Row/Column List
* Each Column and Row has its own size
4. Create the POS Panel Control Lines
* One Panel part is one Control Line
* For each part assign the Control Type and its parameters
* One part can span more than one row and/or column

![ColumnRowsPanels](/images/202411/ColumnRowsPanels.jpg)

### Fixed panel names

Interface Profile ##DEFAULT has some Fixed Panel Names

* #POS is the Main POS panel
- Has to exist in each Interface Profile

* #OFFLINE is the Startup / Logoff panel

* #LOGIN is the Login panel
- Menu LOGON is part of the panel and has the logon possibilities

![DefaultPanels](/images/202411/DefaultPanels.jpg)

## Interface profile - Data grid control

### Data grid control

**Data grid controls are used to display different information on the POS. The #JOURNALGRID is one of these data grid controls.**

Another example is the #LOOKUPGRID. This grid is used to display items when the POS Command LOOKUP is used. The data grid controls have their own setup. Data grid controls are defined on the Panels. 

Data grid controls are used for the journal and for different lookups, such as Item lookup, Item finder, and Variant lookup.

Skin, font, and color values are set up for the data. Each data grid control has its own look. It is also possible to define sliding and scrolling for each data grid control. For journal data grids, check the Journal Mode field.

![DataGridControl](/images/202411/DataGridControl.png)

## Interface profile - Button pad control

### Button pad controls

**Button Pad Controls are placeholders for menus**. By using Button Pad Controls, you can place multiple menus on any panel in the POS. The menus can either be fixed for each Button Pad Control or dynamically assigned on the panels.

Numerous Button Pad Controls are in Interface Profile ##DEFAULT, but when you have a special one you should put it into your Interface Profile.

In the Button Pad Control, you **link the menu that this Button Pad Control uses**, that is, the menu that is displayed in the POS for the area that this Button Pad Control is defined for.

Most Button Pad Controls contain a specific menu. Button Pad Controls with no specified menu are dynamic.

**Dynamic Button Pad Controls**:
The panel defines which menu is loaded into the dynamic control when the panel is displayed.
Two or more panels can use the same dynamic button pad control but with different menus.

![ButtonPadControlCard](/images/202411/ButtonPadControlCard.jpg)

## Interface profile - Input control

### Input controls

Input controls are used for areas in the POS where the user has to enter data. These are used in several panels in the system. 

The #CURRINPUT control on the ##POS pane is an example of input control. This is the main input panel where the user inserts data, for example, entering an item number for sale.

Input is fixed data. This means that the control ID has to exist for the POS function that uses it. The system automatically looks for the #CURRINPUT field on all panels and uses it for filtering, etc.

![InputControlCard](/images/202411/InputControlCard.png)

## Interface profile - Record zoom control

### Record zoom control

The Record zoom controls are fixed data. The Record zoom control is used to zoom and view table records. You should define 'Data Table ID' on the Record Zoom Control Card. 

It has some formatting possibilities. 

![RecordZoomControlCard](/images/202411/RecordZoomControlCard.png)

## Interface profile - Lookup

### Lookup

POS Command **LOOKUP** lets the POS user browse a list of data where they can use the filter options to quickly find the information they are looking for. **POS Lookups run in their own panel and are fixed data**.

By default, this POS Command can be used without any parameter and will open the list of items. Additionally, other information can be displayed with the LOOKUP command by using a parameter with the command.

The side menu to the left on the display shows help topics for functionalities in the Lookup section of the LS Central user interface.

The Panel Control ID is assigned on the POS Lookup Card

![POSLookupCard](/images/202411/POSLookupCard.jpg)

## Style profile

### Style profile

With the POS Style profile, the look of all buttons and fields for the POS is defined. This includes the button look, the font, the color used for all the different controls, and the space between buttons. The Style profile's main purpose is to make the setup easier and quicker; that is, the button look is defined with the Style profile and not individually for each menu line. 

Style profile is used to define the look and color of the different POS parts , such as:

* Buttons
* Input fields
* Journal
* Background color

Styles act as base data. Change the base, and the look of the POS changes. It is so easy to change the colors and text for the POS with the use of a Style and it is normal to have a few Style profiles in every company

**With the Style profile**

* Implementations are quicker
* Maintenance is easy

### Different style profiles for Hyper

The following examples show how the Style profile changes the POS look. They have the same setup apart from the Style. 

#### Style #Hyper

![StyleHyper](/images/202411/StyleHyper.jpg)

#### Style: # LS_Retail

![StyleLSRetail](/images/202411/StyleLSRetail.png)

### POS Style Profile Card

Each Style profile should have a ##DEFAULT code for Skin, Font, and Color Lines. The ##DEFAULT profile has a set of Skin, Font, and Color Lines. All of these lines start with the # sign.

**The demo data company is set up with this Style data**.

The system has its own fixed lines for the Journal lines. These lines start with #SL.

![POSStyleProfileCardDEFAULT](/images/202411/POSStyleProfileCardDEFAULT.png)

* Skin Lines: Define the look of the buttons. Shape, Color, Gradient Mode and more.
* Font Lines: Define the buttons font. Font Name, Color, Size and attributes.
* Color Lines: Define the background color. Only the Color value is set. Can be used for different types of 'background' for example Gridline's color.

## Style profile - Skin, font and color lines

### Skin, font and color are connected to:

**The POS buttons’ color is defined in the skin**, not in the color setup. Color setup is for other parts of the POS and used in the Controls and for the color between buttons in the menus.

By having many skins, fonts, and color lines in one Style profile, it is possible to display the POS buttons with a different look. When you want to change a look, you only have to change the base definition. All parts which use the definition will change accordingly.

Active POS profile style profiles can be assigned to staff/terminal/store, just like other profiles. The settings in the assigned Style profile overwrites the ##DEFAULT settings (explained later) if they exist, otherwise, the ##DEFAULT settings are used.

### Rules: Skin, font and color in the POS

The skin, font, and color values are used from the active Style

An empty field  =>  ##DEFAULT value is used in the active Style

Value not found in the active Style.
- Use the Store‘s style and then the ##Default Style.

A Menu Line value overrules POS Command value and Menu Attribute Value.

POS Command value overrules Menu Attribute Value.
- Note: Menu Properties in the POS do not display the POS command skin and font value.

![POSMenuColorSkinFont](/images/202411/POSMenuColorSkinFont.png)

## Additional Options

### Actions > Where Used

Where Used is a display of all options, where the selected value is used and allows the user to open each option and edit it.

![ActionsWhereUsed](/images/202411/ActionsWhereUsed.jpg)

**Available for**:

* Profiles
* Fonts
* Skins
* Color Setup
* Button Pad Control
* Input Control
* POS Commands
* Data Grid Control
* Record Zoom Control

### Up and down buttons for lines

Use the up and down button to move lines. The line number changes automatically.

![UpAndDown](/images/202411/UpAndDown.png)

**Available For**:

* Menu Lines
* Panel Control Lines
* POS Data Table Columns

## Copy profiles

**With Copy profile, it is possible to copy profiles within the company. The following are the instructions to copy profiles**. 

* Create new profile
* Use the action: Copy to Current Profile / Copy Profile
* Copies data from a profile to the selected profile
* Available copy options depend on the profile type  

*Note: Use the field 'Override if Exists' carefully if field values already exist*.

![CopyFromCurrProfileAction](/images/202411/CopyFromCurrProfileAction.jpg)

## LS Import Export WS

### Import/Export worksheet

It is possible to export selected data from a company and then import it into another company within the same database or another database.

The tool to do this is the Import Export Worksheet or LS Import Export WS.

This tool exports the selected data into an XML file and imports the data from the XML file. The user has to make sure to be active in the company the data is being exported from and imported to.

**The POS setup data for retail recommended to be imported from the Demo Data is**:

* Interface Profile ##DEFAULT
* Menu Profile ##DEFAULT
* Functionality Profile ##DEFAULT
* Hardware Profile ##DEFAULT
* Style Profile ##DEFAULT
* POS Commands
* POS Tag, all tags
* POS Data Table, all tables
* Scheduler Job Header, all jobs
* WS Request, all data
* POS Context Menu, all data

**Optional import data**:

* Other profiles which exist in the Demo Data Company
* POS Search IndexTable
* Hospitality and KDS (Kitchen Display System) data, if needed

![LSImportExportWS](/images/202411/LSImportExportWS.png)

# CF-300 LS Central for retail Part VI

## Tender management - General

### Start of Day Process

* The cashier inserts money in the drawer to be able to give change to the first few customers. This procedure is called **Start Float Entry**.
* The cashier registers the sales on POS and puts the payment tender types into the drawer.
* If necessary, for example, when there is too much of some tender type in the drawer, the cashier can perform a **Pick Up** in order to remove the tender from the drawer. In LS Central this function is called **Remove Tender**.
* If there is a need for placing additional tender into the drawer, the cashier can do that by another Float Entry.

### End of Day Process

1. Declare Tender for each POS/Staff (if done on POS)
2. Create Statement
3. Calculate the Statement
4. Post/Accept Statement

### Management of Tenders

**Three Methods**

1. Count at Statement: No counting at the POS, possible to do a statement count
2. Tender Operations: Count at the POS
3. Cash and Safe Management: Traceability of cash movements within the store

### Demo company

In the demo company, the three methods mentioned can be checked in the listed stores below.

Management of Tenders Methods:

1. Count at Statement	=>	Store S0001
2. Tender Operations	=> Store S0003
3. Cash and Safe management	=> Store S0002

## Count at statement method

### Count at statement

* The simplest cash management method 
* No specific closing process is required at the POS in end of the day
* Counted amount is entered manually into the statement 

### Setup for Count of Statement

**Store setup**

A few settings need to be set to get the Count of the statement.

Set **Safe Mgmt. In Use** as False
Fields **POS Start Amount Method** and **POS Post Safe Ledger** are irrelevant in this setup

![StoreCardSetupCountAtStatement](/images/202411/StoreCardSetupCountAtStatement.png)

### Tender Types 

You need to check the field, **Counting Required**, for each tender type that needs to be counted at the POS

**Note**: Cash, Check and Currency are typical tender types for counting

![CountingRequiredDetail](/images/202411/CountingRequiredDetail.jpg)

### X and Z reports

No closing action is needed on the POS when printing X or Z reports.

* Z Report: prints POS Sales and zeros the totals.
- Command Print_Z

* X Report: prints POS Sales since last X Report.
- Command Print_X

![XZReports](/images/202411/XZReports.jpg)

#### X reports

X reports are accessible on both the Tender Operations and the Supervisor menus, but only for managers.

The **X report prints statistical information for the POS terminal**. It prints the POS totals and other information since the last X report was printed. It can be printed at any time and does not zero totals as the Z report does.

![XReport](/images/202411/XReport.jpg)

#### Z reports

Z reports are accessible on both the Tender Operations and the Supervisor menus, but only for managers. 

The **Z report prints statistical information for the POS terminal**.  It prints the POS totals and other information since the last Z report was printed. It automatically zeros the totals of the POS terminals, and can be a part of the end-of-day procedure for each POS.

To print the Z report, go to either the Tender Operations or the Supervisor menu and select Z-Report.

![ZReport](/images/202411/ZReport.jpg)

## Statement posting with count at statement method

The **Statement** table contains all unposted statements in your business. You use a statement for each store to calculate the amounts in all Transaction Headers that have been created on the POS terminals since the last store statement was calculated. You then post those amounts into the relevant applications: the general ledger, the inventory, or the purchase and payables.

**Creating, calculating, and posting the statement is an essential part of the end-of-day procedure**.

### General about Statements

**Statements**

* Statements are calculated at the Store’s back office or in the central database (HO)
* Statements are posted in the HO
* Statements are tools that collect the store‘s sales data and post it into the company‘s ledger

![Statements](/images/202411/Statements.jpg)

### Store settings for Statement

**Each Store has its own setup for Statement / Closing**

![StoreCardStatement](/images/202411/StoreCardStatement.png)

* Statement Method: **Total**: Creates a line for each tender type in the transactions; **Staff**: Creates a line for each staff member and tender type; **POS Terminal**: Creates a line for each POS Terminal and tender type.
* Tender Decl. Calculation: **Last**: Only the last tender declaration will update the counted amount field in the Statement; **Sum**: The sum of all tender declarations will be shown in the counted amount field in the Statement
* **Closing Method**: **Date and Time**: Statements are calculated and posted at a selected date and time. You can create as many statements as you like; **Shift**: One statement is calculated and posted for each Work Shift set up for the store

![TotalStaffPOSTerminal](/images/202411/TotalStaffPOSTerminal.jpg)

### Creating and posting a statement

![OpenStatementList](/images/202411/OpenStatementList.png)

* **Pending Statement**: When the POS has been logged out a statement will be waiting.

### Options in Statement

#### **Calculate Statement**

Calculated statements can be re-calculated after new sales transactions were created, then the missed transactions are included in the second run.

**A statement can be cleared and calculated multiple times before it is posted.**

#### **Post Sales Entries**

Post Sales Entries register the sales entries separately throughout the day in order to update the inventory.
Statements are then repeatedly calculated and sales entries posted. This is not recommended where there are many transactions.

![CalculateStatement](/images/202411/CalculateStatement.jpg)

### More store options for Statement

![MoreOptionsStatement](/images/202411/MoreOptionsStatement.png)

* **Max Diff. to Allow Posting**: The difference in LCY that can be between the Trans. Amount in LCY  and Counted Amount in LCY in the statement to allow posting.
* **Max. Round. In Stmt.**: This field contains the maximum rounding difference amount allowed when posting the Statement. Rounding difference is a summed-up difference in the statement transactions between the total sales amount and the total payment amount.
* **Rounding Account**: The G/l Account in which the rounding difference is posted.
* **Allowed Diff. in Trans**: The allowed difference between sales and payment per transaction
* **Only accept Statements**: It is a True or False field and depends on several factors:
  - Store has its own database and Posting is on HO
  - Store is online and connected to HO but wants HO user to post it
  - Accounting rules and requirements
  - Most common to post Statements on HO
  - Accepted Statement can at any point later be posted at Head Office level.
* **Posting Groups**: Store needs to have a **VAT Bus. Post. Gr.** and **Gen. Bus. Post. Gr.** assigned, since the POS does not use sales orders but POS transactions. If the sale is customer sale, the posting setup is driven from the Customer master.

## Tender operations method

### Tender operations

In Tender operations, the Float Entry commands starts a float entry transaction. it can only be started as a new transaction. It is not possible to create item lines during this transaction. Only tender types that have the **Counting Required** field in the **Tender Type** table checked can be entered. This makes it possible to keep control of cash other tenders for the drawer. This makes it is easy to use and allows blind counting at the end of the day/shift.

Tender operations include the following processes:

* Float Entry
* Remove Tender
* Declare Tender

With Tender operations method:
* No check on Fixed float
* No counting by denomination
* No warnings on the POS if there is a difference
* Store safe not supported
* Bank bags and transfers not supported

## Tender Operations: Setup Required

**Store Setup**

* Set Safe Mgmt. In Use as False
* Pos Start Amount Method and POS Post-Safe Ledger fields are irrelevant in this setup

**Note**: Cash, Check, and Currency are typical tender types for counting.

![TenderOperationsSetup](/images/202411/TenderOperationsSetup.png)

**Tender Types**

Check field **Counting Required** for tender types the store is counting

![CountingRequiredEnabled](/images/202411/CountingRequiredEnabled.jpg)

### Tender Operations: Setup on the POS

**Tender Operations** buttons calls **TENDEROP** menu as shown below.

![TenderOperationsButton](/images/202411/TenderOperationsButton.png)

### Tender Operations: Setup on POS Menu Profile

Buttons with commands such as Float Entry, Remove Tender, and Declare Tender have a menu behind them which is the **Tender** Menu. It is mapped in the POS Menu Profile as shown below:

![TenderOperationsCommands](/images/202411/TenderOperationsCommands.jpg)

![TenderOperationMenuTender](/images/202411/TenderOperationMenuTender.png)

## Statement posting with tender operations method

### The cash process on the POS

![CashProcess](/images/202411/CashProcess.png)

1. **Starting the day/shift**: Float Entry used to register the starting float amount for the POS  - when money is inserted into the drawer
2. **During the day/shift**: Remove Tender when cash is taken out of drawer. Additional Float Entry when cash is added into the drawer.
3. **End of day/shift**: Declare Tender to register tender taken out of the drawer at the end of the day.

Float Entry, Remove Float, and Declare Tender work for tender types which have **Counting required** as True and **Float Allowed** as True.
*Tender types typical for this are Cash, Check, and Currency.*

![TenderTypesCountingRequired](/images/202411/TenderTypesCountingRequired.jpg)

### Cash Process - Starting the Day

Start by inserting float into the drawer by opening Menu **Tender Operations** and pressing **Float Entry**. Select the button **Cash** and enter the cash amount. **Repeat** for **tender types which are inserted** into the drawer. Press **POST** and the **FLOAT ENTRY ticket is printed**.

![TenderOperationsFloatEntry](/images/202411/TenderOperationsFloatEntry.png)

### Cash Process - During the Day

You can use **Float Entry** each time an additional float is inserted into the drawer and **as many times as needed** throughout the day.

Press the Cash button to enter the cash amount and repeat for tender types which are inserted into the drawer, then press the POST button.

Similarly, **Remove Tender** can also be performed multiple times. The **REMOVE TENDER** ticket is printed in two copies; one ticket for the cashier and then another ticket to be attached with what is removed.

![RemoveTender](/images/202411/RemoveTender.jpg)

### Cash Process - End of Day for each POS / Staff

The user needs to declare tender for their drawer. This includes counting and registering, to the POS, what exists in the drawer. This is only for tender types that are marked as counting required. 

Optional to print Z Report. Use the operation **DECLARE TENDER** to register the amount for each tender needed. Press the POST button and two identical Tender Decl. receipts are printed

![DeclareTender](/images/202411/DeclareTender.png)

### Statement with Tender Option


#### For each POS/Staff in the Store

* At the beginning of the day, use **Start Float** for cash
* Over the day, sell with different tender types 
* Remove Float / Insert Float when needed.
* Print Z Report.
* Declare Tender.

#### In the Store back office,  create the Statement for the Store

* The counted amount is automatically filled out for the tender type counted in Tender Declaration
* The difference is shown in the Difference Amount field

![StatementWithTenderOperation](/images/202411/StatementWithTenderOperation.jpg)

#### Bank 

On Bank, the fast tab cash can be posted to the bank. Create a line on the Bank fast tab manually, select Tender Type and enter the Amount. Select Bal. Account Type and Bal. Account No.

## Cash and safe management method

### Cash and safe management

The Cash & Safe Management function gives you an extended overview and traceability of the tender types that you put into the bank from your store’s safe. Typically, money is counted at the end of the day and stored overnight in a selected place, usually a safe, before being transferred to a secure location. This is facilitated using this function.

|**Into Safe**|**From Safe**|
|---|---|
|Counted from POS|Start of day – drawer|
|Uncounted from POS|To bank|
|From Bank|Transfer to POS|
|Pickup from POS||

### Setups - Store Card

Highlighted below are the setups that are required on the Store Card

**Statement Method**: Statement Method option Total is not supported
**Tend. Decl. Calculation**: This field does not apply to this method.
**Max. Diff. To Allow Post**: This field becomes inactive
**Safe Mgmt. in Use**: This field needs to be **check marked**.
**POS Start Amount Method**: We will use Fixed bag in this demo (other options are *Flexible, Fixed Bag and Flexible Bag*).
**POS Post Safe Ledger**:• Standalone POS = False • Online POS = True

![StoreCardCashManagement](/images/202411/StoreCardCashManagement.png)

|POS Start Amount Method|Clarification|
|---|---|
|Flexible|The Start Float is not automatically requested at the beginning of a day/shift|
|Fixed Bag|Each POS opens automatically with Insert Float at the beginning of a day/shift|
|Flexible Bag|Each POS opens automatically with Insert Float at the beginning of a day/shift|

### Setups - Safe

**Create a Safe for the Store**

• Store can have one or more safes.

**For each safe configure**

• Safe No.
• Description
• Transfer No. Series
• Join Bag No. Series

**Safes are defines for the terminal**

• One safe can be assigned to many terminals.
• POS Terminal can only transfer to/from one Safe.
• The safe is linked to the POS terminal.

### Setups - Fixed Start Amounts

When POS Start Amount Method is Fixed bag

* Create Start Float for each POS/Staff.
* Define the Fixed Start Amounts.
* The use of Denominations is optional.

![POSFixedStartAmounts](/images/202411/POSFixedStartAmounts.jpg)

* **POS Fixed Start Amount**: You will find the POS Fixed Start Amount from the Store Card, under Related, Store, Cash & Safe Management.
* **Denominations**: When a line is selected you go to Denominations to set what amount of coins and notes are set for POS Fixed Start Amount.
* **Terminal**: This is the terminal to which the fixed start amount applies.
* **Tender type and Currency**: Here you select type of Tender and Currency.
* **Amount**: Here you set the amount.

### Setups - Tender types

For those Tender types using the Safe

 General
- May be Used as True

Posting
- Count By Denominations

![SetupsTenderTypes](/images/202411/SetupsTenderTypes.jpg)

![TenderTypeCard](/images/202411/TenderTypeCard.png)

* **Counting Required**: set as True.
* **Float Allowed**: set as True.
* **Taken to Bank**: set as True.
* **Taken to Safe**: set as True.

### Setups - POS Functionality Profile

In the Functionality profile of the Store (or POS if any), it is recoomended to have the field **Z-Rep Autopr. After T. Dec EOD** as **True**.
* This will print a Z-Report automatically each time a Tender Declaration is processed on the POS.
* Z Report can only be used with Declare Tender.


![ZRepAutoprintAfterTDecEOD](/images/202411/ZRepAutoprintAfterTDecEOD.jpg)

### Setups - POS 

**Commands for each button**

X Report - **PRINT_X**

* Sales Totals since last Z Report

Z Report  - **PRINT_Z**

• Sales Totals since last Y Report

Tender operations:
• Declare Tender - **TD_ENDAY**
• Float Entry – **FLOAT_ENT**
• Remove Tender – **REM_TENDER**

![POSCommands](/images/202411/POSCommands.jpg)

**When Float Entry, Remove Tender, and Declare Tender are used**:

* The user enters the amount per tender type requested.
* **Float Entry** inserts the tender amount.
* **Declare Tender** and **Remove Float** remove the tender from the drawer.
* The amount can be done by denomination.
* Amount (for fixed float), Bank amount, and/or Safe Amount can be selected by the user.

## Statement posting with cash and safe management method

### Permission Setup for End of Day

Staff Permission Group has some fields for End of the Day processes. The staff permission, per user, overwrites the Permission Groups setup.

In the Staff Permission Group Card, you can Enable or Disable **Show Trans. Amount** and **Show Difference in Warning**.

![StaffPermissions](/images/202411/StaffPermissions.png)

The Staff Permissions card shows the permission list for the selected staff.

![StaffPermissionsCard](/images/202411/StaffPermissionsCard.jpg)

![DetailShowTransAmount](/images/202411/DetailShowTransAmount.png)

![ShowDifferenceWarning](/images/202411/ShowDifferenceWarning.png)

## Store safe

### Store safe setup

Each store can have as many safes as needed. This section describes how to create and delete safes. You can create a new safe at any time.
We start by creating the Safe and adjusting the settings on the Cash and Float tender type.

![StoreCardStoreSafes](/images/202411/StoreCardStoreSafes.jpg)

![StoreSafeCard](/images/202411/StoreSafeCard.jpg)

![TenderTypeCardBagSafe](/images/202411/TenderTypeCardBagSafe.jpg)

![TenderTypeCardTakenToSafe](/images/202411/TenderTypeCardTakenToSafe.jpg)

### Transferring cash from Bank/GL to safe

We are transferring to the safe, MAIN SAFE, in Store S0002
* Transfer Direction = To Safe
* Bal. Account Type = Bank Account or G/L Account
* Tender Type = 1 (Cash)
* Enter the amount
  
![TransferToSafe](/images/202411/TransferToSafe.jpg)

## Safe transfers

### Transferring cash from Bank/GL to safe

Start by creating the Safe and adjusting settings on Cash and float tender type.

* We are transferring to the safe, MAIN SAFE, in Store S0002
* Transfer Direction = To Safe
* Bal. Account Type = Bank Account or G/L Account
* Bag No = 2 (in this case it can be any number)
* Tender Type = 1 (Cash)
* Amount (with or without denomination)

![TransferToSafeCard](/images/202411/TransferToSafeCard.jpg)

* **Post & Print**: Post can be used to register the safe transfer. Post & print will register as well as print a document.
* **Safe No.**: Displays the list of safes in the system.
* **Transfer Direction**: This option is used to understand if the cash is being deposited or withdrawn from the safe (options are *From Safe* and *To Safe*).
* **Bal. Account Type**: Specifies if the account type is *G/L Account* or *Bank Account*.
* **Bal. Account No**: Specifies the bank account no.
* **Department Code**: For the Global dimension 1.
* **Project Code**: For the Global dimension 2.

**Bag Tender Declaration**

Here you need to define the denominations of the cash tender:

![BagTenderDeclaration](/images/202411/BagTenderDeclaration.jpg)

### On the POS - Adding start float

* Start the day/shift by adding a float. If there is no difference, the bag will be removed from the Safe.
* Note! Start float will not be requested when the user logs on the POS.

![AddingStartFloat](/images/202411/AddingStartFloat.jpg)

### Adding float – Breaking the Bag

* To be able to add a float to the POS during the day, we need to transfer cash from Bank or G/L to the Safe and then select Break Bag.
* The bag will be marked as not active.

![AddingFloatBreakingTheBag](/images/202411/AddingFloatBreakingTheBag.jpg)

### With denomination

If Bank and Safe are marked by denomination, the system will automatically open the denomination input screen on the POS when doing a transfer to Safe from POS, when adding/removing float, or when doing a tender declaration.

![ToSafeByDenomination](/images/202411/ToSafeByDenomination.jpg)

![InsertFloatMenu](/images/202411/InsertFloatMenu.jpg)

### Bags with number series

If the bag no. is not selected when doing a tender declaration, then the system will allocate it  automatically on the POS

![BagsWithNoSeries](/images/202411/BagsWithNoSeries.jpg)

![SafeBagsTypeandNos](/images/202411/SafeBagsTypeandNos.jpg)

### Exclude Coins to Bank

If this option is enabled, then Coins are not shown in the denomination list for the bank bag.

![ExcludeCoinstoBank](/images/202411/ExcludeCoinstoBank.jpg)

### Start amount method: Flexible bag

**Difference between Fixed Bag and Flexible Bag**

When the tender declaration is posted as **uncounted**:
* **Fixed bag**– the fixed start amount will be posted to the fixed float bag and the rest will be posted to the safe bag.
* **Flexible bag**– only posted to the safe bag

![POSStartAmountMethod](/images/202411/POSStartAmountMethod.jpg)

![DeclarationDetailFixedFloat](/images/202411/DeclarationDetailFixedFloat.jpg)

### On the POS

When the user logs on to the POS at the start of a day or shift, the POS will open the insert float window and automatically show the fixed start float for the staff. In this case, the user adds the float to the drawer and removes the bag from the safe, if it exists.

At the end of the day/shift, the cashier does the tender declaration and adds the amount he/she started with to fixed float and the system creates a fixed float bag with either the staff or POS terminal ID.

![SafeLedgerEntryDetails](/images/202411/SafeLedgerEntryDetails.jpg)

### Online/Standalone setup - Store Card

**All POS’s are online in the Store**
* POS Post-Safe Ledger is **True**.

**Mixed online or Standalone POS’s**
* POS Post-Safe Ledger is **False** and the Codeunit, 99001593 Safe Transaction-Post, is run in the scheduler at the back office.
 
**Standalone Store**
* POS Post-Safe Ledger is posted at the store level and replicated to HO.
* 
![POSPostSafeLedgerBoolean](/images/202411/POSPostSafeLedgerBoolean.jpg)

## Navigate statements

**Posted Statement List**

Here, you can view all the lists of posted statements and navigate through them to understand the accounting treatment for the entries.

![PostedStatementList](/images/202411/PostedStatementList.jpg)

![PostedStatementListNavigate](/images/202411/PostedStatementListNavigate.jpg)

* Customer Sale is posted to Cust. Ledger Entry.
* The Document No. is a combination of Store No., POS No. and Transaction No. (The Transaction Header Primary Key). The Description is the Slip No.
* Posting to G/L Entry is according to the standard posting setup for the customer.

![NavigateDetailPostedStatement](/images/202411/NavigateDetailPostedStatement.jpg)

**Statement No. on Transaction Header/Register**

Transactions (POS Sale) belonging to the Statement are all marked with the Statement number and the status posted.

![PostedStatementNo](/images/202411/PostedStatementNo.png)

