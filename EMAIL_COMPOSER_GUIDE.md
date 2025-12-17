# AI-Powered Email Composer Guide

## 🎯 Overview

The in-platform email composer allows you to craft and send professional follow-up emails to customers using AI assistance. You can generate, edit, preview, and send emails directly from the platform.

## ✨ Features

- **AI Email Generation**: Automatically generates professional emails based on feedback
- **In-Platform Composing**: Craft emails directly in the platform
- **Live Preview**: Preview emails before sending
- **Custom Instructions**: Guide AI with specific requirements
- **Edit & Customize**: Full control to edit AI-generated content
- **One-Click Send**: Send emails directly from the platform

## 🚀 How to Use

### Step 1: Access Email Composer

1. Go to **Feedback** page
2. Click on any feedback item that has a customer email
3. Scroll down to **"Send Follow-up Email"** section
4. Click **"🤖 Compose Email with AI"** button

### Step 2: AI Generates Email

- The AI automatically generates:
  - Professional subject line
  - Personalized email body
  - HTML formatted content
- The email is tailored based on:
  - Customer's feedback rating
  - Feedback content
  - Store information
  - Customer name

### Step 3: Customize (Optional)

**Edit Subject:**
- Click on the subject field
- Modify as needed
- Or click "🤖 Regenerate with AI" for a new subject

**Edit Body:**
- Modify the email body text
- Add personal touches
- Include specific details

**AI Instructions:**
- Add custom instructions in the "AI Instructions" field
- Examples:
  - "Make it more empathetic"
  - "Focus on quality issues"
  - "Be more formal"
  - "Add discount offer"
- Click "🤖 Regenerate with AI" to apply instructions

### Step 4: Preview

1. Click **"Preview"** button
2. See how the email will look to the customer
3. Switch back to **"Edit"** to make changes

### Step 5: Send

1. Review the email one final time
2. Click **"Send Email"** button
3. Email is sent (or logged in mock mode)
4. Follow-up is recorded in the system

## 📧 Email Content

### For Negative Feedback (Rating ≤ 2)
- Apologetic tone
- Acknowledges the issue
- Requests more details
- Offers solutions
- Professional and empathetic

### For Positive Feedback (Rating ≥ 4)
- Appreciative tone
- Thanks the customer
- Requests additional details
- Encourages future visits
- Warm and friendly

## 🎨 Email Composer Interface

### Header Section
- Shows customer email
- Customer name
- Store information

### Subject Field
- Editable subject line
- "Regenerate with AI" button
- Auto-generated based on feedback

### Body Editor
- Large text area for editing
- Monospace font for clarity
- Full editing capabilities

### AI Instructions
- Optional field for custom guidance
- Helps refine AI generation
- Examples provided

### Preview Mode
- HTML formatted preview
- Shows exactly how customer will see it
- Professional styling

### Footer Actions
- Cancel button
- Send Email button
- Loading states

## 💡 Tips for Best Results

1. **Use AI Instructions**: Provide specific guidance for better results
   - "Make it more formal"
   - "Focus on delivery issues"
   - "Include discount offer"

2. **Personalize**: Edit AI-generated content to add personal touches

3. **Review Before Sending**: Always preview before sending

4. **Test First**: Use test data to practice before sending real emails

5. **Customize Per Customer**: Adjust tone based on customer's feedback

## 🧪 Testing

### Load Test Data

1. Go to **Upload** page (Admin only)
2. Click **"Load Test Data with Emails"** button
3. 10 test feedback entries with emails will be loaded
4. Use these to test the email composer

### Test Data Includes:
- Various ratings (1-5 stars)
- Different stores
- Different products
- Customer names and emails
- Diverse feedback scenarios

## 📊 Follow-up Tracking

After sending:
- Follow-up is recorded in **Follow-ups** page
- Status: "Sent"
- Can be updated to "Replied", "Resolved", or "Closed"
- Full history maintained

## 🔧 Technical Details

### AI Generation
- Uses OpenAI GPT-3.5 (if API key configured)
- Falls back to rule-based generation (if no API key)
- Considers feedback context and rating
- Generates professional, empathetic content

### Email Formatting
- HTML emails with professional styling
- Responsive design
- UrbanStyle branding
- Plain text fallback

### Storage
- Email content stored in follow-up records
- Subject, body, and HTML preserved
- Full audit trail

## 🎯 Use Cases

1. **Negative Feedback Follow-up**
   - Generate empathetic apology email
   - Request more details about the issue
   - Offer solutions

2. **Positive Feedback Follow-up**
   - Thank customer for feedback
   - Request additional details
   - Encourage future visits

3. **Neutral Feedback Follow-up**
   - Gather more information
   - Understand customer experience
   - Identify improvement areas

## 🚨 Important Notes

- **Email Required**: Customer email must be available
- **Role Permissions**: Admin, Manager, and CX Lead can send
- **Store Managers**: Can only send for their store
- **Mock Mode**: Emails logged to console if not configured
- **Real Emails**: Configure `.env` file for actual sending

## 📝 Example Workflow

1. Customer submits negative feedback (Rating: 2)
2. Manager clicks on feedback → "Compose Email with AI"
3. AI generates empathetic follow-up email
4. Manager adds custom instruction: "Offer 20% discount"
5. Manager regenerates email with new instruction
6. Manager reviews and edits if needed
7. Manager previews email
8. Manager clicks "Send Email"
9. Email sent to customer
10. Follow-up recorded in system

---

**The email composer is fully integrated and ready to use!** 🚀

Start by loading test data, then try composing your first AI-powered email.

