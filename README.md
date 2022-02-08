[![GitHub release](https://img.shields.io/github/release/utenx/gh-dump-context.svg)](https://github.com/utenx/gh-dump-context/releases/latest)
[![CI workflow](https://img.shields.io/github/workflow/status/crazy-max/ghaction-dump-context/ci?label=ci&logo=github)](https://github.com/utenx/gh-dump-context/actions?workflow=dump-context)
[![Marketplace](https://img.shields.io/badge/action-marketplace-orange?logo=github)](https://github.com/marketplace/actions/dump-github-context)

<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

## Table of Contents

- [About this Repository](#about-this-repository)
- [About Context](#what-is-nodejs)
- [How to use this action?](#how-to-use-this-action)
  - [Available Arguments](#available-arguments)
  - [Supported Context](#supported-context)
  - [Usage](#usage)
- [Contributing](#contributing)
- [Changes](#changes)
- [License](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## About this repository

Action to [dump context](https://docs.github.com/en/actions/reference/context-and-expression-syntax-for-github-actions#example-printing-context-information-to-the-log-file) of your github workflow.

## About Contexts

Contexts are a way to access information about workflow runs, runner environments, jobs, and steps. Each context is an object that contains properties, which can be strings or other objects.

Contexts, objects, and properties will vary significantly under different workflow run conditions.

## How to use this action?

### Available Arguments

| Key        |   Description                     |  Default    | Required?  |
| ---------- | :-------------------------------- | :---------: |:---------: |
| `context`  | Arguments for dump context object |    `all`    |   false    |

### Supported Context

| Context Name |  Type       |   Description  |
| ------------ | :---------: | :------------- | 
| `env`        |    object    | Contains environment variables set in a workflow, job, or step.  
| `github`     |    object    | Information about the workflow run.  
| `job`        |    object    | Information about the currently running job.  
| `steps`      |    object    | Information about the steps that have been run in the current job.  
| `runner`     |    object    | Information about the runner that is running the current job.  
| `strategy`   |    object    | Information about the matrix execution strategy for the current job.  
| `matrix`     |    object    | Contains the matrix properties defined in the workflow that apply to the current job.   

### Usage

```yaml
name: Dump Context

on:
  workflow_dispatch:
  pull_request:
  push:

jobs:
  dump-context:
    runs-on: ubuntu-latest
    steps:
      - name: Dump context
        uses: utenx/gh-dump-context@v1
        with:
          context: github
```

## Contributing

If you can help with any of these areas, or have bug fixes, please fork and raise a Pull Request for me. If you want to open a pull request, please read the [contributing guidelines](.github/CONTRIBUTING.md).

## Changes

For changes, see the [CHANGELOG.md](CHANGELOG.md).

## License

This action is distributed under the MIT license, check the [license](LICENSE) for more info.