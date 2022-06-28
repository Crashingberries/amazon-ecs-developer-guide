# Deregistering a task definition revision<a name="deregister-task-definition"></a>

If you decide that you no longer need a specific task definition revision in Amazon ECS, you can deregister the task definition revision so that it no longer displays in your `ListTaskDefinition` API calls or in the console when you want to run a task or update a service\.

When you deregister a task definition revision, it's immediately marked as `INACTIVE`\. Existing tasks and services that reference an `INACTIVE` task definition revision continue to run without disruption\. Existing services that reference an `INACTIVE` task definition revision can still scale up or down by modifying the service's desired count\.

You can't use an `INACTIVE` task definition revision to run new tasks or create new services\. You also can't update an existing service to reference an `INACTIVE` task definition revision\. This is despite that there might be up to a 10\-minute window following deregistration where these restrictions have not already taken effect\.

**Note**  
At this time, `INACTIVE` task definition revisions remain discoverable in your account indefinitely\. However, this behavior is subject to change in the future\. Therefore, don't rely on `INACTIVE` task definition revisions persisting beyond the lifecycle of any associated tasks and services\.

**To deregister a new task definition \(Classic Amazon ECS console\)**

1. Open the Amazon ECS console at [https://console\.aws\.amazon\.com/ecs/](https://console.aws.amazon.com/ecs/)\.

1. From the navigation bar, choose the Region that contains your task definition\.

1. In the navigation pane, choose **task definitions**\.

1. On the **task definitions** page, choose the task definition family that contains one or more revisions that you want to deregister\.

1. On the **task definition Name** page, select the box to the left of each task definition revision that you want to deregister\.

1. Choose **Actions**, **Deregister**\.

1. Verify the information in the **Deregister task definition** window, and then choose **Deregister** to finish\.