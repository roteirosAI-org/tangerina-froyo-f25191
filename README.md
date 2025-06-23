# Travel Itinerary Creator

An AI-powered travel itinerary creator built with React, TypeScript, and Tailwind CSS.

## 🚀 Live Demo

Visit the live application: [Your App URL will be here after deployment]

## Features

- Multi-language support (English, Portuguese, Spanish)
- AI-powered itinerary generation
- Multiple payment methods (Credit Card, PIX, PayPal)
- Responsive design
- Interactive form wizard
- Real-time previews
- PDF export

## Tech Stack

- React 18
- TypeScript
- Vite
- Tailwind CSS
- React Router
- React Intl
- Framer Motion
- Stripe
- PayPal
- Lucide Icons
- Supabase (Database & Authentication)

## Getting Started

1. Clone the repository
   ```bash
   git clone https://github.com/YOUR_USERNAME/travel-itinerary-creator.git
   cd travel-itinerary-creator
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Copy `.env.example` to `.env` and fill in your environment variables:
   ```bash
   cp .env.example .env
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

## 🌐 Deployment

This project is configured for easy deployment on Netlify:

### Automatic Deployment (Recommended)

1. **Push to GitHub** (see instructions below)
2. **Connect to Netlify**:
   - Go to [Netlify](https://netlify.com)
   - Click "New site from Git"
   - Choose GitHub and select your repository
   - Netlify will automatically detect the build settings
3. **Configure Environment Variables** in Netlify dashboard
4. **Deploy!** - Your site will be live at `https://your-site-name.netlify.app`

### Manual Deployment

```bash
npm run build
# Upload the `dist` folder to your hosting provider
```

## 📚 Setup Instructions

### 1. Push to GitHub

```bash
# Initialize git repository (if not already done)
git init

# Add all files
git add .

# Commit changes
git commit -m "Initial commit: Travel Itinerary Creator"

# Add remote repository (replace with your GitHub repo URL)
git remote add origin https://github.com/YOUR_USERNAME/travel-itinerary-creator.git

# Push to GitHub
git push -u origin main
```

### 2. Connect to Netlify

1. **Create a Netlify Account**: Go to [netlify.com](https://netlify.com) and sign up
2. **New Site from Git**: Click "New site from Git" on your dashboard
3. **Choose GitHub**: Select GitHub as your Git provider
4. **Select Repository**: Choose your `travel-itinerary-creator` repository
5. **Build Settings**: Netlify should auto-detect:
   - Build command: `npm run build`
   - Publish directory: `dist`
6. **Environment Variables**: Add your environment variables in Site Settings > Environment Variables
7. **Deploy**: Click "Deploy site"

### 3. Environment Variables for Netlify

Add these in your Netlify dashboard under Site Settings > Environment Variables:

```
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key
VITE_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
OPENAI_API_KEY=your_openai_api_key
```

## Environment Variables

Required environment variables:

- `VITE_STRIPE_PUBLISHABLE_KEY`: Your Stripe publishable key
- `STRIPE_SECRET_KEY`: Your Stripe secret key
- `SMTP_HOST`: SMTP server host
- `SMTP_PORT`: SMTP server port
- `SMTP_USER`: SMTP username
- `SMTP_PASS`: SMTP password
- `EMAIL_FROM`: Sender email address
- `PIX_KEY`: Your PIX key (Brazil)
- `PAYPAL_CLIENT_ID`: PayPal client ID
- `PAYPAL_CLIENT_SECRET`: PayPal client secret

## Project Structure

```
src/
├── components/     # React components
├── context/       # React context providers
├── lib/           # Utility functions and services
├── locales/       # Internationalization files
├── pages/         # Page components
└── styles/        # Global styles
```

## Available Scripts

- `npm run dev`: Start development server
- `npm run build`: Build for production
- `npm run preview`: Preview production build
- `npm run lint`: Run ESLint

## 🔧 Development

### Adding New Features

1. Create a new branch: `git checkout -b feature/your-feature-name`
2. Make your changes
3. Commit: `git commit -m "Add your feature"`
4. Push: `git push origin feature/your-feature-name`
5. Create a Pull Request on GitHub

### Database Changes

This project uses Supabase for the database. To make schema changes:

1. Create a new migration file in `supabase/migrations/`
2. Test locally with Supabase CLI (if available)
3. Deploy changes through Supabase dashboard

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📞 Support

If you encounter any issues:

1. Check the [Issues](https://github.com/YOUR_USERNAME/travel-itinerary-creator/issues) page
2. Create a new issue if your problem isn't already reported
3. Provide detailed information about the problem

## License

MIT License