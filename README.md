# Surana Jewellers Estimate App

This repository hosts static Gold and Silver estimate apps for Surana Jewellers and Surana Silver House.

Live site after GitHub Pages deployment:

```text
https://peeyushsurana.github.io
```

Silver estimate page:

```text
https://peeyushsurana.github.io/silver-estimate.html
```

Both apps run fully in the browser. They use the same access-code screen generated from a GitHub repository secret named `SECRET` during deployment.

## Files In This Repository

- `index.html` - the estimate app opened by GitHub Pages.
- `silver-estimate.html` - the separate Surana Silver House estimate app.
- `surana-header-black.png` - the header logo used by the Gold estimate.
- `surana-silver-house-logo.png` - the header logo used by the Silver estimate.
- `.github/workflows/deploy-pages.yml` - deploys the site and adds the access-code hash.
- `.gitignore` - keeps local/private files out of Git.

## Install Git On Mac

1. Open Terminal.
2. Run:

```bash
git --version
```

3. If Git is not installed, macOS will usually show a prompt to install Command Line Tools. Accept it.
4. After installation finishes, run again:

```bash
git --version
```

You should see a Git version number.

## Create A GitHub Account

1. Go to `https://github.com`.
2. Click `Sign up`.
3. Create your account and verify your email address.

## Create The GitHub Repository

For a personal GitHub Pages site, the repository name must match this format:

```text
your-github-username.github.io
```

For this project, the repository should be:

```text
peeyushsurana.github.io
```

Steps:

1. Go to GitHub.
2. Click `New repository`.
3. Repository name: `peeyushsurana.github.io`.
4. Choose `Public`.
5. Do not add a README from GitHub if you already have local files.
6. Click `Create repository`.

## Push This Code To GitHub

From the folder containing this `README.md`, run:

```bash
git init
git branch -M main
git add index.html silver-estimate.html surana-header-black.png surana-silver-house-logo.png README.md .gitignore .github/workflows/deploy-pages.yml
git commit -m "Deploy Surana Jewellers estimate app"
git remote add origin https://github.com/peeyushsurana/peeyushsurana.github.io.git
git push -u origin main
```

If Git asks you to sign in, follow the prompt. GitHub may ask for browser login or a Personal Access Token instead of a password.

For a fine-grained Personal Access Token, choose the repository `peeyushsurana.github.io` and give:

- `Contents` - Read and write
- `Metadata` - Read-only / required

## Deploy With GitHub Pages

For these apps, GitHub Pages should deploy using GitHub Actions because the workflow reads the repository secret named `SECRET` and adds the same access-code check to both the Gold and Silver pages.

Before the first deployment:

1. Open the GitHub repository.
2. Go to `Settings`.
3. Go to `Secrets and variables` -> `Actions`.
4. Click `New repository secret`.
5. Name: `SECRET`.
6. Value: your private access code.
7. Click `Add secret`.

Then configure Pages:

1. Open the GitHub repository.
2. Go to `Settings`.
3. Click `Pages`.
4. Under `Build and deployment`, choose:
   - Source: `GitHub Actions`
5. Save if GitHub shows a save button.

After pushing, wait a minute and open:

```text
https://peeyushsurana.github.io
```

If it does not appear, open the repository and click `Actions`. The latest workflow run should show whether deployment succeeded or failed.

## Access Code And Security

The access code is the value stored in the GitHub repository secret named `SECRET`.

Important: this is a simple access gate for a static website. It keeps the plain access code out of the repository, but it is not the same as server-side login. A determined technical person may still bypass client-side checks on a public static site.

For stronger protection, use a service with real authentication, such as Cloudflare Access, Netlify password protection, Vercel authentication, or a private internal app.

## Gold Saved Estimates Storage

Gold saved estimates are stored locally in the browser on the same computer using browser storage. They remain after closing and reopening the browser, and they stay saved until they are deleted from the app or the browser's site data is manually cleared.

Use the same browser and the same website address to see the same saved estimates. Local testing at `localhost` and the deployed GitHub Pages site have separate browser storage.

The app also asks the browser for persistent storage to reduce the chance that saved estimates are cleared automatically.

The Silver estimate is print-only. It does not save Silver estimates or change the Gold saved-estimate history. Its VA and Final Amount fields work in both directions: entering VA calculates Final Amount, while entering Final Amount calculates VA. When Cash is entered, Cash becomes the controlling invoice total and is distributed proportionally across all valid item rows.

## Test Locally With `.env`

For local testing, `index.html` tries to read `.env` from the same folder.

Create `.env`:

```env
SECRET=choose-your-private-access-code
```

Open `index.html` in your browser and enter the value from `.env`.

If the browser blocks reading `.env`, run a small local server from the project folder:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

For the Silver estimate, open:

```text
http://localhost:8000/silver-estimate.html
```

Both pages read the same `SECRET` value from `.env` during local testing.

Do not commit `.env`; it is ignored by `.gitignore`.

## About `.env` Secrets

If you add private keys, passwords, API tokens, or other secrets later:

1. Put them in a file named `.env`.
2. Do not commit `.env` to GitHub.
3. Keep `.env` listed in `.gitignore`.
4. For public websites, do not place private secrets inside browser JavaScript or HTML. Anything in a public website can be viewed by visitors.

## Updating The App Later

After changing files, push updates with:

```bash
git add index.html silver-estimate.html surana-header-black.png surana-silver-house-logo.png README.md .gitignore .github/workflows/deploy-pages.yml
git commit -m "Update estimate app"
git push
```

GitHub Pages will redeploy automatically after each push.
