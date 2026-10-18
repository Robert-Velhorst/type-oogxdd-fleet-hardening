# Production deployment target

Production hosting for this project must move to Hetzner. unapproved serverless hosting and ngrok are not approved production hosts or production tunnels.

## Current deployment that needs retirement

The `.github/workflows/mobile-adhoc.yml` workflow currently deploys iOS OTA install assets to unapproved serverless hosting for `mobile-v*` tags. It defaults to `https://type-ota.unapproved serverless hosting.app` through `IOS_AD_HOC_BASE_URL`; repository variables can override the URL and unapproved serverless hosting project identifiers. This path is not the target. Migrate the OTA site and release verification to Hetzner, confirm the unapproved serverless hosting endpoint is retired, then shut down the unapproved serverless hosting project.

## Migration requirements

- Design and verify a Hetzner-hosted replacement for the OTA manifest and install assets before changing release behavior.
- Keep deployment credentials in protected GitHub secrets or a managed secret store; never commit them.
- Verify the release workflow, HTTPS, manifest, install link, and rollback path against the Hetzner target.
- Do not configure a new production unapproved serverless hosting deployment or use ngrok for production traffic.
- If this repository is not currently deployable on Hetzner, record the concrete host, service, storage, DNS, backup, and rollback requirements before enabling production deployment.
