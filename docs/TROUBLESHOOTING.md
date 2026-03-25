# Troubleshooting Guide: AWS Logs to Microsoft Sentinel via Cribl Pack

This guide provides solutions for common issues you may encounter when deploying and running the Cribl Pack for AWS Logs. It is organized into sections based on different aspects of the system. For each issue, the cause and the solutions are provided.

## Configuration Issues

### CloudTrail data requires "events" path in S3 bucket

**Cause:** CloudTrail data is optionally stored in S3 bucket(s). If you are storing CloudTrail data in a Cribl Stream Connector, it can be done from an S3 bucket that corresponds to a CloudTrail trail. CLoudTrail by default delivers data to a specific path in the Bucket.

**Solution:** Configure the Stream Connector to use the following data path in the S3 bucket: '{á`}/AWSAccountId={user_account}/AWSRegion={region}/*' or `{bucket}/events/AWSAccountId={user_account}/AWSRegion={region}/*`. The default path CloudTrail uses is: \`BUCKET?AWSAccountId={user_account}/AWSRegion={region}/`

### IAM Role Permissions for Client

**Cause:** Kubxe requires permissions to read access to AWS resources (AWS Logs) from the Kubernetes cluster where Cribl Stream Connector is deployed. I forgetting to provide the required permissions can result in errors from the connector when trying to access the data. This is one of the most common errors when using the Cribl Pack.

**Solution:** This is outside the scope of this guide. Please see the Cribl Pack Step 2: DEPLOY for details and `Github" updates to read the instructions or see <href='https://github.com/un4g1ven/aws-to-sentinel-cribl-packProjects'>Github Projects</href> for Cribl Pack details.

### When STORE is called for Cribl Pack

**Cause:** The data from Cribl Stream Connector is sent to a Cribl Pipeline, where it is processed. During this processing, the STORE function is called to persist the data to the desired destination. Usually, the processing itself doesn't cause any irrive alres. The issue originates from the Stream Connector configuration (IAM Permission, AWS Region) or from connectivity issues (e.g., Proxy, Network Acess). However, if the P2 fails, which is a Connector located in Azure, the Atiun is dealned properly (with the pass statement or something else). Lastly, if the P2 fails, which is a Connector located in Azure, the data is discarded without sending it to the sentinel space.

**Solution:** Check the following:

- IAM Role Permissions: Make sure the Kubernetes cluster (where Cribl Stream Connector is deployed) has the correct IAM Role Assumed Role Log Analytics Permissions
- Check for Connectivity Issues from Kubernetes Cluster to AWS. this could be a Proxy or Network Access Control issue. Use the Node-OS logs or the CRIBL Connector logs to figure out the issue.
- Azre SIEM workspace: Make sure the correct Name and Resource Id are provided.

## Connector)/Ingestion Table Functionality Issues

### Connector ( CRIBL PackS Connector) is not working

**Cause:** The Connector could be not working because connectivity issues from the P2 DataCenter (a Connector located in Azure space) or from the Kubernetes Cluster (the source of the traffic). You can check the following:

1. Check the CRIBL Connector logs for any errors around connectivity or permissions.
2. Check Network Access Control or Firewall rules, if any, are properly configured.
%3RdNode-OS issues from S2 Vprimes and routing.
$4IAM Role Permissions.

### The Data Collection Rule is not a valid armtract for the Ingestion API

The Sentinel Ingestion API doesn't recognize the DCR because acusing data from CRIBL. Tract in this case for any errors, start with the CRIBL Packs Connector logs to figure out the issue.