# ServiceNow

1. Go to your YellowAnt Dashboard \([yoursubdomain.yellowant.com](https://github.com/yellowanthq/yellowant-help-center/tree/bdad19066023aa6a8b667a1d6f05b72945b49759/yoursubdomain.yellowant.com)\) or head over to the [YellowAnt Marketplace](https://www.yellowant.com/marketplace).
2. In the search bar, look for "ServiceNow" or simply click the icon. If you have already integrated the application, you will be able to see it under "My Applications".

![](../../.gitbook/assets/snow.PNG)

3. Once you find the application either in the dashboard or on the Marketplace click on Integrate. You will be taken to a page where you'll find the integrate option/button. Click on the integrate button.

![](../../.gitbook/assets/image%20%28251%29.png)

4. You will be on the integration page which prompts you to add an account to the application. Click add account which takes you to the ServiceNow OAuth page.  
Note: Select a team before you click "+ ADD ACCOUNT".

![Select &quot;Add Account&quot;](https://lh5.googleusercontent.com/BN2B8Ug3oatfGneTllvVJJBtmcQo8e1u7mRT-OzlEq4bwslYpQQIitmGHfilBgnn7eC8Vlc5-ND8fliEa2EHp6vng5Txi93folxh265wjWU9ittuSa2FaWo6jSwqSf7MOE7xNEF_)

5. Allow the needed permissions to ServiceNow.

![](https://lh6.googleusercontent.com/glmh60ldWjLn6XlljsyIDIF96_8-bJW3AydXZJM40L0Nw0b6nTeVIk3lJ-czcLY934YaVfsF3bp3hC5zRzkiHMTENYgP-0nlX6StSusDO-5FLeBWtXFI_ziHPhKXWsxPgnNx0Hx8)

6. Select "Integrate". YellowAnt will ask you to fill in a few details

![Fill in the details of your ServiceNow Account](../../.gitbook/assets/image%20%2883%29.png)

To find the values for these fields, follow these steps:

\(i\) Open Application registry in System OAuth in your ServiceNow Instance. Click on "New" and then "Connect to a third party OAuth Provider"

![OAuth for ServiceNow Integration](https://lh4.googleusercontent.com/rJN0C7HnHIqiqdnSR7z_rmZ-uh6oOgMrBl-0d5GsZKpHaV2BCk9QclWRuZeinNUam1FyR6P3S9-sBoqaaxQzDnHus3sHJozt40rGrYehD28QULnSL5TR5ajy8iczeWP_rPizETMX)

\(ii\) Click on Create an OAuth API endpoint for external clients. Enter your application name

![We are naming this &quot;YellowAnt&quot;](../../.gitbook/assets/image%20%2842%29.png)

\(iii\) Copy the Client ID and the Client Secret. Set the Access token and Refresh token lifespan to some high value Click on Submit. The redirect URL needs to filled with the value: [https://www.yellowant.com/market/applications/1930/service-now-auth/](https://www.yellowant.com/market/applications/1930/service-now-auth/) 

![Use these details to integrate your YellowAnt App](https://lh6.googleusercontent.com/ArUnA_NxrQkouiGh4VuAEtVFLzKA-cJ35DjeC16SgdMHL6FYWBuCRKhM8l8e_KLjcnFln2gXhQ7_OaGF7bwOivlaKFV9wQ0wWl8BJUuh40AKqxCzLQHjor906QiSqHIjIUt6RKlL)

7. Enter the Instance name,Client ID and Client secret which was copied earlier. Click "Allow" in your ServiceNow instance

![Click Allow to complete Integration](../../.gitbook/assets/image%20%28249%29.png)

8. YellowAnt will send you a message with available functions. Run "Generate Webhooks". A webhook will be generated in your chat console

![Webhooks in Slack](https://lh5.googleusercontent.com/x9S-YZnDLkSWIIsh_NumbahgFPkNa7JDTpzA83nJIpmT6R_LeunKzRHPFOJzif6C3-D-Xg4XqA05Ha3vwAF3DgezEeevXq8cAb7A0V2R6Acs36EgRm4jYTyuj5MICj1m59V-JVBA)

![Webhooks in Microsoft Teams](../../.gitbook/assets/image%20%28126%29.png)

9. In your ServiceNow instance, open "Business Rules" and click "New".

![](https://lh5.googleusercontent.com/PTGI_qMgUnxkvy77PvYkgGIIr8JickOnuGVbbOj26QAuuwhzEkXnhvLQeqzG2qFctDoUY2xOnS5ZhbGV-OcFiVyU1owhw3kN9_Ep37O20eGC2eanR1OaYNWi87ECDeLriM1j75MS)

 10. Enter a Name for the new webhooks rule. Choose the table as "Incident" .Select" Advanced Checkbox". Select "after" from the "When" dropdown. Select "Insert". In Role conditions select web\_service\_admin.

![](https://lh4.googleusercontent.com/1i7Qxxx7us4EvZvNMsWk9ndLpfhrjxIh0BU1f1iElwf4jA_BcS4tf9-A9cruOYTjlj0Go3YP1Bb9q7LgqZVPfZrXoorzF-Wta4KCEZfidJOdS5BX6X7KymwqNyT9eyy4sHjUk03Z)

11. Go to the "Advanced" tab and paste this code:

```text
(function executeRule(current, previous /*null when async*/) {
try { 
var webhook_id="//Your Webhook ID"
var r = new sn_ws.RESTMessageV2();
r.setEndpoint("https://www.yellowant.com/market/applications/1930/webhooks/"+webhook_id);
body ='{' + 
    '"state"' + ':' + '"' + "created"+'"' + ',' + 
    '"sys_id"' + ':' + '"'+current.sys_id+'"' + ',' + 
    '"number"' + ':' + '"'+current.number+'"' + ',' + 
    '"assigned_to"' + ':' + '"'+current.assigned_to+'"' + ',' + 	
    '"description"' + ':' + '"'+current.short_description+'"' + ',' + 
    '"assigned_to"' + ':' + '"'+current.assigned_to+'"' 
    + '}';
r.setRequestBody(body);
r.setHttpMethod("POST");
 var response = r.execute();
 var responseBody = response.getBody();
 var httpStatus = response.getStatusCode();
}
catch(ex) {
 var message = ex.getMessage();
}
})(current, previous);

```

12. Your ServiceNow integration is now complete.

