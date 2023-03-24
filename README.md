# example-good-repo-secrets

This is a well configured repository to show how to prevent to leak Repository Secrets using GitHub Actions.

In this repository is configured is a secret named `SECURE_SECRET`.

Using GitHub Action you can't get the secret (catch the flag).

Scenario:
- `main` has branch protection enabled
- there is a `prod` environment with `Deployment branches` configured with `Protected branches` (if you use multiple protected branches you may need to use `Selected branches`)
- `SECURE_SECRET` is configured on `prod` environment level
- anyone in PagoPA GitHub Organization has `write` permission on this repository

Safe scenario:
- an internal user with `write` permission create a Pull Request to try get `SECURE_SECRET` value (example Pull Request https://github.com/pagopa/example-good-repo-secrets/pull/1)
