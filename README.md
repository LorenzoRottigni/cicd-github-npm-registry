# CI/CD GitHub NPM Registry Template

This is a template repository containing a basic integration between:
- Github CI/CD
- NPM (public/private) Package Registry
- Github Repo
- Lerna monorepo

Packages under the "packages" directory containing a valid package.json are automatically included in Lerna management.

## CI/CD

The github workflow publish.yml will automatically handle the build, setup, versioning, and publishing of all packages.

It uses a patch versioning strategy to allow complete automation of the process.

The pipeline will automatically publish packages accordingly to the registry, and through an automated push, it updates version tags inside the Github repository.

It requires a few CI/CD custom variables:
- NPM_ACCESS_TOKEN: Access token from NPM to allow the publishment of new packages
- CICD_SSH_PRIVATE_KEY: Private key configured on Github to allow pushing versioning changes back to the repo.

