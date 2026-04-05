# Project 1: Secure Multi-Tier VPC with Public & Private Subnets

**Date:** Apri l 2026  
**Program:** B.S. Cloud and Network Engineering (AWS Specialization) – Western Governors University (WGU)

## Project Overview
Built a custom VPC with public and private subnets across two Availability Zones. Deployed a web server on the public tier while keeping the private tier isolated. This project demonstrates core networking concepts and Security+ principles (least privilege and network segmentation).

## Architecture Diagram

**Key Flow:**  
Internet → Internet Gateway → Public Route Table (0.0.0.0/0) → Public Subnet → Public-Web-Tier (Apache)
![Secure Multi-Tier VPC Architecture](images/architecture-diagram.png)

## Key Components
- **VPC**: 10.0.0.0/16
- **Public Subnets**: 10.0.1.0/24 (with Public-Web-Tier)
- **Private Subnets**: 10.0.3.0/24 (with Private-App-Tier)
- **Public-Web-Tier**: EC2 running Apache web server (HTTP accessible)
- **Private-App-Tier**: EC2 (SSH restricted to Public-Web-SG)

## Security Implementation
- **Public-Web-SG**: HTTP 80 from Anywhere, SSH 22 from My IP only
- **Private-App-SG**: SSH 22 only from Public-Web-SG (least privilege)

## Lessons Learned
- Proper route table association is required for internet access
- Security groups act as virtual firewalls between tiers
- Value of separating public-facing and backend resources
- Basic high availability using multiple AZs

## Screenshots Included
- VPC and Subnets
- Public Route Table
- Security Groups
- EC2 Instances
- Live web page at public IP

## Cost
~$0 (AWS Free Tier)

Last updated: April 2026
