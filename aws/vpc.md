# VPC Configuration

## Overview

The application was deployed inside an Amazon VPC to provide network isolation and control communication between the application and database components.

## Network Architecture

The VPC contained:

- One public subnet
- One private subnet
- Internet Gateway
- Route tables
- EC2 instance
- Amazon RDS MySQL database

## Public Subnet

The EC2 instance was placed in the public subnet.

The public subnet allowed the EC2 instance to be accessed from the internet using its public IP address.

The application was accessed through the EC2 public IP.

## Private Subnet

The Amazon RDS MySQL database was placed in the private subnet.

The database was not directly exposed to the internet.

The application running on EC2 communicated with RDS through the VPC network.

## Communication Flow

User
↓
EC2 Instance (Public Subnet)
↓
RDS MySQL (Private Subnet)

The EC2 instance handled the application requests, while RDS stored the student registration data.

## Security

Security Groups were used to control network traffic.

The database security group allowed MySQL traffic on port `3306` from the application/EC2 security group.

This prevented direct database access from the public internet.

## Key AWS Services

- Amazon VPC
- Amazon EC2
- Amazon RDS
- Internet Gateway
- Route Tables
- Security Groups

## Key Learning

This project helped me understand how public and private subnets can be used to separate an application server from a database and how AWS networking and security groups control communication between them.
