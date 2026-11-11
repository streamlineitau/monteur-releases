# Monteur releases

This repository only holds Monteur's updates. Its source code isn't here.

Each release has three files:

- the Monteur Setup (`MonteurSetup-<version>-<date>-<commit>.exe`);
- `latest.json`, which describes that Setup;
- `latest.json.sig`, the Ed25519 signature of `latest.json`.

An installed Monteur checks `releases/latest/download/latest.json` and only installs an update after two checks pass:

1. Its own copy of the signing key confirms the signature.
2. The Setup's SHA-256 matches the one `latest.json` gives.

The private signing key never leaves the build PC.
