# EmailJS Setup Guide for Contact Form

This guide will help you set up EmailJS so your contact form can send emails directly without opening the user's email client.

## Step 1: Create an EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click **"Sign Up"** (top right corner)
3. Sign up using:
   - Email and password, OR
   - Google account (recommended - faster)
4. Verify your email if required

## Step 2: Add an Email Service

1. After logging in, go to **"Email Services"** in the left sidebar
2. Click **"Add New Service"**
3. Choose your email provider:
   - **Gmail** (recommended - most common)
   - **Outlook**
   - **Yahoo**
   - Or any other supported service
4. Click on your chosen service
5. Follow the instructions to connect your email:
   - For Gmail: You'll need to authorize EmailJS to send emails on your behalf
   - Click **"Connect Account"** and sign in with your Gmail
   - Grant the necessary permissions
6. Once connected, you'll see your **Service ID** (e.g., `service_abc123`)
   - **Copy this Service ID** - you'll need it later!

## Step 3: Create an Email Template

1. Go to **"Email Templates"** in the left sidebar
2. Click **"Create New Template"**
3. Choose a template or start from scratch
4. Configure your template:

   **Template Name:** `portfolio_contact` (or any name you prefer)

   **Subject:** `Portfolio Contact: {{subject}}`

   **Content (HTML or Plain Text):**
   ```
   New message from your portfolio contact form!
   
   Name: {{from_name}}
   Email: {{from_email}}
   Company: {{company}}
   Subject: {{subject}}
   
   Message:
   {{message}}
   
   ---
   This email was sent from your portfolio website.
   ```

   **To Email:** `sorenramesh868@gmail.com` (your email address)
   
   **From Name:** `{{from_name}}`
   
   **Reply To:** `{{from_email}}` (so you can reply directly)

5. Click **"Save"**
6. You'll see your **Template ID** (e.g., `template_xyz789`)
   - **Copy this Template ID** - you'll need it later!

## Step 4: Get Your Public Key

1. Go to **"Account"** in the left sidebar (or click your profile icon)
2. Scroll down to **"API Keys"** section
3. You'll see your **Public Key** (e.g., `abcdefghijklmnop`)
   - **Copy this Public Key** - you'll need it later!
   - ⚠️ Keep this key private - don't share it publicly

## Step 5: Update Your Code

1. Open `index.html` in your editor
2. Find the EmailJS script tag (around line 15) and **uncomment it**:
   ```html
   <!-- Change this: -->
   <!-- <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script> -->
   
   <!-- To this: -->
   <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
   ```

3. Find the EmailJS configuration section (around line 1745) and update:
   ```javascript
   const USE_EMAILJS = true; // Change from false to true
   const serviceID = 'service_abc123'; // Paste your Service ID here
   const templateID = 'template_xyz789'; // Paste your Template ID here
   const publicKey = 'abcdefghijklmnop'; // Paste your Public Key here
   ```

4. Save the file
5. Test your contact form!

## Step 6: Test Your Contact Form

1. Open your portfolio website
2. Scroll to the Contact section
3. Fill out the form with test data
4. Click "Send Message"
5. Check your email inbox (sorenramesh868@gmail.com)
6. You should receive the email!

## Troubleshooting

### Email not received?
- Check your spam/junk folder
- Verify your Service ID, Template ID, and Public Key are correct
- Check the browser console (F12) for any error messages
- Make sure the EmailJS script is loaded (uncommented)

### Getting errors?
- **"Service ID not found"**: Double-check your Service ID
- **"Template ID not found"**: Double-check your Template ID
- **"Invalid Public Key"**: Double-check your Public Key
- **"EmailJS is not defined"**: Make sure you uncommented the script tag

### Free Tier Limits
- EmailJS free tier: **200 emails per month**
- This is usually enough for a portfolio website
- If you need more, consider upgrading to a paid plan

## Security Note

Your Public Key is safe to use in frontend code - it's designed to be public. However, for additional security, you can:
- Set up domain restrictions in EmailJS dashboard
- Use environment variables if deploying to a platform that supports them

## Need Help?

- EmailJS Documentation: https://www.emailjs.com/docs/
- EmailJS Support: Check their help center or community forums

---

**Quick Reference:**
- Service ID: Found in "Email Services" → Your service
- Template ID: Found in "Email Templates" → Your template
- Public Key: Found in "Account" → API Keys

