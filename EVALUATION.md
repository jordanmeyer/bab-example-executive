# Evaluation rounds

## Exploratory round 1 — 2026-10-09, before source checkpoint

Not a publishable final evaluation. Initial build succeeded and the dependency checker accepted pinned direct packages and registry lockfile. The initial npm install audit reported zero vulnerabilities. Browser preview loaded on the production prefix. The 13 browser cases passed. They import the actual model functions; expected values were derived in PLAN.md before observing app output. Browser warnings/errors: none observed on the loaded production app through cua_repl logs.

A factual caption defect was discovered while inspecting the rendered ledger: Magnolia's September board copy said 34.3%, but independently calculating `(141000−39762−35250−18200)/141000` yields 33.9% rounded. Corrected before checkpoint. This failed presentation check is retained. The production package was also simplified to ECharts line/bar components; script size fell from approximately 1.97MB to 1.39MB uncompressed. Vite still warns about a >500KB chunk; this is a disclosed performance limitation, not a failed model check.

The first navigation attempted a server before startup and returned connection refused. Starting the owned server fixed the environment. No user data or private files are involved.

Final checkpoint and rendered/keyboard/narrow verification are pending.
