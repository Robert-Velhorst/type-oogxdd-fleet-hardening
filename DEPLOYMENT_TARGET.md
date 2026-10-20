# Production deployment target

Production hosting for this project must move to Hetzner. Local development tunnels and other unapproved hosting providers are not production targets.

## Current release workflow

`.github/workflows/mobile-adhoc.yml` builds and signs an ad-hoc iOS IPA for `mobile-v*` tags. For tag-triggered releases, the workflow attaches the IPA to a GitHub Release; manually dispatched runs publish the IPA as a temporary Actions artifact. The workflow does not deploy an OTA website, manifest, or install assets to a hosting provider.

## Hetzner migration requirements

- If product distribution requires a hosted OTA manifest or install site, design and verify a Hetzner-hosted replacement before changing release behavior.
- Keep deployment credentials in protected GitHub secrets or a managed secret store; never commit them.
- Verify HTTPS, the manifest, install link, release workflow, and rollback path against the Hetzner target before claiming migration.
- If this repository is not currently deployable on Hetzner, record the concrete host, service, storage, DNS, backup, and rollback requirements before enabling production deployment.