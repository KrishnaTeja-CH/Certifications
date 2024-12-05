# AWS Notes and Best Practices

This repository contains detailed notes and best practices for various AWS services, organized by importance.

## Table of Contents
1. [IAM and S3](#1-iam-and-s3)
2. [EC2](#2-ec2)
3. [Databases on AWS](#3-databases-on-aws)
4. [Advanced IAM](#4-advanced-iam)
5. [Route 53](#5-route-53)
6. [VPCs](#6-vpcs)
7. [High Availability Architecture](#7-high-availability-architecture)
8. [Applications (SQS, SNS, API Gateway)](#8-applications-sqs-sns-api-gateway)
9. [Security](#9-security)
10. [Serverless](#10-serverless)

---

## 1. IAM and S3

### IAM
- A global service to manage user access and permissions across AWS.
- **Tips to protect a root account:**
  - Enable MFA (multi-factor authentication).
  - Avoid using the root user; create an IAM user with necessary permissions.
  - Do not share root access keys; disable or delete them instead.
  - Follow the principle of least privilege.

- **Policies:**
  - AWS managed (administered by AWS).
  - Customer managed (administered by you).
  - Inline (embedded in IAM identity).

- **Key IAM Features:**
  - Fine-grained access control.
  - Centralized control of your AWS account.

### S3
- Buckets are region-specific but globally unique.
- **S3 Object Structure:**
  - `key`, `value`, `version id`, `metadata`.
  - Size: 0 bytes < size < 5 TB (160 GB console upload limit).

- **Consistency:**
  - Read-after-write consistency.
  - Eventual consistency.

- **Features:**
  - Lifecycle management.
  - Versioning.
  - Encryption (in-transit and at rest).
  - MFA protection.

- **Storage Classes:**
  - Standard.
  - Standard Infrequent Access.
  - One Zone IA.
  - Intelligent Tiering.
  - Glacier.
  - Glacier Deep Archive.

---

## 2. EC2

- **Pricing Models:**
  - Spot Fleet strategies: `price-capacity-optimized`, `capacity-optimized`, `diversified`, `lowest-price`.

- **Security Groups:**
  - Inbound: Blocked by default.
  - Outbound: Allowed by default.
  
- **Networking:**
  - Elastic Network Adapter (ENA) preferred.
  
- **Placement Groups:**
  - Types: Cluster, Spread, Partition.
  - Homogeneous instances recommended.

- **EBS:**
  - Block-level storage.
  - Dynamically increase volume size without detaching.
  - Types: SSD, HDD.

- **Snapshots:**
  - Incremental.
  - Encryption options available.

---

## 3. Databases on AWS

- **Databases:** RDS, DynamoDB, Aurora, Redshift.
- **Backups:** Automated snapshots, manual snapshots, point-in-time recovery.

---

## 4. Advanced IAM

- IAM Federation, SAML, and Active Directory integration.
- Assume roles for cross-account access.
  
---

## 5. Route 53

- **Functions:**
  - Domain registration.
  - DNS routing.
  - Health checks.

---

## 6. VPCs

- **Components:**
  - Subnets.
  - Route Tables.
  - Internet Gateways.
  - NAT Gateways.

---

## 7. High Availability Architecture

- **Key Elements:**
  - Multi-AZ deployments.
  - Load Balancers.
  - Auto Scaling Groups.

---

## 8. Applications (SQS, SNS, API Gateway)

- **SQS:** Message queuing service.
- **SNS:** Pub/Sub service.
- **API Gateway:** Managed API service for creating, publishing, and securing APIs.

---

## 9. Security

- **Best Practices:**
  - Use Security Groups and Network ACLs.
  - Enable logging and monitoring.
  - Encrypt data at rest and in transit.

---

## 10. Serverless

- **Services:**
  - AWS Lambda.
  - AWS Fargate.
  - DynamoDB (NoSQL).
  
---

## Contributing

Feel free to submit issues or pull requests to contribute to this repository.

## License

This project is licensed under the MIT License.
