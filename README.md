# The Activity Hub Website

This is the landing page for The Activity Hub app, designed to be hosted at activeportland.com.

## Files

- `index.html` - Main landing page
- `privacy-policy.html` - Privacy policy (link to existing)
- `child-safety-standards.html` - Child safety standards (link to existing)

## Deployment: GitHub Pages + Squarespace Domain

### Step 1: Create GitHub Repository

1. Go to [github.com](https://github.com) and create a new repository (e.g., `activeportland-website`)
2. **Important:** Make it a **public** repository (GitHub Pages free tier requires public repos)
3. Upload all files from the `website` folder to this repository:
   - `index.html`
   - `CNAME` (already created with `activeportland.com`)
   - `README.md`

### Step 2: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top right)
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select:
   - Branch: `main` (or `master`)
   - Folder: `/` (root)
5. Click **Save**
6. Your site will be live at `https://yourusername.github.io/activeportland-website` (temporary URL)

### Step 3: Configure Custom Domain in GitHub

1. Still in **Settings > Pages**
2. Under **Custom domain**, enter: `activeportland.com`
3. Check **Enforce HTTPS** (after DNS is configured)
4. GitHub will verify the domain

### Step 4: Configure DNS in Squarespace

1. Log into your Squarespace account
2. Go to **Settings** → **Domains**
3. Find `activeportland.com` and click on it
4. Go to **DNS Settings** or **Advanced DNS Settings**
5. Add the following DNS records:

   **For the root domain (activeportland.com):**
   - Type: `A`
   - Name: `@` (or leave blank)
   - Value: `185.199.108.153`
   - TTL: 3600 (or default)
   
   - Type: `A`
   - Name: `@` (or leave blank)
   - Value: `185.199.109.153`
   - TTL: 3600
   
   - Type: `A`
   - Name: `@` (or leave blank)
   - Value: `185.199.110.153`
   - TTL: 3600
   
   - Type: `A`
   - Name: `@` (or leave blank)
   - Value: `185.199.111.153`
   - TTL: 3600

   **For www subdomain (www.activeportland.com):**
   - Type: `CNAME`
   - Name: `www`
   - Value: `yourusername.github.io` (replace with your actual GitHub username)
   - TTL: 3600

6. Save the DNS records

### Step 5: Wait for DNS Propagation

- DNS changes can take 24-48 hours to propagate
- You can check status at: [whatsmydns.net](https://www.whatsmydns.net)
- Once DNS propagates, GitHub will automatically enable HTTPS

### Troubleshooting

- If the site doesn't load after 24 hours, verify DNS records are correct
- Make sure the `CNAME` file is in the root of your repository
- Check GitHub Pages settings show "Custom domain: activeportland.com"

### Option 2: Vercel (Free & Easy)

1. Install Vercel CLI: `npm i -g vercel`
2. Navigate to the `website` folder: `cd website`
3. Run: `vercel`
4. Follow the prompts
5. Connect your domain `activeportland.com` in Vercel dashboard

### Option 3: Netlify (Free & Easy)

1. Go to [netlify.com](https://netlify.com)
2. Drag and drop the `website` folder
3. Your site will be live immediately
4. Connect your domain `activeportland.com` in Netlify dashboard

### Option 4: Traditional Web Hosting

1. Upload all files in the `website` folder to your web hosting provider
2. Point your domain to the hosting provider
3. Make sure `index.html` is in the root directory

## Domain Setup

After deploying, you'll need to:

1. **Point your domain to your hosting:**
   - Add a CNAME record pointing to your hosting URL (for GitHub Pages, Vercel, Netlify)
   - Or add A records if using traditional hosting

2. **Update DNS settings:**
   - Go to your domain registrar (where you bought activeportland.com)
   - Update DNS records to point to your hosting provider

## Customization

- Update App Store and Google Play links in `index.html` if needed
- Modify colors, text, or sections as desired
- Add more pages (About, Contact, etc.) as needed

## Notes

- The site links to existing privacy policy and child safety pages
- Make sure those pages are accessible at the paths specified
- All links use relative paths for easy deployment

