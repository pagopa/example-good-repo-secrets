# example-good-repo-secrets

This is a well configured repository to show how to prevent to leak Repository Secrets using GitHub Actions.

In this repository is configured is a secret named `SECURE_SECRET`.

Using GitHub Action on Pull Request you can't get the secret (catch the flag).

Scenario:
- `main` has branch protection enabled
- there is a `prod` environment with `Deployment branches` configured with `Protected branches`. Tf you use multiple protected branches you may need to use more strict configuration `Selected branches` (example `prod` environment configuration https://github.com/pagopa/example-good-repo-secrets/blob/main/images/environment-prod.png)
- `SECURE_SECRET` is configured on `prod` environment level
- anyone in PagoPA GitHub Organization has `write` permission on this repository

Safe scenario:
- a user with `write` permission create a Pull Request to try get `SECURE_SECRET` value. The GitHub Action fails to start because only a protected branch can use `prod` environment (example Pull Request https://github.com/pagopa/example-good-repo-secrets/pull/1)

## How to leak unsecure GitHub Secrets?

See this example https://github.com/pagopa/example-bad-repo-secrets
