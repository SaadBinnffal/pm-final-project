# GTM Strategy & Success Dashboard: RouteLogic Velocity

**Module 6 · Deliverable 6**  
**Author:** Saad Binnffal  
**Repository path:** `06-launch/gtm-and-dashboard.md`  
**Status:** Proposed launch plan, conditional on validation. No live experiment or launch has been completed.

## Go-to-market summary

Launch **Guided Compliance Review**, the bounded B1 workflow with its B5 progress support, to existing frontline fleet coordinators who perform required daily compliance reviews. Use a **Tier M targeted launch** with **Engagement** as the primary goal: help eligible coordinators complete their first valid review and keep using the workflow. Reuse verified operational context, retain explicit human review and required validation, and show accurate saved, draft, and exception states.

The first launch audience is the three participating accounts from the proposed M5 validation. Wider availability depends on the experiment decision, account readiness, and operating capacity. Communicate through account-specific email, a contextual in-product entry point, and a short customer-success walkthrough. All three are owned channels. Paid acquisition and public promotion add little to this initial adoption task.

## 1. Prior-work anchors

| Field | Decision and evidence |
| --- | --- |
| Feature from M4 | B1 Guided Compliance Review, including B5 as a supporting component of one workflow package. Three screens: Daily Overview, Compliance Review, and Confirmation. |
| What M5 told us | **M5 designed an experiment. It has not produced results.** The current decision is prepare and verify feasibility. This GTM plan is ready for use if the pre-agreed validation and readiness gates pass. |
| Persona from M2 | A frontline fleet coordinator/dispatcher responsible for daily operational coordination in a regional fleet. Select the subset whose role includes required compliance reviews. Operations leads are sponsors, rather than the primary product user. |
| Why this workflow first | M3 classroom data shows compliance use among 77% of coordinator DAUs, compliance CSAT of 2.2/5, and mean task time of 14.6 minutes against a 3-minute benchmark. High use can coexist with substantial friction. |
| Continuity of discovery | M2 directly establishes delayed route changes, stale status, and a WhatsApp workaround. M3 shifts the first improvement bet toward compliance. This launch does not claim to fix the separate synchronization problem or prove that compliance caused the WhatsApp workaround. |

The clickable M4 prototype uses fictional data and simulated saving. Production integration, approved checklist requirements, instrumentation, and operating readiness remain prerequisites.

## 2. Goal and target audience

**Primary goal: Engagement.** Establish correct first use and sustained adoption of a useful workflow inside an existing product. Awareness activity supports that goal. Retention and renewal remain downstream outcomes to observe, rather than promised launch results.

**Primary audience:** Existing coordinators in participating accounts whose responsibilities include the daily compliance task. Establish the eligible roster and task opportunities before exposure. Include different experience levels, devices, and work patterns, while keeping account results visible.

**Secondary audience:** Account operations leads and the customer-success/support people helping coordinators. They need to understand availability, validation, exception handling, and escalation. Preserve existing enterprise reporting for managers.

**Scope:** Start with accounts and users whose data, access, and operating requirements are verified. A larger or newly introduced account cohort needs its own readiness check. An account count is not a participant sample size.

## 3. Launch tier and positioning

**Tier M: targeted, coordinated launch.** Reach is limited to an existing B2B audience. Revenue relevance comes from restoring operational usefulness and supporting renewal confidence, but no ARR impact is quantified. Silence would leave users unaware of the new path, uncertain about its correctness, and more likely to retain their old habits. This justifies focused communication and assistance.

**Release and launch:** The limited technical release occurs during validation. The targeted adoption launch follows an acceptable M5 read and readiness review. Neither a broad campaign nor a new pricing offer is in scope.

**Core message:** “Review required checks in a focused workflow, using known context and clear confirmation of what has been saved.”

The message describes the available behavior. The proposed 30% time saving remains a validation target until results support a properly qualified claim. Do not promise automatic compliance, eliminated operational risk, or resolution of route-sync delays.

## 4. Top three channels

| Channel | Type | Audience, timing, and action |
| --- | --- | --- |
| Account-specific launch email | Owned | Send after the release gate to eligible coordinators and the operations lead. Explain availability and benefit, link the one-page guide, and direct users to their next required review. Use an approved contact list. |
| Contextual in-product message and entry point | Owned | Show to released eligible users at the existing compliance entry point. Offer Start Review or Resume Review, keep the instruction short, and suppress the first-use prompt after a valid save. This reaches active users in the relevant task. |
| Customer-success walkthrough and follow-up | Owned | Invite the account's coordinators to a 15-minute remote walkthrough using an existing meeting tool. Demonstrate normal completion, an exception, and a failed-save retry. Contact eligible non-starters through account email when in-app messaging cannot reach them. |

All three channels serve this audience. The plan does not require one channel of each type. No paid media or manufactured earned coverage is needed for the initial launch. Customer stories would require permission and verified results in a later expansion.

**Experiment isolation:** During the M5 confirmatory window, keep recruitment, contact intensity, training policy, and support access comparable across A and B. Do not run the variant-only adoption campaign during the test. Version-specific exposure belongs to the specified workflow intervention. Start the additional launch communications only after the fixed read and decision.

## 5. Enablement and assets

Prepare these materials before the targeted launch:

1. **One-page user guide:** entry point, review steps, mandatory confirmations, save status, and what to do when an exception remains open.
2. **Three-minute demo:** the same three M4 screens, including one failed-save retry and the distinction between unsaved edits and the saved record. Label demo data clearly.
3. **CS, Support, and Sales brief:** audience, current availability, benefit, known limits, common objections, and the escalation path. Sales must distinguish verified results from proposed targets.
4. **Approved email and in-product copy:** a consistent message with a single next action and an accurate availability statement.
5. **Support issue template:** account/user reference, task reference, time, observed outcome, reproduction steps, and severity. Use existing approved support handling.

| Likely question | Agreed explanation |
| --- | --- |
| Does prefill mean the system approved the check? | No. Known context reduces entry effort. The coordinator still reviews required information and explicitly confirms the outcome. |
| Does a saved exception count as complete and clear? | No. A valid saved review can record an open exception. Its follow-up status remains visible and it does not count as clean completion for the timing metric. |
| What happens if saving fails? | Keep the draft visible, explain that it has not saved, and allow retry. A success state requires an actual confirmed save. |
| Will managers lose reporting? | Existing reporting remains available. This release changes the bounded compliance-review path. |
| Can everyone use it immediately? | Availability follows the verified account/user release roster. The prototype does not establish production availability. |

## 6. Named ownership and budget

**Saad Binnffal is the named accountable owner for this individual project's launch-planning activities.** The table assigns his planning and coordination work. It does not imply that he alone deploys, approves required policies, or provides every production service. Names of the scenario's engineering, design, CS, and account counterparts are not supplied. Obtain those named execution commitments before declaring the operational launch ready.

| Activity | Named owner | Required delivery or approval | Planning effort |
| --- | --- | --- | ---: |
| Eligibility, launch decision, and account readiness tracker | Saad Binnffal | Eligible roster, account consent, and a recorded gate decision | 4 hours |
| Positioning, email, user guide, and internal brief | Saad Binnffal | Content reviewed with the account and CS counterparts | 5 hours |
| Demo script and walkthrough coordination | Saad Binnffal | Working demonstration, booked session, and an agreed support contact | 3 hours |
| Dashboard definitions and instrumentation handoff | Saad Binnffal | Engineering verifies events, assignment, timing, and record checks | 4 hours |
| Post-launch reviews and decision log | Saad Binnffal | Weekly account-level review and recorded next action | 4 hours |

**Proposed GTM capacity:** 20 PM hours above, plus 4 designer hours for materials, 6 CS hours for account preparation/support, and 6 engineering hours for launch/instrumentation readiness, **36 hours total**. These are unapproved planning estimates. They exclude production feature development, the four-week experiment, and ongoing operational support.

**Incremental media budget:** SAR 0. **Incremental tools/production spending:** SAR 0 planned, conditional on existing approved email, meeting, analytics, and editing tools being available. Staff time still has a cost. If tools, captioning, analytics, or asset-production capacity are missing, Saad records the gap and secures a named executor and an approved estimate before committing the launch date. No purchase or budget approval is claimed.

## 7. Timeline and launch gates

All dates below are **proposed, Asia/Riyadh**. The clock moves only after pre-launch conditions pass. The M5 schedule is retained for continuity.

| Phase | Proposed timing | Work and exit condition |
| --- | --- | --- |
| Preparation | 6-8 November 2026 | Verify production readiness, baseline definition/variance, eligible headcount, account consent, approved requirements, telemetry, and rollback. Draft launch materials without exposing variant-only coaching. Assign named operational counterparts. |
| Phase 1: beta / controlled validation | 9 November-6 December 2026 inclusive | Run the planned stable 50/50 coordinator-level M5 test over 28 days, if its design is feasible. Monitor integrity and harm throughout. Keep additional GTM treatment comparable. |
| Evidence read and decision | 8 December 2026 at 12:00 | Apply M5's pre-agreed effect, sample, uncertainty, quality, completion, and CSAT rules. Inconclusive or harmful evidence prevents an automatic expansion. |
| Phase 2: targeted launch | Earliest proposed date: 9 December 2026 | If gates pass, enable the approved cohort, send the account email, activate the contextual message, and run the walkthrough. Start a fresh adoption measurement window. |
| Phase 3: post-launch adoption | Launch day through day 28, with weekly reviews | Check first-week adoption, weeks 3-4 repeated use, task outcomes, quality, and account-level differences. Follow up on friction and decide the next rollout step. |
| Business follow-through | Day 60 and day 90 after launch | Review account usage and renewal feedback where the contract calendar allows. Report denominators and uncertainty. Do not attribute retention or revenue changes to this launch alone. |

If the proposed launch date holds, day 1 is **9 December**, day 7 is **15 December**, weeks 3-4 are **23 December-5 January**, and the 28-day window ends **5 January 2027**. Review that window on **6 January 2027**. If readiness or the M5 decision delays launch, reset the adoption dates from the actual release date, before starting the new window.

**M5 feasibility gate:** 42 evaluable independent coordinators per arm is conditional on an assumed 7-minute SD of coordinator-level mean task times, 80% power, and a valid independent-unit design. Neither the SD nor 84 available coordinators is established by the scenario. Recalculate using measured variance and a feasible design before exposure. If three accounts support only a smaller pilot, label the findings directional and plan confirmatory validation separately. Do not turn repeated tasks into independent users.

The production version must retain verified context, required human checks, truthful exception/draft/save states, audited validation, and a tested feature-flag rollback. The standalone M4 prototype is not that production implementation. Saad records a go/no-go after engineering, CS, and account counterparts confirm their responsibilities.

## 8. Success dashboard

Three launch metrics track first use, continued use, and task value. Targets below are **proposed operating thresholds**, not source data or achieved results. Report absolute counts with percentages, by account and relevant pre-defined user segments. With small counts, thresholds guide investigation and do not establish statistical significance.

| KPI | Baseline | Proposed target | Measurement window | Bad signal and action |
| --- | --- | --- | --- | --- |
| **First valid review adoption** | The new workflow has no live baseline. Pre-release use is 0 by availability, not a measured adoption failure. The M3 77% figure describes existing compliance use among coordinator DAUs and is a different denominator. | At least **80%** of the released, pre-defined eligible coordinator cohort saves at least one valid review in the first 7 days. The cohort is scheduled to have at least one required task during that week. | Launch days 1-7, read on day 8. | Message delivery is high but valid first use is below 80%: check access, eligible task opportunities, findability, and instructions before changing the channel or buying reach. |
| **Repeated review use** | Not measured for the new workflow. Establish a release-cohort baseline instead of importing the 77% daily-active-user rate. | At least **70%** of released coordinators pre-identified as having a required task in both weeks 3 and 4 saves at least one valid review in **each** week. | Weeks 3 and 4, read after day 28. | First use reaches 80% but repeat use is below 70%: inspect task burden, technical failures, recurring exceptions, and return to older habits. |
| **Mean correctly completed compliance-task time** | Classroom reference **14.6 minutes**. Confirm the M5 definition and actual concurrent A reference. | Preserve the M3/M5 goal of **at least 30% relative reduction versus comparable concurrent A**. At A=14.6, the planning B mean is **10.22 minutes**. This remains conditional on M5 evidence. | M5's four-week controlled read, then weekly post-launch monitoring over 28 days using the same timing rule. | Adoption is healthy but time does not improve, or the mean falls while abandonment/quality worsens: investigate the mechanism and case mix. A post-launch before/after comparison alone cannot verify the causal 30% target. |

**Definitions:** A valid review has required fields, explicit checks, and a confirmed saved record. It may truthfully document an open exception. An open exception can show adoption, but it is not a clean completion in the timing metric. Count each coordinator once per adoption numerator. Keep the eligible roster, access dates, and expected task opportunities fixed for each metric window. Show roster changes and unavailable opportunities separately rather than silently removing non-users after observing results.

**New versus continuing users:** Apply the first-use target to coordinators newly enabled after the M5 decision, such as former-control users or previously unexposed eligible coordinators. Report participants already exposed to B as a separate continuing-beta cohort. Their prior use cannot be relabeled as new activation. Apply the repeat-use target to the same newly released cohort with the required pre-defined task opportunities, and report continuing-beta repeat use separately. Start each later release cohort's clock from its own access date rather than mixing exposure ages.

**Timing analysis:** Keep equal-weighted coordinator-level mean clean-completion times, the M5 elapsed-time definition, and separate reporting of all starts, exceptions, abandonment, failures, and missing outcomes. Do not let a faster subset of successful users hide falling completion.

### Guardrails and downstream signals

- **Core Dispatch CSAT:** Maintain at least **4.1/5** and no observed deterioration against comparable A/pre-launch evidence. Check survey wording, response counts, coverage, and account mix. Unknown or weak evidence cannot be called a pass.
- **Required-record integrity:** Keep mandatory validation and explicit review. No new confirmed critical bypasses, and no observed increase in missing/invalid required records under comparable audits. A confirmed critical false-completion or validation defect triggers an immediate pause and rollback review.
- **Correct task-completion share:** No observed deterioration against comparable control among all eligible starts. Track exceptions separately and investigate differential missingness.
- **Broader product signal:** M3's supplied handoff completion is 31% of all workflow starts, with a proposed 40% goal. Revalidate the denominator for the released population and monitor as secondary. The 30% task-time target does not guarantee handoff or renewal improvement.

These are operational boundaries, not proof of zero risk. The primary sample is not a rare-defect certification. Post-launch adoption and time monitoring describe behavior unless a valid concurrent comparison supports a causal claim.

**Dashboard operation:** Saad updates adoption counts daily during the first week and reviews accounts weekly thereafter. Maintain a dated table with cohort size, numerator, value, target, status, quality notes, and next action. Until real data exists, show **Not measured** rather than a fabricated value or green status. Internal analytics tooling is a production dependency, not something implemented by the HTML presentation.

## 9. Post-launch decisions

**Most likely first action: Iterate if first use is healthy but repeated use or task value is weak.** This is a planned response to a plausible pattern, not a forecast of the experiment result.

| Decision | Trigger | Action |
| --- | --- | --- |
| Double-down | Sustained adoption meets the proposed 80% first-use and 70% repeat-use thresholds, M5 supports the practical time benefit, and guardrails/data quality hold across comparable accounts | Expand the feature flag to the next verified cohort and repeat readiness checks. Avoid immediate universal rollout. |
| Iterate | A weak adoption or repeat-use metric with usable quality data and no critical harm | Change one diagnosed variable, such as entry-point wording or walkthrough guidance, record the change, and start a fresh defined measurement window. |
| Investigate / pause | Broken guardrail, uncertain exposure, missing data, conflicting account results, or apparent speed gained by losing difficult tasks | Investigate before expansion. Pause immediately for a confirmed critical correctness defect and restore the approved path under operational review. |
| Pivot | Users adopt the flow but observation shows the dominant burden is another mechanism, such as technical waiting | Revise the intervention around the confirmed cause. Keep separate synchronization work visible on the roadmap. |
| Deprioritize | Adequate evidence rules out worthwhile benefit, or another supported problem offers greater value | Document the learning and redirect capacity. Insufficient sample alone produces an inconclusive decision. |

## 10. Pressure-test and provenance

The audience follows the Engagement goal, Tier M matches a limited existing-customer scope, and three owned channels reach both active users and non-starters. Saad is the named planning owner. Unconfirmed operational executors, capacity, baseline, participant count, and production readiness are explicit launch gates rather than assumed commitments.

Sources: the supplied M6 Lab Guide/Builder, [M2 persona and workaround](../02-discovery/competitive-and-journey.md), [M3 evidence and metrics](../03-analytics/hypothesis-and-metrics.md), [M4 PRD](../04-roadmap/simplified-prd.md), and [M5 experiment plan](../05-experimentation/experimentation-plan.md).

Prepared with ChatGPT from classroom materials. No customer interviews, executed experiment, production release, measured adoption, approved spending, GitHub commit, or LMS submission is claimed. Proposed targets, dates, resource estimates, and adoption thresholds require review before operational use.
