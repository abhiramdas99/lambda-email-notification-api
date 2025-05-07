# Email Notification API (AWS Lambda + API Gateway + SES)

This project implements a **RESTful email notification service** using **AWS Lambda**, **API Gateway**, and **Simple Email Service (SES)**. It also maps the API to a **custom subdomain** (e.g., `notifications.yourdomain.com`) without using Route 53 — DNS is handled externally (e.g., GoDaddy, Cloudflare).

---

## 🔧 Features

- Send rich HTML email notifications via a POST API
- Uses AWS SES for email delivery
- Serverless backend powered by AWS Lambda
- Custom subdomain (e.g., `notifications.yourdomain.com`)
- SSL secured using AWS ACM with manual DNS validation
- Infrastructure managed with Terraform

---

## 🚀 Technologies

- AWS Lambda (Python)
- AWS API Gateway (HTTP API)
- AWS SES (Simple Email Service)
- AWS ACM (Certificate Manager)
- Terraform (Infrastructure as Code)

---

## 📬 Example API Request

**Endpoint:**  
POST https://notifications.yourdomain.com/notifications/rest/notifications


**Request Body:**
```json
{
  "application": "INT_UX_RLP_LIVE",
  "content": [
    {
      "format": "Html",
      "subject": "[RosettaLive Booking] Notification.event.created.subject",
      "message": "Test email message content.",
      "url": ""
    }
  ],
  "recipients": [
    {
      "type": "Email",
      "value": "someone@example.com"
    }
  ],
  "senderEmail": "noreply@uniquex.com",
  "type": "EVENT_CREATED"
}
```

# Deploy  & testing 

**take aws sso**
- list all vault  hou have 
```
aws-vault list
```
- take the session for as per your  required hour 
```
aws-vault exec AdministratorAccess-084828565305 duration=8hour
```
