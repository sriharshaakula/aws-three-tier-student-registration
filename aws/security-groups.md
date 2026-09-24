# Security Groups Configuration

## Overview

Security Groups were used to control network traffic to the EC2 instance and Amazon RDS MySQL database.

They act as virtual firewalls that control inbound and outbound traffic at the instance level.

## EC2 Security Group

The EC2 Security Group controlled traffic reaching the application server.

The required ports were allowed for:

- Application access
- SSH administration

The application was accessed through the EC2 public IP.

## RDS Security Group

The RDS Security Group controlled access to the MySQL database.

MySQL traffic was configured on:

`TCP 3306`

Database access was restricted to the application/EC2 source instead of allowing unrestricted public access.

## EC2 to RDS Communication

The communication flow was:

EC2 Instance
↓
RDS Security Group
↓
MySQL Port 3306
↓
RDS MySQL Database

This allowed the application to communicate with the database while keeping the database separated from direct internet access.

## Security Principle

The project followed the principle of allowing only the required network communication between application and database components.

The database was not intended to be directly exposed to the public internet.

## Key Learning

This project helped me understand:

- How AWS Security Groups work
- Inbound and outbound rules
- TCP ports
- MySQL port 3306
- EC2-to-RDS communication
- Basic network security in AWS
