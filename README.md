# GitHub Actions workflow development

Workflows to automatically build (with Vite) and deploy a website to (a specific folder within) GitHub pages (via the gh-pages git branch). Also creation of 'preview' folders within GitHub pages for each and all Pull Requests created (and then further modified). These PR preview folders are then automatically deleted when the associated PR is closed.

Specific workflows in folder `.github/workflows/`:
- **reusable-vite-build.yml**: Common production/preview Vite build workflow for code in examples-vite folder
- **vite-deploy-production.yml**: Call above common workflow to build code in branch 'main', then deploy it to GitHub Pages folder: [github-actions-test/examples-vite/](https://richard-thomas.github.io/github-actions-test/examples-vite/)
- **vite-preview.yml**: Call above common workflow to build code in branch associated with Pull Request, then deploy it to a GitHub Pages folder: `github-actions-test/examples-vite/preview/pr-(ID)/` (actual link automatically added to the Pull Request as a comment)
- **cleanup-preview.yml**: Automatically delete associated GitHub pages `preview/pr-(ID)/` folder on closure of a Pull Request

## Acknowledgements

Under the hood, these use (thanks!) the following (Marketplace) GitHub Actions:
- **[JamesIves/github-pages-deploy-action](https://github.com/JamesIves/github-pages-deploy-action)**
- **[rajyan/preview-pages](https://github.com/marketplace/actions/preview-pages)**