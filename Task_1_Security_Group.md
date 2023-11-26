# Create A Security Group  

Written by [OT](https://github.com/Otlhomame)



## About Security Groups! <a name="about"></a>

Imagine you were a security officer of a building of multiple floors and offices and your duty was to perform a lock up and periodic patrols for the night for every room. This would include accessing each office to inspect the window locks to confirm that everything is secure and no intrusion had happened. Every office door has a unique key which must be used to access an office. One particular advantage of this security control setup is that it offers a layer of security at an office level to protect each office by its unique key.

AWS security groups work in a similar way to offer instance level protection for different aws resources within the cloud. They are a virtual firewall service by AWS which protects what internet connections can reach EC2 instances within your private computing network. Apart from other network traffic control services like Network access controls, NAT and internet gateways, security groups can be used to control whether a website can be accessed and how it could be accessed. On AWS, a cloud administrator could manually set which internet protocol can be used to access a web page by attaching the virtual machine instance hosting that website to a security group. This gives granular control over how exposed your website is to the internet.

## Why use security groups in practice?

Permission management:
 
In an infrastructural configuration, an administrator may choose to make decoupled services which require different security permissions for other services to access them. By default, if one creates an EC2 machine without a security group, the default security group wll be used. The shortfall of this approach is that if you have more than one resource which requires different methods of instance level protection, you may not be able to have a one size fits all security group configuration. Classically, public files and private files cannot share the same security permissions if that is what the website design requires. The ability to have multiple security groups enables the architect team to separate software services by instance gives access permission control for software services.

## Common Cloud Mistakes Corrected By Proper Security Group Usage

In a concise article by [corestack](https://www.corestack.io/aws-security-best-practices/aws-security-group-best-practices/), the table below indicates the best practices for using security groups everyday in the cloud configuration environment.

| Common Mistake | Issue                                  | Best Practice          |
|-------------|-----------------------------------------|----------------------|
| Using the AWS default security group for active resources       | New instances can adopt the group by default – potential unintentional security compromise        | Create new security groups and restrict traffic appropriately |
| Allow all inbound access  (using 0.0.0.0/0) to some or all ports       | Enables external security attacks e.g. port scans, DoS, and brute force password attempts  | Where possible, restrict inbound access to required IP address(es) and by port, even internally |
| Allow all outbound access (using 0.0.0.0/0) on all ports       | Enables data loss through exfiltration attacks        | Where possible, restrict outbound access to required IP address(es) and by port, even internally |
| Creation of multiple security groups e.g. one for each EC2 instance       | Difficult to manage, maintain and audit        | Use a strategy to combine similar usage into a single security group |
| Allow access to large subnet ranges e.g. for the whole VPC       | Enables internal security attacks e.g. packet sniffers and  OS credential dumping        | Where possible, restrict to single IPs / small subnet ranges and preferably other AWS security groups |
| No Security Group strategy used       | Difficult to manage, maintain and audit        | Develop and enforce a Security Group strategy |
| Security groups are not monitored and / or managed       | No alerting of suspicious activity or unintentional security risks        | Develop and enforce a Security Group monitoring solution |




## :information_source: Pre-requisites

- [x]  Have a free tier AWS Account at: aws.amazon.com
- [x]  Login to AWS account and get started on step 1 below


## Steps To Create a Security Group

### 1 - Search for “Security Groups” in the main navigation bar at the top:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/1.png" width="100%" height="100%"><br>

### 2 - Click on “Create Security Group” as indicated: <br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/2.png" width="100%" height="100%"><br>

### 3 - Name your Security group by name “MyFirstSecurityGroup”. In this case, it serves to be used for the default VPC called “Do Not Touch”:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/3.png" width="100%" height="100%"><br>

### 4 - Click “Add Rule” to begin editing Inbound rules to specify what kind of connection can be made to the security group:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/4.png" width="100%" height="100%"><br>

### 5 - Set the details as shown with a description which indicates “SSH from Home”:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/5.png" width="100%" height="100%"><br>

### 6 - Click “Add Rule” again to create another inbound rule with a description of “HTTP from Home”:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/6.png" width="100%" height="100%"><br>

### 7 - Once complete, both inbound should have the same source of “Anywhere-IP-v4” and look like this:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/7.png" width="100%" height="100%"><br>

### 8 - DO NOT touch the Outbound rules in any way. Leave them as they are:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/8.png" width="100%" height="100%"><br>

### 9 - Click on “Add new tag” to create a label for your Security Group:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/9.png" width="100%" height="100%"><br>

### 10 - Set your Key and Value and then click “Create security group”:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/10.png" width="100%" height="100%"><br>

### 11 - Congratulations. You have successfully created your security group. You can scroll down to see the inbound rules and also click on tags to see what you created earlier.

To confirm that you have created one, click on the red boxed test to navigate to the “Security groups” page:
<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/11.png" width="100%" height="100%"><br>

### 12 - As shown, the security group called “MyFirstSecurityGroup” has been created:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/12.png" width="100%" height="100%"><br>

## Tear down or delete your Security Group

### 13 - To delete your security group, select the checkbox as shown, click on “Actions” and the click on “Delete security groups”:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/13.png" width="100%" height="100%"><br>

### 14 - On Popup window, confirm that you’re not deleting the default security group and then click on “delete”:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/14.png" width="100%" height="100%"><br>

### 15 - Once the green bar appears in confirming that your security group was deleted, click on the refresh button to confirm once more that “MyFirstSecurityGroup” has been deleted and is no longer visible:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/15.png" width="100%" height="100%"><br>

### 16 - As can be seen below, the only security group resource remaining is our default which we DO NOT delete:<br>

<img src="https://github.com/the5barbarians/AWS_Click_Ops/blob/security_group_supporting_docs/16.png" width="100%" height="100%"><br>

<br>
That is how you create and delete a security group.

## Additional resources

More about [Security Groups](https://docs.aws.amazon.com/managedservices/latest/userguide/about-security-groups.html)
