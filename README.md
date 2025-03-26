# Docker Nginx Elastic Beanstalk Deployment

A minimal project demonstrating how to deploy a static website using **Docker**, **Nginx**, and **AWS Elastic Beanstalk**.

---

## 🧱 Project Structure

- `Dockerfile`: Uses the official Nginx image to serve a static HTML page.
- `index.html`: Your static website homepage.
  
To package your app for deployment, run:
zip -r app.zip Dockerfile index.html

## 🔐 IAM Role Setup

1. Go to the [AWS IAM Console](https://console.aws.amazon.com/iam/).
2. Create a new **IAM Role** with the following:
   - **Trusted entity**: AWS service
   - **Use case**: EC2
3. Attach this policy:
   - `AmazonEC2ContainerServiceforEC2Role`
4. Name it something like `ecsInstanceRole`.


## 🚀 Deploying to Elastic Beanstalk

1. Go to the [AWS Elastic Beanstalk Console](https://console.aws.amazon.com/elasticbeanstalk/).
2. Create a new environment:
   - **Platform**: Docker
   - **OS**: Amazon Linux 2023 (or newer)
3. Upload your `app.zip` file and deploy.
4. Assign the IAM role you created.
5. Deploy the environment.


## 🌐 Result

You’ll get a public domain with your deployed website:
![image](https://github.com/user-attachments/assets/851dcea6-16a7-4699-8744-dff87dbe7af2)


