---
title: Getting started with a Microsoft account  | Microsoft Docs
description: Getting started with a Microsoft account
author: mariosleon

ms.subservice: desktop-flow
ms.topic: article 
ms.date: 09/22/2020
ms.author: marleon
ms.custom: intro-internal
ms.reviewer:
search.app: 
  - Flow
search.audienceType: 
  - flowmaker
  - enduser
---

# Getting started with a Microsoft account

Power Automate  enables regular and power users alike to create flows, which save time and eliminate human error. 

Focus on other activities by automating routine and repetitive tasks like organizing or backing up your files and folders. Create flows to extract product prices from a website and save them in an Excel spreadsheet then [email it](actions-reference/email.md) as an attachment. [Fill in web forms](automation-web.md#data-population-on-the-web) by supplying information dynamically from your files.  

Create automated workflows with step-by-step guidance and an intuitive, no-code interface anyone can use, regardless of their technical expertise. Build flows from a wide variety of pre-made actions, or [record your interactions as steps](recording-flow.md) to be played back anytime. 

Using Power Automate  with a Microsoft account is available at no additional cost.

>[!Note]
>Flows built with Power Automate using a Microsoft account are stored automatically on the users' OneDrive.

## Build your first flow



The following example demonstrates the creation of a short flow. The completed flow will prompt the user to select a folder. The flow will then copy the folder to another folder named **backup** on the user's desktop.

To create the flow:

1. Launch Power Automate and select the New flow button in the console.

    ![Screenshot of the New flow button in the console.](media\getting-started-msa\console-new-flow.png)


1. Enter a name for the flow and then select **Create**. In this example, the flow is named **Copy Folder to Desktop**.

    ![Screenshot of the Build a flow dialog.](media\getting-started-msa\build-flow-dialog.png)


1. When the Flow Designer opens, go to the Actions pane, open the **Folders** group, and drag and drop the **Get special folder** action to the workspace to add it to the flow.

    ![Screenshot of an action getting dragged into the workspace.](media\getting-started-msa\add-action.png)



1. In the resulting action properties dialog, the desktop folder is selected by default. Select OK to add the action to the flow.

    ![Screenshot of the Get special folder action.](media\getting-started-msa\get-special-folder-action-properties.png)


1. Similarly to step 3, go to the **Message boxes** group, and add the **Display select folder dialog** action to the flow. Set **Dialog description** to **Select a folder to back up:**.

    ![Screenshot of the Display select folder dialog action.](media\getting-started-msa\display-select-folder-dialog-action-properties.png)


1. In the **Folders** group, add **Create folder** to the flow. Set the **Create new folder into** field to **%SpecialFolderPath%** and **New folder name** to **backup**.

    ![Screenshot of the Create folder action.](media\getting-started-msa\create-folder-action-properties.png)


1. In the same group, select the **Copy folder** action. Set **Folder to copy** to **%SelectedFolder%**, **Destination folder** to **%SpecialFolderPath%\backup** and add the action to the flow.

    ![Screenshot of the Copy folder action.](media\getting-started-msa\copy-folder-action-properties.png)


1. Select run to run the flow.

    ![Screenshot of the Run button in the flow designer.](media\getting-started-msa\run-flow.png)

1. Close flow designer and save the flow. Now you can run the flow from the console.

    ![Screenshot of the Run button in the console.](media\getting-started-msa\run-flow-console.png)


When prompted for a folder, select any folder you wish to copy. The flow will create a new folder on your desktop called **backup** with the selected folder inside.

Following this example, it is possible to imagine a wide range of scenarios where these actions could be combined with other actions. Among the many possibilities, users could:
* Select an additional folder on a flash drive to back up to
* Back up files based on specific criteria
* Create a file structure for the backup
* Iterate through a list of folders and only back up selected folders


## Next Steps

- Learn how to [set up Power Automate](setup.md).

- Begin your journey in Power Automate by [creating a Power Automate desktop flow](create-flow.md). 

- Get familiar with the [console](console.md) and the [flow designer](flow-designer.md), which are part of Power Automate for desktop. 

- You'll find the list of actions available in the [Actions reference](actions-reference.md).