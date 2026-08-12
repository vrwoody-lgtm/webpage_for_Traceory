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
- `script.js`: shared bilingual switch logic

## Deployment

This site is deployed as a static website on a Tencent Cloud Ubuntu server.

- Domain: `support.rwoodylabs.org`
- Server IP: `43.165.178.158`
- Web root: `/var/www/support-site`
- Web server: `nginx`
- HTTPS: Let's Encrypt via `certbot`

## GitHub Actions Deployment

The workflow at `.github/workflows/deploy.yml` automatically deploys the site
after a relevant file is pushed to `main`. It can also be started manually from
the repository's **Actions** tab.

The workflow:

1. Validates and packages the six public website files.
2. Uploads the package to the server over SSH.
3. Replaces only the Traceory files at the top level of `/var/www/support-site`.
   Other sites in that directory, including `chinese-chess`, are preserved.
4. Verifies every production page and shared asset over HTTPS.

Configure these repository secrets under
**Settings → Secrets and variables → Actions** before the first run:

- `SERVER_HOST`: `43.165.178.158`
- `SERVER_USER`: `ubuntu`
- `SERVER_SSH_KEY`: the private key for the server deployment user
- `SERVER_SSH_KNOWN_HOSTS`: the trusted `known_hosts` entry for the server

The server directory must already exist and be writable by the deployment user:

```bash
sudo mkdir -p /var/www/support-site
sudo chown ubuntu:ubuntu /var/www/support-site
```

Pushing only documentation or unrelated repository files does not trigger a
production deployment.

## Notes

- The privacy policy reflects Traceory's local storage, iCloud, AI processing, maps, and online sharing behavior. The app has no account, advertising, or cross-app tracking system, while user-initiated online features may transmit or retain the content required to provide those features.
- If the app's data usage changes, update `privacy.html` before submitting a new App Store version.
