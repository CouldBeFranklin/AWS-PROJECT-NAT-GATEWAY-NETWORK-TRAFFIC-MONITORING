# AWS PROJECT: NAT GATEWAY NETWORK TRAFFIC MONITORING


## MONITORING PRIVATE SUBNET EGRESS TRAFFIC THROUGH NAT GATEWAY USING VPC FLOW LOGS AND AMAZON CLOUDWATCH



## INTRODUCTION

In this project, I implemented network traffic monitoring for a NAT Gateway in AWS using VPC Flow Logs and Amazon CloudWatch. This project was carried out in an environment where a default VPC already existed, containing only public subnets across multiple Availability Zones.
The project involves extending the existing default VPC by introducing a private subnet, configuring proper routing through a NAT Gateway, and then monitoring the resulting network traffic.
This approach closely mirrors real-world cloud environments, where engineers often have to adapt and secure existing infrastructure rather than build from scratch.



## PROJECT OBJECTIVES

- Extend an existing default VPC to support private networking
-	Create a private subnet with no direct internet access
-	Route private subnet outbound traffic through a NAT Gateway
-	Capture NAT Gateway traffic using VPC Flow Logs
-	Store and analyze flow logs in Amazon CloudWatch




# <p align = "center"> STEPS INVOLVED




## STEP 1 - CREATING A PRIVATE SUBNET IN THE EXISTING VPC


-	Since the Existing VPC only contained public subnets, the first task was to create a new private subnet.
-	I created a new subnet within the default VPC
-	Selected a non-overlapping CIDR block within the default VPC address range
-	Disabled auto-assignment of public IPv4 addresses for the subnet this ensured that resources launched in this subnet would not have direct internet access.
-	I then edited the route table association of the subnet, removing its route to the internet gateway (IGW).
