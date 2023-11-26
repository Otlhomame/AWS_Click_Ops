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

<img src="https://raw.githubusercontent.com/mindmotivate/multicloudclass/gh-pages-vpc/fullcreatevpcscreen.png" width="100%" height="100%"><br>

### 2 - Click on “Create Security Group” as indicated: <br>
