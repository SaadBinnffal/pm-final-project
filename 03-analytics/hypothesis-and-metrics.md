[hypothesis-and-metrics.md](https://github.com/user-attachments/files/34389616/hypothesis-and-metrics.md)
# Hypothesis & Success Metrics: RouteLogic Velocity

Module 3 - Deliverable 3  
Repository path: 03-analytics/hypothesis-and-metrics.md

## Finalized product hypothesis

Based on M2 evidence that frontline users bypass RouteLogic and struggle to find essential work, together with M3 coordinator compliance usage of 77%, compliance satisfaction of 2.2/5, and a 14.6-minute task time against a 3-minute benchmark, I believe reducing unnecessary friction in required compliance checks for frontline fleet coordinators will help them complete their daily workflow inside RouteLogic. I will test for a 30% reduction in mean compliance-task completion time (14.6 to 10.22 minutes), protect coordinator Core Dispatch satisfaction at 4.1/5 and the completeness and validity of required compliance records, and make a limited-pilot go/no-go decision after four full working weeks if the minimum evidence threshold is met.

**Bet type:** Optimizing the existing.

**Strategic outcome:** More coordinators complete the dispatch-to-handoff workflow inside RouteLogic with less effort, supporting repeat use and renewal confidence. A retention or revenue improvement is a downstream hypothesis, not a measured result.

**Evidence status:** All source figures are supplied classroom data. The effect targets, intervention, sampling floor, and decision rules below are proposed planning choices, not experiment results or statistically powered guarantees.

## Success metrics

| Metric | Type | Baseline | Proposed target | Why it matters |
| --- | --- | --- | --- | --- |
| Share of eligible daily coordinator workflow starts reaching Complete Shift Handoff | North Star / product-value signal | 31% of all workflow starts in Snapshot 2 | 40%, a 9-percentage-point increase (about 29% relative) | Tracks whether users finish a meaningful operational workflow, rather than merely click a new control. |
| Mean elapsed time to complete required compliance checks correctly | Primary success metric / leading initiative signal | 14.6 minutes in Snapshot 2; revalidate its start/end and population definition before testing | At most 10.22 minutes, a 30% relative reduction | Targets the largest supplied task-time gap: 11.6 minutes above benchmark. |
| Coordinator satisfaction with Core Dispatch, using the same 5-point question | Guardrail / existing product-value signal | 4.1/5 in Snapshot 3 | At least 4.1/5; also inspect any deterioration against a comparable baseline or control | Protects a highly used, relatively well-rated core capability while simplifying adjacent work. |
| Completeness and validity of mandatory compliance records | Additional quality guardrail | Not supplied; establish through baseline record audits | No increase in the share of attempts with missing or invalid required information; retain every mandatory check and validation | Prevents apparent speed gains caused by skipping required work or recording incomplete results. |

Targets are hypotheses, not source facts. The 3-minute benchmark is a reference point, not a promised first-pilot result. The supplied 31% handoff figure uses all workflow starts; confirm which workflows actually require the step and establish the matching pilot denominator before using it as a baseline.

The provisional 30% time target would recover 4.38 minutes per completed task, or about 37.8% of the 11.6-minute gap to benchmark. It is a material first-step improvement to validate with operations, not a forecast derived from the separate +34% route-speed pilot. The 40% handoff target is likewise a proposed product-level goal that needs baseline and feasibility confirmation.

### Measurement definitions

- **Population:** Frontline fleet coordinators undertaking a daily workflow that includes required compliance checks. Keep role, account, fleet/workload, device/connectivity context, and workflow eligibility visible.
- **Primary timing:** Start when the compliance task is opened; end when its required record is saved successfully and validated. Include interruptions and retries under a consistent rule. Confirm that the course's 14.6-minute baseline uses the same definition; otherwise rebaseline before the test.
- **Avoid survivor bias:** Report all eligible attempts, failed or abandoned attempts, and task completion rate alongside mean completion time. A faster mean among the few remaining completers is not sufficient evidence of success.
- **North Star denominator:** All in-scope daily workflow starts, not just users who reached compliance. Numerator: those reaching the defined shift-handoff completion event.
- **Guardrails:** Use a consistent satisfaction question and inspect response counts and account mix. Audit required records for missing/invalid items and verify that validation rules remain in place.
- **Interpretation:** Compare like-for-like users and workload. Repeated workflows from one coordinator are not independent users. A simple before/after comparison does not establish causality; a larger causal test should use an appropriate comparison group.

## Hypothesis Builder - completed fields

### Step 1 - Project path

RouteLogic Velocity - B2B.

### Step 2 - Where is the bet?

Optimizing the existing: reduce friction in an established daily coordinator workflow.

### Step 3 - Reconcile qualitative and quantitative evidence

**Qualitative evidence:** The M2 dispatcher says, "We keep a WhatsApp group as the real system" [UXR-02]. An operations manager reports that frontline staff cannot find the small set of features they need [UXR-04], and a regional manager connects poor daily driver experience with adoption and renewal risk while still valuing enterprise reporting [UXR-10].

The direct dispatcher quote concerns delayed route changes, not compliance checks. These observations establish bypassing, usability problems, and business risk; they do not prove that compliance complexity is the cause of the WhatsApp workaround.

**Quantitative evidence:** M3 identifies a more specific workflow priority: 77% of coordinator DAUs use compliance, yet coordinators rate it 2.2/5, and checks take 14.6 minutes versus a 3-minute benchmark. Only 48% of workflow starters reach compliance completion and 31% reach shift handoff.

**Reconciliation:** Retain the coordinator persona and the M1 operational-simplicity strategy, but shift the first improvement bet from reassignment acknowledgement alone to the compliance bottleneck. Keep route synchronization as an evidenced problem; the M3 snapshots do not quantify or invalidate it. Observe the compliance task before committing to a particular UI or technical fix.

### Step 4 - Persona and problem

**Role:** A frontline fleet coordinator / dispatcher managing the daily dispatch-to-handoff workflow for a regional delivery fleet.

**Goal:** Complete the day's required operational coordination accurately and efficiently inside RouteLogic.

**Confirmed friction:** Compliance checks are heavily used but time-consuming and poorly rated; they interrupt progress from route assignment toward shift handoff. Existing M2 evidence separately shows delayed shared state and external messaging dependence.

**Problem to solve:** Required compliance work creates a disproportionate time burden within the coordinator's daily workflow.

### Step 5 - Outcome and metrics

**Strategic outcome:** More coordinators finish their required daily workflow within RouteLogic, with less effort and no reduction in record quality or core-dispatch usefulness. Improved retention and renewal are outcomes to validate later.

**Primary success metric:** Reduce mean correctly completed compliance-task time by 30%, from 14.6 to at most 10.22 minutes, after verifying a comparable baseline.

**Guardrail metric:** Coordinator Core Dispatch CSAT must remain at least 4.1/5, supported by comparable survey responses. In addition, mandatory-record completeness and validity must not deteriorate.

**Decision window:** Review after four full working weeks of the pilot, with at least 100 eligible compliance-workflow starts across at least 20 coordinators and three accounts, plus comparable baseline data, usable satisfaction responses, and record-quality audits. These counts are proposed feasibility floors for a directional pilot, not a power calculation; inadequate coverage or uncertainty means no scale decision.

## Exercise Guide - pre-work carried from Modules 1 and 2

| Field | Answer before reviewing M3 data |
| --- | --- |
| Role | Frontline fleet dispatcher coordinating route changes and delivery exceptions. |
| Goal | Keep drivers executing the latest route and coordinate exceptions using operational status they can trust. |
| Friction / moment of misery | Route changes reach drivers 8-15 minutes late, while dashboard status separately lags 20-60 minutes [M2: BUG-2044, BUG-2072]. |
| Current workaround | A WhatsApp group, explicitly described as the real coordination system [M2: UXR-02]. No spreadsheet workaround is established. |
| Problem Hook | We must protect RouteLogic's largest enterprise account from switching to a leaner competitor by addressing the administrative friction that slows frontline fleet coordination. |
| Value Proposition | For frontline fleet coordinators, RouteLogic Velocity will make urgent coordination tasks simpler and faster while keeping advanced enterprise capabilities available, because declining usage and our largest account's competitor trial make restoring operational usefulness an immediate priority. |

## Exercise Guide - Snapshot 1 reflection

### Feature adoption by role

The snapshot partly confirms the broader complexity diagnosis, but it does not prove that every low-adoption feature burdens coordinators. Coordinators use Live Dispatch Board at 91%, Route Optimizer at 85%, and Compliance Checklist at 77%. High adoption can coexist with frustration, especially for a required task.

Scheduling is used by 42% of coordinator DAUs, compared with 79% of manager DAUs. That difference is worth investigating, but M2 does not explicitly identify scheduling as the dispatcher's moment of misery. I will not invent that connection.

Financial Reporting is used by 86% of manager DAUs but only 8% of coordinator DAUs and 3% of driver DAUs. Low frontline use is not a reason to remove reporting; the manager role still gets value from it. AI Predictive ETAs have low usage (23% of coordinator DAUs and 11% of driver DAUs), but low adoption alone does not explain why.

**Pivot check:** Keep the coordinator persona. Prioritize a frequently used task with additional evidence of friction, rather than automatically prioritizing a feature because its adoption is low. Snapshots 2 and 3 make compliance the stronger first bet.

**Denominator caveat:** These adoption figures describe daily active users by role, not all licensed users or overall retention.

## Exercise Guide - Snapshot 2 reflection

### Daily dispatch workflow completion and task times

The workflow data supports the broad M2 finding that RouteLogic fails to support the full operational job, but it does not directly measure the reassignment-sync delay or the exact WhatsApp sequence. It adds a substantial compliance bottleneck that was not explicit in the M2 interviews.

Compliance checks take 14.6 minutes against a 3-minute benchmark: an 11.6-minute gap and approximately 4.87 times the benchmark. This is the largest supplied task-time gap. Shift handoff also deserves attention: 11.3 minutes against 4.5 minutes, a 6.8-minute gap.

| Stage | Share of all workflow starts reaching stage | Loss from previous stage | Conditional loss from previous stage |
| --- | ---: | ---: | ---: |
| Open RouteLogic | 100% | - | - |
| Load Today's Fleet View | 94% | 6 percentage points | 6.0% |
| Assign Routes via Optimizer | 71% | 23 percentage points | 24.5% |
| Log Compliance Checks | 48% | 23 percentage points | 32.4% |
| Complete Shift Handoff | 31% | 17 percentage points | 35.4% |
| File Daily Report | 18% | 13 percentage points | 41.9% |

There are two equally large absolute stage losses of 23 percentage points. Compliance has the largest time gap, but it is not the sole largest funnel drop. The last reporting transition has the largest conditional loss, so stating a "biggest drop" requires naming the denominator.

Only 31% of all starters reach handoff, meaning 69% do not reach that stage. Among the 71% who reach route assignment, the drop to handoff is 40 percentage points of all starts, or approximately 56.3% of those reaching assignment. The handout's blanket "69% abandon after assignment" should not be used as that conditional rate.

The listed time gaps sum to 29.8 minutes, rather than exactly matching the supplied 31-minute daily time-loss figure. These measures have unspecified definitions and methods; their rough similarity does not prove that the listed tasks cause all reported workaround time, and they must not be added together as separate losses.

**Pivot check:** Shift the first improvement bet to compliance-task friction, while verifying whether its time is driven by navigation, repeated entry, validation, technical waiting, or necessary operational work. The exact mechanism remains a hypothesis.

## Exercise Guide - Snapshot 3 reflection

### Account health, NPS, and satisfaction by role

The most relevant cell is **Coordinators x Compliance: 2.2/5**. Combined with 77% coordinator adoption and 14.6-minute task time, it indicates a frequently encountered, low-satisfaction task. Coordinator Core Dispatch is relatively well rated at 4.1/5; retain its usefulness while addressing adjacent friction.

Reporting is actually the lowest-scoring coordinator cell at 1.3/5, but managers rate it 4.5/5 and use it heavily. Role and task relevance matter: the lowest cell alone is not sufficient grounds for removing a capability. Manager Compliance satisfaction is 3.9/5, also highlighting differing role experiences.

The handout reports a 30-point Coordinator NPS decline from +18; the pasted current value has a corrupted sign. A current value of -12 is implied by that change, but should be checked against the original source before being quoted as a clean raw value. Reported daily time lost increased from approximately 9 to 31 minutes (about 3.4 times), and 4 of 5 accounts in the reported churn-reason group cite complexity, compared with 1 of 8 previously. These are small reported samples, not population churn rates.

The Velocity pilot's "+34% route-assign speed" is a promising supplied signal, but its method, sample, metric definition, and uncertainty are absent. It does not demonstrate a 34% reduction in task duration, prove a compliance benefit, or establish improved retention.

**Pivot check:** The broad M1 business crisis is supported. Keep the coordinator persona and preserve manager reporting; narrow the first test to the compliance workflow, where adoption, time, and satisfaction evidence converge. The M2 reassignment journey remains evidence for a separate problem, rather than being rewritten as if it had researched compliance.

## Proposed intervention and validation boundary

Prototype a focused compliance task within the coordinator's existing daily workflow. Make required actions easy to find, reuse only already-known and verified operational data where appropriate, preserve validation and exception handling, and keep enterprise reporting available to managers.

This is a design hypothesis. The source does not establish repeated data entry or navigation as the actual cause of the 14.6-minute task. Observe and instrument the task first; if technical waits or synchronization dominate, address that mechanism rather than assuming fewer screens will solve it.

### Pilot decision rules

1. **Proceed to a larger controlled validation:** The primary target is met, handoff completion reaches the proposed 40% target, both guardrails hold, and the evidence is sufficiently complete and consistent across the included accounts. This is not automatic authorization for full rollout.
2. **Iterate:** Task time improves but handoff does not, or results differ by role/account/workload. Investigate remaining bottlenecks, including the 11.3-minute handoff step.
3. **Stop or pivot:** Time savings come from omitted required work, quality or core-dispatch usefulness deteriorates, or the proposed intervention does not address the observed bottleneck.
4. **Inconclusive:** Sampling coverage, baseline comparability, survey response, instrumentation, or uncertainty prevents a defensible decision. Replan the next read rather than call a win.

## Source-reading audit

- RouteLogic's supplied snapshots cover adoption by role, a workflow funnel with timings, and account health/CSAT. No RouteLogic time-based retention-cohort heatmap is supplied; StreamLine's cohort figures must not be imported.
- The summary claim that everything beyond the three core features is below 25% does not match coordinator Scheduling adoption of 42%.
- Compliance and Scheduling are not literally the two lowest CSAT clusters across every frontline role: Reporting is lower, but has a different role-value context.
- Funnel percentages use all starts; percentage-point loss and conditional abandonment are distinct.
- The pilot effect, benchmark, bug-report delays, interview estimates, and proposed targets are different kinds of evidence. None is substituted for a measured test result.

## One-line key learning for the cohort channel

My M1 bet was to restore frontline simplicity; M3 keeps the coordinator persona but shifts the first improvement test from reassignment acknowledgement alone to compliance, where high use, long task time, and low satisfaction converge.

## Sources and provenance

- Module 1: 01-product-thinking/problem-hook.md - strategic crisis, Problem Hook, and Value Proposition.
- Module 2: 02-discovery/ai-synthesis.md and 02-discovery/competitive-and-journey.md - supplied UXR and bug evidence, selected persona, and the documented workaround.
- Module 3: the supplied Exercise Guide, RouteLogic Snapshots 1-3, and Hypothesis Builder fields.

Prepared with ChatGPT from classroom sample data. Proposed benefits, thresholds, and design mechanisms require validation; no new field research, live telemetry analysis, experiment execution, repository commit, or cohort-channel post is claimed.
