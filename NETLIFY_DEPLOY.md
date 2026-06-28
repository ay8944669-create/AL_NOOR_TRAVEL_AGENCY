# Netlify Deployment Guide

## AL NOOR Travel Agency - Netlify Hosting

This guide will help you deploy the AL NOOR Travel Agency website to Netlify.

---

## Why Netlify?

✅ Free tier available  
✅ Automatic deployments from GitHub  
✅ Built-in SSL/HTTPS  
✅ Custom domain support  
✅ Fast CDN worldwide  
✅ Easy environment variables  

---

## Step 1: Create Netlify Account

1. Go to https://netlify.com
2. Click "Sign up"
3. Choose "Sign up with GitHub" (recommended)
4. Authorize Netlify to access your GitHub account

---

## Step 2: Connect GitHub Repository

1. After login, click "Add new site"
2. Select "Import an existing project"
3. Choose "GitHub"
4. Find and select `al-noor-travel-agency` repository
5. Click "Install"

---

## Step 3: Configure Build Settings

Netlify will auto-detect settings, but verify:

**Build Command:**
```
pnpm install && pnpm run build
```

**Publish Directory:**
```
dist
```

**Node Version:**
```
18.17.0
```

---

## Step 4: Set Environment Variables

In Netlify Dashboard:

1. Go to **Site settings** → **Build & deploy** → **Environment**
2. Click **Add environment variables**
3. Add these variables:

```
VITE_APP_TITLE = AL NOOR Travel Agency
VITE_APP_LOGO = AL NOOR
NODE_ENV = production
```

For database and API keys (if needed):
```
DATABASE_URL = your-database-url
JWT_SECRET = your-secret-key
```

---

## Step 5: Deploy

1. Click **Deploy site**
2. Netlify will:
   - Clone your repository
   - Install dependencies
   - Build the project
   - Deploy to CDN

3. Your site will be live at: `https://your-site-name.netlify.app`

---

## Step 6: Custom Domain (Optional)

1. Go to **Site settings** → **Domain management**
2. Click **Add custom domain**
3. Enter your domain: `al-noor-travel.com`
4. Follow DNS setup instructions from your domain registrar

---

## Automatic Deployments

Every time you push to GitHub:
1. Netlify automatically detects changes
2. Builds the project
3. Deploys to production
4. Updates your live site

No manual deployment needed! 🎉

---

## Troubleshooting

### Build Fails
- Check build logs in Netlify dashboard
- Verify environment variables are set
- Ensure `pnpm-lock.yaml` is in repository

### Site Shows 404
- Check that `dist` is the publish directory
- Verify build command is correct
- Clear Netlify cache and redeploy

### Custom Domain Not Working
- Wait 24 hours for DNS propagation
- Verify DNS records in your domain registrar
- Check Netlify domain settings

---

## Performance Tips

1. **Enable Netlify Analytics**: Track visitor behavior
2. **Set up Netlify Forms**: Capture contact form submissions
3. **Configure Cache Headers**: Improve page load speed
4. **Enable Compression**: Reduce file sizes

---

## File Structure for Netlify

```
al-noor-travel-agency/
├── netlify.toml          ← Netlify configuration
├── package.json
├── pnpm-lock.yaml
├── client/               ← React frontend
├── server/               ← Node.js backend
├── drizzle/              ← Database schema
└── dist/                 ← Build output (auto-generated)
```

---

## Next Steps

1. **Monitor Deployments**: Check Netlify dashboard for build status
2. **Set up Analytics**: Track visitor metrics
3. **Add Contact Form**: Use Netlify Forms for submissions
4. **Enable HTTPS**: Already enabled by default
5. **Set up CDN**: Automatic with Netlify

---

## Support

- Netlify Docs: https://docs.netlify.com
- Netlify Support: https://support.netlify.com
- AL NOOR Support: +91 7482014332 (Anshu Yadav)

---

## Comparison: Netlify vs GitHub Pages

| Feature | Netlify | GitHub Pages |
|---------|---------|--------------|
| Free Tier | Yes | Yes |
| Custom Domain | Yes | Yes |
| Automatic Deployments | Yes | Yes |
| Database Support | Yes (with backend) | Limited |
| Environment Variables | Yes | No |
| Form Submissions | Yes (Netlify Forms) | No |
| Analytics | Yes (Netlify Analytics) | No |
| CDN | Global | Global |

**Recommendation**: Use Netlify for better features and easier management.
