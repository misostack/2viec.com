# 2Viec Landing

## Deploy to GitHub Pages

This project is configured for static SPA deployment on GitHub Pages.

#### 1. Deploy

Run the following command to build and publish to the `gh-pages` branch:

```bash
npm run deploy
```

This will:

- Build the project in SPA mode (`ssr: false`)
- Copy `index.html` to `404.html` (for client-side routing)
- Push the `build/client/` output to the `gh-pages` branch via `gh-pages`

#### 2. Configure GitHub Pages Settings

1. Go to your GitHub repo **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Set branch to `gh-pages` and folder to `/ (root)`
4. Click **Save**

#### 3. Configure Custom Domain (optional)

To use a custom domain (e.g. `2viec.com`):

**DNS records** — Add the following in your domain registrar's DNS settings:

| Type  | Name | Value                  |
| ----- | ---- | ---------------------- |
| A     | @    | `185.199.108.153`      |
| A     | @    | `185.199.109.153`      |
| A     | @    | `185.199.110.153`      |
| A     | @    | `185.199.111.153`      |
| CNAME | www  | `<username>.github.io` |

**GitHub settings:**

1. In **Settings → Pages**, enter your custom domain (e.g. `2viec.com`) and click **Save**
2. Enable **Enforce HTTPS** once DNS verification passes

**CNAME file** — Make sure [public/CNAME](public/CNAME) contains your domain. This is automatically included in the build output.
