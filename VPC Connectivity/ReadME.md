# Testing VPC Connectivity

![Image](https://github.com/dev-boris67/AWS-Basics/blob/main/Project%20images/8.png?raw=true).

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-connectivity)

**Author:** Nchindo Boris  
**Email:** nchindoboris37@gmail.com

---

## Testing VPC Connectivity

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-connectivity_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that lets you create a private, isolated network inside AWS, where you can launch and manage your cloud resources

### How I used Amazon VPC in this project

I used Amazon VPC in today's project to test connectivity of resources within a VPC

### One thing I didn't expect in this project was...

In this project I did expect that connectivity in networks will be this interesting

### This project took me...

this project took me 45 minutes to complete

---

## Connecting to an EC2 Instance

Connectivity means how well different parts of your network talk to each other and with external networks.

My first connectivity test was whether I could connect to the public server

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-connectivity_88727bef)

---

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, which is a browser-based way to securely connect to your Amazon EC2 instances using SSH without needing to manage a private key file

My first attempt at getting direct access to my public server resulted in an error, because;
The security group associated with NextWork Public Server lets in all inbound HTTP traffic, but We're trying to access NextWork Public Server using SSH 

I fixed this error by updating NextWork Public Server's security group rules so it can let in SSH traffic 

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-connectivity_1cbb1b88)

---

## Connectivity Between Servers

Ping isa common computer network tool used to check communication between devices on a network. I used ping to test the connectivity between my server  and NextWork Private Server, sending a small packet of data to that and asking for a response

The ping command I ran was ping 10.0.1.104

The first ping returned PING 10.0.1.104 (10.0.1.104) 56(84) bytes of data. This meant that your Public Server has sent out a ping message... and that's about it. No reply 

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-connectivity_defghijk)

---

## Troubleshooting Connectivity

I troubleshooted this by editing the inbound and outbound rules of the private subnet NACLs and security groups

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-connectivity_4a9e8014)

---

## Connectivity to the Internet

Curl is a tool to test connectivity in a network. 

I used curl to test the connectivity between my public server and the internet

### Ping vs Curl

Ping and curl are different because ping checks if one computer can contact another while curl is used to transfer data to or from a server.

---

## Connectivity to the Internet

I ran the curl command curl https://learn.nextwork.org/projects/aws-host-a-website-on-s3  which returned the complete HTML content of NextWork's web app 

![Image](http://learn.nextwork.org/soothed_rose_serene_peach/uploads/aws-networks-connectivity_8ee57662)

---

---

