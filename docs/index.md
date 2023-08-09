# GitHub Actions

For full documentation visit [docs.github.com](https://docs.github.com/en).

## Understanding GitHub Actions 

`GitHub Actions` is a continuous integration and continuous delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. You can create workflows that build and test every pull request to your repository, or deploy merged pull requests to production.
You must host your own Linux, Windows, or macOS virtual machines to run workflows for your GitHub Enterprise Server instance. Self-hosted runners can be physical, virtual, in a container, on-premises, or in a cloud.
    

## Creating an example workflow

Workflow example:

```
name: learn-github-actions
run-name: ${{ github.actor }} is learning GitHub Actions
on: [push]
jobs:
  check-bats-version:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

## The Components of GitHub Actions

!!! note "Workflows"
    A workflow is a configurable automated process that will run one or more jobs. Workflows are defined by a YAML file checked in to your repository and will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule.Workflows are defined in the .github/workflows directory in a repository, and a repository can have multiple workflows, each of which can perform a different set of tasks.

!!! info "Jobs"
    A job is a set of steps in a workflow that is executed on the same runner. Each step is either a shell script that will be executed, or an action that will be run. Steps are executed in order and are dependent on each other. Since each step is executed on the same runner, you can share data from one step to another. For example, you can have a step that builds your application followed by a step that tests the application that was built.

!!! tip "Events"
    An event is a specific activity in a repository that triggers a workflow run. For example, activity can originate from GitHub when someone creates a pull request, opens an issue, or pushes a commit to a repository. You can also trigger a workflow to run on a schedule, by posting to a REST API, or manually.

!!! abstract "Runners"
    A runner is a server that runs your workflows when they're triggered. Each runner can run a single job at a time. You must host your own runners for GitHub Enterprise Server. For more information, see "Hosting your own runners."

## Activity of a workflow run

![image](https://docs.github.com/assets/cb-21779/mw-1440/images/help/repository/actions-tab.webp){ align = right }

![image](https://docs.github.com/assets/cb-40551/mw-1440/images/help/actions/superlinter-workflow-sidebar.webp){ align = right 0}



