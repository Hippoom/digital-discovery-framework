# Digital Discovery Framework

Public presentation site for the Digital Discovery Framework.

## Publish updates

1. Replace `index.html` with the latest approved external presentation build.
2. Review the changes: `git diff -- index.html`
3. Commit and push:

   ```bash
   git add index.html
   git commit -m "Update public presentation"
   git push
   ```

GitHub Actions deploys each push to the `main` branch to GitHub Pages.
