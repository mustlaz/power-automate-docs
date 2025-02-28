---
title: Message boxes | Microsoft Docs
description: Message boxes Actions Reference
author: mariosleon

ms.subservice: desktop-flow
ms.topic: reference
ms.date: 12/02/2020
ms.author: marleon
ms.reviewer:
search.app: 
  - Flow
search.audienceType: 
  - flowmaker
  - enduser
---

# Message boxes



Interact with users and request input through message boxes

[Display message](#showmessagedialog)  
[Display input dialog](#inputdialog)  
[Display select date dialog](#selectdatedialog)  
[Display select from list dialog](#selectfromlistdialog)  
[Display select  file dialog](#selectfiledialog)  
[Display select folder dialog](#selectfolder)  
[Display custom form](#showcustomdialog)  

## Getting started with message boxes

Message boxes can be used in desktop flows to interact with users, request input, and provide output of flow data.

To display a message to the user while a flow runs, use the **Display message** action. The example below displays a message box that informs the user that parsing is complete and asks whether to parse an additional file. 

The message box has been set to display the question icon and always be on top of other windows. The user's selection is stored in the **ButtonPressed** variable. 

![Screenshot of the Display message action.](media/display/display-message-example.png)

The displayed message box looks like the following figure:

![Screenshot of a message box.](media/display/message-box-example.png)

To display a dialog that requests input data, use the **Display input dialog** action. This action requires a title for the dialog window and a message as a prompt for the user. Optionally, you can set a default value and an input type (single line, multiline, or password).

Use the **Display select file dialog** to prompt users to browse for a file. In the following example, the action prompts the user to select an image file. The initial folder has been set to a variable, and the file filter allows specific file extensions.

![Screenshot of the Display select file dialog action.](media/display/display-select-file-example.png)

The select file dialog looks like the following figure. Note that the file filter in the bottom right cornoner of the dialog is specified in the action properties. 

![Screenshot of a Select file dialog example.](media/display/select-file-example.png)

To create a custom form that accepts multiple elements, use the **Display custom form** action. Using this action, you can create custom forms that contain various input types and buttons. You can find more information regarding custom forms in [Create custom forms](../custom-forms.md).

![Screenshot of the custom form designer.](media/display/custom-form-designer.png)


## Message boxes actions


### <a name="showmessagedialog"></a> Display message
Displays a message box

##### Input Parameters
|Argument|Optional|Accepts|Default Value|Description|
|-----|-----|-----|-----|-----|
|Message box title|Yes|[Text value](../variable-data-types.md#text-value)||The text to use as the message box title|
|Message to display|Yes|[Text value](../variable-data-types.md#text-value)||The text to display as the actual message|
|Message box icon|N/A|None, Information, Question, Warning, Error|None|The icon to display with the message box|
|Message box buttons|N/A|OK, OK - Cancel, Yes - No, Yes - No - Cancel, Abort - Retry - Ignore, Retry - Cancel|OK|The buttons to display on the message box|
|Default button|N/A|First button, Second button, Third button|First button|The button to highlight by default. If the user presses **Enter**, this button will be pressed|
|Keep message box always on top|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Specify whether the message box should always remain on top of all other windows|
|Close message box automatically|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Specify whether the message box closes automatically after a preset time, as if the default button was pressed. Otherwise, the flow will wait until a button is pressed by the user|
|Timeout|Yes|[Numeric value](../variable-data-types.md#numeric-value)|3|The seconds to pause the automation while waiting for input, until continuing automatically|


##### Variables Produced
|Argument|Type|Description|
|-----|-----|-----|
|ButtonPressed|[Text value](../variable-data-types.md#text-value)|The text of the button pressed|


##### <a name="showmessagedialog_onerror"></a> Exceptions
|Exception|Description|
|-----|-----|
|Failed to display message box|Indicates a problem displaying the message dialog|
|Can't display message box in non interactive mode|Indicates a problem displaying the message dialog in non-interactive mode|

### <a name="inputdialog"></a> Display input dialog
Displays a dialog box that prompts the user to enter text

##### Input Parameters
|Argument|Optional|Accepts|Default Value|Description|
|-----|-----|-----|-----|-----|
|Input dialog title|Yes|[Text value](../variable-data-types.md#text-value)||The dialog title|
|Input dialog message|Yes|[Text value](../variable-data-types.md#text-value)||The dialog message|
|Default value|Yes|[Text value](../variable-data-types.md#text-value)||Specify the text to display by default. If the user wishes to change this, they can type over it. Otherwise, the default text will be used|
|Input type|N/A|Single line, Password, Multiline|Single line|The format for the input text. Choose Single line - password to hide the text or multiline so that a larger display box makes visible more than one line of text|
|Keep input dialog always on top|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Specify whether the input dialog should always remain on top of all other windows|


##### Variables Produced
|Argument|Type|Description|
|-----|-----|-----|
|UserInput|[Text value](../variable-data-types.md#text-value)|The text entered by the user, or the default text|
|ButtonPressed|[Text value](../variable-data-types.md#text-value)|The text of the button pressed. The user will automatically be given the choice of OK or Cancel|


##### <a name="inputdialog_onerror"></a> Exceptions
|Exception|Description|
|-----|-----|
|Failed to display input dialog|Indicates a problem displaying the input dialog|
|Can't display input dialog in non interactive mode|Indicates a problem displaying the input dialog in non-interactive mode|

### <a name="selectdatedialog"></a> Display select date dialog
Displays a dialog box that prompts the user to enter a date or date range

##### Input Parameters
|Argument|Optional|Accepts|Default Value|Description|
|-----|-----|-----|-----|-----|
|Dialog title|Yes|[Text value](../variable-data-types.md#text-value)||The dialog title|
|Dialog message|Yes|[Text value](../variable-data-types.md#text-value)||The dialog message|
|Dialog type|N/A|Single date, Date range (2 Dates)|Single date|Whether the user will enter a single date or two dates as the endpoints of a range of dates|
|Prompt for|N/A|Date only, Date and time|Date only|Specify whether the user will enter the date only or the date and time|
|Default value|Yes|[Datetime](../variable-data-types.md#dates-and-time)||The default value for the date|
|Default value for second date|Yes|[Datetime](../variable-data-types.md#dates-and-time)||The default value for the end date in a range|
|Keep date selection dialog always on top|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Specify whether the date selection dialog should always remain on top of all other windows|


##### Variables Produced
|Argument|Type|Description|
|-----|-----|-----|
|SelectedDate|[Datetime](../variable-data-types.md#dates-and-time)|The date entered by the user or the default date|
|SecondSelectedDate|[Datetime](../variable-data-types.md#dates-and-time)|The second date entered by the user or that default date|
|ButtonPressed|[Text value](../variable-data-types.md#text-value)|The text of the button pressed by the user. The user will automatically be given the choice of OK or Cancel|


##### <a name="selectdatedialog_onerror"></a> Exceptions
|Exception|Description|
|-----|-----|
|Failed to display select date dialog|Indicates a problem displaying the select date dialog|
|Can't display select date dialog in non interactive mode|Indicates a problem displaying the input dialog in non-interactive mode|

### <a name="selectfromlistdialog"></a> Display select from list dialog
Displays a dialog box with options that lets the user select from a list

##### Input Parameters
|Argument|Optional|Accepts|Default Value|Description|
|-----|-----|-----|-----|-----|
|Dialog title|Yes|[Text value](../variable-data-types.md#text-value)||The dialog title|
|Dialog message|Yes|[Text value](../variable-data-types.md#text-value)||The dialog message|
|List to choose from|No|[General value](../variable-data-types.md#general-value)||The list to display as a drop-down menu for the user to choose from|
|Keep select dialog always on top|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Specify whether the select dialog should always remain on top of all other windows|
|Limit to list|N/A|[Boolean value](../variable-data-types.md#boolean-value)|True|Whether to allow the user to enter their own answer outside of the list being displayed|
|Allow empty selection|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Allow the user to not select anything, creating an empty selected item output|
|Allow multiple selection|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Allow the user to select more than one choice. This means that the selected item and selected index variables will hold a list of items|
|Preselect items starting with a + sign|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Specify whether the items with a prepended '+' sign will appear automatically preselected|


##### Variables Produced
|Argument|Type|Description|
|-----|-----|-----|
|SelectedItem|[Text value](../variable-data-types.md#text-value)|The item selected from the list as text|
|SelectedItems|[List](../variable-data-types.md#list) of [Text values](../variable-data-types.md#text-value)|The items selected from the list as a list of text|
|SelectedIndex|[Numeric value](../variable-data-types.md#numeric-value)|The index number of the item selected from the list. This allows the user to use the item number instead of the full text of the user's choice|
|SelectedIndexes|[List](../variable-data-types.md#list) of [Numeric values](../variable-data-types.md#numeric-value)|The index number of the items selected from the list. This allows the user to use the item number instead of the full text of the user's choice|
|ButtonPressed|[Text value](../variable-data-types.md#text-value)|The name of the button pressed by the user (OK or Cancel)|


##### <a name="selectfromlistdialog_onerror"></a> Exceptions
|Exception|Description|
|-----|-----|
|Failed to display select dialog|Indicates a problem displaying the select dialog|
|Can't display select dialog in non interactive mode|Indicates a problem displaying the input dialog in non-interactive mode|

### <a name="selectfiledialog"></a> Display select  file dialog
Displays the select file dialog and prompts the user to select one or more files

##### Input Parameters
|Argument|Optional|Accepts|Default Value|Description|
|-----|-----|-----|-----|-----|
|Dialog title|Yes|[Text value](../variable-data-types.md#text-value)||The dialog title|
|Initial folder|Yes|[Folder](../variable-data-types.md#files-and-folders)||The initial folder to open when browsing for a file. This is where the select file dialog action will start the user looking for the file(s)|
|File filter|Yes|[Text value](../variable-data-types.md#text-value)||A filter to limit the files retrieved. This allows wild cards, for example "*.txt" or "document?.doc" (without the quotes). To allow the user to choose from multiple file filters, separate the choices with a semi-colon, for example "*.txt;*.exe"|
|Keep file selection dialog always on top|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Whether the file selection dialog should always remain on top of all other windows|
|Allow multiple selection|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Whether the user will be able to select more than one file or not|
|Check if file exists|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Whether only files that already exist will be accepted|


##### Variables Produced
|Argument|Type|Description|
|-----|-----|-----|
|SelectedFile|[File](../variable-data-types.md#files-and-folders)|The file that will be selected through the dialog|
|SelectedFiles|[List](../variable-data-types.md#list) of [Files](../variable-data-types.md#files-and-folders)|The file(s) selected|
|ButtonPressed|[Text value](../variable-data-types.md#text-value)|The text of the button pressed. The user will automatically be given the choice of Open or Cancel|


##### <a name="selectfiledialog_onerror"></a> Exceptions
|Exception|Description|
|-----|-----|
|Failed to display select file dialog|Indicates a problem displaying the select file dialog|
|Can't display select file dialog in non interactive mode|Indicates a problem displaying the input dialog in non-interactive mode|

### <a name="selectfolder"></a> Display select folder dialog
Displays the select folder dialog and prompts the user to select a folder

##### Input Parameters
|Argument|Optional|Accepts|Default Value|Description|
|-----|-----|-----|-----|-----|
|Dialog description|Yes|[Text value](../variable-data-types.md#text-value)||The description of the select folder dialog For example, "Please select the folder into which you wish to copy the files"|
|Initial folder|Yes|[Folder](../variable-data-types.md#files-and-folders)||The initial folder to open. This will be the default folder unless the user picks a new one|
|Keep folder selection dialog always on top|N/A|[Boolean value](../variable-data-types.md#boolean-value)|False|Whether the folder selection dialog should always remain on top of all other windows|


##### Variables Produced
|Argument|Type|Description|
|-----|-----|-----|
|SelectedFolder|[Folder](../variable-data-types.md#files-and-folders)|The selected folder|
|ButtonPressed|[Text value](../variable-data-types.md#text-value)|The text of the button pressed. The user will automatically be given the choice of OK or Cancel|


##### <a name="selectfolder_onerror"></a> Exceptions
|Exception|Description|
|-----|-----|
|Failed to display select folder dialog|Indicates a problem displaying the select folder dialog|
|Can't display select folder dialog in non interactive mode|Indicates a problem displaying the input dialog in non-interactive mode|


### <a name="showcustomdialog"></a> Display custom form
Display a customized form that can include multiple types of elements, like text, number or file inputs etc.

##### Input Parameters

Input parameters are configured through the [custom form designer](../custom-forms.md).

##### Variables Produced
|Argument|Type|Description|
|-----|-----|-----|
|CustomFormData|[Custom object](../variable-data-types.md#custom-object)|A custom object containing the user's input|
|ButtonPressed|[Text value](../variable-data-types.md#text-value)|The ID of the button pressed|


##### <a name="showcustomdialog_onerror"></a> Exceptions
|Exception|Description|
|-----|-----|
|Failed to display custom form|Indicates a problem displaying the custom form|


[!INCLUDE[footer-include](../../includes/footer-banner.md)]