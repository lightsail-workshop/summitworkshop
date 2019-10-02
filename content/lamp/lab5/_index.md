+++
title = "Lab #5: Use RDS"
weight = 90
+++

### Using RDS

There may reach a point where you find that one of Lightsail's services doesn't meant your needs, and you'll want to use another AWS service instead. 

In this lab you're going to replace the Lightsail database with an RDS database. You'll need to enable VPC peering in Lightsail, add the Lightsail subnet to the RDS security group, and then update the application to use the RDS database. 

![](../../images/rds_diagram.png?classes=border)