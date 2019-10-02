+++
title = "5.1 - Configure RDS"
weight = 35
+++

# Enable VPC Peering

In order for Lightsail resources to communicate with other AWS resources, you need to enable VPC peering between Lightsail and the default AWS VPC for the same region as your Lightsail resources. Note that Lightsail can only peer with the default AWS VPC. 

*  Return to the <a href="https://lightsail.aws.amazon.com/ls/webapp/home/" target="_blank">Lightsail console home page</a> and click ***Account*** in the top right corner. Choose ***Account*** from the pop out menu.

![](../../images/account_menu.png?classes=border)

* Click on ***Advanced*** from the horizontal menu

* Under VPC peering ensure the ***Enable VPC peering*** box is checked **for the region where your application is deployed**. 

![](../../images/enable_vpc_peering.png?classes=border)

# Edit RDS Security Group

The next step is to edit the security group for the RDS instance to allow traffic from the Lightsail subnet

* Return to the <a href="https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2" target="_blank">RDS console home page</a> (this link goes to the US West 2 region, if you've deployed your resouces into a differnt region, you'll need to move into that region)

* Under ***Resources*** click on ***DB Instances*** 

![](../../images/rds_resources.png?classes=border)

* Click on the name of the database you created at the beginning of the workshop

* Under ***Connectivity and security*** click on the security group name

![](../../images/rds_sg.png?classes=border)

* Click the ***Inbound*** tab near the bottom of the screen

![](../../images/inbound.png?classes=border)

* Click the ***Edit*** button

![](../../images/sg_edit.png?classes=border)

* Click ***Add rule*** in the pop up box

* From the ***Type*** drop down choose ***MySQL/Aurora*** 

* In the source box enter ***172.26.0.0/16*** (this is the CIDR address for the Lightsail subnet)

![](../../images/sg_values.png?classes=border)

* Click ***Save***

* Return to the RDS console entry for your RDS database

* Under ***Connectivity and security*** copy the ***Endpoint*** value 

![](../../images/rds_endpoint.png?classes=border)

The final step is to edit the application settings to point to the RDS endpoint. You will do this on a new application instance that you will create from the snapshot earlier. 

* Return to the Lightsail home page and click on ***Snapshots*** from the horizontal menu

* Click ***>*** under the instance name

![](../../images/snapshot_carat.png?classes=border)

* Click the three-dot menu to the right of the snapshot name and choose ***Create new instance***

* Scroll down and name the instance ***php-fe-rds***

* Click ***Create instance*** at the bottom of the screen

Once the ***php-fe-rds*** instance is up and running point your web browser to the instance's IP address. The todo application should load up. 

* From the todo application menu click on ***Settings***

* Under ***DB Hostname*** paste in the endpoint value for the RDS instance

* Click ***Save Settings***

* Click ***List Tasks*** from the application menu. Notice there are no tasks because the RDS database is empty. Also note that the ***Database host*** variable at the bottom of the screen lists the endpoint for the RDS instance. 

The Lightsail front-end is now communicating with the RDS database. In the final lab you will export the front-end from Lightsail to EC2. 

