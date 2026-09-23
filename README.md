# AWS Three-Tier Student Registration Application

## 📌 Project Overview

This project demonstrates the deployment of a student registration application on AWS using a three-tier application architecture.

The application is divided into three logical tiers:

1. **Presentation Tier** – Student registration form
2. **Application Tier** – Backend business logic running on Apache Tomcat
3. **Database Tier** – Amazon RDS MySQL

The application is deployed inside a custom Amazon VPC. The EC2 instance hosting the application is placed in a public subnet, while the RDS MySQL database is placed in a private subnet.

Users access the application through the EC2 public IP. The backend processes the registration request and communicates with the RDS MySQL database to store student information.

---

## 🏗️ Architecture


                         USER
                           │
                           │ HTTP
                           ▼
                ┌─────────────────────┐
                │  PRESENTATION TIER  │
                │                     │
                │ Student Registration│
                │       Form          │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │  APPLICATION TIER   │
                │                     │
                │ EC2 + Apache Tomcat │
                │ Backend Logic       │
                └──────────┬──────────┘
                           │
                           │ MySQL / TCP 3306
                           ▼
                ┌─────────────────────┐
                │    DATABASE TIER    │
                │                     │
                │    RDS MySQL        │
                │    Private Subnet   │
                └─────────────────────┘


### AWS Infrastructure


                         Internet
                            │
                            ▼
                    ┌───────────────┐
                    │  Public Subnet│
                    │               │
                    │  EC2 Instance │
                    │  Apache Tomcat│
                    └───────┬───────┘
                            │
                       TCP 3306
                            │
                            ▼
                    ┌───────────────┐
                    │ Private Subnet│
                    │               │
                    │   RDS MySQL   │
                    └───────────────┘


> The three tiers are logical application layers. The presentation and application tiers run on the same EC2 instance, while the database tier is provided by Amazon RDS.

---

## ☁️ AWS Services Used

| Service              | Purpose                                             |
| -------------------- | --------------------------------------------------- |
| **Amazon VPC**       | Provides the isolated network environment           |
| **Amazon EC2**       | Hosts the application and backend                   |
| **Apache Tomcat**    | Runs the backend/application                        |
| **Amazon RDS MySQL** | Stores student registration data                    |
| **Security Groups**  | Controls network access between resources           |
| **Subnets**          | Separates public and private resources              |
| **Internet Gateway** | Provides internet connectivity to the public subnet |

---

## 🔄 Application Flow

The application works through the following flow:


User
  │
  ▼
Registration Form
  │
  ▼
Backend Logic
  │
  ▼
RDS MySQL
  │
  ▼
Student Data Stored

### Step-by-step

1. The user opens the student registration application.
2. The registration form collects student information.
3. The form sends the submitted data to the backend.
4. The backend logic processes the request.
5. The backend establishes a connection with Amazon RDS MySQL.
6. Student information is inserted into the database.
7. The application returns the result to the user.

---

## 🌐 AWS Network Architecture

The application is deployed inside a custom Amazon VPC.

### Public Subnet

The EC2 instance is deployed in the public subnet.

The EC2 instance provides access to the application through its public IP address.

### Private Subnet

The RDS MySQL database is deployed in the private subnet.

The database is not directly exposed to the public internet.

Communication between the application server and database is controlled using Security Groups.

## 🔐 Security Configuration

Security Groups are used to control communication between the EC2 instance and RDS database.

The application communicates with MySQL using:

Protocol : TCP
Port     : 3306


The RDS Security Group allows database traffic from the application server rather than allowing unrestricted access from the internet.

### Security Flow


EC2
 │
 │ TCP 3306
 ▼
RDS MySQL


This design helps keep the database isolated from direct public access.

---

## 🖥️ Application Tier

The application tier runs on an Amazon EC2 instance.

Apache Tomcat is used to host and execute the backend application.

The backend logic is responsible for:

* Receiving registration data
* Processing the request
* Connecting to MySQL
* Inserting student information
* Returning the result to the application

---

## 🗄️ Database Tier

Amazon RDS for MySQL is used as the database layer.

The database stores the information submitted through the student registration form.

The application connects to RDS using the database endpoint.

The database is deployed in the private subnet to reduce direct exposure to the internet.

---

## 📝 Presentation Tier

The presentation tier provides the interface through which users enter their information.

The student registration form collects details from the user and sends the information to the backend application.

The presentation layer is responsible for user interaction, while the application tier handles the processing logic.

---

## 🚀 Deployment Process

### 1. Create VPC

Created a custom VPC for the application infrastructure.

### 2. Create Subnets

Configured:

* Public subnet for EC2
* Private subnet for RDS

### 3. Configure Internet Gateway

Configured internet connectivity for the public subnet.

### 4. Launch EC2

Launched an EC2 instance in the public subnet.

### 5. Install Apache Tomcat

Configured Apache Tomcat on the EC2 instance.

### 6. Deploy Application

Deployed the student registration application to Tomcat.

### 7. Create RDS MySQL

Created an Amazon RDS MySQL database in the private network.

### 8. Configure Security Groups

Configured Security Groups to allow the required communication between EC2 and RDS.

### 9. Configure Database Connection

Configured the backend application to connect to the RDS MySQL database.

### 10. Test Application

Accessed the application through the EC2 public IP and tested student registration.

### 11. Verify Database

Verified that submitted student information was successfully stored in RDS MySQL.

---

## 🧪 Testing

The application was tested by:

* Accessing the application through the EC2 public IP
* Opening the registration form
* Entering student information
* Submitting the form
* Verifying successful processing
* Checking that the student data was inserted into RDS MySQL

---

## 🚧 Challenges & Troubleshooting

During the project, I worked on:

* Configuring the AWS VPC
* Creating public and private subnets
* Deploying the application on EC2
* Installing and configuring Apache Tomcat
* Connecting the backend application to RDS
* Configuring Security Group rules
* Troubleshooting MySQL connectivity on port 3306
* Verifying database insertion
* Testing communication between EC2 and RDS

---

## 📸 Screenshots

Screenshots demonstrating the project implementation will be added to the screenshots/ directory.

Planned screenshots:

* VPC configuration
* Public subnet
* Private subnet
* EC2 instance
* Security Groups
* RDS configuration
* Running registration application
* Student registration result
* Database records

---

## 🎯 Key Learning Outcomes

Through this project, I gained practical experience in:

* AWS VPC networking
* Public and private subnet architecture
* Amazon EC2
* Apache Tomcat
* Amazon RDS MySQL
* Security Groups
* EC2-to-RDS connectivity
* Application deployment
* Database connectivity
* AWS troubleshooting
* Three-tier application architecture

---

## 🛠️ Technologies Used

**Cloud:** AWS

**Compute:** Amazon EC2

**Database:** Amazon RDS MySQL

**Application Server:** Apache Tomcat

**Networking:** VPC, Subnets, Internet Gateway

**Security:** Security Groups

**Application:** HTML/JSP, Backend Logic, MySQL

---

# 👨‍💻 Author

Sri Harsha Akula

Cloud & DevOps Engineer Aspirant

Skills:  AWS | Linux | Docker | Jenkins | Ansible | Git | CI/CD | Bash

---
