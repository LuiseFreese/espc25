# Send an approval to the approver

In this lab we'll create our first flow that will be triggered when a new trip reaches the status `Submitted`. The trip is then sent to Approval to our selected Approver and can be Accepted or Rejected. That change is then reflected in the SharePoint list.

## Create a new Power Automate flow and select the trigger

We head over to [make.powerautomate.com](https://make.powerautomate.com/) and select the correct environment.

> [!TIP]
> A best practice would be to create all your Apps, Flows (and other artifacts) from within solutions.
> Read up about solutions [here](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/solutions-overview).

Click on **Create** and select **Automated Cloud Flow**
![Placeholder](images/powerapps-container.png)

We will name the flow `Trip approval` and set the trigger to `When an item is created or modified (SharePoint)`.
![Placeholder](images/powerapps-container.png)

Hit create and after a short while the resulting flow should look like this.
![Placeholder](images/powerapps-container.png)

## Add a trigger condition

> [!WARNING]
> Trigger conditions are an advanced technique, but are the absolute correct approach in this scenario. Don't feel intimidated, it gets easier from here on.
> If you want to dive deeper into the concept, here is the [documentation](https://learn.microsoft.com/en-us/power-automate/customize-triggers?tabs=new-designer)

The trigger would currently trigger in unwanted scenarios. It would start the flow the first time the item is created and any subsequent time that the item is modified. With the trigger condition we'll make sure, that the flow only runs when the item is in the **Status** `Submitted`.

We can check that programmatically with a trigger condition. Click on the trigger and select **Settings**. Add the following code as a new trigger condition
```
@equals(triggerOutputs()?['body/Status/Value'], 'Submitted')
```

## Add the approval workflow

## Inform the user and set the new status









## Create new Trips

We now want to allow users to add new trips.

### Insert Add new Trip Button

1. Select **ctn_Sidebar_Trips**
2. Insert a new button, rename it to `btn_AddTrip`
   - **Text**: `Add new Trip`
   - **Icon**: `+`
   - **Layout**: `Icon Before
   - **Type**: `Subtle`
   - **Width**: `140`
   - **Align in container**: `End`
3. Move that button to the top: `...` > **Reorder** > **Move to the top**

### Create a new Screen

We still have **Screen1** - this has been auto-generated when we created the app. We can now repurpose this screen for the form to add new trips

1. Rename the **Screen1** to `Add Trips Screen`
2. Rename the existing containers to this: 

![Power Apps Container](images/powerapps-container.png)

(If you have ideas for the Footer container: Go for it, you also also delete it)

3. Insert a header control into the header container. Style it the way you did with the one on the Trips Screen.
4. In ctn)Main_AddTrips, add a Form control, rename it to `frm_addTrip` and 
5. Select **Trips** as the datasource
6. Set its **Default mode** to `New`

![Form Datasource](images/powerapps-form-datasource.png)

7. Remove the **Content type** and the **Status** field

![Field remove](images/powerapps-form-field-remove.png)

8. Change to **Columns**: `2` Layout
9. Rightclick the **Approver_Datacard`, select **Unlock**
10. Select the **DataCardValue** and select **Fields: Edit** in the Property pane > **Add field** > **DisplayName**
11. Select the **ctn_Main_AddTrips** container and add a Button:
   - **Text**: `Save`
   - **Icon**: `Save`
   - **Type** `Subtle`
   - **Align in container**: `End`
12. Now move the button to the top
13. In the **OnSelect** of the button, put `SubmitForm(frm_addTrip); ResetForm(frm_addTrip); Navigate('Trips Screen')` to submit the form, reset its entries and Navigate back to the Trips Screen.
14. On the Trips Screen, select the **Add New Trip** button and set its **Onselect** to `Navigate('Add Trips Screen')`

Your Add Trips Screen should look like this:

![Add Trips Screen](images/powerapps-screen_addTrips.png)

☘️ Whoohoo, you made it through lab 3 and with that completed your main quests! If you still have time, you can now work on the Sidequests!