# 🔐 Tafus OAuth Integration (n8n)

Google OAuth 2.0 integration with n8n workflows for automated WhatsApp message handling.

## 📁 Contents
- `README.md`: This guide
- `credentials.txt`: OAuth credentials configuration  
- `notes.md`: Implementation notes and best practices
- 
![WhatsApp Image 2025-08-03 at 2 24 06 PM](https://github.com/user-attachments/assets/c37f1be0-e6ac-480b-8aec-4af40b38aa94)


## 🚀 Quick Setup

### 1. Google Cloud Configuration
1. Create project in [Google Cloud Console](https://console.cloud.google.com/)
2. Enable required APIs (Google+, Gmail, Drive)
3. Create OAuth 2.0 Client ID with redirect URI:
   ```
   https://your-n8n-instance.com/rest/oauth2-credential/callback
   ```

### 2. n8n Configuration
1. Create **OAuth2 Generic** credential in n8n
2. Add Google OAuth details:
   - **Client ID**: Your Google client ID
   - **Client Secret**: Your Google client secret  
   - **Auth URL**: `https://accounts.google.com/o/oauth2/v2/auth`
   - **Token URL**: `https://oauth2.googleapis.com/token`
   - **Scope**: `https://www.googleapis.com/auth/userinfo.profile https://www.googleapis.com/auth/userinfo.email`

### 3. Environment Variables
```bash
# Google OAuth
GOOGLE_CLIENT_ID=your_client_id
GOOGLE_CLIENT_SECRET=your_client_secret
GOOGLE_REDIRECT_URI=https://your-n8n-instance.com/rest/oauth2-credential/callback

# WhatsApp API
WHATSAPP_API_URL=https://api.whatsapp.business/v1
WHATSAPP_ACCESS_TOKEN=your_token
WHATSAPP_PHONE_NUMBER_ID=your_phone_id

# n8n Instance
N8N_HOST=https://your-n8n-instance.com
```

## 🔧 Basic Workflow

1. **Webhook Trigger** → Receives WhatsApp messages
2. **OAuth Authentication** → Validates user with Google
3. **Process Message** → Handles authenticated requests

## 🎯 Key Features

- **Secure OAuth 2.0** authentication
- **Automated WhatsApp** message processing  
- **Error handling** and retry mechanisms
- **Scalable architecture** for production use

## 📋 Prerequisites

- n8n instance (self-hosted or cloud)
- Google Cloud Platform account
- WhatsApp Business API credentials
- Basic OAuth 2.0 knowledge

## 🔍 Testing

1. Use `http://localhost:5678` for local development
2. Ensure redirect URIs match exactly in Google Console
3. Test token refresh functionality
4. Validate all required API scopes

---

**Ready to integrate!** Follow the setup steps above and your OAuth + WhatsApp automation will be running smoothly.
