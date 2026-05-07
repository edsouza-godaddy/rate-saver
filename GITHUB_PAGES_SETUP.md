# GitHub Pages Setup Instructions

Your repository is now ready for GitHub! Follow these steps to publish the Rate Saver prototype.

## Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Name your repository (e.g., `zero-fees` or `rate-saver-prototype`)
3. Choose **Public** or **Private** (GitHub Pages works with both)
4. **Don't** initialize with README, .gitignore, or license (we already have these)
5. Click "Create repository"

## Step 2: Push to GitHub

Copy the commands from GitHub's "push an existing repository" section, or use these (replace `YOUR_USERNAME` and `YOUR_REPO`):

```bash
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

Example:
```bash
git branch -M main
git remote add origin https://github.com/edsouza/zero-fees.git
git push -u origin main
```

## Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Click **Pages** (left sidebar)
4. Under "Build and deployment":
   - **Source**: Select "GitHub Actions"
5. Click **Save**

## Step 4: Trigger Deployment

The GitHub Actions workflow will automatically run when you pushed to `main`. You can also:
- Go to **Actions** tab
- Click **Deploy to GitHub Pages** workflow
- Click **Run workflow** button

## Step 5: Access Your Prototype

After 1-2 minutes, your prototype will be live at:

```
https://YOUR_USERNAME.github.io/YOUR_REPO/
```

Example:
```
https://edsouza.github.io/zero-fees/
```

## What's Deployed

- **Main prototype**: `https://YOUR_USERNAME.github.io/YOUR_REPO/` (the Rate Saver merchant prototype)
- The prototype is the `docs/index.html` file (copied from "Rate Saver - Merchant Prototype.html")

## Updating the Prototype

To update the prototype:

1. Edit `Rate Saver - Merchant Prototype.html` (original source file)
2. Copy changes to `docs/index.html`:
   ```bash
   cp "Rate Saver - Merchant Prototype.html" docs/index.html
   ```
3. Commit and push:
   ```bash
   git add docs/index.html
   git commit -m "Update Rate Saver prototype"
   git push
   ```

The GitHub Actions workflow will automatically deploy the changes.

## Alternative: Simpler Setup (Without GitHub Actions)

If you prefer a simpler setup without GitHub Actions:

1. In GitHub Settings > Pages
2. Set **Source** to "Deploy from a branch"
3. Select **Branch**: `main` and **Folder**: `/docs`
4. Click Save

This deploys directly from the `docs` folder without needing the Actions workflow.

## Troubleshooting

**Workflow fails?**
- Check **Actions** tab for error details
- Ensure GitHub Pages is enabled in Settings > Pages
- Verify permissions in Settings > Actions > General > Workflow permissions (set to "Read and write permissions")

**404 error?**
- Wait 2-3 minutes after first deployment
- Check that `docs/index.html` exists in your repository
- Verify GitHub Pages is looking at the right source

**Need to share privately?**
- If using a private repo, viewers need GitHub access to your repo
- Consider using a public repo for broader sharing
- Or export the HTML and host on internal servers

## Next Steps

Once deployed, you can share the live URL in:
- The exec readout
- Meeting invites
- Slack messages
- Email communications

The prototype will update automatically whenever you push changes to the `main` branch.

---

**Created**: May 5, 2026  
**Repository Structure**: All files committed and ready to push
