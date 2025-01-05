# AWS Documentation  

This documentation explains the setup process for **Database Initialization**, **Application Deployment**, and related AWS services like **CloudFront**, **RDS**, and **Beanstalk**.  

---

## Database Initialization  

The following steps outline the process for initializing an Amazon RDS database using a temporary EC2 instance.  

### Steps to Initialize the Database  

1. **Launch a Temporary EC2 Instance**  
   - Launch an EC2 instance to temporarily connect and configure the database.  

2. **Install MySQL Client**  
   - SSH into the instance and run the following commands:  
     ```bash
     apt update && apt install mysql-client -y
     ```  

3. **Configure Security Groups**  
   - Connect the EC2 instance SG (Security Group) to the RDS backend SG.  
   - Copy the instance SG ID, navigate to the backend SG, and allow port **3306** for the instance SG.  

4. **Connect to RDS**  
   - Run the following command to connect to the RDS database:  
     ```bash
     mysql -h database-2.crsk4imuo6ui.ap-south-1.rds.amazonaws.com -u admin -pTaqih501# accounts
     ```  

5. **Clone Git Repository and Import Data**  
   - Clone the Git repository containing the table data:  
     ```bash
     git clone <repo-url>
     cd <repo-directory>
     ```  
   - Import the data into RDS:  
     ```bash
     mysql -h database-2.crsk4imuo6ui.ap-south-1.rds.amazonaws.com -u admin -pTaqih501# accounts < src/main/resources/db_backup.sql
     ```  

6. **Delete EC2 Instance**  
   - Once the database is initialized, terminate the EC2 instance.  

---

## Application Deployment  

1. **Clone Source Code**  
   - Clone the source code from the GitHub repository and switch to the `refactor` branch:  
     ```bash
     git clone <repo-url>
     cd <repo-directory>
     git checkout refactor
     ```  

2. **Import Additional Database Files**  
   - Import any additional files as required:  
     ```bash
     mysql -h database-1.crsk4imuo6ui.ap-south-1.rds.amazonaws.com -u admin -pTaqih501# accounts < /src/main/resources/application_db
     ```  

3. **Update Application Properties**  
   - Update the `application.properties` file with the RDS, Amazon MQ, and Memcache details:  
     - **RDS**: `database-2.crsk4imuo6ui.ap-south-1.rds.amazonaws.com`  
     - **Amazon MQ**: `b-1edd9c59-5335-4c5b-8a05-1be39c176dfd.mq.ap-south-1.amazonaws.com:5671`  
     - **Memcache**: `vprfile-rearch-cache.w2xkga.0001.aps1.cache.amazonaws.com:11211`  

4. **Build the Artifact Using Maven**  
   - Build the `.war` file using Maven:  
     ```bash
     mvn install
     ```  

5. **Deploy to Elastic Beanstalk**  
   - Upload the generated `vprofile.war` file to the Elastic Beanstalk environment.  

6. **Verify Deployment**  
   - Check the Elastic Beanstalk URL to ensure the service is running.  

---

## CloudFront  

AWS Cloud is used to enhance website availability and performance.  

### Steps to Set Up CloudFront  

1. **Create a CloudFront Distribution**  
   - Navigate to the CloudFront service.  
   - Use mostly default settings during the setup process.  

2. **Verify Setup**  
   - Once created, verify that the CloudFront distribution is properly serving your website content.  

---

This guide provides a concise step-by-step process for configuring these AWS services. For further customization, refer to the official AWS documentation.  

