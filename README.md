# AWS Three-Tier Student Registration Application

## 📌 Project Overview

This project demonstrates the deployment of a student registration application on AWS using a multi-tier architecture.

The application is hosted on Amazon EC2 using Apache Tomcat, while student registration data is stored in an Amazon RDS MySQL database.

The infrastructure is deployed inside a custom Amazon VPC with separate public and private subnets. Security Groups are used to control communication between the application and database components.

The application can be accessed through the public IP address of the EC2 instance, and submitted student registration data is stored in the RDS MySQL database.

## 🏗️ Architecture

`
                         Internet
                            │
                            ▼
                    Public EC2 Instance
                            │
                     Apache Tomcat
                            │
                            │ MySQL : 3306
                            ▼
                    Private Subnet
                            │
                            ▼
                       RDS MySQL
                            │
                            ▼
                  Student Registration Data


The project uses:

* 2 EC2 instances
* 1 public subnet
* 1 private subnet
* Apache Tomcat
* Amazon RDS MySQL
* Security Groups
* Amazon VPC

---

 ☁️ AWS Services Used

| AWS Service      | Purpose                                             |
| ---------------- | --------------------------------------------------- |
| Amazon VPC       | Provides the isolated network environment           |
| Amazon EC2       | Hosts the application and supporting infrastructure |
| Apache Tomcat    | Hosts the student registration application          |
| Amazon RDS MySQL | Stores student registration data                    |
| Security Groups  | Controls network traffic between resources          |
| Subnets          | Separates public and private resources              |
| Internet Gateway | Provides internet connectivity to the public subnet |

---

## 🔄 Application Flow

User
 │
 │ HTTP Request
 ▼
EC2 Public IP
 │
 ▼
Apache Tomcat
 │
 │ Database Connection
 │ TCP 3306
 ▼
RDS MySQL
 │
 │ Insert / Retrieve Data
 ▼
Student Registration Database

When a user submits the registration form:

1. The request reaches the EC2 instance through its public IP.
2. Apache Tomcat processes the application request.
3. The application connects to the RDS MySQL database.
4. Student information is inserted into the database.
5. The application returns the response to the user.

 Network Architecture

The infrastructure is deployed inside an Amazon VPC.

### Public Subnet

The public subnet contains the EC2 instance used to provide access to the application.

The instance has public connectivity through the Internet Gateway.

### Private Subnet

The private subnet contains the database layer.

Amazon RDS MySQL is deployed in the private network so that the database is not directly exposed to the internet.

---

# Security Configuration

AWS Security Groups are used to control traffic between the EC2 application server and the RDS database.

The application server communicates with MySQL using:

Protocol: TCP
Port: 3306

 The database access is restricted through Security Group rules rather than allowing unrestricted internet access.

### Security Flow

text
EC2 Security Group
        │
        │ TCP 3306
        ▼
RDS Security Group

This allows the application to communicate with the database while keeping the database layer private.

--

# Application Deployment

The student registration application is deployed on an EC2 instance using Apache Tomcat.

The application is accessed through the EC2 public IP address.

Example:

http://<EC2-PUBLIC-IP>:<APPLICATION-PORT>

---

# Database

Amazon RDS for MySQL is used as the database service.

The RDS database stores the student registration information submitted through the application.

The application connects to the RDS database using its database endpoint.

The database is located in the private subnet and is not directly exposed to the public internet.

--

# Application Testing

The application was tested by:

1. Accessing the application through the EC2 public IP.
2. Opening the student registration form.
3. Entering student information.
4. Submitting the registration form.
5. Verifying that the data was successfully inserted into the RDS MySQL database.

--

# Technologies Used

## Cloud

* AWS
* Amazon VPC
* Amazon EC2
* Amazon RDS

## Application

* Apache Tomcat
* Java
* MySQL

## Networking & Security

* Public Subnet
* Private Subnet
* Internet Gateway
* Security Groups
* TCP/IP

---

## Challenges & Troubleshooting

During the implementation of this project, I worked on:

* Creating and configuring a custom VPC
* Configuring public and private subnets
* Deploying the application on EC2
* Installing and configuring Apache Tomcat
* Deploying the application
* Connecting the application to RDS MySQL
* Configuring Security Group rules
* Troubleshooting MySQL connectivity on port 3306
* Verifying successful data insertion into RDS

--

##  Screenshots

Screenshots demonstrating the implementation will be added to the  screenshots/ directory.

Examples include:

* VPC configuration
* Subnet configuration
* EC2 instances
* Security Groups
* RDS configuration
* Running application
* Registered student data

---

## 🎯 Key Learning Outcomes

Through this project, I gained practical experience in:

* AWS VPC networking
* EC2 deployment
* Public and private subnet configuration
* Apache Tomcat application deployment
* Amazon RDS MySQL
* Security Group configuration
* EC2-to-RDS connectivity
* Database connectivity troubleshooting
* Deploying and testing a real web application on AWS

---

# Author

Sri Harsha Akula

Cloud & DevOps Engineer Aspirant

Skills:AWS | Linux | Docker | Jenkins | Ansible | Git | CI/CD | Bash

--

