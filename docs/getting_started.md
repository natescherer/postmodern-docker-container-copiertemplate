# Getting Started

## Prerequisites

### Your Machine

There are two ways to install the prerequisites needed on your machine: running them inside of a [devcontainer](https://containers.dev/), or installing them manually. Please see linked documentation for details:

[Prerequisites via Devcontainer](docs/prereqs_devcontainer.md) **Recommended**

[Prerequisites via Manual Installation](docs/prereqs_manual.md)

### GitHub

### One-Time Actions for all Postmodern repositories

1. Install the [AllContributors GitHub App](https://github.com/apps/allcontributors/installations/new) for your user or organization.
   - You can either give it access to all your repositories, which means you only need to do this step once, or you can select repositories individually, in which case you will need to do this for each new repo you create.
1. Ensure `Private vulnerability reporting > Automatically enable for new public repositories` is checked [here](https://github.com/settings/security_analysis).

## Using this template

1. Open a terminal to the parent directory where you want the repo subdirectory to be created
1. Run the following to initialize the template:

   ```bash
   copier copy --trust gh:natescherer/postmodern-docker-container-copiertemplate .
   ```
