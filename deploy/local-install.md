# Local development and testing

This repository is public-safe source, not a ready-to-run personal deployment.
A profile distribution can be installed directly as the profile you use every
day; a separate sandbox is optional, not required.

From the repository root, install a package under its private runtime name:

```sh
hermes profile install "$(pwd)/profiles/restaurant-scout" --name restaurantscoutdev --alias
```

Later, update that profile from the Worldo source with:

```sh
hermes profile update restaurantscoutdev -y
```

Hermes replaces only the files declared distribution-owned by the package. It
preserves private runtime state such as `.env`, OAuth, sessions, memories, and
local configuration. Add real values through the ignored runtime profile;
never commit them.

Recommended direct workflow:

1. Edit the relevant source under `profiles/<specialist>/`.
2. Review the diff, commit, and push it.
3. Run `hermes profile update <live-profile-name> -y`.
4. Test one focused behavior in the profile's normal chat surface.
5. Revert the source commit or make a focused follow-up change if the behavior
   is not correct.

For a profile that already has private values embedded in a source-owned file,
first move those values into a private configuration layer before installing it
as a distribution. This is why the existing Activity Scout is not yet updated
directly from the public package.

Before a VPS deployment, replace local paths with deployment paths and use a
secret manager or protected environment file.
