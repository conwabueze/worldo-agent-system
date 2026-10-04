# Local Installation Notes

This repository is a public-safe source package, not a ready-to-run personal
deployment.

1. Install Hermes Agent and create a named profile.
2. Copy or package the relevant agent directory into that profile.
3. Add real values locally through the profile's ignored configuration and
   OAuth flows; never place them in this repository.
4. Connect Discord with an allowlisted user and limited channel permissions.
5. Connect the official Notion MCP only to the intended profile.
6. Select the smallest tool set needed, test reads first, then test one
   explicit write.

Before a VPS deployment, replace local paths with deployment paths and use a
secret manager or protected environment file.
