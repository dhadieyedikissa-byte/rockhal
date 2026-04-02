# Deployment Guide - RockHal Project

## ✅ What's Already Done

✓ **GitHub Actions CI/CD Workflow** - Created `.github/workflows/main.yml`
  - Automatically runs tests on every push to `main`
  - Installs dependencies with `npm ci`
  - Builds the Next.js project
  - Runs linter checks

✓ **Vercel Configuration** - Added `vercel.json`
  - Configures Next.js build settings
  - Sets up environment variables placeholder
  - Enables auto-deployment on main branch

✓ **GitHub Integration** - Vercel GitHub App installed and permissions updated
  - Vercel can read your repositories
  - Vercel can create deployments and set commit statuses

## 🚀 Next Steps - Add Project to Vercel

### Step 1: Log in to Vercel
1. Go to https://vercel.com
2. Click "Log in"
3. Choose "Continue with GitHub"
4. Authorize Vercel to access your GitHub account

### Step 2: Import the Project
1. Once logged in, click "New Project" or "Add New" button
2. Select "Import Git Repository"
3. Find "dhadieyedikissa-byte/rockhal" in the list
4. Click "Import"

### Step 3: Configure Build Settings
Vercel should auto-detect Next.js. Accept the default settings:
- **Framework**: Next.js ✓ (auto-detected)
- **Root Directory**: ./ ✓ (auto-detected)
- **Build Command**: `npm run build` ✓ (from vercel.json)
- **Output Directory**: `.next/standalone` ✓ (from vercel.json)
- **Install Command**: `npm install` ✓ (from vercel.json)

Click "Deploy" to start the first deployment.

### Step 4: Configure Custom Domain
1. After deployment completes, go to project settings
2. Click "Domains" in the left sidebar
3. Click "Add Domain"
4. Enter "rockhal.lu"
5. Follow Vercel's DNS instructions to configure your domain provider

**DNS Configuration Steps:**
- Go to your domain registrar (likely ovh.net or similar for .lu domain)
- Add a CNAME record pointing to your Vercel deployment
- Vercel will provide the exact values to use

### Step 5: Verify Deployment
1. Wait 10-30 minutes for DNS propagation
2. Visit https://rockhal.lu
3. Confirm your Next.js app is live

## 🔄 Automatic Deployments

Once configured, deployments will happen automatically:
- **On every push to main** → Production deployment
- **On pull requests** → Preview deployment (temporary URL)
- **Automatic rollback** if deployment fails

## 📝 Environment Variables

If your app needs environment variables:
1. In Vercel Project Settings → Environment Variables
2. Add any required variables (API keys, URLs, etc.)
3. Redeploy for changes to take effect

## ⚠️ Troubleshooting

**Build fails on Vercel but works locally?**
- Ensure all dependencies are in `package.json`, not just `package-lock.json`
- Check that build commands match your local setup

**Domain not working after 30 minutes?**
- Clear your browser cache (Ctrl+Shift+Delete)
- Check DNS propagation at https://dnschecker.org
- Review Vercel's domain configuration in project settings

**Need to rollback?**
- Vercel keeps deployment history
- Click the deployment you want to promote from project dashboard
- Click "Promote to Production"

## 📚 Useful Links

- [Vercel Documentation](https://vercel.com/docs)
- [Next.js on Vercel](https://vercel.com/docs/frameworks/nextjs)
- [Custom Domains Guide](https://vercel.com/docs/concepts/projects/custom-domains)
- [Deployment Troubleshooting](https://vercel.com/docs/deployments/troubleshooting)

---

**Project Status**: Ready for production deployment ✓
**Last Updated**: April 2, 2026
