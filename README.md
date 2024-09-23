# AWS_Migration

#Objective

Modernized AWS Infrastructure for Braveheart Technologies
This repository contains the proposed architecture and migration plan for modernizing the existing AWS infrastructure for Braveheart Technologies. The goal is to achieve high availability, scalability and empower developers to take an active role in infrastructure management.

#Table of Contents

1.Introduction
2.Proposed Architecture
3.Migration Plan
4.Implementation Steps
5.Validation Test/User Acceptance Testing
6.Conclusion
7.Assumptions

#Introduction
This project outlines the initial phase of modernizing Braveheart Technologies' existing AWS infrastructure. The proposed architecture aims to improve scalability, reliability, and developer involvement in the infrastructure management process.

#Proposed Architecture

The proposed architecture utilizes a three-tier architecture with separate layers for:

1.	UI/UX/Presentation
2.	Application logic
3.	Data storage 

AWS Concepts
•	Application Load Balancers (ALB): Distribute incoming traffic across healthy backend instances.
•	Auto Scaling Groups (ASG): Automatically manage backend instances based on predefined scaling policies.
•	Amazon ECS: Container Orchestration for containerized application deployments and scaling.
•	CloudFront: Content Delivery Network (CDN) for improved performance and global reach.
•	Route 53: Managed DNS service providing domain name management and routing configuration.
•	Amazon RDS: Managed relational database service for data storage.

#Migration Plan
The migration should be attempted in small phases, this minimizes downtime and risk and makes roll-back easier to achieve. 

--Preparation:
Define migration sequence by prioritizing non-critical services or functionalities.
Set up an IAC tool (Terraform)
--Back-up
Ensure all current infrastructure, applications and data are backed up to a HA solution
--Phase 1:
Migrate non-critical services to the new architecture using containerized deployments on ECS.
Test and validate functionality in the new environment.
--Phase 2:
Migrate remaining services while maintaining high availability.
Update DNS records in Route 53 to point to the new infrastructure.
--Go-Live:
Once all services are migrated, switch the traffic from the old to the new infrastructure.
Decommission the old infrastructure.

#Implementation Steps
These are the steps that would be taken at a high-level of the implementation process:

Create security groups for the application.
1.Define IAM roles with appropriate permissions for these resources. 
2.Create an RBAC model with 3 main job families, with further granularity per role (Eg 1 Role for Backend Developer, another role for Lead Frontend Developer)
3.Provision resources like ASGs, ECS clusters, and databases using Terraform.
4.Containerize existing applications and deploy them to ECS
5.Configure CloudFront and Route 53 for load balancing and corret traffic routing.
6.Migrate data to the new database service/Amazon RDS

#Validation Test/User Acceptance Testing

The 4 main areas to be tested are: 
  1. Load
  2. Functionality
  3. Performance
  4. Security

#Conclusion

This plan lays the groundwork for modernizing Braveheart Technologies' AWS infrastructure. By implementing this architecture and migration process, along with making the application more resilient, the company can achieve high availability, improved performance and it empowers developers to participate actively in managing this infrastructure. 

#Assumptions

1.Application frameworks do not rely on a legacy framework that cannot be containerised.
2.Cost optimization has not been considered. However moving to a more elastic solution should help reduce costs.
3.There are several dependancies in this plan, for example a data migration plan, a back-up plan, a roll-back plan etc that I have not mentioned. These should be in place prior to any migration.
4.As the plan is to get the developers involved, it's assumed that they would be involved in the migration. For example, they could be working on the IAC piece, or code refactoring for microservices. 
5.Network infratructure is in place to allow the migration of the data
6.Post Migration, the adequate monitoring and logging is enforced.
7.Governance policies are applied 


