# Application Layer

## Overview

The application layer handled the student registration functionality of the project.

A PHP-based student registration application was hosted on the Amazon EC2 instance.

The application accepted student details through a registration form and processed the submitted data before storing it in the Amazon RDS MySQL database.

## Application Flow

The application followed this flow:

```text
User
  ↓
Student Registration Form
  ↓
PHP Application Logic
  ↓
Amazon RDS MySQL
  ↓
Student Registration Data
```

## Application Components

### Student Registration Form

The application provided a form through which users could enter student registration details.

### PHP Application Logic

PHP was used to process the submitted registration data and establish a connection with the MySQL database hosted on Amazon RDS.

### Database Connection

The PHP application used the Amazon RDS MySQL endpoint to connect to the database.

MySQL communication used port:

`3306`

## Deployment

The application was hosted on an Amazon EC2 instance inside the AWS VPC.

The EC2 instance was located in the public subnet so that users could access the application through its public IP address.

The database was hosted separately on Amazon RDS in the private part of the VPC.

## Data Flow

1. User opens the application using the EC2 public IP.
2. User enters student registration details.
3. The PHP application receives the submitted information.
4. PHP establishes a connection with Amazon RDS MySQL.
5. The registration data is inserted into the database.
6. The application returns the result to the user.

## Security

The database was not directly exposed to the internet.

Access to the MySQL database was controlled using an RDS Security Group, with MySQL traffic allowed on port `3306` from the appropriate application/EC2 source.

## Project Limitation

The original application files were created and tested during the project implementation but are no longer available because the EC2 environment was deleted.

Therefore, this repository focuses on documenting the architecture, AWS infrastructure, database design, networking, and implementation approach rather than providing the original application source code.

## Key Learning

This project helped me understand:

* Hosting an application on Amazon EC2
* Connecting a PHP application to Amazon RDS MySQL
* Public and private subnet concepts
* AWS Security Groups
* Database connectivity
* Basic three-tier application architecture
* Separating application and database responsibilities
