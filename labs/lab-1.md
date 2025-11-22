# Lab 1: Create SharePoint Lists with a LookUp Column

*Objective:** Create two SharePoint lists, **Trips** and **Receipts**, and connect them with a lookup column to establish a pseudo-relational data structure.

## Part A: Creating the **Trips** List

1. **Navigate to SharePoint Home**: Go to your SharePoint site and select **New** > **List**

![Create a new List](/images/create-list.png)


2. Under **Create from blank**, select **List**:  Choose the option to create a blank list
![Create a new List](/images/create-list-blank.png)

3. **Name the List**: Enter the name **Trips**. Select **Create**

![Name the list](/images/create-list-name.png)


1. **Add Columns to **Trips** List:
   - **Title Column** (automatically created)
   - **Start**:
     - Select **Add Column** > **Date and Time** 
     - Name it **Start**
     - (Include time: no)
     - Default value: **Today's Date**
     - Select **Save**

![Create the column](/images/create-column-save.png)
     - Select **Add Column** > **Date and Time** 
     - Name it **End**
     - (Include time: no)
     - Default value: **Today's Date**
     - Select **Save**
   - **Status**:
     - Select **Add Column** > **Choice**
     - Name it **Status** and rename the placeholder choices to `Draft`, `Submitted`, `Approved`, `Rejected`. If you like to, you can change the styling of the choices.
     - Set **Default Value** to `Draft`
     - Select **Save**
![Create the column](/images/create-column-choice.png)

   - **Approver**:
     - Select **Add Column** > **Person**
     - Name it **Approver**
     - Select **Save**
  
Your **Trips** list should now look like this:


![Verify Trips list](/images/list-schema.png)
---

## Part B: Creating the **Receipts** List

1. **Create a New List**: Return to the SharePoint site home, select **New** > **List**, and select a blank list once again

2. **Name the List**: Enter **Receipts** as the list name. Select **Create**

3. **Add Columns to Receipts List**:
   - **Date**:
     - Select **Add Column** > **Date and Time** 
     - Name it **Start**
     - (Include time: no)
     - Default value: **Today's Date**
     - Select **Save**
   - **Amount**:
     - Select **Add Column** > **Number** 
     - Name it **Amount**
     - **Number of decimal places**: 2
     - Select **Save**
   - **Currency**
     - Select **Add Column** > **Text** 
     - Name it **Currency**
     - Select **Save**
   - **Trip (Lookup Column)**:
     - Select **Add Column** > **Lookup**
     - Name it **Trip**
     - Under "Get information from," select the **Trips** list
     - Choose **Title** in the column dropdown
     - Select **Save**
   - **isPresent** > yes/no (default no)

![create a Lookup column](/images/list-lookup.png)

Your **Receipts** list should now look like this:

![Verify Trips list](/images/list-schema-receipts.png)

🥳 Congrats, you made it through lab 1! [Continue with lab 2](/lab-2.md)

