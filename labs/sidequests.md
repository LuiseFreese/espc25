# Sidequests

## Power Apps

If you completed all labs and still have time (and energy), we have some additional sidequests for you. In these side quests, we will not give you detailed instructions, but rather a few hints.

1. Create an **Add Receipt** experience as a modal

Hints for creating an **Add Receipt** Experience: 

- you will need a button that will open a popup window. Popup (or modal) windows are an elegant solution if you want to display content in the context of a screen.
- For a popup, you'd typically 

  - create a semitransparent rectangle shaped overlay over the entire screen
  - place a smaller rectangle with your content (a form and a save-button) on it. 
  - This save button should submit the form.
  - To hide it, you insert an `X` icon that on its **OnSelect** will set a variable, for example `Set(isModalvisible, false)`
  - To make the popup appear, that very same variable needs to be to `true` (preferably in the **ONSElect** of your **Add Trip** button)
  - Now  the only thing left to do would be to set the **Visible** property of your popup to `isModalVisible`

2. Create a filter experience for your Trips to be allow filtering for Status (Draft, Submitted, Approved, Rejected)

Hints for creating a filter experience

- You need to populate a dropdown with the Choices of the Status column in the **Trips** list
- The `Filter()` function is your friend, use it in the gallery to show only records of the Trips list, where the Status columns value is the same as the selected value of the Dropdown control.
- You can put containers inside of containers for placing your dropdown next to the Add new trip button

## Power Automate

It would be very convenient for the approver to get a direct link in the approval flow. Store the Approval ID in an extra column in the `Trips` list and create a hyperlink in the teams message.

Our friend Tomasz has written a [guide](https://poszytek.eu/en/microsoft-en/office-365-en/powerautomate-en/direct-link-to-power-automate-approval-task/) how you can achieve this.