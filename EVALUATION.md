# Evaluation rounds

## Exploratory round 1 — 2026-10-09, before source checkpoint

Not a publishable final evaluation. Initial build succeeded and the dependency checker accepted pinned direct packages and registry lockfile. The initial npm install audit reported zero vulnerabilities. Browser preview loaded on the production prefix. The 13 browser cases passed. They import the actual model functions; expected values were derived in PLAN.md before observing app output. Browser warnings/errors: none observed on the loaded production app through cua_repl logs.

A factual caption defect was discovered while inspecting the rendered ledger: Magnolia's September board copy said 34.3%, but independently calculating `(141000−39762−35250−18200)/141000` yields 33.9% rounded. Corrected before checkpoint. This failed presentation check is retained. The production package was also simplified to ECharts line/bar components; script size fell from approximately 1.97MB to 1.39MB uncompressed. Vite still warns about a >500KB chunk; this is a disclosed performance limitation, not a failed model check.

The first navigation attempted a server before startup and returned connection refused. Starting the owned server fixed the environment. No user data or private files are involved.

Final checkpoint and rendered/keyboard/narrow verification are pending.

## Round 2 — source 66c29a1717c39c8945a59cf04b37885cb8aa0b4b — keyboard FAIL

Freshness/plan checks passed before testing and a clean build produced unchanged notices. Node22.19.0/npm10.9.3 and the dedicated cua_repl IAB tab were used. Browser model suite passed13/13. Production reference Meadow House showed $100,000 sales/$25,000 contribution/25.0%/+11.1% growth. Full-period ledger showed72 records, $8,325,000 sales and $2,038,411 contribution. Unmatched search showed0 rows/$0/ unavailable margin. All three board questions navigated with Enter. The 1440px desktop and320px production frames rendered; narrow document measured319px client/scroll widths (frame border accounts for one pixel), so no page horizontal overflow.

FAIL: Escape closed a store detail but focus fell to body because the modal was removed rather than retained closed. Ledger data was also needlessly replaced during modal state changes, replacing row triggers. Fix: retain a closed modal, memoize filtered rows so unrelated changes preserve triggers. Remove unlabeled numeric stepper buttons (typed target remains), and explicitly set white-on-royal outline-button hover. Re-evaluation required at the next commit. No source changes were represented as covered by this old round.
