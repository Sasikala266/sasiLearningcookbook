# 🚀 Q Application for Jira Assistant

**Q is a lightweight, command-driven assistant that integrates with Jira to streamline team collaboration, automate workflows, and simplify issue tracking.**

---

[<img src="images/q/assistant.png">]()

## 📋 Prerequisites

Before you begin building and connecting your custom Q application with Jira, make sure the following prerequisites are in place:

🧰 **Jira Setup**

    ✅ A Jira account with admin access
    
    ✅ A Jira project or board created for your team
    
    ✅ Permissions to create and manage Jira apps and plugins
    
    ✅ Access to Jira's OAuth credentials (Client ID and Secret)

**☁️ AWS Setup**

    ✅ An active AWS account
    
    ✅ IAM user or role with permissions to access:

        - Amazon S3 (for storing logs or assets)
        - AWS Lambda (if using serverless functions)
        - Amazon API Gateway (for exposing Q endpoints)

    ✅ AWS CLI configured locally (optional but recommended)

**Let's Start Building!!!**

1. **Create a Custom Q App**  
   Build your own Q interface tailored to your team's needs.  
   👉 [Create custom Q app](create-custom-q-app.md)

2. **Connect Q to Jira using Data sources**  
   Establish a secure data source to fetch and update Jira issues.  
   👉 [Create the data connection with Jira](q-data-source-for-jira.md)

3. **Set Up Jira App & OAuth**  
   Register your Jira app and configure OAuth for secure authentication.  
   👉 [Create Jira app & OAuth](create-jira-app-oauth.md)

4. **Deploy Jira Plugin for Q Assistant**  
   Enable Q to interact with Jira natively via plugin integration.  
   👉 [Create Jira plugin for Jira Assistant](create-jira-plugin.md)

5. **Demo**

   👉 [Demo video showing the creation of the assistant and usage](demo.md)

6. **Additional Learnings**

   👉 [Addional Learnings](additional-learning.md)


---

## 🧩 What’s Next?

Once setup is complete, your team can:
- Use Q to create, update, and track Jira issues via simple commands
- Receive real-time notifications and status updates
- Collaborate seamlessly across Jira projects

---

