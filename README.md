## Highly available IaC using cloudformation
This repo contains the yaml files required to launch highly available infrastructure readily into your account
1. Network: a VPC with four subnets each 2 are in a single Availability Zone. one is public and one is private and two NAT gateways in each public subnet. the file also creates all the necessary route tables and associations needed

2. Servers: this file launches an autoscaling group that deploys a minimum of 4 instances each two in a single private subnet. and a public load balancer that forwards HTTP traffic to those two servers. as well as a bastion host in a public subnet to access the webservers on port 22 via SSH


### Dependencies
##### 1. AWS account
You would require to have an AWS account to run the scripts

##### 2. a programmatic access key
You need to have your CLI configured on your machine


### How to use
Simply run ./create.bat or ./update.bat with the following arguments:
1- Name of stack you want -could be anything-
2- destination to either network or server files located under /src/
3- params.json file in the same directory