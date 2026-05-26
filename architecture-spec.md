Infrastructure Design & AWS Cloud Topology
This document specifies the architectural decisions, network topology, and security standards applied to the cloud infrastructure configurations hosted in this repository.

1. High-Availability Network Topology (VPC)
The network architecture is designed across multiple Availability Zones (AZs) to ensure fault tolerance and strict isolation of public and private resources.

[ Internet ]
      │
      ▼
[ Internet Gateway ]
      │
      ├─────────────────────────┬─────────────────────────┐
      ▼                         ▼                         ▼
[ Public Subnet AZ1 ]     [ Public Subnet AZ2 ]     [ Public Subnet AZ3 ]
  - NAT Gateway (AZ1)       - NAT Gateway (AZ2)       - NAT Gateway (AZ3)
  - Application Load Balancer
      │                         │                         │
      └─────────────────────────┼─────────────────────────┘
                                ▼
                  [ Private Isolated Subnets ]
                    - ECS Fargate Tasks (Backend Services)
                    - Internal Microservices
                                │
                                ▼
                  [ Database Subnets (No Internet) ]
                    - Amazon RDS (PostgreSQL/MySQL Multi-AZ)


Network Allocation
CIDR Block: 10.0.0.0/16

Public Subnets: Managed routing via Internet Gateway (IGW) for public-facing load balancers.

Private Subnets: Egress-only internet access restricted through AWS NAT Gateways for secure application deployment.

Database Subnets: Fully isolated subnets without a route to the internet; accessible only from the application tier.

2. Compute & Orchestration (ECS Fargate)
Application workloads are containerized and orchestrated using Amazon ECS with AWS Fargate to achieve a serverless, maintenance-free compute layer.

Task Placement: Tasks are distributed evenly across private subnets in multiple AZs using spread placement strategies.

Auto Scaling: Managed via AWS Application Auto Scaling targets based on:

Average CPU Utilization > 70%

Memory Reservation > 75%

Service Discovery: Integrated with AWS Cloud Map for microservice-to-microservice communication within the VPC namespace.



Resource,Service,Configuration / Strategy
Relational Data,Amazon RDS,"PostgreSQL, Multi-AZ deployment, Storage Auto-scaling enabled."
Object Storage,Amazon S3,"Server-side encryption (SSE-S3), Lifecycle rules for transition to Glacier."
Caching Tier,Amazon ElastiCache,Redis cluster running in cluster mode enabled for session state.

4. Security & Access Control (IAM)
Security is implemented following the Principle of Least Privilege (PoLP):

IAM Execution Roles: Separate roles for ECS Task Execution (pulling images from ECR, writing logs to CloudWatch) and ECS Task Role (application-level AWS API calls).

Security Groups:

Load Balancer SG accepts traffic only on ports 80 and 443 from the public internet.

ECS Tasks SG accepts traffic only from the Load Balancer Security Group.

Database SG accepts inbound traffic only from the ECS Tasks Security Group on port 5432.

5. Environment & Variable Blueprint
When provisioning this infrastructure via IaC (Terraform/CloudFormation), the following environment matrices are mapped:

{
  "Environment": "Production",
  "Region": "eu-central-1",
  "ProjectName": "cloud-core-infra",
  "ManagedBy": "Infrastructure-as-Code",
  "Compliance": "SOC2-Ready"
}

