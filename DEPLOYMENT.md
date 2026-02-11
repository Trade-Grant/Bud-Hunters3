# Deployment Guide for Bud Hunters

This document provides detailed deployment instructions for the Bud Hunters application.

## Prerequisites

- Node.js 16.x or higher
- npm or yarn package manager
- Git

## Deployment Options

### 1. GitHub Pages (Recommended - Free & Automatic)

GitHub Pages deployment is automatically configured via GitHub Actions.

**Setup Steps:**

1. Go to your repository settings on GitHub
2. Navigate to **Pages** section
3. Under "Source", select **GitHub Actions**
4. Push changes to the `main` branch
5. The workflow will automatically:
   - Install dependencies
   - Build the React app
   - Deploy to GitHub Pages
6. Your site will be available at: `https://[username].github.io/Bud-Hunters3/`

**Workflow File:** `.github/workflows/static.yml`

The workflow runs on:
- Every push to `main` branch
- Manual trigger via Actions tab

### 2. Vercel (Recommended for Production)

Vercel offers excellent performance and automatic deployments.

**Quick Deploy:**

1. Click the "Deploy to Vercel" button in README
2. Or install Vercel CLI: `npm i -g vercel`
3. Run `vercel` in project directory
4. Follow the prompts
5. Your site will be live at a Vercel URL

**Configuration:** The `vercel.json` file is already configured with:
- Build command: `npm run build`
- Output directory: `build`
- Framework: Create React App

### 3. Netlify

Netlify is another excellent option for React apps.

**Deploy Steps:**

1. Create account at netlify.com
2. Click "New site from Git"
3. Connect your GitHub repository
4. Configure build settings:
   - Build command: `npm run build`
   - Publish directory: `build`
5. Click "Deploy site"

### 4. Other Static Hosting

The built application in the `build` folder can be deployed to any static hosting service:

- **AWS S3 + CloudFront**
- **Google Cloud Storage**
- **Azure Static Web Apps**
- **Firebase Hosting**
- **Surge.sh**

**Build the app:**
```bash
npm run build
```

Then upload the contents of the `build` folder to your hosting service.

## Environment Variables

Currently, the app doesn't require any environment variables. All data is stored in the browser's localStorage.

If you need to add environment variables in the future:

1. Create a `.env` file in the root directory
2. Add variables prefixed with `REACT_APP_`:
   ```
   REACT_APP_API_URL=https://api.example.com
   ```
3. Access in code: `process.env.REACT_APP_API_URL`

## Post-Deployment Verification

After deployment, verify:

1. ✅ Homepage loads correctly
2. ✅ Can add new strain reviews
3. ✅ Search functionality works
4. ✅ Data persists after page reload (localStorage)
5. ✅ All strain type filters work
6. ✅ External links open correctly

## Troubleshooting

### Build Fails

- Ensure Node.js version is 16.x or higher
- Delete `node_modules` and `package-lock.json`, then run `npm install`
- Check for TypeScript errors: `npm run build`

### App Not Loading

- Check browser console for errors
- Verify all assets are loading (check Network tab)
- Ensure JavaScript is enabled

### Data Not Persisting

- Check if localStorage is enabled in browser
- Verify browser privacy settings allow localStorage
- Check browser console for localStorage errors

## Performance Optimization

The app is already optimized with:
- Production build minification
- Code splitting
- Lazy loading where applicable

For further optimization:
- Enable Gzip/Brotli compression on your hosting
- Use a CDN for static assets
- Implement service workers for PWA capabilities

## Support

For issues or questions:
- Open an issue on GitHub
- Check existing issues for solutions
- Review the main README for additional information
