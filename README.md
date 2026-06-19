# weather-poly-runner

Free public-repo GitHub Actions compute for a **private** project.

This repo contains **no strategy code and no data** — only the workflow in
`.github/workflows/runner.yml`. On a dense schedule it:

1. Checks out the private `weather_polymarket` repo at runtime (write-scoped
   deploy key), runs its **dry-run** pipeline, and pushes state back to the
   **private** repo.
2. Keeps all strategy stdout in a logfile pushed to the private repo, so these
   public Action logs stay generic.

No wallet key lives here: the pipeline runs dry-run only (it never places
real-money orders without a private key, which is intentionally absent).

Public-repo Actions are free and unlimited on standard runners, which is the
whole point — full worldwide intraday coverage at $0, strategy stays private.
