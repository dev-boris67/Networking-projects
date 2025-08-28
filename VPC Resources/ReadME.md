# Launching VPC Resources

![Image](https://github.com/dev-boris67/AWS-Basics/blob/main/Project%20images/7.png?raw=true).

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-ec2)

**Author:** Nchindo Boris  
**Email:** nchindoboris37@gmail.com

---

## Launching VPC Resources

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-ec2_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a service that lets you create a private, isolated network in the cloud

### How I used Amazon VPC in this project

I used Amazon VPC in today's project to;
- Define your own IP address ranges
- Create public and private subnets
- Set up routing, firewalls, and security rules

### One thing I didn't expect in this project was...

It was an allround easy project

### This project took me...

This project took me 1hr to complete

---

## Setting Up Direct VM Access

Directly accessing a virtual machine means logging into and managing the operating system or software of the machine as if you were using it in front of you, but over the internet.

### SSH is a key method for directly accessing a VM

SSH traffic means Secure Shell. It is the protocol we use for this secure access to a remote machine.

### To enable direct access, I set up key pairs

Key pairs are sets of two cryptographic keys; a public key and a private key, used to securely access your EC2 instances.

A private key's file format means Privacy-Enhanced Mail. My private key's file format was .pem

---

## Launching a public server

I had to change my EC2 instance's networking settings by launching this instance in NextWork VPC and the NextWork Public Subnet!

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-ec2_88727bef)

---

## Launching a private server

My private server has its own dedicated security group because Private servers  should be only accessible from trusted sources inside my VPC to avoid security problems

My private server's security group's source is NextWork Public Security Group. which means only resources that are part of the NextWork Public Security Group can communicate with your instance.

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-ec2_4a9e8014)

---

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I went back to your VPC console > select Your VPCs > Select Create VPC > select VPC and more.
Did some relevant configurations and launched the new VPC

A VPC resource map is basically a visual or documented overview of all the key components inside your Amazon VPC and how they relate or connect to each other.

New VPC CIDR block is 10.0.0.0/16. It is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because VPCs are isolated from each other by default, so there are no IP conflicts unless you explicitly connect them using peering

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-ec2_1cbb1b88)

---

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options This was because the VPC wizard limits you to two public subnets to keep things straightforward. 

The set up page also offered to create NAT gateways, which are an AWS-managed service that allows instances in a private subnet to connect to the internet, without exposing them to inbound internet traffic.

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-ec2_8ee57662)

---

---
