# Contact Form Setup Guide

The contact form is configured to send emails to **nareshkumarreddy1912@gmail.com** using EmailJS.

## Quick Setup Steps:

### Step 1: Create EmailJS Account
1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

### Step 2: Add Email Service
1. Go to **Email Services** in your EmailJS dashboard
2. Click **Add New Service**
3. Choose your email provider (Gmail recommended)
4. Follow the setup instructions
5. **Note your Service ID** (e.g., `service_xxxxx`)service_1k0gw2j

### Step 3: Create Email Template
1. Go to **Email Templates** in your EmailJS dashboard
2. Click **Create New Template**
3. Set up the template with these variables:
   - **Subject**: `{{subject}}`
   - **Content**:
     ```
     From: {{from_name}} ({{from_email}})
     
     Subject: {{subject}}
     
     Message:
     {{message}}
     ```
4. Set **To Email** to: `nareshkumarreddy1912@gmail.com`
5. **Note your Template ID** (e.g., `template_xxxxx`)

### Step 4: Get Public Key
1. Go to **Account** > **General**
2. Scroll down to **API Keys**
3. Copy your **Public Key** (e.g., `xxxxxxxxxxxxxxx`)

### Step 5: Update script.js
Open `script.js` and replace these values:

1. Line ~139: Replace `YOUR_PUBLIC_KEY` with your Public Key
   ```javascript
   emailjs.init("9ciqvt-c1ieqMlHq2")
   ```

2. Line ~163: Replace `YOUR_SERVICE_ID` with your Service ID
   ```javascript
   'service_1k0gw2j',
   ```

3. Line ~164: Replace `YOUR_TEMPLATE_ID` with your Template ID
   ```javascript
   'YOUR_TEMPLATE_ID',   // Replace this
   ```

## Example:
```javascript
emailjs.init("9ciqvt-c1ieqMlHq2");

// Later in the code:
const response = await emailjs.send(
    'service_abc123',    // Your Service ID
    'template_xyz789',   // Your Template ID
    {
        from_name: formData.from_name,
        from_email: formData.from_email,
        subject: formData.subject,
        message: formData.message,
        to_email: formData.to_email
    }
);
```

## Testing:
1. Open your portfolio website
2. Navigate to the Contact section
3. Fill out and submit the form
4. Check your email inbox for the message

## Free Tier Limits:
- EmailJS free tier: 200 emails/month
- Perfect for a personal portfolio website

## Troubleshooting:
- Make sure all three IDs are correctly replaced
- Check browser console for any error messages
- Verify your EmailJS service is connected properly
- Ensure your template variables match the code

---

**Alternative**: If you prefer a simpler setup without EmailJS, you can use services like:
- Formspree (formspree.io)
- Web3Forms (web3forms.com)
- Getform (getform.io)

