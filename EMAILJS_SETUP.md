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
- **Subject:** New CleanPro Booking - {{name}}
- **Template content (HTML):**
```html
<div style="font-family: 'DM Sans', system-ui, sans-serif; font-size: 14px; max-width: 600px; margin: 0 auto; background: #f8fafc; padding: 20px">
  <div style="background: #0d1b2a; color: white; padding: 25px; border-radius: 12px 12px 0 0; text-align: center">
    <h1 style="margin: 0; font-family: 'Bebas Neue', sans-serif; font-size: 32px; letter-spacing: 2px">Clean<span style="color: #007BFF">Pro</span></h1>
    <p style="margin: 10px 0 0; color: rgba(255,255,255,0.7); font-size: 13px">🧼 NEW BOOKING RECEIVED</p>
  </div>
  
  <div style="background: white; padding: 30px; border-radius: 0 0 12px 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1)">
    <table role="presentation" style="width: 100%; border-collapse: collapse">
      <tr>
        <td style="padding: 15px; background: #f0f9ff; border-radius: 8px; margin-bottom: 20px">
          <div style="color: #007BFF; font-size: 12px; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 15px">📋 Service Details</div>
          <div style="margin-bottom: 12px">
            <div style="color: #64748b; font-size: 11px; text-transform: uppercase; letter-spacing: 0.5px">Service Package</div>
            <div style="color: #0d1b2a; font-size: 16px; font-weight: 600; margin-top: 4px">{{service}}</div>
          </div>
          <div style="display: inline-block; width: 48%; margin-bottom: 12px">
            <div style="color: #64748b; font-size: 11px; text-transform: uppercase; letter-spacing: 0.5px">Date</div>
            <div style="color: #0d1b2a; font-size: 15px; font-weight: 500; margin-top: 4px">📅 {{date}}</div>
          </div>
          <div style="display: inline-block; width: 48%; margin-bottom: 12px">
            <div style="color: #64748b; font-size: 11px; text-transform: uppercase; letter-spacing: 0.5px">Time</div>
            <div style="color: #0d1b2a; font-size: 15px; font-weight: 500; margin-top: 4px">⏰ {{time}}</div>
          </div>
        </td>
      </tr>
      <tr>
        <td style="padding: 20px 0">
          <div style="color: #007BFF; font-size: 12px; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 15px">👤 Customer Details</div>
          <table role="presentation">
            <tr>
              <td style="vertical-align: top">
                <div style="padding: 10px 15px; margin-right: 15px; background: #007BFF; border-radius: 8px; font-size: 24px" role="img">👤</div>
              </td>
              <td style="vertical-align: top">
                <div style="color: #0d1b2a; font-size: 18px; font-weight: 600; margin-bottom: 4px">{{name}}</div>
                <div style="color: #64748b; font-size: 14px; margin-top: 6px">📞 {{phone}}</div>
                <div style="color: #64748b; font-size: 14px; margin-top: 6px">📍 {{location}}</div>
              </td>
            </tr>
          </table>
        </td>
      </tr>
    </table>
    
    <div style="margin-top: 25px; padding: 15px; background: #dcfce7; border-left: 4px solid #16a34a; border-radius: 6px">
      <div style="color: #16a34a; font-weight: 600; font-size: 14px">✅ Action Required</div>
      <div style="color: #166534; font-size: 13px; margin-top: 4px">Call customer to confirm appointment</div>
    </div>
  </div>
  
  <div style="text-align: center; margin-top: 20px; color: #94a3b8; font-size: 12px">
    <p>CleanPro - Complete Cleaning Solutions</p>
  </div>
</div>
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
