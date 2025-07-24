# Email Contact Form Setup Guide

Your contact form has been configured to send emails using EmailJS. Follow these steps to complete the setup:

## Step 1: Create an EmailJS Account

1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

## Step 2: Create an Email Service

1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the instructions to connect your email account
5. Note down the **Service ID** (you'll need this later)

## Step 3: Create an Email Template

1. Go to "Email Templates" in your dashboard
2. Click "Create New Template"
3. Use this template structure:

**Subject:** New Contact Form Message from {{from_name}}

**Content:**
```
Hello Njoh,

You have received a new message from your portfolio contact form:

From: {{from_name}}
Email: {{from_email}}

Message:
{{message}}

---
This message was sent from your portfolio website contact form.
```

4. Save the template and note down the **Template ID**

## Step 4: Get Your Public Key

1. Go to "Account" → "General" in your EmailJS dashboard
2. Find your **Public Key** (also called User ID)

## Step 5: Update Your Website Code

Open `script.js` and replace the following placeholders:

1. Replace `"YOUR_PUBLIC_KEY"` with your actual public key
2. Replace `"YOUR_SERVICE_ID"` with your service ID
3. Replace `"YOUR_TEMPLATE_ID"` with your template ID

Example:
```javascript
// Replace this line:
emailjs.init("YOUR_PUBLIC_KEY");

// With something like:
emailjs.init("your_actual_public_key_here");

// And replace this line:
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)

// With something like:
emailjs.send('service_123abc', 'template_456def', templateParams)
```

## Step 6: Test Your Contact Form

1. Save all your files
2. Open your website in a browser
3. Fill out the contact form and submit it
4. Check your email to see if you received the message

## Important Notes

- EmailJS free plan allows up to 200 emails per month
- Make sure your email service is properly configured and verified
- Test with different email addresses to ensure it's working
- The form will show success/error messages to visitors

## Troubleshooting

If emails aren't being sent:
1. Check the browser console for error messages
2. Verify all IDs are correct in your code
3. Make sure your email service is active in EmailJS
4. Check your spam folder for test emails

## Security

Your EmailJS credentials are safe to use in client-side code as they're designed for public use. However, you can set up domain restrictions in your EmailJS dashboard for added security.
