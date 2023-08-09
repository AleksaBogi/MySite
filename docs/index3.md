# GitHub Packages

For full documentation visit [docs.github.com](https://docs.github.com/en).

## About GitHub Packages

{==
GitHub Packages is a platform for hosting and managing packages, including containers and other dependencies. GitHub Packages combines your source code and packages in one place to provide integrated permissions management and billing, so you can centralize your software development on GitHub.
==}

## Permissions for GitHub Packages

#### Granular permissions for user/organization-scoped packages

Packages with granular permissions are scoped to a personal account or organization. You can change the access control and visibility of the package separately from a repository that is connected (or linked) to a package.

#### Permissions for repository-scoped packages

A repository-scoped package inherits the permissions and visibility of the repository in which the package is published. You can find a package scoped to a repository by going to the main page of the repository and clicking the Packages link to the right of the page. For more information, see "Connecting a repository to a package."

## Publishing a package

!!! note "Note"
    GitHub Packages is available with GitHub Free, GitHub Pro, GitHub Free for organizations, GitHub Team, GitHub Enterprise Cloud, GitHub Enterprise Server 3.0 or higher, and GitHub AE.GitHub Packages is not available for private repositories owned by accounts using legacy per-repository plans. Also, accounts using legacy per-repository plans cannot access registries that support granular permissions, because these accounts are billed by repository

You can publish packages in a public repository (public packages) to share with all of GitHub, or in a private repository (private packages) to share with collaborators or an organization. A repository can be connected to more than one package. To prevent confusion, make sure the README and description clearly provide information about each package.

## Installing a package

You can install a package from GitHub Packages using any supported package client by following the same general guidelines.
1 - Authenticate to GitHub Packages using the instructions for your package client. For more information, see "Introduction to GitHub Packages."
2 - Install the package using the instructions for your package client.

## Deleting a version of a repository-scoped package

```
curl -X POST \
-H "Accept: application/vnd.github.package-deletes-preview+json" \
-H "Authorization: bearer TOKEN" \
-d '{"query":"mutation { deletePackageVersion(input:{packageVersionId:\"MDIyOlJlZ2lzdHJ5UGFja2FnZVZlcnNpb243MTExNg==\"}) { success }}"}' \
HOSTNAME/graphql
```

## Deleting a version of a user-scoped package on GitHub

![image](https://docs.github.com/assets/cb-66754/mw-1440/images/help/package-registry/package-settings.webp){ align = right }
![image](https://docs.github.com/assets/cb-54845/mw-1440/images/help/package-registry/delete-container-package-version.webp){ align = right }



