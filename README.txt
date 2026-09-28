NEXAPLAY STATIC WEBSITE
=======================

Files:
- index.html
- styles.css
- script.js
- assets/favicon.svg

Deploy:
1. Upload everything inside this folder to your server's public web root (for example public_html, www, or /var/www/html).
2. Make sure index.html is in the root.
3. Point nexaplays.com / www.nexaplays.com DNS to your server if not already configured.
4. Enable HTTPS with your hosting panel or Let's Encrypt.

Nginx example:
server {
    listen 80;
    server_name nexaplays.com www.nexaplays.com;
    root /var/www/nexaplay-website;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}

Notes:
- The public Google Sites version uses image assets hosted by Google. The provided package intentionally uses self-contained graphics/placeholders instead of hot-linking those assets.
- The Core Values illustrations and the Google Ads, AppLovin, Meta, and Unity logos are bundled under assets/.
- Privacy Policy and Terms of Use are included as privacy-policy/index.html and teams-of-use/index.html, with their supplied text. Upload both folders alongside the home page. The existing /teams-of-use spelling is preserved.
- app-ads.txt is in the website root. After uploading, confirm https://www.nexaplays.com/app-ads.txt displays its plain-text lines.
