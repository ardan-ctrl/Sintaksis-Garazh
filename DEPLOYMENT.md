# GitHub Pages Deployment Guide

## 🎉 Your site is now live!

**Live URL:** https://ardan-ctrl.github.io/Sintaksis-Garazh/

## ✅ What has been set up:

### 1. GitHub Actions Workflow
A workflow file has been created at `.github/workflows/deploy.yml` that automatically:
- Builds your Vite project on every push to the `main` branch
- Deploys the built `dist` folder to GitHub Pages
- Uses the official GitHub Pages deployment actions

### 2. Vite Configuration
The `vite.config.ts` file has been updated with:
```typescript
base: '/Sintaksis-Garazh/'
```
This ensures all assets are loaded from the correct subdirectory on GitHub Pages.

### 3. GitHub Pages Settings
- Source: GitHub Actions (configured in repository settings)
- Branch: Deployment happens automatically via Actions
- Custom domain: Not configured (using default github.io domain)

## 🔄 How it works:

1. **Push to main branch** → Triggers the GitHub Actions workflow
2. **Workflow runs** → Installs dependencies, builds the project
3. **Automatic deployment** → Uploads `dist` folder to GitHub Pages
4. **Site updates** → Changes are live in ~1 minute

## 📋 Next Steps for Development:

### If you don't have package.json and node_modules yet:

1. **Initialize your project locally:**
   ```bash
   npm install
   ```

2. **Verify the build works:**
   ```bash
   npm run build
   ```

3. **Test locally:**
   ```bash
   npm run dev
   ```

4. **Push changes to deploy:**
   ```bash
   git add .
   git commit -m "Your commit message"
   git push origin main
   ```

### Important Notes:

- ✅ The workflow uses `npm install` (works without package-lock.json)
- ✅ The base path is correctly set to `/Sintaksis-Garazh/`
- ✅ GitHub Pages is configured to use GitHub Actions as the source
- ✅ Every push to `main` will trigger a new deployment

## 🔍 Monitoring Deployments:

- View workflow runs: https://github.com/ardan-ctrl/Sintaksis-Garazh/actions
- Check deployment status: Settings → Pages
- View deployment history: https://github.com/ardan-ctrl/Sintaksis-Garazh/deployments

## 🛠️ Troubleshooting:

If deployment fails:
1. Check the Actions tab for error logs
2. Verify `package.json` has a `build` script: `"build": "vite build"`
3. Ensure all dependencies are listed in `package.json`
4. Check that the build outputs to the `dist` folder

## 📝 Workflow Configuration:

The workflow is configured to:
- Run on: Push to `main` branch
- Node version: 20
- Build command: `npm run build`
- Deploy directory: `./dist`
- Permissions: Read contents, write to Pages, use ID tokens

---

**Congratulations! Your Sintaksis-Garazh app is now automatically deployed to GitHub Pages!** 🚀
