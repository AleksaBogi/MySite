# GitHub Pages

For full documentation visit [docs.github.com](https://docs.github.com/en).

## Understanding GitHub Pages

`GitHub Pages` is a static site hosting service that takes HTML, CSS, and JavaScript files straight from a repository on GitHub, optionally runs the files through a build process, and publishes a website. You can see examples of GitHub Pages sites in the GitHub Pages examples collection. You can create GitHub Pages sites that are publicly available on the internet. Organizations that use GitHub Enterprise Cloud can also publish sites privately by managing access control for the site. For more information, see "Changing the visibility of your GitHub Pages site" in the GitHub Enterprise Cloud documentation.

## Types of GitHub Pages sites

There are three types of GitHub Pages sites: `project`, `user`, and `organization`. `Project` sites are connected to a specific project hosted on GitHub, such as a JavaScript library or a recipe collection. `User` and `organization` sites are connected to a specific account on GitHub.com.

!!! warning "Warning"
    Warning: GitHub Pages sites are publicly available on the internet, even if the repository for the site is private. If you have sensitive data in your site's repository, you may want to remove the data before publishing.

## Deploying GitHub Pages artifacts

The `deploy-pages` action handles the necessary setup for deploying artifacts.

```
jobs:
  deploy:
    permissions:
      contents: read
      pages: write
      id-token: write
    runs-on: ubuntu-latest
    needs: jekyll-build
    environment:
      name: github-pages
      url: ${{steps.deployment.outputs.page_url}}
    steps:
      - name: Deploy artifact
        id: deployment
        uses: actions/deploy-pages@v1
```

## Configuring a publishing source for GitHub Pages site

!!! example

    === "Publishing from a branch "
        
        ``` markdown
        * Settings, Pages, Deploy from a branch, select a branch
        ```

    === "Publishing with a custom GitHub Actions workflow"

        ``` markdown
        * Settings, Pages, GitHub Actions
        ```

## Deleting a Github Pages site

``` mermaid
stateDiagram-v2
  state fork_state <<fork>>
  [*] --> fork_state
  fork_state --> Deleting_a_repo
  fork_state --> Changing_a_source
```