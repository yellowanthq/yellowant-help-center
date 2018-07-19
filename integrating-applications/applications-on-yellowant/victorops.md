# VictorOps



1. Go to your YellowAnt Dashboard \([yoursubdomain.yellowant.com](https://github.com/yellowanthq/yellowant-help-center/tree/bdad19066023aa6a8b667a1d6f05b72945b49759/yoursubdomain.yellowant.com)\) or head over to the [YellowAnt Marketplace](https://www.yellowant.com/marketplace).

![YellowAnt Dashboard - Available Applications Panel](../../.gitbook/assets/image%20%2866%29.png)

2. If you are in the dashboard, go to the tab called "Applications" and look for "VictorOps" under available applications. You can also search for this application in the search bar.

![](../../.gitbook/assets/image%20%2846%29.png)

3. Once you find the application either in the dashboard or on the Marketplace click on Integrate. You will be taken to a page where you'll find the integrate option/button. Click on the integrate button.

![](../../.gitbook/assets/image%20%28117%29.png)

4. You will be on the integration page which prompts you to add an account to the application. Click add account which takes you to the VictorOps OAuth page.  
Note: Select a team before you click "+ ADD ACCOUNT".

![](../../.gitbook/assets/image%20%28165%29.png)

5. For the next step, API access needs to be turned on in the VictorOps portal and an API key should be generated. 

\(i\) To enable API access go to the API tab in the settings page of the VictorOps portal. Click on the "Activate API" button. On activating the API an API ID is generated.

![](../../.gitbook/assets/image%20%28152%29.png)

\(ii\)  Click on the "New Key" button to generate an API Key

![](../../.gitbook/assets/image%20%28175%29.png)

6. Enter the information in the integration window

![](../../.gitbook/assets/image%20%28310%29.png)

7. VictorOps is now integrated and you get a message on your chat application for the same. You will be able to see it under your applications in the Dashboard too.

8. VictorOps has webhooks for incident triggered,incident acknowledged and incident resolved. The webhooks need to be created manually.

Steps to create a webhook:

\(i\)  Go to the settings page in the VictorOps portal.  In settings select outgoing webhooks in the Alert Behavior dropdown.  Click on the add webhook button.

\(ii\)  Select the event type as "Any-Incident", method as POST, Content Type as application/json

\(iii\) The webhook URL needs to be given in the "To" box. The webhook url should be of the format `"https://59efbf61.ngrok.io/webhook/webhook_id"` The webhook\_id is present in the database which should be provided to the user.

\(iv\) The payload should be the below content

`{"display_name":"${{ALERT.entity_display_name}}","message_type":"${{ALERT.message_type}}", "alert_count": "${{STATE.ALERT_COUNT}}","alert_phase": "${{STATE.CURRENT_ALERT_PHASE}}", "entity_id": "${{STATE.ENTITY_ID}}","incident_number": "${{STATE.INCIDENT_NAME}}", "message": "${{STATE.SERVICE}}"}`

\(v\) Add a description and click on save.

This will send a webhook to the specified url whenever a new incident is triggered, acknowledged or resolved.

![](../../.gitbook/assets/image%20%28119%29.png)

9. VictorOps is now integrated. 



