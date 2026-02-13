# Vercel Deployment Guide for Bud Hunters

This guide will help you deploy the Bud Hunters application to Vercel.

## Prerequisites

- A GitHub account with access to the repository
- A Vercel account (free tier works perfectly)

## Quick Deploy (Recommended)

### Method 1: One-Click Deploy Button

Click the button below to deploy directly to Vercel:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Trade-Grant/Bud-Hunters3)

This will:
1. Fork/clone the repository to your account
2. Automatically configure the project
3. Deploy the application
4. Provide you with a live URL

### Method 2: Import from Vercel Dashboard

1. **Go to Vercel Dashboard**
   - Visit https://vercel.com/new
   - Log in with your GitHub account

2. **Import Repository**
   - Click "Import Git Repository"
   - Select "Trade-Grant/Bud-Hunters3" from your repositories
   - Or paste the repository URL: `https://github.com/Trade-Grant/Bud-Hunters3`

3. **Configure Project**
   - Vercel will auto-detect the framework (Create React App)
   - The configuration is already set in `vercel.json`:
     - Build Command: `npm run build`
     - Output Directory: `build`
     - Install Command: `npm install`
   
4. **Deploy**
   - Click "Deploy"
   - Wait 2-3 minutes for the build to complete
   - Your site will be live!

## Project Configuration

The repository includes a pre-configured `vercel.json` file with:

### Build Settings
```json
{
  "buildCommand": "npm run build",
  "outputDirectory": "build",
  "devCommand": "npm start",
  "installCommand": "npm install",
  "framework": "create-react-app"
}
```

### Routing Configuration
- **SPA Routing**: All routes redirect to `index.html` for client-side routing
- This ensures the React app works correctly on all URLs

### Security Headers
The deployment includes security headers for:
- `X-Content-Type-Options`: Prevents MIME type sniffing
- `X-Frame-Options`: Prevents clickjacking
- `X-XSS-Protection`: Enables XSS filtering

### Caching Strategy
- Static assets in `/static/` are cached for 1 year (immutable)
- Optimizes performance and reduces bandwidth

## After Deployment

### Your Live URL
After deployment, Vercel will provide you with:
- Production URL: `https://bud-hunters3.vercel.app` (or similar)
- Preview URLs for each branch/PR
- Custom domain options (optional)

### What Users Can Do
✅ View and search cannabis strains
✅ Add strain reviews and ratings
✅ Filter by strain type (Indica, Sativa, Hybrid)
✅ Track effects and experiences
✅ Data persists in browser localStorage

## Environment Variables (Optional)

Currently, the app doesn't require environment variables as it uses:
- **localStorage** for data persistence (client-side only)
- No backend API or database

If you need to add environment variables in the future:
1. Go to Project Settings in Vercel dashboard
2. Navigate to "Environment Variables"
3. Add variables with the format: `REACT_APP_VARIABLE_NAME`

## Custom Domain (Optional)

To use a custom domain:
1. Go to your project settings in Vercel
2. Click "Domains"
3. Add your domain and follow DNS instructions
4. Vercel automatically provisions SSL certificates

## Continuous Deployment

Vercel automatically sets up continuous deployment:
- **Production**: Deploys from `main` branch
- **Preview**: Deploys from all other branches and PRs
- Automatic builds on every push

## Troubleshooting

### Build Fails

If the build fails:
1. Check the build logs in Vercel dashboard
2. Ensure all dependencies are in `package.json`
3. Verify Node.js version compatibility (Vercel uses Node 18.x by default)

**Common fixes:**
```bash
# Clear cache and rebuild
rm -rf node_modules package-lock.json
npm install
npm run build
```

### App Not Loading

If the app deploys but doesn't load:
1. Check browser console for errors (F12)
2. Verify all assets loaded in Network tab
3. Check that `vercel.json` rewrites are configured correctly

### 404 Errors on Routes

If you get 404 errors when refreshing pages:
- Ensure the `rewrites` section in `vercel.json` is configured
- This redirects all routes to `index.html` for SPA routing

## Local Development

To test locally before deploying:

```bash
# Install dependencies
npm install

# Start development server
npm start

# Build for production
npm run build

# Test production build locally
npx serve -s build
```

## Support

For issues:
- **Vercel Documentation**: https://vercel.com/docs
- **Repository Issues**: https://github.com/Trade-Grant/Bud-Hunters3/issues
- **Deployment Logs**: Check Vercel dashboard for detailed logs

## Performance

The deployed app is highly optimized:
- **Bundle Size**: 49.31 kB (gzipped)
- **Load Time**: < 1 second on fast connections
- **CDN**: Vercel's global edge network
- **SSL**: Automatic HTTPS
- **Compression**: Automatic Gzip/Brotli

## Next Steps After Deployment

1. ✅ Visit your live site
2. ✅ Test all features (add strain, search, filter)
3. ✅ Share the URL with users
4. ✅ Monitor analytics in Vercel dashboard (optional)
5. ✅ Set up custom domain (optional)

---

## Quick Reference

**Vercel Dashboard**: https://vercel.com/dashboard
**Deploy Button**: [Click Here](https://vercel.com/new/clone?repository-url=https://github.com/Trade-Grant/Bud-Hunters3)
**Documentation**: See `DEPLOYMENT.md` for other deployment options

---

🎉 **Your Bud Hunters app is ready for Vercel!**

The configuration is complete. Just click the deploy button or import from Vercel dashboard!
