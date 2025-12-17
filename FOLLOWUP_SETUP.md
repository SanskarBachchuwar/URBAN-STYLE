# Customer Follow-up Email System

## 📧 Overview

The follow-up email system allows store managers and CX leads to send personalized follow-up emails to customers who have submitted feedback. This helps gather more details about customer experiences and improve service quality.

## ✨ Features

- **Send Follow-up Emails**: Managers can send personalized emails to customers
- **Track Follow-ups**: All follow-ups are recorded and tracked
- **Status Management**: Track follow-up status (sent, replied, resolved, closed)
- **CX Lead Visibility**: CX leads can view all follow-ups across all stores
- **Email Templates**: Professional HTML email templates
- **Mock Mode**: Works without email configuration for testing

## 🚀 Setup

### Option 1: Mock Mode (No Email Configuration)

The system works in mock mode by default. Emails will be logged to the console instead of being sent.

**No setup required!** Just use the system and check the backend console for email logs.

### Option 2: Real Email (Production)

To send actual emails, configure email settings:

1. **Install nodemailer** (already in package.json):
   ```bash
   cd backend
   npm install
   ```

2. **Create `.env` file** in the `backend` directory:
   ```env
   EMAIL_HOST=smtp.gmail.com
   EMAIL_PORT=587
   EMAIL_SECURE=false
   EMAIL_USER=your-email@gmail.com
   EMAIL_PASS=your-app-password
   ```

3. **For Gmail**:
   - Enable 2-factor authentication
   - Generate an App Password: https://myaccount.google.com/apppasswords
   - Use the app password in `EMAIL_PASS`

4. **For Other Email Providers**:
   - Update `EMAIL_HOST` with your SMTP server
   - Update `EMAIL_PORT` (587 for TLS, 465 for SSL)
   - Set `EMAIL_SECURE=true` for SSL

## 📋 Data Format

### CSV Upload Format

When uploading feedback from Microsoft Forms, include these columns:

```csv
store,channel,product,rating,comment,customerName,customerEmail,createdAt
Mumbai,Microsoft Form,T-Shirt,2,"delivery was late",Rajesh Kumar,rajesh.kumar@email.com,2025-01-15
```

**Required Fields:**
- `store`: Store name
- `rating`: Rating (1-5)
- `comment`: Feedback comment
- `customerName`: Customer's name (optional but recommended)
- `customerEmail`: Customer's email (required for follow-ups)

### JSON Format

```json
[
  {
    "store": "Mumbai",
    "channel": "Microsoft Form",
    "product": "T-Shirt",
    "rating": 2,
    "comment": "delivery was late",
    "customerName": "Rajesh Kumar",
    "customerEmail": "rajesh.kumar@email.com",
    "createdAt": "2025-01-15"
  }
]
```

## 🎯 How to Use

### For Store Managers

1. **View Feedback**: Go to Feedback page
2. **Click on Feedback**: Click any feedback item to see details
3. **Send Follow-up**: 
   - If customer email is available, you'll see "Send Follow-up Email" button
   - Add optional custom message
   - Click "Send Follow-up Email"
4. **Track Follow-ups**: Go to "Follow-ups" page to see all sent follow-ups

### For CX Leads

1. **View All Follow-ups**: Go to "Follow-ups" page
2. **See Statistics**: View follow-up statistics across all stores
3. **Monitor Status**: Track which follow-ups have been replied to or resolved
4. **View Feedback**: Click "View Feedback" to see original feedback

## 📊 Follow-up Status

- **Sent**: Email has been sent to customer
- **Replied**: Customer has replied to the follow-up
- **Resolved**: Issue has been resolved
- **Closed**: Follow-up is closed

## 📧 Email Template

The system generates professional HTML emails with:

- **Personalized greeting** with customer name
- **Store-specific content** based on feedback rating
- **Professional formatting** with UrbanStyle branding
- **Clear call-to-action** for customer response
- **Manager signature** with store information

### Email Content

**For Negative Feedback (Rating ≤ 2):**
- Apology for the experience
- Request for more details about the issue
- Commitment to improvement
- Contact information

**For Positive Feedback (Rating ≥ 4):**
- Thank you message
- Request for additional details
- Appreciation for feedback

## 🔧 API Endpoints

### Send Follow-up
```
POST /followup/send
Body: {
  feedbackId: "FB001",
  customMessage: "Optional custom message"
}
```

### Get Follow-ups
```
GET /followup
GET /followup/feedback/:feedbackId
```

### Update Status
```
PUT /followup/:id/status
Body: {
  status: "replied",
  notes: "Customer responded with..."
}
```

### Get Statistics
```
GET /followup/stats
```

## 📝 Follow-up Tracking

All follow-ups are stored in `backend/data/followUps.json` with:

- Follow-up ID
- Feedback ID reference
- Customer information
- Store information
- Sent by (manager/CX lead)
- Status and timestamps
- Email result (message ID, mode)

## 🎨 UI Features

### Feedback Detail Modal
- Shows customer name and email (if available)
- "Send Follow-up Email" button (if email available)
- Custom message field
- Status indicator if follow-up already sent

### Follow-ups Page
- Statistics dashboard
- Complete follow-up history table
- Status badges
- Filter by store (for managers)
- View original feedback

## 💡 Best Practices

1. **Send Follow-ups Promptly**: Send within 24-48 hours of feedback
2. **Personalize Messages**: Use custom message field for specific cases
3. **Track Responses**: Update status when customers reply
4. **Follow Up on Follow-ups**: Check status regularly
5. **Document Resolutions**: Add notes when resolving issues

## 🔐 Permissions

- **Store Manager**: Can send follow-ups for their store only
- **CX Lead**: Can send follow-ups for any store, view all follow-ups
- **Admin**: Full access to all follow-up features

## 🐛 Troubleshooting

### Email Not Sending
- Check `.env` file configuration
- Verify email credentials
- Check SMTP server settings
- Review backend console for errors

### Mock Mode Active
- If emails are logged to console, mock mode is active
- Configure `.env` file to enable real emails
- Restart backend server after configuration

### Customer Email Missing
- Ensure CSV/JSON includes `customerEmail` or `email` field
- Check Microsoft Forms includes email field
- Verify data format matches expected structure

## 📈 Future Enhancements

- Email reply tracking
- Automated follow-up scheduling
- Email templates customization
- Customer response integration
- Follow-up analytics dashboard

---

**The follow-up system is ready to use!** Start by uploading feedback with customer emails, then use the Feedback page to send follow-ups.

