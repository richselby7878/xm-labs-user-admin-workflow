# User Admin Workflow
Not an integration. Just a time-saver for xMatters administrators. Do you ever find yourself scrolling through the xMatters User list and manually updating user status? Perhaps the HR department sends you a long list of leavers each day via Excel for you to action and it's the bane of your life? Then this little utility will save you heaps of time. It allows you to paste in a list of xMatters User IDs and flick their status to inactive or back the other way to active. 

---------

<kbd>
  <a href="https://support.xmatters.com/hc/en-us/community/topics">
  <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
  </a>
</kbd>

---------


# Pre-Requisites
* xMatters account - If you don't have one, [get one](https://www.xmatters.com)!
* Some users to administer

# Files
* [UserAdminWorkflow.zip](UserAdminWorkflow.zip) - User Admin Workflow containing four forms, two flows and a custom step.  

# How it works
In the xMatters UI, navigate to Messaging > User Admin Workflow > Deactivate Users (or Activate Users).
<kbd>
  <img src="/media/messaging_useradmin.png" width="500">
</kbd>
Enter the list of users you wish to deactivate (can be pasted from Excel). Set the separator character from a Choice of three; default is new line. The system is fairly forgiving when it comes to input, e.g. blank lines or duplicate entrees. Then press the big blue Send Message button.
<kbd>
  <img src="/media/deactivate_form.png" width="750">
</kbd>
 You confirm it's OK to send without a recipient. Then you wait a minute for a report via email to arrive. 
<kbd>
  <img src="/media/no_recipient.png" width="500">
</kbd>
Pop over to the Rcent Events report. Deactivate-users kicker will be there, as that's the form you just sent. A minute later, the Deactivated User Report will appear above. 
<kbd>
  <img src="/media/recent_events.png" width="500">
</kbd>
Hover your mouse on the right under the Date Started column. Click the envelope icon that slides into view to see your report. It lets you know who was deactivated, who was already inactive etc. Read the key in the report for more information.
<kbd>
  <img src="/media/deactivated_user_report.png" width="750">
</kbd>
Alternatively, you can configure so the Deactivated User Report gets emailed to any user or group on the system. See Installation Step 3 below.

Should you check your User list in xMatters you will see how those users are now deactivated.
<kbd>
  <img src="/media/user_list.png" width="750">
</kbd>


# Installation

## xMatters set up
1. Log into xMatters as a user with the Developer role. Navigate to Workflows, click the Import button on the top right and import the [UserAdminWorkflow.zip](UserAdminWorkflow.zip) file.
2. Click the Open Workflow button. You will see a list of four forms. If other users are allowed to use it, you will need to set Sender Permissions on all four forms. To do this, click the left most button (says Web UI) and then Sender Permissions. Add the users or roles who can use the form.
<kbd>
  <img src="/media/sender_permissions.png" width="750">
</kbd>

3. Optional: If you want the results emailed to a user or group, you can set this on the report forms. Edit the *Deactivate User report* form by clicking Edit > Layout. Add recipients to the Recipient box then save changes. Navigate back a level and repeat for *Activate User report*.

4. Optional: There's a litle trick you can use to eliminate the No Recipients Selected warning. First create an xMatters user called Nobody who has no devices. Open the *Deactivate Users* form and set this user as recipient. You can also grey out the eye-icon to stop recipient from being displayed.  Repeat for *Activate Users*. Don't forget to Save Changes. 
<kbd>
  <img src="/media/nobody" width="500">
</kbd>



# Testing
Do a browser page reload,  navigate to Messaging > User Admin Workflow > Deactivate Users and give it a whirl.



# Troubleshooting
Debug logs are available. Navigate to the workflows's Integration Builder tab, expand Outbound integrations, then select Activity Stream from the right-hand gear icon. The Activity Stream contains logs.
<kbd>
  <img src="activity_stream" width="750">
</kbd>
You can also see the same logs via Flow Designer. Navigate to the Flows tab, Deacticate Users flow, click the Activity button, click the lomg Name, then click the Log tab.
<kbd>
  <img src="flow_logs" width="750">
</kbd>
The JavaScript code is contained within the Deactivate Users custom step. This can also be edited from the Flow tab > Custom section.
<kbd>
  <img src="custom_step" width="750">
</kbd>
