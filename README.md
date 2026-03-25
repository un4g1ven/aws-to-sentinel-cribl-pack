# AWS to Sentinel Cribl Pack

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Cribl Stream](https://img.shields.io/badge/Cribl%20Stream-v4.x%2B-blue)](https://cribl.io/)
[![Azure Sentinel](https://img.shields.io/badge/Azure%20Sentinel-SIEM-0078D4)](https://azure.microsoft.com/en-us/products/microsoft-sentinel/)

## Overview

A production-grade **Cribl Pack** that ingests 9 AWS log types from S3 via SQS in Cribl Stream Cloud, normalizes them to Microsoft Sentinel native table schemas, and delivers data via the **Azure Monitor Logs Ingestion API** using **Data Collection Rules (DCRs)**.

**Who This Is For:**
- Cribl Stream Cloud administrators managing AWS log ingestion
- Azure/Sentinel security operations teams
- Organizations building hybrid AWS-Azure security platforms
- Teams requiring native Sentinel table integration (not custom tables)

**Key Capabilities:**
- Automatic routing of 9 AWS log types by path, source, or structure
- Schema mapping to exact Sentinel native table specifications (PascalCase fields, correct data types)
- High-performance JSON serialization for Sentinel ingestion
- Isolated destination per log type for granular control
- Complete DCR ARM templates for one-command deployment
- Comprehensive documentation and per-log-type guides

---

## Supported AWS Log Types

All 9 log types are **Active** and production-ready:

| Log Type | Destination Table | Input Format | Pipeline Functions | Stat