# Security Policy

## Scope

This repository documents an Azure Static Web Apps deployment lab. It does not contain the application source code for the deployed projects and should not contain credentials or secrets.

## Secret Handling

Never commit:

- Azure deployment tokens
- GitHub personal access tokens
- Microsoft Entra client secrets
- Azure subscription credentials
- private keys or certificates
- `.env` files containing secrets

The Azure Static Web Apps workflows in the application repositories reference deployment credentials through GitHub Actions secrets.

## Reporting a Security Issue

If you discover a security issue in one of the applications documented here, report it privately to the repository owner rather than publishing sensitive exploitation details in a public issue.

## Public Deployment Considerations

Azure resource-management access and application access are separate:

- Azure RBAC controls who can manage Azure resources.
- A Static Web App may still be publicly reachable unless application-level authentication and authorization rules are configured.

## Repository Hygiene

Before publishing screenshots, recordings, or documentation, verify that the following are not exposed:

- subscription IDs when unnecessary
- tenant IDs when unnecessary
- deployment tokens
- API keys
- user email addresses
- private hostnames
- internal IP addresses
- secrets displayed in portal blades or terminal output
