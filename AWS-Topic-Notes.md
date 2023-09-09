# Real Time Production AWS Project - Deploy Application
- VPC
- EC2
- Public Subnet
- Private Subnet
- Security Groups
- Load Banalcer
# Overview 
```
To improve resiliency, we deploy the servers in 2 availablility zones by using Auto Scaling Group and AWS Application Load Balancer. To provide additional security application/servers will be 
deployed in private sub-nets of VPC. Server would receive request via Load Balancer and NAT gateway is used to connect servers to Internet. NAT gateway is deployed in both zones.
```
# TWO availablity zones: 
- If 1 of the zones faces any issues, we don't want our traffic to servers/application to stop.
# Load Balancer: 
- It balances the traffic between no of servers configured on availablity zones.
# NAT Gateway: 
- A application/server deployed in private sub-net and if they need to connect with internet to get some info like json, connect with other api's available. We would want to
hide the IP address of server/application. NAT Gateway helps to hide the private IP of sub-net by mapping it to public IP provided by NAT for internet access.
# Auto Scaling Group: 
- We have deployed our application in 2 availability zones, the incoming traffic on application is not manageable by 2 servers then we can define Auto Scaling Group to
handle situation. ASG would check and provide additional servers to handle the heavy traffic and would not allow appication to fail.
# Bastion Host: 
A bastion host is a server used to manage access to an internal or private network from an external network - sometimes called a jump box or jump server.
