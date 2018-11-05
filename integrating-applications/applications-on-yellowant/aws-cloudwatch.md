# AWS Cloudwatch

1. Go to your YellowAnt Dashboard \([yoursubdomain.yellowant.com](https://github.com/yellowanthq/yellowant-help-center/tree/bdad19066023aa6a8b667a1d6f05b72945b49759/yoursubdomain.yellowant.com)\) or head over to the [YellowAnt Marketplace](https://www.yellowant.com/marketplace).
2.  In the search bar, simply look for “AWS Cloudwatch”, or click on the icon. If you have already integrated the application, you will be able to see it under “My Applications”.

![](../../.gitbook/assets/capture.PNG)

3. Once you find the application either in the dashboard or on the Marketplace click on view. You will be taken to a page where you'll find the integrate option/button. Click on the integrate button.

![](../../.gitbook/assets/image%20%28312%29.png)

4. You will be on the integration page which prompts you to add an account to the application. Click add account which takes you to the AWS Cloudwatch Access page.  
Note: Select a team before you click "+ ADD ACCOUNT".  


![](../../.gitbook/assets/1.png)

5. In this step, YellowAnt asks you for some details of your AWS Cloudwatch Account for authentication.  


![](../../.gitbook/assets/2.png)

6. Fill in the details and hit "SUBMIT". Your screen should look like this:

![](../../.gitbook/assets/3.png)

7. AWS Cloudwatch is now integrated and you get a message on your chat application for the same. You will be able to see it under your applications in the Dashboard too.

![](../../.gitbook/assets/5.png)

8. To get notifications, follow these steps: 

a. Select the "create-webhook"command on slack to get your url for webhook configurations.

![](../../.gitbook/assets/6%20%281%29.png)

b. Alternatively, you will also find the webhook url on your integrations page:

![](../../.gitbook/assets/7.png)

c. The next step is to set up your Cloudwatch alarm. For this, complete the following steps. Go to your SNS dashboard and create a new topic.

![](../../.gitbook/assets/8%20%281%29.png)

![](../../.gitbook/assets/9%20%282%29.png)

d. In the endpoint, past the url we received earlier

![](../../.gitbook/assets/inked10_li.jpg)

e. Click on "create subscription" to find a list of your subscriptions. Refresh this page to confirm.

![](../../.gitbook/assets/11.png)

![](../../.gitbook/assets/inked12_li.jpg)



f. You will get a YellowAnt notification confirming your subscription

![](../../.gitbook/assets/inked13_li.jpg)

g. In your EC2 dashboard, select the topic which you created earlier, and click create alarm.

![](../../.gitbook/assets/inked14_li.jpg)

![](../../.gitbook/assets/15.png)

9. Your AWS Cloudwatch integration is complete and notifications are now set up!

