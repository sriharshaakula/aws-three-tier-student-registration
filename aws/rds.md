# Amazon RDS Configuration

## Overview

Amazon RDS for MySQL was used as the database tier of the student registration application.

RDS provided a managed MySQL database for storing student registration data.

## RDS Role

The RDS database was responsible for:

- Storing student registration details
- Managing MySQL database operations
- Providing database connectivity to the EC2 application
- Maintaining the database separately from the application server

## Network Placement

The RDS database was deployed in the private part of the VPC.

The database was not directly accessible from the public internet.

The application running on EC2 communicated with the RDS database through the VPC network.

## Database Connection

The PHP application running on EC2 connected to the RDS MySQL endpoint.

MySQL uses port:

`3306`

The RDS endpoint was used by the application to establish the database connection.

## Data Flow

User
↓
EC2 / PHP Application
↓
RDS MySQL
↓
Student Registration Data

When a student submitted the registration form, the application processed the request and stored the data in the RDS MySQL database.

## Security

The RDS Security Group controlled access to the database.

MySQL traffic on port `3306` was allowed only from the appropriate application/EC2 source.

The database was therefore separated from direct public access.

## Key Learning

This project helped me understand how Amazon RDS can be used as a managed database service and how an application hosted on EC2 can securely communicate with a private MySQL database.
