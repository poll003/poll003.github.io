# SQL_Change_Tier_Azure_SQL

To change the pricing tier, you need the database name, and the updated pricing tier (Edition & Service object).
 
The edition is the tier like Basic, Standard, Premium and Service objects are DTUs, like Basic, S0, S1, S2, S3, etc.

The SQL Script wil look like:
``` sql
-- ==========================================
-- Change Azure SQL Service Tier
-- ==========================================

ALTER DATABASE [<dbName>] MODIFY(EDITION='<edition>' , SERVICE_OBJECTIVE='<serviceObjective>')
```
## Scale down to Standard S1 
``` sql
-- ==========================================
-- Change Azure SQL Service Tier to GeneralPurpose Serverless with 6VCores
-- ==========================================

ALTER DATABASE [TestAzureDB] MODIFY(EDITION='Standard' , SERVICE_OBJECTIVE='S1')   
```
## Scale down Up GeneralPurpose Serverless with 6 VCores 
``` sql
-- ==========================================
-- Change Azure SQL Service Tier to GeneralPurpose Serverless with 6 VCores
-- ==========================================

ALTER DATABASE [TestAzureDB] MODIFY(EDITION='GeneralPurpose' , SERVICE_OBJECTIVE='GP_S_Gen5_6')   
```