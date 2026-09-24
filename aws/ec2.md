# EC2 Configuration

## Overview

Amazon EC2 was used as the application server for the student registration application.

The EC2 instance hosted the PHP application and provided the public endpoint through which users accessed the application.

## EC2 Role

The EC2 instance was responsible for:

- Hosting the PHP application
- Processing student registration requests
- Connecting to the Amazon RDS MySQL database
- Receiving requests through the EC2 public IP

## Network Placement

The EC2 instance was deployed inside the VPC in a public subnet.

This allowed the application to be accessed from the internet using the instance's public IP address.

## Application Flow

1. User accesses the application using the EC2 public IP.
2. The PHP application receives the registration request.
3. The application connects to Amazon RDS MySQL.
4. Student registration data is inserted into the database.
5. The application returns the result to the user.

## Security

Security Groups were used to control inbound and outbound traffic to the EC2 instance.

Only the required ports were opened for application access and administration.

The database connection used MySQL port `3306`.

## EC2 and RDS Communication

The EC2 instance communicated with the RDS database through the VPC private network.

The RDS database was not directly exposed to the internet.

## Key Learning

This project helped me understand how an EC2 instance can be used as an application server and how it can securely communicate with a database hosted in Amazon RDS.
