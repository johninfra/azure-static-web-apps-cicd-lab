# Verification Checklist

Use this checklist when validating an Azure Static Web Apps deployment.

## Azure Resource

- [ ] Static Web App exists in the intended subscription
- [ ] Resource is in the intended resource group
- [ ] Resource name is correct
- [ ] Hosting plan is appropriate
- [ ] Resource tags are applied where useful

## GitHub Integration

- [ ] Correct GitHub account connected
- [ ] Correct repository selected
- [ ] Correct branch selected
- [ ] Azure-generated workflow exists under `.github/workflows/`
- [ ] Deployment token is stored as a GitHub Actions secret
- [ ] No token value is committed to the repository

## Build Configuration

- [ ] Build preset is appropriate for the application
- [ ] App location points to the static application source
- [ ] API location is blank when no API exists
- [ ] Output configuration matches the repository layout

## CI/CD

- [ ] Initial workflow run completed successfully
- [ ] Push to `main` triggers a deployment
- [ ] Pull-request workflow behavior is understood
- [ ] Failed workflow runs are investigated before merging changes

## Application Validation

- [ ] Azure-generated HTTPS URL loads successfully
- [ ] Main page renders correctly
- [ ] JavaScript functionality works
- [ ] Browser console has no unexpected deployment-related errors
- [ ] Static assets load correctly
- [ ] Mobile/desktop layout remains usable

## Security Review

- [ ] No deployment token exposed in commits
- [ ] No secrets visible in screenshots or videos
- [ ] Public-vs-private application access is understood
- [ ] Azure RBAC permissions are reviewed separately from website access
- [ ] Content Security Policy remains appropriate for the hosted application

## Portfolio Evidence

- [ ] Architecture documented
- [ ] Deployment process documented
- [ ] Source repositories linked
- [ ] Creator/author attribution included
- [ ] Walkthrough video linked
- [ ] Claims accurately distinguish lab/project work from enterprise production experience
