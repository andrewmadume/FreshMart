# Publish FreshMart on GitHub Pages

The `freshmart-pages-upload.zip` package contains the finished static website. It is a clearly labelled demo: browsing and the basket work, while checkout is simulated. No customer details, payments, orders, messages or subscriptions are sent.

## Easiest method — no build required

1. Extract `freshmart-pages-upload.zip`.
2. Create a GitHub repository, such as `freshmart`, and upload **all extracted files and folders to its root**. `index.html`, `assets`, `favicon.svg`, `product-placeholder.svg`, `404.html` and `.nojekyll` must be at the repository root, not inside another enclosing folder. Show hidden files to include `.nojekyll`.
3. Open **Settings → Pages**. Set Source to **Deploy from a branch**, Branch to **main**, Folder to **/(root)**, then Save. If your default branch has a different name, choose that branch.
4. Wait for GitHub's deployment to complete. The actual website URL appears in Settings → Pages, normally `https://YOUR-USERNAME.github.io/freshmart/`.

GitHub documents these settings in its [publishing-source guide](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site). The package uses relative assets and hash navigation, so no username or repository name needs to be entered in its code.

## To edit the website

Use `freshmart-github-pages.zip` instead. That package contains editable React/Vite source, locked dependencies, a prebuilt `docs` folder, and `.github/workflows/pages.yml` for optional automatic rebuilding.

Follow its README. With the source package, use **main → /docs** for branch publishing, or **GitHub Actions** for the supplied automated workflow. The upload-only package uses **main → /(root)**. Keep these publishing locations consistent with the package you choose.

The source build commands are `npm ci` and `npm run build` with Node.js 22.13 or later. The refreshed static website is generated in `docs`. Commit those generated files for branch publishing; Actions can build them automatically.

The complete original database/admin website remains in the separate FreshMart source package. GitHub Pages cannot execute its backend. Enabling real commerce requires a compatible server host and verified authentication/payment configuration.

## Checks completed

The static version passes TypeScript and production build checks. Browser checks cover the repository subpath, product-detail navigation, basket addition, applied FRESH10 discount, simulated checkout and reference restoration. Compiled JavaScript, CSS, favicon and placeholder assets resolve under both the site root and a repository subpath. No backend source, database state or credentials are included in the static upload.

This prepares the files for your GitHub account; no repository was created and no GitHub publication was performed.
