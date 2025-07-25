# 📢 Event Announcer – Serverless AWS App

This is a simple serverless web application built using AWS services. It allows users to subscribe via email to receive event announcements and enables event creators to publish messages via SNS.

---

## 🛠️ Technologies Used

- **Frontend:** HTML + JavaScript, hosted on S3 (static website hosting)
- **Backend:** AWS Lambda + HTTP API Gateway
- **Messaging:** Amazon SNS
- **CORS:** Configured on API Gateway
- **Deployment:** Manual setup via AWS Console (no IaC yet)

---

## 🚀 Features

- 📬 **Email Subscription:** Users can enter their email and get added to an SNS topic
- 📢 **Event Creation:** Admins or users can publish event announcements
- 🌐 **Fully Serverless:** No backend servers or containers needed
- 🔐 **CORS Ready:** Configured for frontend-to-API communication

---

## 🧩 Architecture

```
[Frontend (S3 Static Website)]
        |
        | fetch() POST /subscribe or /event
        ↓
[API Gateway (HTTP API with CORS)]
        ↓
[Lambda Functions]
        ↓
[Amazon SNS]
        ↓
[Email Notification to Subscribers]
```

---

## 📂 Project Structure

```
📁 event-announcer
├── index.html            # Frontend HTML page
├── style.css             # Optional styling
├── subscribeUser.js      # Lambda function for email subscriptions
├── createEvent.js        # Lambda function for publishing events
├── openapi.json          # (Optional) OpenAPI definition used to deploy API Gateway
└── README.md             # This file
```

---

## 🔧 How to Use

1. **Frontend**:
   - Upload `index.html` to an S3 bucket with static website hosting enabled
2. **Backend**:
   - Deploy both Lambda functions in AWS
   - Create an HTTP API with two routes: `/subscribe` and `/event`
   - Enable CORS and attach the functions
   - Connect both routes to an SNS topic
3. **Test**:
   - Open your S3 site in a browser
   - Submit an email or event to see it in action

---

## 🔒 Security Notes

- Use `*` for CORS during development, then lock down to your domain
- Consider adding authentication (e.g., Cognito or IAM) for event publishing

---

## 📬 Contact

Made by Adrian.  
If you have questions, feel free to reach out or fork the project!
