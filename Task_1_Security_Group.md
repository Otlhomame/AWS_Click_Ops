# Create A Security Group  

Written by [Otlhomame](https://github.com/Otlhomame)



## About Security Groups! <a name="about"></a>

Imagine you were a security officer of a building of multiple floors and offices and your duty was to perform a lock up and periodic patrols for the night for every room. This would include accessing each office to inspect the window locks to confirm that everything is secure and no intrusion had happened. Every office door has a unique key which must be used to access an office. One particular advantage of this security control setup is that it offers a layer of security at an office level to protect each office by its unique key.

AWS security groups work in a similar way to offer instance level protection for different aws resources within the cloud. They are a virtual firewall service by AWS which protects what internet connections can reach EC2 instances within your private computing network. Apart from other network traffic control services like Network access controls, NAT and internet gateways, security groups can be used to control whether a website can be accessed and how it could be accessed. On AWS, a cloud administrator could manually set which internet protocol can be used to access a web page by attaching the virtual machine instance hosting that website to a security group. This gives granular control over how exposed your website is to the internet.

## Why use security groups in practice?

Permission management:
 
In an infrastructural configuration, an administrator may choose to make decoupled services which require different security permissions for other services to access them. By default, if one creates an EC2 machine without a security group, the default security group wll be used. The shortfall of this approach is that if you have more than one resource which requires different methods of instance level protection, you may not be able to have a one size fits all security group configuration. Classically, public files and private files cannot share the same security permissions if that is what the website design requires. The ability to have multiple security groups enables the architect team to separate software services by instance gives access permission control for software services.

## Common Cloud Mistakes Corrected By Proper Security Group Usage

In a concise article by [corestack](https://www.corestack.io/aws-security-best-practices/aws-security-group-best-practices/), the table below indicates the best practices for using security groups everyday in the cloud configuration environment.
