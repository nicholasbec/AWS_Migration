# AWS_Migration

#Objective

Modernized AWS Infrastructure for Braveheart Technologies
This repository contains the proposed architecture and migration plan for modernizing the existing AWS infrastructure for Braveheart Technologies. The goal is to achieve high availability, scalability and empower developers to take an active role in infrastructure management.

#Table of Contents

1.Introduction
2.Proposed Architecture
3.Migration Plan
4.Implementation Steps
5.Testing and Validation
6.Conclusion
7.Assumptions

#Introduction
This project outlines the initial phase of modernizing Braveheart Technologies' existing AWS infrastructure. The proposed architecture aims to improve scalability, reliability, and developer involvement in the infrastructure management process.

#Proposed Architecture

The proposed architecture utilizes a three-tier architecture with separate layers for:

1.	UI/UX/Presentation
2.	Application logic
3.	Data storage 

#AWS Concepts
•	Application Load Balancers (ALB): Distribute incoming traffic across healthy backend instances.
•	Auto Scaling Groups (ASG): Automatically manage backend instances based on predefined scaling policies.
•	Amazon ECS: Container Orchestration for containerized application deployments and scaling.
•	CloudFront: Content Delivery Network (CDN) for improved performance and global reach.
•	Route 53: Managed DNS service providing domain name management and routing configuration.
•	Amazon RDS: Managed relational database service for data storage.
