# Local development and testing

This repository is public-safe source, not a ready-to-run personal deployment.
Use a disposable Hermes profile for changes before applying them to a live
profile.

From the repository root, install the Activity Scout package from the local
source directory:

```sh
hermes profile install "$(pwd)/profiles/activity-scout" --name activity-scout-sandbox --alias
```

Hermes copies the distribution-owned files into the sandbox runtime profile.
Then configure the sandbox locally: choose its model, complete any OAuth flow,
and add its credentials through the profile's ignored runtime configuration.
Never commit those values.

Recommended loop:

1. Edit Worldo source under `profiles/activity-scout/`.
2. Reinstall or update the disposable `activity-scout-sandbox` profile.
3. Test basic research in the CLI/TUI first.
4. Test Notion reads, then one explicit, reversible test write.
5. Review the result and only then apply the same vetted source to the live
   profile.

Do not force-install over a live profile until its runtime state is backed up
and you have reviewed which files the distribution owns. Before a VPS
deployment, replace local paths with deployment paths and use a secret manager
or protected environment file.
