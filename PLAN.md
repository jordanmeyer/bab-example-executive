# Stillwater Coffee operating review

Agreed through a simulated student conversation on 2026-10-09. This is a synthetic classroom example, not an actual student's product or a real business.

## Purpose and smallest useful version

A fictional coffee-chain COO prepares a board discussion about labor productivity and product purchasing/waste. The app compares 12 mature stores in Coast, Piedmont and Highlands over April–September 2026. The user can filter reporting month, region and store, inspect cost changes, examine all 72 store-month records, and walk through three September board questions. Expansion decisions, forecasts, imports, live accounting, accounts and storage are excluded.

## Model and inputs

All authored accounting amounts are integer USD cents. `app/data.js` describes the synthetic stores, sales, expense ratios, occupancy/other costs, transactions and hours; this file deterministically constructs the 72 records. No records represent an actual customer or business. Store contribution equals sales minus product cost, labor and occupancy/other store costs. Product cost includes waste; headquarters, taxes and financing are excluded. Net sales exclude sales tax. This metric is not company profit.

Margin is contribution divided by sales. Comparable growth is current sales divided by same-month 2025 sales, minus one. All stores are mature and present in every month, so this is a consistent comparable base. Prior-year sales are synthetic rounded cents derived from authored growth assumptions except the independent reference case. Ticket is sales divided by transactions. Sales per labor hour is sales divided by hours. Aggregate rates always use sums of numerators and denominators. No simple average of store rates is used. The cost bridge compares dollar changes and changes in each cost's share of that month's sales; it is an accounting decomposition, not causal attribution.

Displayed totals round to whole USD; unit economics retain cents. Source calculations retain exact cents. Rates round to one decimal and changes to one percentage point decimal. Decisions use unrounded values. Zero denominators return unavailable ratios; an empty ledger shows zero dollars and unavailable margin. The margin target starts at 20%, is explicitly a classroom assumption, and accepts 0–100 inclusive; blank/out-of-range values show an error and suppress the comparison. A store at the target meets it. Margin and comparable growth remain distinct; no composite health score.

## Libraries and design

Managed Vite build with approved Mantine 9.7.1 and React 19.3.0 for controlled filters/modal focus, Apache ECharts 6.1.0 for margin comparisons and trends, and a native HTML table for the 72-record sortable operational ledger. No additional library is needed. The bundled Campus Designer supplies unchanged navy/royal, purposeful copper/neutral accents, locally bundled EB Garamond 400 headings and Open Sans 400/600 body with published fallback stacks and OFL licenses. No institutional marks, affiliations or remote fonts.

## Independently expected results

Student-supplied reference: sales $100,000 less product $32,000, labor $28,000 and occupancy/other $15,000 equals $25,000 and 25%. Same-month prior sales $90,000 yields $10,000/$90,000 = 11.111…% growth. 5,000 transactions yields $20 ticket. September Meadow House must match this. An independently constructed unequal-size pair ($100k sales/$25k contribution and $300k sales/$0 contribution) has margin $25k/$400k = 6.25%, not the simple average 12.5%.

September company totals were independently added from the authored store inputs before browser results: sales $1,441,000 and contribution $341,800; margin 341800/1441000; four stores below 20%. Harbor August labor is $153,000 ×32.5% = $49,725 and September is $156,000 ×37% = $57,720: +$7,995 and +4.5 percentage points. Harbor contributions are $32,621 and $26,360, so the fall is $6,261. Cases also cover empty selection, negative contribution, exact-target equality, cent arithmetic, 72-record uniqueness and literal HTML-like table data.

## Acceptance

Desktop and 320 CSS-pixel production frames must show readable hierarchy, wrapped controls and no whole-page horizontal overflow; genuinely wide tables may scroll. Keyboard users can select filters, sort native ledger headers, open store/board modals, navigate steps and dismiss with Escape. Modal focus returns to its trigger. Charts have textual/table alternatives. Region and store filters apply to indicators, trend, regional comparison and ledger; reporting month changes the snapshot while the trend retains six months. The fixed September board briefing is explicitly labeled independently of filters. Search changes ledger rows/totals only. The Operating ledger view and its full-period switch expose 72 records in the company scope. Reset restores initial values. The independent browser suite must pass and the production repository prefix, source link and notices must load. Reduced motion is honored; no external runtime calls are authored.

No material planning questions remain. Limitations are disclosed in the product and README, including lack of causal, staffing adequacy or expansion evidence.

## Authorized live revision — 2026-10-09

The user asked to bring the live apps up to the revised guidance. This authorizes the scope changes here; no new simulated student exchange is implied. First load teaches that sales growth can coexist with contribution pressure. The overview keeps current indicators and two charts together; the ledger is a separate primary evidence view with native table semantics, keyboard-sortable headers and store-detail buttons. It shows no fixed month column in selected-month mode, no duplicate sort selector and no redundant disabled inspect action. Every filter updates immediately.

Each board question now includes its own chart and evidence table: Harbor indexes sales and labor hours to April=100 and compares August/September levels; Market Square compares product-cost share and margin; Magnolia compares September margin and sales/hour with its regional peers. All conclusions remain investigation prompts. The line-chart percentage axis is visibly labeled as zoomed, and the target label sits in the caption to avoid collision. Regional bars retain a zero origin and the explicit Region selector owns filtering.

Prior-year contribution is newly authored synthetic history: per-store rates [25,25.5,23.1,26.3,28.5,19.3,25.2,22,27.2,24.6,25.4,24]% plus monthly offsets [0,0.2,-0.1,0.4,0.1,0] percentage points. Multiply each record's prior-year sales by that rate and round to cents. Aggregate prior-year margin is sum(prior contribution)/sum(prior sales), on the same stores as current margin; if any selected record lacks prior contribution or positive prior sales, the comparison is unavailable. This provides the requested annual margin context without implying actual historical data.

Additional independent expectations: prior contributions $10+$90 on prior sales $100+$300 imply weighted prior margin 25%; a missing prior contribution suppresses the comparison. Harbor September sales per labor hour=$156,000/2,600=$60; August=$153,000/2,210=$69.23077. Market product spend August=$129,000×35.4%=$45,666, September=$132,000×39%=$51,480. Magnolia September contribution=$47,788 and margin=33.8922%. Public BUILD-STORY.md links the original brief, actual simulated planning record, current plan and evaluation. No source or model is certified by this narrative.

Returning navigation resets controls, views and results together. The browser may restore native select values after mounting; the pageshow handler remounts the controlled view after that restoration so a restored selector cannot describe stale results.

## Authorized checklist corrections — 2026-10-09

The revised checklist adds bounded student tasks and remaining interpretation fixes. Keep every existing calculation/default. Make comparison periods explicit, show threshold-only status changes, add regional exact values and signed effects on contribution to the bridge. Before supplied board interpretations, ask for a prediction and next evidence check. A small local text takeaway carries scope, metrics, evidence inspected and the student's next investigation; it is copied explicitly and never persisted by the app. Store detail entered from the briefing returns to that same question, while ledger details return to their original trigger. The public build-story walkthrough contains prediction, specified control change, independent answer and limitation, including the existing unequal-size Harbor/Meadow pair. Actual novice and screen-reader evidence are not inferred from automated tests and remain explicitly unverified until performed.


## Executive review repair — October 9, 2026

The production review at source2116c4b found two real defects: an unchanged expense produced negative zero and displayed +-$0, and one Escape from the briefing's cost detail closed both the detail and the restored briefing. Costs now use previous minus current directly so equal expenses have positive zero. The bridge case asserts whole-USD zero formatting as well as its signed sum.

Both existing dialogs now belong to Mantine's Modal.Stack with explicit IDs. The pinned implementation shares a handled-Escape set and gives only the active dialog its Escape/focus-trap behavior. This makes one key event close only the detail even when its close handler restores the briefing during that same event. Keep the existing return-to-question focus behavior and direct-ledger trigger behavior; no timeout or synthetic wait hides the failure. Rebuild production and repeat each of the three briefing→detail→Escape→next-question paths plus direct ledger→detail→Escape. Observe +$0 for unchanged occupancy. Root owns actual browser execution because this agent has no available CUA browser.
