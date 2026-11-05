[experimentation-plan (1).md](https://github.com/user-attachments/files/34447578/experimentation-plan.1.md)
# Experimentation Plan (Module 5)

**Experiment:** RouteLogic Velocity - Guided Compliance Review A/B Test  
**Author:** Saad Binnffal  
**Scenario:** RouteLogic (B2B logistics)  
**Repository path:** 05-experimentation/experimentation-plan.md  
**Status:** Completed classroom design; not executed. Live launch requires a comparable measured baseline/variance, sufficient eligible coordinators, and an instrumented implementation.

## Overview

Test whether the M4 B1 guided compliance-review workflow reduces coordinator task time while preserving required record quality and existing Core Dispatch usefulness. Use a coordinator-randomized A/B test, with stable assignment and 50/50 allocation within each participating account. A feature flag controls exposure and rollback; it does not replace the comparison.

The M4 HTML is a local-state prototype, not an instrumented production implementation. Its scripted checks validate UI behavior, not the 14.6-minute operating baseline or a measured 30% time saving. The A/B test starts only after both live experiences and measurement are ready.

## Get your documents ready

- **From M3, your hypothesis sentence:** Based on frontline usability problems and the M3 evidence that compliance is used by 77% of coordinator DAUs, scores 2.2/5 in coordinator satisfaction, and takes 14.6 minutes against a 3-minute benchmark, reducing unnecessary compliance friction should help coordinators complete their daily workflow inside RouteLogic. The proposed goal is a 30% reduction in correctly completed task time, while protecting Core Dispatch satisfaction at 4.1/5 and complete, valid required records.
- **From M3, your primary success metric & guardrail metric:** Primary: mean elapsed time to complete required compliance checks correctly. Guardrails: coordinator Core Dispatch CSAT and required-record completeness/validity. Handoff completion (31% supplied baseline; 40% proposed target) remains a secondary product outcome, not a substitute primary metric.
- **From M4, the feature you scoped in your PRD - this is what you are testing:** B1 One-Click Compliance Checklist, narrowed to a guided review-before-save workflow. It pre-fills known operational context, retains explicit human review and exceptions, and gives truthful save/draft feedback. B5 progress is included as a supporting component of this one workflow intervention.

Prior artifacts: [M3 hypothesis](../03-analytics/hypothesis-and-metrics.md) and [M4 Simplified PRD](../04-roadmap/simplified-prd.md).

## Define your experiment parameters

| Parameter | Decision |
| --- | --- |
| **Feature under test - M4 PRD** | B1 Guided Compliance Review with its B5 progress support, as a single defined workflow package. No automatic certification or generated authoritative facts. |
| **Persona - M2** | Frontline fleet coordinators/dispatchers who regularly perform the required daily compliance task. Confirm eligibility before randomization. |
| **Expected outcome - M3** | Coordinators complete required reviews with less time and friction inside RouteLogic, without reducing completion or record quality. Better retention/renewal is a downstream hypothesis, not a measured result of this design. |
| **Primary success metric - M3** | Equal-weighted mean of coordinator-level mean correctly completed compliance-task times during the test, measured in minutes. Each coordinator contributes one aggregate, rather than treating repeated tasks as independent users. Lower is better. |
| **Baseline rate - M3** | **14.6 minutes**, a supplied classroom task-time mean, not 14.6%. Revalidate the timing definition and coordinator-weighted baseline before launch; the actual treatment comparison uses concurrent A, not the historical mean alone. |
| **Guardrail metric & boundary** | Core Dispatch CSAT: B must remain at least **4.1/5** and must not have a lower observed mean than A (operational boundary: 0-point deterioration). Report response counts, comparable question wording, account mix, and uncertainty; weak or differential response prevents an unqualified rollout decision. |
| **Second guardrail - distinct harm** | Required-record completeness/validity: no removed mandatory validation or automatic attestation, **0 new confirmed critical bypasses**, and no higher observed invalid/missing-required-record rate in B than A (0-percentage-point deterioration). Baseline defect rate is not supplied; collect it, audit both arms under the same rules, and report uncertainty. |
| **Completion/selection check** | Correct-completion share among all eligible task starts must not decline in B versus A (0-percentage-point operational boundary). Report exceptions, failures, abandonment, and missing outcomes separately. A lower mean among an easier subset of completers is not enough to ship. The supplied 48% workflow-stage figure is not assumed to be this rate. |
| **MDE - today's decision** | Design to detect a **4.38-minute** difference, equivalent to a **30% relative reduction** at 14.6 minutes (planning B mean **10.22 minutes**). The chosen practical success threshold is also a 30% observed reduction versus concurrent A. Minutes/relative change are appropriate; percentage-point inputs are not. |
| **Sample size per arm** | **42 evaluable independent coordinators per arm, 84 total**, conditional on an explicitly assumed SD of **7 minutes for coordinator-level means**, two-sided alpha 0.05, 80% power, balanced allocation, and appropriate independence assumptions. The supplied materials do not contain this SD or the available coordinator count; validate both before launch. This is a planning calculation, not a measured requirement from the course's binary-rate calculator. |
| **Traffic split** | **50/50** of eligible coordinators, randomized within each account and held stable across sessions and devices. Include all three pilot accounts in both arms where feasible. Do not randomize individual clicks or switch coordinators between versions. |
| **Test duration** | **28 consecutive days**, covering four weekly cycles, with the eligible panel enrolled before first exposure. Data sufficiency is an additional condition, not guaranteed by elapsed time. |
| **Proposed schedule and fixed read** | Exposure: **9 November 2026, 00:00 to 7 December 2026, 00:00 Asia/Riyadh**, end exclusive. Fixed efficacy read: **8 December 2026 at 12:00 Asia/Riyadh**, allowing a day for data/audit reconciliation. These are proposed future dates, not an already launched test. If pre-launch conditions are unmet, set a new schedule before first exposure. |
| **Significance threshold** | One confirmatory primary test, **two-sided p < 0.05**, with a **95% confidence interval** for the mean time difference. Use the pre-specified coordinator-level analysis. p is not the probability that the result is random or that the feature is correct. |

### Sample-size calculation and feasibility

The builder's calculator is for a binary rate and an effect in percentage points. Our inherited M3 primary metric is continuous time. Entering 14.6 as a percent would silently change the question, so the brief uses a two-independent-means calculation instead.

Planning inputs:

- A mean: 14.6 minutes from classroom data, subject to baseline-definition validation.
- Expected difference: 14.6 x 0.30 = **4.38 minutes**.
- B planning mean: 14.6 - 4.38 = **10.22 minutes**.
- Assumed common SD: **7 minutes across coordinator-level mean times**. This is not a task-level SD and is not supplied or observed.
- Alpha: 0.05, two-sided. Power: 0.80. Equal allocation.

The usual normal approximation is:

`n per arm = 2 x (z(0.975) + z(0.80))^2 x SD^2 / difference^2`

It gives 41 after rounding up. A noncentral-t power calculation gives **42 per arm** (approximately **80.9% power** under those assumptions). This is power to reject no difference when the true difference is 4.38 minutes; it is not an 80.9% probability of meeting every shipping rule or proving a minimum 30% saving.

| Assumed SD of coordinator means | Required coordinators per arm | Total |
| --- | ---: | ---: |
| 3 minutes | 9 | 18 |
| 5 minutes | 22 | 44 |
| **7 minutes - working assumption** | **42** | **84** |
| 10 minutes | 83 | 166 |

All rows are calculated scenarios, not measured variances. Estimate the real variance from comparable pre-experiment data and finalize the sample before randomization. The primary sample calculation does not establish power for rare quality defects or survey guardrails.

**Feasibility decision:** The M4 constraint supplies three accounts, not 84 available coordinators. Confirm account consent to mixed experiences, the eligible headcount, and likely observation coverage. If three accounts cannot support the required sample, retain a smaller directional/usability pilot and plan a separately scoped confirmatory test with adequate enrollment. Do not count 100 repeated tasks as 100 independent coordinators or label an underpowered pilot a conclusive A/B win.

**Interference check:** Coordinator-level assignment is appropriate only if one coordinator's new UI does not materially change another's measured task or treatment. If the shared-workflow or enterprise-policy constraints require account-level assignment, redesign and recalculate for that cluster design; three account clusters must not be analyzed as 84 independent coordinators.

## Define your control and variant

### Control (A) - the current experience

Keep RouteLogic's existing required compliance workflow, associated field requirements, validations, permissions, and record storage. M3 reports a 14.6-minute task and a fall from 71% at route assignment to 48% at compliance completion; M2 describes broader frontline complexity and separate synchronization/WhatsApp problems.

The supplied material does not specify the exact current compliance screen layout. Document it from the existing product before implementation; do not invent a three-screen legacy design, duplicate-entry count, or live control from the mock prototype.

### Variant (B) - one defined workflow intervention

Replace only the compliance-review workflow with the M4 B1 package. The relevant PRD screens are carried over below:

1. **Daily Overview / entry point:** Coordinator workspace shell; shift reference; sample fleet/route context; review status; Start/Resume Review action; a small four-step daily workflow summary. Handoff/reporting are contextual, not additional functional screens.
2. **Compliance Review / feature core:** Known driver/vehicle dropdowns; two unchecked review confirmations; explicit outcome radios; conditional exception note; section progress (context, reviews, outcome); inline errors; back/save actions; save-failure feedback.
3. **Confirmation / outcome:** Saved reference and entered values; clear No Exception or Follow-up Required result; note when relevant; Back to Overview and Edit Review actions. This is one screen with two truthful outcome variants.

These descriptions are from the prototype PRD. For a live experiment, use the existing verified operational records and real approved checklist/record requirements; fictional fixtures and illustrative demo checkboxes are not production policy.

Preserve the PRD's behavior: known context only, explicit human review, required-data validation, truthful exception status, accurate save/failure feedback, one logical saved record, and a visible distinction between draft edits and saved values. No Exception and Needs Follow-up must keep the same operational meanings in A and B. A recorded exception is not counted as clean completion.

**Attribution boundary:** This tests the B1 workflow package, including B5. It does not isolate prefill, progress, or any individual UI element. Do not claim which component caused a measured effect. A component-isolation test would be a separate design.

### Isolation check - what has NOT changed

- App release/version and platform eligibility, except the flagged compliance workflow.
- Required checklist items, validation policy, permissions, and the definition of correct completion.
- Underlying records, save API behavior, backend performance configuration, routing/optimization logic, route notifications, and status synchronization.
- Handoff workflow, daily reports, manager reporting, onboarding/training policy, and support access.
- Eligibility, instrumentation definitions, survey wording/timing, record-audit rules, and operational handling of exceptions.
- No parallel experiment or rollout that changes this compliance task. Verify exposure and assignment logs before interpreting outcomes.

A difference in route mix or task difficulty can occur by chance; inspect and report it under the pre-specified account/experience segments. Do not reassign users or redefine metrics to remove an inconvenient result.

## Measurement and analysis

1. **Eligibility before assignment:** Coordinators whose role includes the required daily compliance task and who are expected to undertake it during the test. Establish criteria using pre-period activity; do not select people because they later completed the variant successfully.
2. **Timing:** Start at the first opening of the required task; end when all required checks are correctly completed and the record is confirmed saved. Keep retries and interruptions under the same elapsed-time rule in both arms. Validate that the 14.6-minute reference uses a comparable definition.
3. **Outcomes:** Label clean completion, correctly documented open exception, validation/save failure, abandonment, and missing telemetry distinctly. Exception recordings receive their own timing/status analysis and are not silently counted as clean completion.
4. **Primary analysis unit:** Compute each assigned coordinator's mean clean-completion time over the test, then compare the two sets of coordinator means with a pre-specified two-sided Welch t-test. Report the absolute difference A minus B, its 95% confidence interval, and the relative saving `(mean A - mean B) / mean A`. Inspect account-stratified and experience/device results as diagnostics; do not hunt among segments for a replacement winner.
5. **Selection and missingness:** Account for all randomized coordinators and every eligible attempt. A coordinator with no clean completions has a missing primary time, not a zero-minute success. Do not use post-treatment exclusions or fabricated times to meet the sample target. Unresolved missingness, changed exception/abandonment mix, or a falling completion rate prevents a clean shipping claim even if completers are faster.
6. **Guardrail interpretation:** Compare observed thresholds and report uncertainty, response/audit coverage, and account mix. No significant harm is not proof of zero harm. This primary-metric sample is not a rare-defect safety certification.
7. **Pre-launch model check:** The 42-per-arm calculation assumes independent coordinator aggregates with approximately the planning spread; if measured variance, clustering, or data distribution makes that inappropriate, change and document the model/sample before exposure. An invalid model after launch leads to investigation, not an improvised favorable p-value.
8. **Monitoring:** Operational integrity, required-record correctness, exposure, and telemetry health are monitored throughout. Pause/roll back for a confirmed critical defect. The fixed read concerns efficacy decisions; it does not forbid detecting or stopping harm.

## Formalize your hypothesis & shipping criteria

### Your hypothesis - filled in

I believe that the **B1 guided compliance-review workflow, including its B5 progress support**, for **frontline fleet coordinators** will reduce the effort of completing required reviews inside RouteLogic, measured by a **30% relative reduction in mean correctly completed compliance-task time versus concurrent control** over **28 days** (planning reference: **14.6 to 10.22 minutes**). We will protect **Core Dispatch CSAT at 4.1/5, required-record completeness and validity, and task completion** throughout the test.

### Your shipping criteria - filled in

The **fixed efficacy read is 8 December 2026 at 12:00 Asia/Riyadh**, for the proposed 9 November-6 December exposure window. Make no early efficacy-win decision and do not extend the test simply until significance appears. Observe operational harm and data quality throughout.

- **SHIP - staged rollout to comparable eligible coordinators:** At least 42 evaluable independent coordinators per arm under the validated design; trustworthy exposure/timing and no unresolved outcome-selection problem; observed mean-time saving of **at least 30% versus A**, primary **two-sided p < 0.05**, and a **95% time-saving confidence interval excluding zero**; B Core Dispatch CSAT **at least 4.1/5 and not below A**; no record-quality or completion guardrail breach; and no unresolved material segment harm. Report uncertainty. This is a controlled expansion under the feature flag, not proof of a 30% minimum population effect or universal benefit.
- **ITERATE / INCONCLUSIVE:** Favorable direction below the practical target, an interval too wide to support the decision, inadequate enrollment, incomplete guardrail evidence, or insufficient comparable observations. Record what was learned and design a new test if warranted; a non-significant result from inadequate data is not evidence of no value.
- **INVESTIGATE:** A guardrail crosses its boundary, exposure/measurement is questionable, account/experience segments conflict, or a lower mean accompanies more abandonment/exceptions. A confirmed critical validation or false-completion defect triggers immediate pause/rollback, not a wait until the read date.
- **KILL / PIVOT:** Trustworthy, adequately precise results demonstrate harm or rule out the pre-agreed worthwhile improvement, or the mechanism does not address the observed bottleneck. Stop this intervention and use the evidence to frame the next one. Do not equate every p >= 0.05 with a negative result.

The test is designed for detecting a nonzero difference at the planning effect, not for guaranteeing that the confidence interval's lower bound exceeds 30%. Meeting a point-estimate threshold and proving a minimum population effect are different claims.

### Hardest parameter to define, and did it change your hypothesis?

**Sample size was the hardest parameter.** M3 supplies a time mean, but the builder calculator expects a percentage, and no SD or independent-user count is provided. I kept the M3 user problem, metric, 30% goal, and M4 feature rather than invent a conversion baseline. I added an explicitly assumed 7-minute coordinator-level SD, a reproducible 42-per-arm calculation, sensitivity cases, and an enrollment gate. This changed the evidence requirements and feasibility status, not the product hypothesis. The earlier M3 floor of 100 workflow starts across 20 coordinators was directional-pilot coverage, not a powered confirmatory sample.

## Pre-launch pressure test

| Question | Resolution |
| --- | --- |
| Is B exactly one change? | One bounded compliance-workflow intervention containing several specified UI components. Estimate the package effect; make no component-level causal claim. |
| Does the primary metric measure the pain? | Correct task time targets the supplied 14.6-minute burden. Completion, exception mix, and record quality must accompany it to prevent a misleading completer-only win. |
| Are primary and guardrails distinct? | Yes: time is primary; satisfaction, validity, and completion protect different harms. Handoff is secondary. |
| Is sample/duration feasible? | Conditional: 42 coordinators per arm follows the stated unmeasured SD assumption, while three accounts alone do not establish available sample. Validate variance, headcount, and independence before launch. |
| Are the shipping rules enforceable? | Yes: numeric time and guardrail thresholds, a fixed future read, a minimum independent sample, data-quality gates, and explicit inconclusive/investigate outcomes are specified. |

## Findings & decision (after running it)

**Not run.** No participants have been randomized, and there are no measured A/B means, p-values, confidence intervals, or business outcomes to report. The current decision is **prepare and verify feasibility**, with no evidence-based rollout recommendation yet. Update this section only with results from an actual executed experiment.

## Method references and provenance

- Course sources: supplied Module 5 Lab Guide / Builder; M3 hypothesis-and-metrics.md; M4 simplified-prd.md. Source metrics are classroom data, not research newly conducted by the student.
- [NIST - Two-sample t-test for equal means](https://itl.nist.gov/div898/handbook/eda/section3/eda353.htm): comparing independent means and unequal-variance analysis.
- [NIST - Sample sizes required](https://itl.nist.gov/div898/handbook/prc/section2/prc222.htm): variance, effect, significance, and power assumptions.
- [Microsoft Research - Pre-experiment trustworthiness](https://www.microsoft.com/en-us/research/articles/patterns-of-trustworthy-experimentation-pre-experiment-stage/): stable randomization units, collaboration/enterprise constraints, and measurement design.

Prepared with ChatGPT. Calculations use a continuous-outcome noncentral-t planning model; proposed SD, calendar dates, and operational decision thresholds are explicit assumptions. No binary-calculator result, live test, participant study, GitHub commit, or measured benefit is fabricated.
