# 📧 Jenkins Email Notification on Build Failure  

This project demonstrates how to configure **email notifications in Jenkins** using Gmail SMTP. Whenever a Jenkins job fails, an automated email is sent to the specified recipients to ensure quick awareness and resolution.  

---

## 🚀 Project Overview  
- Configure **Jenkins with Gmail SMTP** to send emails.  
- Use **App Password** in Gmail for secure authentication.  
- Automate **build failure notifications** to one or more recipients.  
- Practical use case for DevOps teams working on CI/CD pipelines.  

---

## 🛠️ Prerequisites  
- Jenkins set up on an **AWS EC2 instance (Linux/Ubuntu)**.  
- Active Gmail account (with **App Password** enabled).  

---

## ⚙️ Step 1: Configure Gmail App Password  

1. Log into your Gmail account.  
2. Go to **Google Account → Security → App passwords**.  
3. Create a new app password for **“Jenkins”**.  
4. Copy and save the generated password securely.  

📌 Example:  

![gmail config](/images/gmail-confi.png)  

---

## ⚙️ Step 2: Configure SMTP in Jenkins  

1. Log into Jenkins:  

```bash
http://<EC2-Public-IP>:8080
```

2. Navigate to **Manage Jenkins → Configure System**.  
3. Scroll down to **E-mail Notification**.  
   - SMTP Server: `smtp.gmail.com`  
   - SMTP Port: `465`  
   - User Name: your Gmail ID  
   - Password: App password created in Step 1  
   - Use SSL: ✅ Enabled  
4. Save the configuration.  

📌 Example:  

![jenkins config](/images/email-set-up.png)  

---

## ⚙️ Step 3: Create a Jenkins Job  

1. Click **New Item** → Enter a job name (e.g., `Email-Notification`).  
2. Select **Freestyle project** and click **OK**.  
3. Configure the job:  
   - **Description**: Add project details.  
   - **Source Code Management**: Git → Enter repository URL.  
   ```bash
   https://github.com/pratikdaspppd3/GitLab-to-GitHub-Repo-Mirroring.git
   ```
   - **Branches to build**: Adjust (`main` or `master`) as per repo.  
4. Go to **Post-build Actions** → Select **E-mail Notification**.  
5. Enter recipient email addresses (comma-separated for multiple).  
6. Save the job.  


---

## ⚙️ Step 4: Build and Test  

1. Click **Build Now**.  
2. If the build fails, Jenkins will automatically send an email.  

📌 Example:  

- **Build Failure**  

![build fails](/images/build-fails.png)  

- **Email Notification Received**  

![notification email](/Images/notification.png)  

---

## ✅ Summary  

This project configures Jenkins to send **real-time build failure notifications** via Gmail SMTP. Using App Passwords ensures secure authentication. The setup is especially useful in **team projects**, where developers need instant alerts when builds break.  

---

## 📖 Learnings  

- Configuring Gmail SMTP with Jenkins.  
- Using App Passwords for secure email authentication.  
- Automating post-build notifications in Jenkins.  
- Collaboration benefits for DevOps teams.  

---

## 🤝 Connect With Me

📬 [LinkedIn](www.linkedin.com/in/pratik-das-a47493231)  
💬 Open to discussions on AWS, Linux, Web App Hosting, and DevOps!