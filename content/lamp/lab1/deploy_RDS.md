+++
title = "1.4 - Deploy the RDS db"
weight = 40
+++ 

Finally, you're going to deploy an Amazon Relational Database Service (RDS) database. Amazon RDS is a hosted database services that offers more advanced features than Lightsail databases (multiple database engines, more instances sizes, read replicas, etc). As your application requirements change, you may find that you need to move from an Amazon Lightsail database to Amazon RDS. Later in this workshop, you'll do just that: migrate your existing Amazon Lightsail database to Amazon RDS. 



* Navigate to the <a href="https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2#GettingStarted:" target="_blank">Amazon RDS getting started page</a> 

{{% notice tip %}}
The link above redirects to the US West 2 AWS region. Ensure that you're deploying your RDS database into the same region as you deployed your Lightsail resources. 
{{% /notice %}} 

* Select ***Create database*** from the card on the right. 

    ![](../../images/rds_create_database.jpg?classes=border)

* Under ***Engine options*** choose ***MySQL*** for the engine type and ***5.7.26*** for the version

    ![](../../images/engine_options.jpg?classes=border)

* Scroll down and choose ***Free tier*** under ***Templates***

    ![](../../images/rds_template.jpg?classes=border)

* Scroll down to ***Credential settings*** and enter ***dbmasteruser*** under Master username and then for the Master password and Confirm password parameters enter ***taskstasks***

    ![](../../images/credential_settings.png?classes=border)

{{% notice %}}
You want to make sure that your username and password for the RDS instance match the values you used for your Lightsail database. 
{{% /notice %}}

* Scroll down to ***Connectivity*** and make sure the default VPC is selected. If you do not have a default VPC, you will need to create one. 

    ![](../../images/default_vpc.png?classes=border)

* Scroll to the bottom of the screen and click ***Create database***

{{% notice tip %}}
It will take several minutes for the creation process to complete, so feel free to move on to the next step while this happens. You'll come back to the Amazon RDS database in Lab #5.
{{% /notice %}} 

    