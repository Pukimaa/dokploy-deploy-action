# Dokploy Simple Deploy Action

This repository contains GitHub Actions for triggering deployments of applications in Dokploy. 
This is useful if you want to trigger it after a build/push of your docker image in your CI.

## Features

- Trigger deployment on Dokploy
- Easy integration with GitHub workflows

## Usage

To use these actions in your GitHub workflow, add the following to your `.github/workflows/deploy.yml` file:

```yaml
name: Deploy application

on:
  push:
    branches:
      - main

jobs:
  dokploy_deploy:
    uses: Pukimaa/dokploy-deploy-action@2.1.0
    with:
      APPLICATION_ID: cG-ttW6-r-HBWy1XC4Qja
      DOKPLOY_HOST: ${{ secrets.DOKPLOY_HOST }}
      DOKPLOY_TOKEN: ${{ secrets.DOKPLOY_TOKEN }}
    
```

## Inputs

- `APPLICATION_ID`: The ID of the application you want to trigger the deploy for. If you open up the application in the Dokploy Dashboard, it's the last ID in the URL.
- `DOKPLOY_HOST`: The host ip or domain of your dokploy instance. (`example.com`)
- `DOKPLOY_TOKEN`: Create an API token in your profile settings on Dokploy.
