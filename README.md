# Mitosu Agent releases

Public downloads for signed Mitosu Agent releases. The agent's source code is maintained separately in private repositories.

The installer entry point is:

```sh
https://install.mitosu.io/agent
```

The versioned bootstrap downloads its signed manifest, platform payload, and installation helper from this repository's GitHub Release assets. Downloads require no GitHub account or token.

Immutable asset URLs have this form:

```text
https://github.com/mitosu-cloud/mitosuagent-releases/releases/download/v<VERSION>/<ASSET>
```

Each completed release includes:

- Linux arm64 and x86_64 payloads, and signed, notarized macOS packages for both architectures.
- Platform installation helpers.
- `manifest.tsv` and its `manifest.tsv.sig` Ed25519 SSHSIG signature.
- `mitosuagent.spdx.json` and `provenance.json`.
- The rendered `agent` bootstrap, which pins the manifest's SHA-256 and the release verification key.

The bootstrap verifies the manifest signature and selected asset digest before installation. Release assets are published only after the signed bundle has been verified. A published version's assets must not be replaced with different bytes.
