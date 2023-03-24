# example-bad-repo-secrets

This is a misconfigured repository to show how to leak Repository Secrets using GitHub Actions.

In this repository is configured is a secret named `UNSECURE_SECRET`.

Using GitHub Action you can get the secret (catch the flag).

- `main` has branch protection enabled
- anyone in PagoPA GitHub Organization has write permission on this repository
