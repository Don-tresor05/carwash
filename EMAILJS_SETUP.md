# EmailJS Setup Guide

## Quick Setup (5 minutes)

### 1. Create EmailJS Account
- Go to https://www.emailjs.com/
- Sign up (free - 200 emails/month)

### 2. Add Email Service
- Dashboard → Email Services → Add New Service
- Choose Gmail/Outlook/etc
- Connect your email account

### 3. Create Email Template
- Dashboard → Email Templates → Create New Template
- Template content:
```
New CleanPro Booking

Service: {{service}}
Date: {{date}}
Time: {{time}}
Customer: {{name}}
Phone: {{phone}}
```

### 4. Get Your Keys
- Dashboard → Account → Copy these 3 values:
  - **Public Key** (starts with user_...)
  - **Service ID** (from Email Services)
  - **Template ID** (from Email Templates)

### 5. Update index.html
Replace in the JavaScript section:
```javascript
emailjs.init('YOUR_PUBLIC_KEY');  // Line ~1050
// ...
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', params)  // Line ~1070
```

## Done! 🎉
Test by submitting a booking. You'll receive an email with all booking details.
