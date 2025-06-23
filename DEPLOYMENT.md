# Deployment Guide

This guide will help you deploy your Travel Itinerary Creator to Netlify.

## Prerequisites

- GitHub account
- Netlify account
- Your project code ready

## Step 1: Push to GitHub

### Option A: Using GitHub CLI (Recommended)

```bash
# Install GitHub CLI if you haven't already
# Visit: https://cli.github.com/

# Authenticate with GitHub
gh auth login

# Create a new repository
gh repo create travel-itinerary-creator --public --description "AI-powered travel itinerary creator"

# Initialize git and push
git init
git add .
git commit -m "Initial commit: Travel Itinerary Creator"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/travel-itinerary-creator.git
git push -u origin main
```

### Option B: Using GitHub Web Interface

1. **Create Repository on GitHub**:
   - Go to [github.com](https://github.com)
   - Click "New repository"
   - Name: `travel-itinerary-creator`
   - Description: "AI-powered travel itinerary creator"
   - Make it Public
   - Don't initialize with README (we already have one)
   - Click "Create repository"

2. **Push Your Code**:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Travel Itinerary Creator"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/travel-itinerary-creator.git
   git push -u origin main
   ```

## Step 2: Connect to Netlify

### 1. Sign Up/Login to Netlify
- Go to [netlify.com](https://netlify.com)
- Sign up with GitHub (recommended) or create an account

### 2. Create New Site
- Click "New site from Git" on your Netlify dashboard
- Choose "GitHub" as your Git provider
- Authorize Netlify to access your GitHub repositories

### 3. Configure Build Settings
- Select your `travel-itinerary-creator` repository
- Netlify should auto-detect the settings:
  - **Build command**: `npm run build`
  - **Publish directory**: `dist`
  - **Branch to deploy**: `main`

### 4. Add Environment Variables
Before deploying, add your environment variables:

1. Go to Site Settings > Environment Variables
2. Add the following variables:

```
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key
VITE_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
OPENAI_API_KEY=your_openai_api_key
VITE_APP_URL=https://your-site-name.netlify.app
```

### 5. Deploy
- Click "Deploy site"
- Netlify will build and deploy your site
- You'll get a URL like `https://amazing-name-123456.netlify.app`

## Step 3: Custom Domain (Optional)

### Using Netlify Subdomain
- Go to Site Settings > Domain Management
- Click "Change site name"
- Choose a custom name: `your-app-name.netlify.app`

### Using Your Own Domain
1. Go to Site Settings > Domain Management
2. Click "Add custom domain"
3. Enter your domain name
4. Follow Netlify's DNS configuration instructions

## Step 4: Configure Supabase

### Update Supabase Settings
1. Go to your Supabase dashboard
2. Navigate to Authentication > Settings
3. Add your Netlify URL to "Site URL" and "Redirect URLs":
   - `https://your-site-name.netlify.app`
   - `https://your-site-name.netlify.app/**`

### Update Environment Variables
Make sure your `VITE_APP_URL` environment variable in Netlify matches your deployed URL.

## Step 5: Test Your Deployment

1. **Visit Your Site**: Go to your Netlify URL
2. **Test Key Features**:
   - User registration/login
   - Itinerary creation
   - Payment flow (use Stripe test mode)
   - PDF generation

## Continuous Deployment

Once connected, Netlify will automatically:
- Deploy when you push to the `main` branch
- Show build logs and deployment status
- Provide deploy previews for pull requests

## Troubleshooting

### Build Fails
- Check build logs in Netlify dashboard
- Ensure all environment variables are set
- Verify your code builds locally: `npm run build`

### Environment Variables Not Working
- Ensure variables start with `VITE_` for client-side access
- Restart deployment after adding variables
- Check variable names match exactly

### Supabase Connection Issues
- Verify Supabase URLs in environment variables
- Check Supabase authentication settings
- Ensure RLS policies are correctly configured

### Payment Issues
- Use Stripe test keys for testing
- Verify webhook endpoints in Stripe dashboard
- Check CORS settings if needed

## Next Steps

1. **Monitor**: Set up monitoring and analytics
2. **Optimize**: Enable Netlify's performance features
3. **Secure**: Review security headers in `netlify.toml`
4. **Scale**: Consider upgrading Netlify plan for higher limits

## Support

- [Netlify Documentation](https://docs.netlify.com/)
- [Supabase Documentation](https://supabase.com/docs)
- [GitHub Issues](https://github.com/YOUR_USERNAME/travel-itinerary-creator/issues)