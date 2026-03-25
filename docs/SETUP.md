# AWS to Microsoft Sentinel Cribl Pack - Complete Setup Guide

This guide provides step-by-step instructions for configuring the AWS to Microsoft Sentinel Cribl Pack to ingest and forward AWS logs to Microsoft Sentinel for security monitoring and analysis.

## Overview

The AWS to Sentinel Cribl Pack ingests logs from the following AWS services via S3:

1. CloudTrail (API activity)
2. VPC Flow Logs (network traffic)
3. GuardDuty (threat detection)
4. WAF (web application firewall)
5. Route53 Resolver (DNS query logs)
6. ALB Access Logs (load balancer traffic)
7. NLB Access Logs (network load balancer traffic)
8. S3 Server Access Logs (object storage access)
9. Security Hub (security findings)

Each log type is mapped to a corresponding table in Microsoft Sentinel via Data Collection Rules (DCRs).

---

## 1. Azure Prerequisites Setup

### 1.1 Register Azure AD Application

The Cribl Pack requires an Azure AD application with appropriate permissions to send logs to Microsoft Sentinel.

#### Step 1: Access Azure Portal

1. Log in to the [Azure Portal](https://portal.azure.com)
2. Navigate to **Azure Active Directory** (or search 