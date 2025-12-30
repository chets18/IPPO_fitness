# 🚀 Deployment Guide - GitHub, Vercel & Netlify

This guide will walk you through deploying your IPPO Fitness app to GitHub and then to Vercel or Netlify.

## 📋 Table of Contents
1. [Preparing Your Project](#preparing-your-project)
2. [Pushing to GitHub](#pushing-to-github)
3. [Deploying to Vercel](#deploying-to-vercel)
4. [Deploying to Netlify](#deploying-to-netlify)
5. [Troubleshooting](#troubleshooting)

---

## 🔧 Preparing Your Project

### Step 1: Create a `.gitignore` File

First, make sure you have a `.gitignore` file to exclude unnecessary files from Git.

Create or update `.gitignore` in your project root:

```gitignore
# Dependencies
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
package-lock.json

# Build outputs
dist/
build/
*.tsbuildinfo

# Environment variables
.env
.env.local
.env.production
.env.development

# IDE
.vscode/
.idea/
*.swp
*.swo
*~

# OS
.DS_Store
Thumbs.db

# Database
*.db
*.sqlite
*.sqlite3

# Logs
logs/
*.log

# Temporary files
tmp/
temp/
```

### Step 2: Check Your Project Structure

Make sure your project is ready:
- ✅ All dependencies are in `package.json`
- ✅ Build script works (`npm run build`)
- ✅ No sensitive data (API keys, passwords) in code
- ✅ Database migrations are set up (if needed)

### Step 3: Environment Variables (if needed)

If your app uses environment variables, create a `.env.example` file:

```env
# Example environment variables
# Copy this to .env and fill in your values
NODE_ENV=production
PORT=3000
DATABASE_URL=your_database_url_here
```

**Important**: Never commit `.env` files! Only commit `.env.example`.

---

## 📤 Pushing to GitHub

### Step 1: Create a GitHub Account (if you don't have one)

1. Go to [github.com](https://github.com)
2. Sign up for a free account
3. Verify your email

### Step 2: Create a New Repository on GitHub

1. Click the **"+"** icon in the top right → **"New repository"**
2. Fill in the details:
   - **Repository name**: `ippo-fitness` (or your preferred name)
   - **Description**: "AI-powered fitness tracking webapp"
   - **Visibility**: Choose Public (free) or Private
   - **DO NOT** initialize with README, .gitignore, or license (we already have these)
3. Click **"Create repository"**

### Step 3: Initialize Git in Your Project

Open your terminal/command prompt in your project folder (`IPPOfitness`):

**For Windows (PowerShell or Command Prompt):**

```powershell
# Navigate to your project root
cd "C:\Users\A C E R\Downloads\IPPOfitness"

# Initialize Git (if not already initialized)
git init

# Add all files to staging
git add .

# Create your first commit
git commit -m "Initial commit: IPPO Fitness app"
 git config --global user.email "kjaishi62@gmail.com"
  git config --global user.name "chetraj jaishi"

# Add your GitHub repository as remote
# Replace YOUR_USERNAME with your GitHub username
git remote add origin https://github.com/chets18/IPPO_fitness.git

# Rename main branch (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

**Note**: 
- You'll be prompted for your GitHub username and password. For password, use a **Personal Access Token** (not your account password).
- If you get an error about `NODE_ENV=development` in package.json scripts, that's normal on Windows. The deployment platforms (Vercel/Netlify) will handle this automatically.
- If Git is not installed, download it from [git-scm.com](https://git-scm.com/download/win)

### Step 4: Create a Personal Access Token (if needed)

If Git asks for authentication:

1. Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click **"Generate new token (classic)"**
3. Give it a name: "IPPO Fitness Deployment"
4. Select scopes: Check **"repo"** (full control of private repositories)
5. Click **"Generate token"**
6. **Copy the token** (you won't see it again!)
7. Use this token as your password when Git prompts you

### Step 5: Verify Your Push

1. Go to your GitHub repository page
2. You should see all your files there
3. Your README.md should be visible on the repository homepage

---

## ☁️ Deploying to Vercel

Vercel is great for React/Node.js apps and offers free hosting with automatic deployments.

### Step 1: Sign Up for Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click **"Sign Up"**
3. Choose **"Continue with GitHub"** (easiest option)
4. Authorize Vercel to access your GitHub

### Step 2: Import Your Project

1. In Vercel dashboard, click **"Add New..."** → **"Project"**
2. Find and select your `ippo-fitness` repository
3. Click **"Import"**

### Step 3: Configure Build Settings

Vercel should auto-detect your settings, but verify:

**Framework Preset**: Vite (or React)

**Root Directory**: `pushups` (since your app is in the pushups folder)

**Build Command**: 
```bash
npm run build
```

**Output Directory**: 
```
dist/public
```

**Install Command**: 
```bash
npm install
```

### Step 4: Environment Variables (if needed)

If your app needs environment variables:

1. In the project settings, go to **"Environment Variables"**
2. Add each variable:
   - Key: `NODE_ENV`
   - Value: `production`
   - Add for: Production, Preview, Development
3. Click **"Save"**

### Step 5: Deploy!

1. Click **"Deploy"**
2. Wait 2-3 minutes for the build to complete
3. Once done, you'll get a URL like: `https://ippo-fitness.vercel.app`

### Step 6: Custom Domain (Optional)

1. Go to Project Settings → Domains
2. Add your custom domain (if you have one)
3. Follow the DNS configuration instructions

### Important Notes for Vercel:

- **Server-Side Rendering**: If your Express server needs to run, you might need to use Vercel's serverless functions
- **Static Site**: If your app is fully client-side, Vercel will serve it as a static site
- **API Routes**: For backend API, you may need to restructure to use Vercel's serverless functions

---

## 🌐 Deploying to Netlify

Netlify is another excellent option, especially for static sites and JAMstack apps.

### Step 1: Sign Up for Netlify

1. Go to [netlify.com](https://netlify.com)
2. Click **"Sign up"**
3. Choose **"Sign up with GitHub"**
4. Authorize Netlify

### Step 2: Deploy from GitHub

1. In Netlify dashboard, click **"Add new site"** → **"Import an existing project"**
2. Choose **"Deploy with GitHub"**
3. Authorize Netlify (if not already done)
4. Select your `ippo-fitness` repository
5. Click **"Next"**

### Step 3: Configure Build Settings

**Base directory**: `pushups`

**Build command**: 
```bash
npm run build
```

**Publish directory**: 
```
pushups/dist/public
```

**Advanced settings** (if needed):
- Click **"Show advanced"**
- Add environment variables if your app needs them

### Step 4: Deploy

1. Click **"Deploy site"**
2. Wait for the build to complete (usually 1-2 minutes)
3. Your site will be live at: `https://random-name-12345.netlify.app`

### Step 5: Customize Your Site Name

1. Go to **Site settings** → **Change site name**
2. Choose a custom name: `ippo-fitness` (if available)
3. Your URL becomes: `https://ippo-fitness.netlify.app`

### Step 6: Custom Domain (Optional)

1. Go to **Domain settings**
2. Click **"Add custom domain"**
3. Enter your domain
4. Follow the DNS setup instructions

### Important Notes for Netlify:

- **Server Functions**: Netlify supports serverless functions for backend logic
- **Redirects**: You may need a `_redirects` file for client-side routing
- **Build Plugins**: Netlify has plugins for various frameworks

---

## 🔄 Continuous Deployment

Both Vercel and Netlify support automatic deployments:

- **Every push to `main` branch** → Deploys to production
- **Pull requests** → Creates preview deployments
- **No manual deployment needed!**

Just push to GitHub, and your site updates automatically! 🎉

---

## 🐛 Troubleshooting

### Build Fails

**Problem**: Build command fails

**Solutions**:
- Check that all dependencies are in `package.json`
- Ensure build script exists: `"build": "tsx script/build.ts"`
- Check build logs for specific errors
- Make sure Node.js version is compatible (18+)

### 404 Errors on Routes

**Problem**: Routes return 404 when navigating directly

**Solution**: Add a redirect file:

**For Netlify** - Create `pushups/dist/public/_redirects`:
```
/*    /index.html   200
```

**For Vercel** - Create `pushups/vercel.json`:
```json
{
  "rewrites": [
    { "source": "/(.*)", "destination": "/index.html" }
  ]
}
```

### Environment Variables Not Working

**Problem**: Environment variables are undefined

**Solutions**:
- Make sure variables are set in Vercel/Netlify dashboard
- Restart the deployment after adding variables
- Use `process.env.VARIABLE_NAME` in your code
- For client-side, prefix with `VITE_` (Vite) or `REACT_APP_` (Create React App)

### Camera Permissions

**Problem**: Webcam doesn't work on deployed site

**Solution**: 
- HTTPS is required for camera access
- Both Vercel and Netlify provide HTTPS by default
- Make sure users allow camera permissions in their browser

### Database Issues

**Problem**: Database not working in production

**Solutions**:
- Use a cloud database (Supabase, PlanetScale, MongoDB Atlas)
- Update `DATABASE_URL` in environment variables
- For SQLite, consider migrating to a cloud solution
- Check database connection strings

### MediaPipe CDN Issues

**Problem**: Pose detection not loading

**Solution**: 
- MediaPipe loads from CDN (jsdelivr.net)
- Ensure CDN URLs are accessible
- Check browser console for CORS errors
- Consider hosting MediaPipe files yourself if needed

---

## 📚 Additional Resources

- [Vercel Documentation](https://vercel.com/docs)
- [Netlify Documentation](https://docs.netlify.com)
- [GitHub Guides](https://guides.github.com)
- [Vite Deployment Guide](https://vitejs.dev/guide/static-deploy.html)

---

## ✅ Deployment Checklist

Before deploying, make sure:

- [ ] `.gitignore` is set up correctly
- [ ] No sensitive data in code
- [ ] Build command works locally (`npm run build`)
- [ ] All dependencies are in `package.json`
- [ ] Environment variables are documented in `.env.example`
- [ ] README.md is complete
- [ ] Code is pushed to GitHub
- [ ] Build settings are configured correctly
- [ ] Custom domain is set up (if needed)
- [ ] HTTPS is enabled (automatic on Vercel/Netlify)

---

**Congratulations! 🎉 Your IPPO Fitness app is now live on the internet!**

Share your deployed link and start tracking those workouts! 💪

