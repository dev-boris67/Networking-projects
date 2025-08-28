# VPC Peering

![Image](https://github.com/dev-boris67/AWS-Basics/blob/main/Project%20images/9.png?raw=true).

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-peering)

**Author:** Nchindo Boris  
**Email:** nchindoboris37@gmail.com

---

## VPC Peering

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-peering_88727bef)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a foundational AWS service that lets you create a private, isolated network environment within the cloud

### How I used Amazon VPC in this project

I used Amazon VPC in this project to test VPC Peering



### One thing I didn't expect in this project was...

I did not expect that this project wil be this easy  to do

### This project took me...

It took me 45 minutes to complete this project

---

## In the first part of my project...

### Step 1 - Set up my VPC

In this step I will;
-Create two VPCs from scratch!
- Use the visual VPC resource map to create your VPCs supa fast 

### Step 2 - Create a Peering Connection

In this step I will set up a connection link between my VPCs.

### Step 3 - Update Route Tables

In this step I will;
- Set up a way for traffic coming from VPC 1 to get to VPC 2.
- Set up a way for traffic coming from VPC 2 to get to VPC 1.

### Step 4 - Launch EC2 Instances

In this step I will launch an EC2 instance in each VPC, so we can use them to test your VPC peering connection later.



---

## Multi-VPC Architecture

I started my project by launching 2 VPCs. I also created 2 public subnets

The CIDR blocks for VPCs 1 and 2 are  10.1.0.0/16 and 10.2.0.0/16. They have to be unique so the IP addresses of their resources don't overlap. Having overlapping IP addresses could cause routing conflicts and connectivity issues!

### I also launched 2 EC2 instances

'I didn't set up key pairs for these EC2 instances as   we've already learnt how to set up key pairs twice in the last two projects, we don't need to do it again this time. .

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-peering_11111111)

---

## VPC Peering

A VPC peering connection is a direct connection between two VPCs.

VPCs would use peering connections to route traffic between them using their private IP addresses. This means data can now be transferred between VPCs without going through the public internet.

The difference between a Requester and an Accepter in a peering connection is the Requester is the VPC that initiates a peering connection while the Accepter is the VPC that receives a peering connection request!

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-peering_1cbb1b88)

---

## Updating route tables

After accepting a peering connection, my VPCs' route tables need to be updated because even if your peering connection has been accepted, traffic in VPC 1 won't know how to get to resources in VPC 2 without a route in your route table

My VPCs' new routes have a destination of 10.1.0.0/16 and 10.2.0.0/16 The routes' target was peering connection

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-peering_4a9e8014)

---

## In the second part of my project...

### Step 5 - Use EC2 Instance Connect

In this step I will;
- Use EC2 Instance Connect to connect to your first EC2 instance.
- Fix a connection error!

### Step 6 - Connect to EC2 Instance 1

In this step I will;
- Use EC2 Instance Connect to connect to Instance 1 (one more time)!
- Fix (another) error.

### Step 7 - Test VPC Peering

In this step I will;
- Get Instance 1 to send test messages to Instance 2.
- Solve connection errors until Instance 2 is able to send messages back.

---

## Troubleshooting Instance Connect

Next, I used EC2 Instance Connect to access your Amazon EC2 instances without needing to manage SSH key files. It’s especially useful for quick, temporary, and secure access to Linux instances.

I was stopped from using EC2 Instance Connect as I kept Disable for the Auto-assign IP address option in my EC2 instance's network settings 

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-peering_7685490c)

---

## Elastic IP addresses

To resolve this error, I set up Elastic IP addresses. Elastic IP addresses are static IPv4 addresses that get allocated to your AWS account, and is mine to delegate to an EC2 instance.

Associating an Elastic IP address resolved the error because Elastic IPs are also a great way to assign an instance a public IPv4 address after launching it! 

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-peering_45663498)

---

## Troubleshooting ping issues

To test VPC peering, I ran the command ping 10.2.4.226

A successful ping test would validate my VPC peering connection by checking if instances in two different VPCs can communicate across the peering connection using their private IPs.

I had to update my second EC2 instance's security group because... I added a new rule that allows Inbound and outbound ICMP traffic

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-peering_7a29d352)

---

---
