# Database Layer

## Overview

Amazon RDS for MySQL was used as the database layer of the student registration application.

The database stored the student information submitted through the PHP application running on the EC2 instance.

## Database Architecture

```text
User
  ↓
EC2 / PHP Application
  ↓
RDS MySQL
  ↓
Student Registration Data
```

## Amazon RDS

Amazon RDS was selected to provide a managed MySQL database service.

The application connected to the RDS database using its database endpoint.

### Database Technology

* Database Engine: MySQL
* AWS Service: Amazon RDS
* Port: `3306`

## Database Connectivity

The PHP application running on EC2 established a connection to the RDS MySQL database.

The connection required the RDS endpoint, database credentials, database name, and MySQL port.

Credentials and sensitive connection information are not stored in this repository.

## Network Security

The RDS database was placed in the private part of the VPC.

The RDS Security Group controlled access to the database.

MySQL traffic on port `3306` was allowed from the appropriate EC2/application source.

This prevented unrestricted public access to the database.

## Data Storage

Student registration information submitted through the application was stored in the MySQL database.

The application successfully inserted registration data into the RDS database during testing.

## Key Learning

This project helped me understand:

* Amazon RDS
* MySQL database connectivity
* RDS endpoints
* MySQL port `3306`
* Private database networking
* Security Groups
* EC2-to-RDS communication
* Managed database services in AWS
