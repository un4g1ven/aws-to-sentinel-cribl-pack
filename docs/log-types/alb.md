# AWS ALB Logs

This document describes the AWS APplication Load Balancer (ALB) Logs and how they are processed by the Cribl Pack. AWS Application Load Balancer (ALB) Logs contain information about the requests sent to a load balancer. Each log contains information such as the time the request was received, the client's IP adress, latencies, request paths, and server responses among other things.

## Log Format

AWS ALB Logs are delivered as plain text files in an S3 bucket.