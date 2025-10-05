# Google Authentication Setup

## 1. Google OAuth Configuration

1. Go to the [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. Enable the Google+ API
4. Go to "Credentials" and create OAuth 2.0 Client IDs
5. Set authorized redirect URIs:
   - For development: `http://localhost:3000/auth/callback/google`
   - For production: `https://yourdomain.com/auth/callback/google`

## 2. Environment Variables

Copy the `.env.local` file and fill in your Google OAuth credentials:

```bash
# NextAuth.js Configuration
AUTH_SECRET=your-random-secret-string-here
NEXTAUTH_URL=http://localhost:3000

# Google OAuth Configuration  
AUTH_GOOGLE_ID=your-google-client-id
AUTH_GOOGLE_SECRET=your-google-client-secret
```

## 3. Generate AUTH_SECRET

Run this command to generate a secure secret:

```bash
openssl rand -base64 32
```

## 4. Start the Development Server

```bash
npm run dev
```

Your app will be available at `http://localhost:3000`