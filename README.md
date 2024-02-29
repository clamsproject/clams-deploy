# CLAMS-deploy

This repository contains deployment scripts for CLAMS apps

## Create new CLAMS app

### Install cookiecutter

```bash
pip install cookiecutter
```

### Checkout this repository

```bash
git clone https://github.com/clamsproject/clams-deploy.git
```

### Create the template

From the root of this repository, run the following command:

```bash
cookiecutter .
```

Then fill out the values in the prompt:

- `app_name` should be the name of the app you want to create, e.g. `app-transmogrifier`
- `app_slug` will be the folder name in ths repository.

_If you're unsure about a value, the defaults are probably fine to start with._

Check the generated `app-*` folder to make sure everything looks good. Add any additional files or make any changes as needed.

### Commit the changes

Create a branch and commit the new `app-*` folder to the repository. Open a pull request to document the app and get feedback. If the app is not yet ready for deployment, create the pull request as a draft.

### Deploy the app

The app can now be deployed Kubernetes cluster using a Continuous Deployment (CD) tool like `ArgoCD`.

For a simple, unmanaged deployment, use can the following command:

```bash
kubectl apply -f app-transmogrifier
```
