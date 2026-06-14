# webpage_for_Traceory

Static website for App Store support, marketing, and privacy policy pages.

## Live URLs

- Home: https://support.rwoodylabs.org/
- Support: https://support.rwoodylabs.org/support.html
- Marketing: https://support.rwoodylabs.org/marketing.html
- Privacy: https://support.rwoodylabs.org/privacy.html

## Project Files

- `index.html`: landing page linking to the required App Store pages
- `support.html`: technical support page
- `marketing.html`: marketing page
- `privacy.html`: privacy policy page
- `styles.css`: shared styling for all pages

## Deployment

This site is deployed as a static website on a Tencent Cloud Ubuntu server.

- Domain: `support.rwoodylabs.org`
- Server IP: `43.165.178.158`
- Web root: `/var/www/support-site`
- Web server: `nginx`
- HTTPS: Let's Encrypt via `certbot`

## Update Workflow

1. Edit the local files in this repository.
2. Upload the updated files to the server web root.
3. Verify the live pages over HTTPS.

## Notes

- The current privacy policy is written for an app with no account system and no personal data collection.
- If the app's data usage changes, update `privacy.html` before submitting a new App Store version.
