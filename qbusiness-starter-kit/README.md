# amazonq-starter-kit

## Getting started
Here are the steps to running this Cloudformation template

If you already have IAM Identity Center setup you can jump to Step 7

1. Navigate to the IAM Identity Center service menu in the AWS Management Console and create an IAM Identity Center. Click the Enable button.
2. To create IAM Identity Center, the AWS Organizations service must be created in advance. If the AWS Organization service is not created, a pop-up window will appear. Read the contents of the pop-up window and click the Create AWS organization button.
3. Add Users to IAM Identity Center. To add a user to the IAM Identity Center, select Users from the left menu and click the Add User button.
4. If the IAM Identity Center User is successfully created, an invitation email is sent to the email address entered when creating a user in step 3
5. Click Accept invitation in the invitation email, you will be taken to a screen where you can set a password
6. Set a new password and click Set new password.
7. Deploy the Q Business App CloudFormation template in AWS Console
8. In the AWS Console click on CloudFormation and click on create stack
9. In the Prerequisite - Prepare template section select Choose an existing template
10. In the Specify template section select Upload a template file and upload the Q Business CloudFormation template name QBusiness kickstarter template and click on next
11. In the Stack name enter a stack name
12. In the parameters section, enter the name of th bucket you already created as S3DataSourceBucket
13. For the QBusinessApplicationName you can change the name to a unique Q business application name or you can use the default name
14. For the WebCrawlerDataSourceUrl, enter any URL of your choice
15. Go to your IAM Identity Center through the AWS console and copy the ARN of your IAM Identity Center Instance and enter as the IAMIdentityCenterARN and click next
16. In the Configure stack options section leave everything as default and click next
17. In the Review and create section check the I acknowledge that AWS CloudFormation might create IAM resources and click on submit
18. In the AWS console click on Amazon Q Business and you will see the new Q business application that was created from the cloudFormation template you deployed
19. Click on the new Q Business application and in the Data sources section click on the data source name DataSource_Name and click on Sync now
20. Go back to the application select the Group and users section and click Manage access and subscriptions.
21. Click on Users and click on Add groups and users. Select Add and assign new users if you didn’t create users in step 3 or select Assign existing users and groups if you created users in step 3
22. If you are adding new users enter its Username, First name, last name, Email address, confirm email address and click next and click Add and finally click Assign. Click on Accept invitation that was sent to your email
23. Select the user and click on Change subscription dropdown and select Update subscription tier. In the New subscription dropdown select either Q Business lite or Q Business pro and click confirm and Done.
24. If you select Assign existing users and groups click on Next and put the user First name and select the user and click on Assign. Repeat step 25 to activate the subscription of the existing user
25. Click on Web experience settings and click on the deployed URL to access the Q application 


