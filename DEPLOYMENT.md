# Deployment Guide

## 🚀 Deployment Options

### 1. Netlify (Recommended)

1. Build the project:
```bash
npm run build
```

2. Deploy the `dist` folder to Netlify
3. Configure redirects for SPA routing

### 2. Vercel

1. Connect your GitHub repository to Vercel
2. Vercel will automatically detect Vite configuration
3. Deploy with default settings

### 3. GitHub Pages

1. Install gh-pages:
```bash
npm install --save-dev gh-pages
```

2. Add to package.json scripts:
```json
"deploy": "gh-pages -d dist"
```

3. Build and deploy:
```bash
npm run build
npm run deploy
```

### 4. Custom Server

1. Build the project:
```bash
npm run build
```

2. Serve the `dist` folder with any static file server
3. Configure server for SPA routing (redirect all routes to index.html)

## 🔧 Environment Configuration

### Production Environment Variables

Create `.env.production` file:
```
VITE_APP_TITLE=Buonoco - Premium Bell Peppers Wholesale
VITE_CONTACT_EMAIL=buonoco.pepper@gmail.com
VITE_CONTACT_PHONE=+989120748879
```

### Server Configuration

For proper SPA routing, configure your server to redirect all routes to `index.html`:

#### Nginx
```nginx
location / {
  try_files $uri $uri/ /index.html;
}
```

#### Apache (.htaccess)
```apache
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.html [L]
```

## 🌐 Domain Configuration

1. Point your domain `buonoco.com` to your hosting provider
2. Configure SSL certificate
3. Set up redirects from www to non-www (or vice versa)
4. Ensure admin route `/skyloginadmin` is accessible

## 📊 Analytics Setup

The website includes built-in visitor tracking. For production:

1. Consider integrating Google Analytics
2. Set up proper error tracking
3. Monitor performance metrics

## 🔒 Security Considerations

1. Change default admin credentials in production
2. Implement proper authentication for admin panel
3. Use HTTPS for all communications
4. Regular security updates for dependencies

## 📱 Mobile Optimization

The website is fully responsive, but verify:
1. Touch targets are appropriate size
2. Text is readable on small screens
3. Forms work well on mobile devices
4. WhatsApp/Telegram links work on mobile

## 🔍 SEO Optimization

1. Add meta descriptions for all pages
2. Implement structured data for products
3. Create XML sitemap
4. Optimize images with proper alt tags
5. Ensure fast loading times