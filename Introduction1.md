# 🌟 About the Project: **Architecting Web Apps on AWS Cloud** 🌟

This project is **Part 2 of the Lift and Shift Initiative**, where we move the complete web application setup to AWS Cloud. The focus is on utilizing AWS-managed services to eliminate the challenges of on-premises setups like **Memcached**, **MySQL**, and **RabbitMQ**.

---

## 💡 Problem with On-Premises Setup:
- High **Operational Overhead**.
- Struggles with **Uptime and Scalability**.
- **High upfront CapEx** and regular OpEx.
- Manual processes that are **difficult to automate**.

---

## ✅ Solution: AWS Cloud Setup
Transitioning to AWS cloud services addresses these challenges, offering scalability, reliability, and automation.

---

## AWS Services Used in the Project:
1. **Elastic Beanstalk**: Manages instances, creates load balancers, and provides auto-scaling.  
2. **S3**: Stores artifacts for deployments.  
3. **RDS**: Provides database management for MySQL tasks.  
4. **ElastiCache**: Handles caching requirements.  
5. **ActiveMQ**: Replaces RabbitMQ for message queuing.  
6. **Route 53**: Manages DNS records.  
7. **CloudFront**: Acts as a Content Delivery Network (CDN).

---

## 🚀 Workflow:
1. User accesses the application via **Route 53**.
2. Request goes through **CloudFront**.
3. **Load Balancer** forwards the request to **EC2 instances**.
4. Backend services include **Amazon MQ** and **Memcached**.
5. Database tasks are handled by **Amazon RDS**.

---

## ⚙️ Flow of Execution:
1. Login to your AWS account.  
2. Create a **Key Pair** for logging into Beanstalk instances.  
3. Set up **Security Groups** for:
   - Elasticache
   - RDS
   - ActiveMQ  

4. **Create the following AWS services**:
   - **RDS**
   - **Amazon Elasticache**
   - **Amazon ActiveMQ**  

5. Set up an **Elastic Beanstalk Environment**.  
6. Update backend **SG** to allow traffic from the Beanstalk SG.  
7. Configure backend SG to allow **internal traffic**.

---

## 🌈 Outcome  
This project demonstrates the seamless integration of AWS services for running a web application efficiently, eliminating the pain points of on-premises setups. It’s an excellent addition to your portfolio, showcasing your expertise in deploying cloud-based solutions. 💻✨

---

Feel free to replicate this project for your learning and resume enhancement! 😊

