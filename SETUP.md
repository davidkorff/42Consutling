# Quick Setup Guide for GitHub Pages

Follow these steps to get your 42 Consulting website live on GitHub Pages with a working contact form.

## Step 1: Prepare Your Files

### Contact Form Endpoint
The form in [index.html](index.html) posts to the first-party endpoint at
`https://42ims.com/api/public/contact`. Keep the hidden `source` field set to
`42consultingllc.com`; the server owns the recipient and success redirect.

### Update Email in Contact Section
1. In the same [index.html](index.html) file
2. Search for `contact@42consultingllc.com`
3. Update to your actual email if different

## Step 2: Deploy to GitHub Pages

### Option A: Create New Repository
1. Go to GitHub and create a new repository
2. Name it something like `42consulting-website`
3. Upload all your website files to the repository

### Option B: Use GitHub Desktop
1. Download GitHub Desktop
2. Create a new repository from this folder
3. Publish to GitHub

### Enable GitHub Pages
1. Go to your repository on GitHub.com
2. Click **Settings** → **Pages**
3. Under "Source", select **main** branch
4. Click **Save**
5. Your site will be published at: `https://yourusername.github.io/repositoryname/`

## Step 3: Verify Contact Form

1. Visit your live website
2. Fill out the contact form and submit
3. Confirm the thank-you page displays a confirmation reference
4. Confirm the message arrives through `contact@42consultingllc.com`

## Step 4: Add Client Logos (Optional)

1. Place client logo images in `assets/images/clients/`
2. Open [index.html](index.html)
3. Find the "Clients" section (around line 280)
4. Replace the placeholder divs with actual images:
   ```html
   <div class="clients-grid">
       <img src="assets/images/clients/client1.png" alt="Client Name" style="width:100%; height:auto; object-fit:contain;">
       <img src="assets/images/clients/client2.png" alt="Client Name" style="width:100%; height:auto; object-fit:contain;">
       <!-- Add more -->
   </div>
   ```

## Step 6: Optional Enhancements

### Add a Favicon
1. Create or download a favicon.ico file
2. Place it in the root folder
3. Add to [index.html](index.html) `<head>` section:
   ```html
   <link rel="icon" type="image/x-icon" href="favicon.ico">
   ```

### Add Google Analytics
1. Get your Google Analytics tracking ID
2. Add before `</body>` in [index.html](index.html):
   ```html
   <!-- Google Analytics -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'GA_MEASUREMENT_ID');
   </script>
   ```

### Use a Custom Domain
1. Buy a domain (e.g., from Google Domains, Namecheap)
2. In GitHub repository settings → Pages → Custom domain
3. Enter your domain and follow GitHub's instructions
4. Update DNS settings at your domain registrar

## Testing Checklist

- [ ] Website loads correctly on desktop
- [ ] Website loads correctly on mobile
- [ ] Navigation menu works (including mobile hamburger menu)
- [ ] All anchor links scroll smoothly to sections
- [ ] Contact form submits successfully
- [ ] The thank-you page displays a confirmation reference
- [ ] Form submissions arrive through `contact@42consultingllc.com`
- [ ] Thank you page displays after form submission
- [ ] Client logos display properly (if added)

## Troubleshooting

### Form Not Working
- Confirm `https://42ims.com/health` reports healthy
- Confirm the form action is `https://42ims.com/api/public/contact`
- Use the displayed confirmation reference when checking delivery logs

### Website Not Loading
- Wait 5-10 minutes after enabling GitHub Pages
- Check that index.html is in the root of your repository
- Verify GitHub Pages is enabled in repository settings

### Styles Not Showing
- Ensure styles.css is in the same folder as index.html
- Check browser console for errors (F12)
- Clear your browser cache

## Need Help?

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- Check the main [README.md](README.md) for more details

---

**You're all set!** Your website should now be live with a fully functional contact form that sends emails directly to you.
