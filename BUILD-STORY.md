# How Stillwater Coffee was built

## The original request

“I'm the COO of a fictional specialty coffee chain. I need a board-ready executive dashboard to see which stores are healthy, where contribution is slipping, and what to investigate this month. I want to compare regions and stores, examine a meaningful operating table, and walk the board through a few decisions. This is a classroom example with synthetic data.”

## Planning and choices

The [simulated planning exchange](PLANNING-CONVERSATION.md) is an actual recorded exchange between developer and coordinating agent, not a real student interview. It selected 12 mature stores, six months, store contribution excluding headquarters/taxes/financing, and labor/product-cost investigations. [PLAN.md](PLAN.md) defines the complete model, assumptions, independent reference cases and revision acceptance; [DECISIONS.md](DECISIONS.md) records changes.

The October 9 live revision puts a chart and comparison table inside each board question, adds synthetic same-store prior-year margin, makes the primary ledger a native sortable table, and loads licensed local fonts. The original Tabulator component and duplicate fallback table were removed because one accessible primary interface is clearer. No university marks or endorsement are used.

## Recipes

Browser App Builder supplied the Plan, Build, Evaluate and Deploy workflow. Mantine/React provide controlled filters and focus-aware dialogs; Apache ECharts provides the analytical views. Native HTML provides the operating ledger. Campus Designer guidance supplies published blues and locally bundled EB Garamond/Open Sans, with OFL notices. Vite bundles all runtime assets; no external service or customer data is involved.

## Evidence and limits

[EVALUATION.md](EVALUATION.md) retains failed and passing developer rounds, exact source checkpoints and observed browser results. [REVIEW.md](REVIEW.md) records independent review; [DEPLOYMENT.md](DEPLOYMENT.md) distinguishes the deployed version. A source build is not evidence of live publication. The model supports an investigation, not causal staffing or expansion conclusions. All figures and stores are synthetic.


## Student investigation

Do this before opening the supplied interpretation in the briefing. Write each prediction in your own notes, then use **Record your investigation** to copy the scope, values, evidence and your next check. Notes are transient; copy before leaving or reloading. This exercise is authored guidance, not evidence that a novice has completed it.

1. Reset the dashboard to September, all regions/stores, target20%. Predict whether Harbor Wharf's contribution decline is primarily associated with sales, product cost or labor. Open the first board question, inspect August/September, and name one further check before revealing the interpretation. Open full cost detail, reconcile the signed contribution effects, then close it to return to the same question. Continue through all three questions.
2. Predict which stores change status if the target rises from20% to25%. Change only the target. Explain why sales, contribution and margin do not change. Enter101 to observe a rejected target, then correct it to25; financial results remain available while an invalid classification is suppressed.
3. Use September ledger rows for Harbor Wharf and Meadow House. Predict whether averaging their percentages gives their combined margin. Add their sales and contribution, divide those totals, then reconcile the company headline from the full ledger totals.
4. Copy a takeaway with the evidence inspected and one next investigation. State a limitation that prevents turning the observed association into a staffing cut or expansion recommendation.

<details>
<summary>Worked answers — reveal after your prediction</summary>

Harbor sales rose from$153,000 to$156,000 while labor hours rose2,210→2,600. Sales per hour fell from$69.23 to$60. The bridge's effects on contribution are sales+$3,000, product−$1,266, labor−$7,995 and occupancy/other$0: total−$6,261, matching$26,360−$32,621. Ask for daypart demand, overtime and service-quality evidence; revenue productivity alone does not justify reducing staff. Market Square's product spend grew$45,666→$51,480, and Magnolia's33.9% margin is a peer comparison, not a transferable causal result.

At20%, four stores are below target; at25%, six are below. Tidewater and Summit Park newly change status. Meadow House at exactly25% meets the target. These are classifications under a classroom assumption, not performance changes.

Harbor contributes$26,360 on$156,000 sales (16.8974%); Meadow contributes$25,000 on$100,000 (25%). The simple average is20.9487%. Their combined margin is$51,360/$256,000=20.0625%, because the larger Harbor store carries more weight. The company headline similarly uses$341,800/$1,441,000=23.7196%, displayed23.7%. Sales and margin comparison cards use the same month last year; the contribution change uses August. They answer different time questions.

Regional September contributions/sales are Coast$102,180/$502,000=20.4%, Piedmont$126,102/$513,000=24.6%, Highlands$113,518/$426,000=26.6%. These company-wide peer values remain visible even when a store is selected.

</details>

### Observation protocol

For a real novice session, ask for the default interpretation, target prediction, invalid-target recovery and one limitation without coaching or showing the answers first. Record the participant's own explanation and confusion with consent; use no identifying details. No such session is claimed here until evidence records it. Actual screen-reader verification must complete the chart/table, invalid-target and chained-modal tasks using the reader; DOM/keyboard inspection alone cannot close that requirement.
