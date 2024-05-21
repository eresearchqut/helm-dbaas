# DBaaS Helm Repository

This repository contains Helm charts for the DBaaS project.

## Installation

To install this Helm repository on your machine, follow these steps:

1. Add the repository to your Helm client:

    ```bash
    helm repo add dbaas https://eresearchqut.github.io/helm-dbaas/
    ```
2. Update your Helm client with the latest charts:
    ```bash
    helm repo update
    ```
3. Now, you can install the charts from this repository. For example, to install a chart named dbaas-tenant, you would run:
    ```bash
    helm install dbaas-tenant dbaas/dbaas-tenant
    ```

For more information on using Helm, refer to the official [Helm documentation](https://helm.sh/docs/).


## Publishing a New Release

To publish a new release of a Helm chart, you need to push a new tag to the repository. Here's how you can do it:

1. Make sure all your changes are committed. You can check this by running the following command:

    ```bash
    git status
    ```

    If there are uncommitted changes, commit them with the `git commit` command.

2. Create a new tag. The tag name should be the new version number. You can create a new tag with the `git tag` command. For example, to create a tag named `v1.0.1`, you would run:

    ```bash
    git tag v1.0.1
    ```

3. Push the tag to the repository. You can do this with the `git push` command followed by the tag name. For example, to push the `v1.0.1` tag, you would run:

    ```bash
    git push origin v1.0.1
    ```

After you push the tag, the GitHub Actions workflow defined in the repository will automatically run. This workflow is triggered by tag pushes. It packages the Helm charts in the repository and publishes them to the `gh-pages` branch using the `helm-gh-pages` action. The `gh-pages` branch is then used to serve the Helm repository.
