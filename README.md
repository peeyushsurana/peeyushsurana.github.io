# Surana Jewellers Estimate App

This repository hosts a simple static HTML estimate app for Surana Jewellers.

Live site after GitHub Pages deployment:

```text
https://peeyushsurana.github.io
```

The app runs fully in the browser. It does not need a server, database, or `.env` secrets right now.

## Files In This Repository

- `index.html` - the estimate app opened by GitHub Pages.
- `surana-header-black.png` - the header logo used inside the estimate.
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
git add index.html surana-header-black.png README.md .gitignore
git commit -m "Deploy Surana Jewellers estimate app"
git remote add origin https://github.com/peeyushsurana/peeyushsurana.github.io.git
git push -u origin main
```

If Git asks you to sign in, follow the prompt. GitHub may ask for browser login or a Personal Access Token instead of a password.

## Deploy With GitHub Pages

For a repository named `peeyushsurana.github.io`, GitHub Pages normally deploys automatically from the `main` branch.

After pushing, wait a minute and open:

```text
https://peeyushsurana.github.io
```

If it does not appear:

1. Open the GitHub repository.
2. Go to `Settings`.
3. Click `Pages`.
4. Under `Build and deployment`, choose:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/ (root)`
5. Save and wait for GitHub to deploy.

## About `.env` Secrets

This app does not need `.env` secrets right now.

If you add private keys, passwords, API tokens, or other secrets later:

1. Put them in a file named `.env`.
2. Do not commit `.env` to GitHub.
3. Keep `.env` listed in `.gitignore`.
4. For public websites, do not place private secrets inside browser JavaScript or HTML. Anything in a public website can be viewed by visitors.

## Updating The App Later

After changing files, push updates with:

```bash
git add index.html surana-header-black.png README.md .gitignore
git commit -m "Update estimate app"
git push
```

GitHub Pages will redeploy automatically after each push.
