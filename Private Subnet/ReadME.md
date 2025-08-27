# Creating a Private Subnet

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-private)

**Author:** Nchindo Boris  
**Email:** nchindoboris37@gmail.com

---

## Creating a Private Subnet

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-private_afe1fdbd)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon Virtual Private is a service that lets you create your own private, isolated network within the cloud. It is useful to controll internet access

### How I used Amazon VPC in this project

Amazon VPC was used in today's project to create;
Private subnets
Routing
Security (via security groups and NACLs)
Internet access (via gateways)

### One thing I didn't expect in this project was...

I did not expect that this project will be this easy

### This project took me...

It took me 1hr to complete this project

---

## Private vs Public Subnets

The difference between public and private subnets internet access.
Public Subnet has direct internet access while 
Private Subnet does not have direct internet access

Having private subnets are useful because improve security, control, and architectural design in cloud environments. This protects sensitive data

My private and public subnets cannot have the same Internet Gateway and route table

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-private_afe1fdbd)

---

## A dedicated route table

By default, my private subnet is associated with the VPC's main route table

I had to set up a new route table because I want to control routing separately from public subnets and keep the Private Subnet Isolated From the Internet

My private subnet's dedicated route table only has one inbound and one outbound rule that allows Local Traffic Inside the VPC and No Internet Access by Default

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-private_b4b904b5)

---

## A new network ACL

By default, my private subnet is associated with default network ACL of the VPC

I set up a dedicated network ACL for my private subnet because it will restrict traffic and protect my private subnet

My new network ACL has two simple rules; All inbound and outbound  traffic is denied

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-private_1ed2cb07)

---

---
