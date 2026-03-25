# AWS Security Hub Logs

This document describes the AWS Security Hub findings and how they are processed by the Cribl Pack. AWS Security Hub is a cloud-native SIEM central dashboard that provides a unified view of your security posture across your AWS accounts. It's a best practice to centralize security findings from multiple AWS accounts into a single account.

## Log Format

Security Hub Findings are delivered as JSON format files to an S3 bucket.