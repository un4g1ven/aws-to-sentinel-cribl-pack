# AWS S3 Access Logs

This document describes the AWS S3 Access Logs and how they are processed by the Cribl Pack. AWS S3 Server Access Logs provide detailed records about requests made to an Amazon S3 bucket. Each log contains information such as the request type, the principal that sent the request, the request time, and the result  of the operation among other details.

## Log Format

S3 Access Logs are delivered as PJSON format in files in an S3 bucket that you specify.