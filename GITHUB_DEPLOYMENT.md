# Deploying Semai's Birthday Webpage to GitHub Pages

This guide will help you deploy your romantic birthday webpage to GitHub Pages for free hosting.

## Prerequisites

- A GitHub account (create one at https://github.com if you don't have one)
- Git installed on your computer (download from https://git-scm.com)
- The project files from Manus

## Step-by-Step Deployment Guide

### 1. Download Project Files

First, download all the project files from Manus. You should have a folder containing:
- `client/` - Frontend code
- `package.json` - Dependencies
- `vite.config.ts` - Build configuration
- And other configuration files

### 2. Create a New GitHub Repository

1. Go to https://github.com/new
2. Name your repository: `semai-birthday` (or any name you prefer)
3. Choose "Public" (so it can be accessed online)
4. Click "Create repository"
5. Copy the repository URL (it will look like `https://github.com/YOUR_USERNAME/semai-birthday.git`)

### 3. Initialize Git and Push to GitHub

Open a terminal/command prompt in your project folder and run:

```bash
# Initialize git repository
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: Romantic birthday webpage for Semai"

# Add remote repository
git remote add origin https://github.com/YOUR_USERNAME/semai-birthday.git

# Push to GitHub
git branch -M main
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

### 4. Build the Project for Production

Run the build command to create optimized files:

```bash
npm install
npm run build
```

This creates a `dist/public` folder with all the files ready for deployment.

### 5. Deploy to GitHub Pages

#### Option A: Using GitHub Pages with `gh-pages` Package (Recommended)

1. Install the gh-pages package:
```bash
npm install --save-dev gh-pages
```

2. Update `package.json` scripts section to add:
```json
"scripts": {
  "deploy": "npm run build && gh-pages -d dist/public"
}
```

3. Run the deploy command:
```bash
npm run deploy
```

4. Go to your repository settings on GitHub:
   - Click "Settings" tab
   - Scroll to "Pages" section
   - Under "Source", select "gh-pages" branch
   - Click "Save"

#### Option B: Manual Deployment

1. After running `npm run build`, copy all files from `dist/public` folder
2. Create a new branch called `gh-pages`:
```bash
git checkout --orphan gh-pages
git rm -rf .
```

3. Copy the built files into this branch, commit, and push:
```bash
# Copy files from dist/public here
git add .
git commit -m "Deploy to GitHub Pages"
git push origin gh-pages
```

4. In GitHub repository settings → Pages → select `gh-pages` branch as source

### 6. Access Your Website

Your website will be available at:
```
https://YOUR_USERNAME.github.io/semai-birthday
```

Or if you use a custom domain, configure it in GitHub Pages settings.

## Updating the Website

To make changes and redeploy:

1. Edit files locally
2. Run `npm run build` to rebuild
3. Run `npm run deploy` (if using Option A)
4. Or manually push changes to `gh-pages` branch (if using Option B)

## Troubleshooting

**Website shows 404 error:**
- Make sure you selected the correct branch in GitHub Pages settings
- Wait 1-2 minutes for GitHub to process the deployment

**Styles or images not loading:**
- Check that all image URLs are using the CDN links (starting with `https://`)
- Verify the build process completed without errors

**Want a custom domain:**
- In GitHub Pages settings, add your custom domain
- Update your domain's DNS settings to point to GitHub Pages
- GitHub provides detailed instructions in the Pages settings

## Need Help?

- GitHub Pages Documentation: https://docs.github.com/en/pages
- Vite Build Documentation: https://vitejs.dev/guide/build.html

---

**Happy Birthday to Semai! 🎉💖**

This webpage is now live and ready to celebrate her special day!
