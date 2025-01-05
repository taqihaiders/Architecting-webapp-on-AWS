## Creating Beanstalk Environment  

### Step 1: IAM Roles for Beanstalk  
1. Create a role for Elastic Beanstalk with the following policies:  
   - **Administrator Access**  
   - **EC2 Role**  
   - **WebTier Role**  
2. Select default settings during the role creation process.  
3. Review the settings and create the environment.  

### Step 2: Build and Deploy the Artifact  

#### Collect Backend Service Details  
Before building the artifact, ensure you have the following backend service details:  
- **RDS Endpoint**: `database-2.crsk4imuo6ui.ap-south-1.rds.amazonaws.com`  
- **Amazon MQ Endpoint**: `b-1edd9c59-5335-4c5b-8a05-1be39c176dfd.mq.ap-south-1.amazonaws.com:5671`  
  - **Username**: `rabbit`  
  - **Password**: `Taqih501#Taqih501#`  
- **Memcache Endpoint**: `vprfile-rearch-cache.w2xkga.cfg.aps1.cache.amazonaws.com:11211`  

#### Clone and Build the Source Code  
1. Clone the source code repository locally:  
   ```bash
   git clone <repo-url>
   cd <repo-director>

## Building and Deploying the Artifact  

### Step 1: Build the Artifact Using Maven  
Run the following command to build the artifact:  
```bash
mvn install
   

