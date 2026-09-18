# Deployment Guide

This document records the deployment process used for the two applications in this lab.

## Applications

- `johninfra/security-plus-command-center`
- `johninfra/phishing-email-detector`

Both applications were created by John Tyler / `johninfra`.

## Prerequisites

- Microsoft Azure subscription
- GitHub account with access to the application repository
- application repository on the `main` branch
- static application entry point at the repository root

## Azure Portal Procedure

1. Open **Azure Static Web Apps**.
2. Select **Create**.
3. Choose the target Azure subscription and resource group.
4. Enter a unique Static Web App resource name.
5. Select the **Free** hosting plan for the lab.
6. Choose **GitHub** as the source.
7. Authorize the GitHub account if prompted.
8. Select:
   - organization/account: `johninfra`
   - target repository
   - branch: `main`
9. Configure the build details:
   - **Build preset:** Custom
   - **App location:** `/`
   - **API location:** blank
   - **Output location:** blank in the portal configuration used for this static source layout
10. Select the deployment authorization policy using a **deployment token**.
11. Add resource tags as appropriate.
12. Review and create the resource.
13. Wait for the Azure-generated GitHub Actions workflow to complete.
14. Open the Azure Static Web App resource and launch the generated site URL.

## Generated GitHub Actions Workflows

Azure created one deployment workflow in each source repository:

### Security+ Command Center

`.github/workflows/azure-static-web-apps-mango-forest-0889e121e.yml`

### PhishLens

`.github/workflows/azure-static-web-apps-proud-ground-0f2eb851e.yml`

Both workflows use `Azure/static-web-apps-deploy@v1` and reference a repository secret containing the Azure deployment token.

## CI/CD Trigger Behavior

The workflows are configured for:

- pushes to `main`
- pull requests opened, synchronized, or reopened against `main`
- pull request close events for environment cleanup

This means application changes can be deployed through the GitHub workflow rather than by manually uploading site files to Azure.

## Verification

After deployment:

1. Confirm the GitHub Actions workflow completes successfully.
2. Open the Azure Static Web App.
3. Launch the application URL.
4. Verify expected UI and functionality.
5. Verify a subsequent code change to `main` triggers a new workflow run.

## Walkthrough Video

Public deployment walkthrough:

https://youtu.be/Gj0A1xJ5hoo
