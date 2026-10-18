# Mobile ad hoc GitHub Actions

The Mobile Ad Hoc workflow validates the release tag, signs the iOS app, checks its provisioning profile and registered devices, and attaches the IPA to a GitHub Release. The workflow does not publish an OTA installation website.

Direct Safari installation requires a public HTTPS static endpoint and a deployment path to the Hetzner host. That hosting path is not configured in this repository yet. Until it is configured and verified, use the attached IPA through the approved distribution process. Do not describe the release as an OTA website deployment.
