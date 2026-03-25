# AWS Logs to Microsoft Sentinel — Cribl Pack

Production-grade Cribl Pack that ingests AWS logs collected via S3 (SQS-based) in Cribl Stream Cloud, transforms and normalizes them, and delivers them to Microsoft Sentinel via the Azure Monitor Logs Ingestion API using Data Collection Rules (DCRs).

## Supported Log Types

| # | AWS Log Source | Sentinel Table | Status |
|---|---------------|----------------|--------|
| 1 | CloudTrail | AWSCloudTrail | Active |
| 2 | VPC Flow Logs | AWSVPCFlow | Planned |
| 3 | GuardDuty | AWSGuardDuty | Planned |
| 4 | WAF | AWSWAF | Planned |
| 5 | Route53 Resolver | AWSRoute53Resolver | Planned |
| 6 | ALB Access Logs | AWSALBAccessLogs | Planned |
| 7 | NLB Access Logs | AWSNLBAccessLogs | Planned |
| 8 | S3 Server Access | AWSS3ServerAccess | Planned |
| 9 | Security Hub | AWSSecurityHubFindings | Planned |
