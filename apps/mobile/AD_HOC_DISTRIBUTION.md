# Ad hoc iOS distribution

The release workflow signs and validates the IPA, then attaches it to a GitHub Release. It no longer publishes or verifies a hosted installation page.

For direct Safari installation, the static OTA site still can be generated with the ota build command. Production hosting and upload must be configured on Hetzner before a hosted installation flow can be restored. The endpoint must serve manifest.plist as XML and the IPA as a binary download over HTTPS. Keep the generated files private until the intended distribution and device access have been reviewed.
