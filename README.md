## What is this Repo?
This repository contains all technical artifacts for Distributor/Partner SMB Starter Kits. All GTM materials and instructions for using these kits can be found in APN Marketing Central.
## About SMB Starter Kits:
Designed for AWS Distribution Partners, SMB Starter Kits are packaged customer solutions that address key SMB greenfield use cases. They consist of templated go-to-market and technical content which AWS Distribution Partners can customize and launch with their Distribution sellers to begin selling AWS solutions to customers. Each folder in this repository consists of the technical artifacts for a kit.

**Kit 1 - Windows Migration Starter Kit**
Latest Unit Test - 7/28/2024 in us-east-1 region
This Starter Kit deploys everything you need to migrate an on-prem Windows Domain and File Server to AWS. Out of the box, the intances are sized for domains that are 50 users or less. Included in the setup is the VPC networking, Network ACLs, Virtual Machines, Security Groups, a Site to Site VPN Tunnel, Dashboard, Alarms, and Backup Jobs. All of this is deployed automatically for you. In addition, each EC2 instance contains automation scripts that automate the migration of Active Directory and the file server at the click of a button. No advanced cloud knowledge is necessary!

**Kit 2 - Secure Website Starter Kit**
Latest Unit Test - 7/6/2024 in us-east-1 region
This Starter Kit deploys everything you need to securely publish a website on the internet. It deploys the Route 53 hosted zone (if required), the zone records, S3 buckets, an SSL certificate, a CloudFront distribution, a Web Application Firewall, and a performance dashboard. Deploy the template, upload your HTML and images to the S3 bucket, and you are up and running, no advanced cloud knowledge necessary!

**Kit 3 - Windows Migration Add-On - AD Connector**
Latest Unit test - 7/30/2024 in us-east-1 region
This starter kit adds to the capabilities of the Windows Migration Starter Kit by adding an AD Connector. AWS AD Connector is part of the AWS Directory Service, connecting your EC2-based Active Directory that was deployed in the Windows Migration Starter Kit to AWS services such as Amazon WorkSpaces and others. 

**Kit 4 - Windows Migration Add-On - WorkSpaces**
Latest Unit Test - 7/30/2024 in us-east-1 region
This starter kit deploys an automation solution to automate the deployment of WorkSpaces (Virtual Desktops) by adding users to Active Directory Security Groups. Deleting a WorkSpace is achieved by removing the user from the AD Security Group. This allows easy administration of WorkSpaces without having to open the AWS Console. 

**Kit 5 - Amazon QBusiness Starter Kit**
This starter kit deploys Amazon Q Business for you, using an S3 bucket and Web Crawlers that you specify as data sources for it's knowledge base. 

## We welcome your feedback!
Please feel free to raise issues or ask for feature requests. Distributors and Partners are encouraged to download these templates and customize them for their specific governance and use cases. 
