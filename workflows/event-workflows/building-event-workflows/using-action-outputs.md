# Using Action Outputs

## Using Action Outputs

One important feature while creating workflows is to use action outputs. Action outputs are the outputs of a previously added action or coming right from the trigger event itself. In case of command workflows, if no parameter is passed then the action outputs of the trigger remains empty. You can access the action outputs by using "@" in any text field in the subsequent actions.

Example 1:

### In the trigger command, since no parameters are being passed, we don't see any outputs available in the next step. And using "@" gives us no options. 

![](../../../.gitbook/assets/image%20%28241%29.png)

![](../../../.gitbook/assets/treg7.png)

### In this case, a parameter was passed in the trigger command, so we see "build" appearing as a data option. 

![](../../../.gitbook/assets/image%20%28231%29.png)

![](../../../.gitbook/assets/image%20%28161%29.png)

