+++
title = "Lab #6: Migrating to EC2"
weight = 100
+++

### Using RDS

Just like there might be a case where you need to move your database to RDS, there could also be a case where you might need to migrate your Lightsail instances to EC2. 

In this final lab you're going to export the Lightsail instance you created in Lab 5 (php-fe-rds) to EC2, and ensure it can communicate with the RDS database. 

At the end of this section you're architecture will look like this:

![](../../images/ec2_rds.png?classes=border)