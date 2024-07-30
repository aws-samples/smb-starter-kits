CloudFormation template to deploy automation for Amazon WorkSpaces. After deploying this template, WorkSpaces creation,
migration, and deletion is automated via Lambda Functions. 
#
Security Groups which correspond to the library of AWS Public Bundles will be built in your Active Directory based on the selections you make in the 
CloudFormation template parameters. 
The environment (Test or Production) parameter determines whether AD groups for Hourly Billed bundles or Hourly and Monthly billed bundles are created. 
The Retention policy parameter determines how automation deal with users that are removed from all workspaces groups. Retain sets the workspace to auto-stop
and stops the workspace; Delete deletes the workspace automatically with no possible recovery of the instance. 
Protocol choices are WSP and PCoIP. You cannot put a user into both protocol AD groups as a user can only have a single workspace. If you need 
a user to have access to both protocols, create an additional AD user account for that user.
Once the automation is deployed:
  To create a WorkSpace: Add a user to one of the WorkSpaces groups that are created in the Active Directory
  To migrate a WorkSpace: Move a user from their existing WorkSpaces AD group to the AD group to migrate their WorkSpace to.
  To delete a WorkSpace: Remove a user from the AD group to delete their WorkSpace.
  To create a WorkSpace to be used as a "Golden Image": Create an Active Directory User with "ImageCreation" (not case sensitive) 
  in the Username (Login Name). Use the "Workspaces-Create-Bundle" CloudFormation template to create the bundle with your golden
  image. 
Pro Tip: Use the STANDARD built in bundle to create your golden image, taking advantage of the WorkSpaces free tier. See
https://aws.amazon.com/workspaces/pricing/ and select the "Special pricing offers" link for more information.
#
This Starter Kit is an expansion for the Windows Migration Starter Kit. Deployment will fail if there is no 
Windows Migration Starter Kit or AD-Connector Starter Kit deployed. Ensure that you are in the correct AWS region before attempting to deploy this Starter Kit.
With some added parameters, you could add this to a Windows domain which is not created with the Windows Migration Kit. Refer to the environment
Variables in each Lambda function for guidance on the required data.

You are responsible for the cost of usage of the resources deployed in this Starter Kit. Please refer to the AWS Pricing Calculator to verify the costs
of the resources deployed in this Starter Kit prior to deployment. The costs displayed in the Parameters dialogs are subject to change and may not be accurate.

This Starter Kit template deploys all AWS components required to run an automated AWS WorkSpaces with your migrated Windows domain.
It deploys the following:

- Roles for execution of the Lambda Functions
- Activation of your Directory Connector for WorkSpaces via Lambda Function
- Lambda Layer which enables Lambda to query Active Directory for group membership and automatically
  spins up workspaces
- A Lambda function which checks daily for the latest workspace bundle IDs and updates them as SSM Parameters
- A Lambda function which checks every 15 minutes for changes in workspaces AD groups membership and creates/deletes or stops instances
- KMS Key for the Log Files that the Lambda functions generate
- A temporary S3 bucket which stores the Lambda Layer - which is deleted after the Lamda Layer is ceated
- A temporary EC2 instance which creates the Lambda Layer and uploads it to S3. The instance is deleted 
  after the Lambda Layer is created.
#
IMPORTANT - THIS Starter Kit IS NOT SUITABLE FOR BRING-YOUR-OWN-(WINDOWS)-LICENSING. If you require BYOL, please open a 
support case at console.aws.amazon.com/workspaces/v2/account-settings or contact your channel partner. This does not apply 
to M365 Licensing. M365 apps may be installed with M365 licenses by creating a WorkSpace image.
#
This template exports outputs to facilitate easy additions of future services or components such as additional servers, VDI (WorkSpaces), Database, etc. 
It is recommended that these values are NOT changed in any way. 
#
For more details, refer to the Deployment Guide and Troubleshooting Guide.