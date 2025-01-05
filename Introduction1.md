# AWS Documentation  

This documentation covers the process of setting up and configuring **Amazon RDS**, **AWS Elastic Cache**, and **Amazon MQ**.  

---

## Amazon RDS  

Amazon RDS (Relational Database Service) allows you to set up, operate, and scale a relational database in the cloud. Unlike traditional databases, RDS does not allow SSH access for configuration changes. Instead, it uses **Parameter Groups** to manage database settings.  

### Steps to Set Up RDS  
1. **Create a Parameter Group**  
   - A Parameter Group is a collection of configuration settings applied to an RDS instance.  
   - Navigate to the RDS service on AWS.  
   - Create a new Parameter Group and select appropriate settings based on your requirements.  

2. **Create a Subnet Group**  
   - Specify the subnets where your database will be available.  

3. **Launch an RDS Instance**  
   - Select **MySQL** as the database engine.  
   - Keep most settings as default unless specific customizations are needed.  
   - Start the database creation process.  

---

## AWS Elastic Cache  

AWS Elastic Cache is a fully managed in-memory caching service that is easy to set up and configure. Its creation process is similar to RDS and also uses **Parameter Groups**.  

### Steps to Set Up Elastic Cache  

1. **Create a Parameter Group**  
   - Select the parameter family as **Memcached**.  
   - Use the default settings or make adjustments as required.  

2. **Create a Subnet Group**  
   - Assign a name to the Subnet Group.  
   - Select the appropriate **VPC** and subnets.  

3. **Create a Cluster**  
   - Use the default settings for simplicity.  
   - Start the creation process—no advanced configurations are required.  

---

## Amazon MQ  

Amazon MQ is a managed message broker service. Follow these steps to set up an **Amazon MQ** instance:  

### Steps to Set Up Amazon MQ  

1. **Select RabbitMQ**  
   - Navigate to the Amazon MQ service and get started with **RabbitMQ**.  

2. **Instance Configuration**  
   - Choose **Single Instance**.  
   - Provide a name for the instance.  
   - Select the smallest instance type for basic use cases.  

---

This guide ensures a smooth setup process for each service with minimal configurations. For advanced setups, refer to the official AWS documentation.  

