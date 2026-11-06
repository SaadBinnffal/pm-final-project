# Individual Insights: Development Process

**Product Management Foundations · Module 6**  
**Project:** RouteLogic Velocity  
**Author:** Saad Binnffal

## Friction points

The hardest strategic challenge was keeping the project coherent when the evidence changed the first priority. M2 highlighted delayed route updates, stale status, and a WhatsApp workaround. M3 added a different, well-supported opportunity: coordinators use compliance frequently, but rate it 2.2/5 and spend 14.6 minutes on the task against a 3-minute benchmark. I kept the coordinator persona and the broader simplicity strategy, while moving the first improvement test toward compliance. I had to preserve the original research accurately instead of rewriting it as if the interviews had already established the compliance problem.

Scoping was another challenge. A full dashboard redesign, new reporting, and predictive ETAs could all sound useful, but they would dilute this four-week pilot. The roadmap narrowed Now to B1 Guided Compliance Review with B5 progress as a supporting component. Existing manager reporting still matters, even though frontline users rarely use it.

The prototype also exposed a concrete requirement gap. After a saved review was edited, the overview could still imply that the displayed state was fully saved. The revised flow distinguishes unsaved changes from the saved record. This taught me to inspect the states between the happy-path screens, including failed saves and open exceptions.

## Key learnings

- **High adoption can hide pain.** Compliance is used by 77% of coordinator DAUs, yet satisfaction is only 2.2/5. Required usage alone does not prove a good experience.
- **Segmentation changes priorities.** Reporting has low frontline usage but is heavily used and valued by managers. Simplification should protect the value each role needs.
- **The real competitive baseline includes workarounds.** A WhatsApp group can be the operational system people trust. An interface improvement alone cannot solve delayed shared state.
- **Metrics need precise definitions.** Percentage points differ from relative change, a benchmark gap differs from a measured saving, and repeated tasks differ from independent participants.
- **Experiment feasibility is part of product judgment.** My primary metric is minutes, so the builder's percentage-rate calculator does not fit it. M5 uses an explicitly conditional continuous-outcome calculation. Three accounts alone do not establish enough independent coordinators for a conclusive test.
- **AI needs an evidence audit.** It helped structure synthesis, prioritization, and requirements. I still had to challenge unsupported causes, optimistic effort estimates, and language that turned targets into results.
- **Launch planning starts before release.** A useful workflow needs an audience, an explanation, internal support, named ownership, and measurement. Engagement fits this existing-user feature better than a broad awareness campaign.

## Aha! moment

My main aha was realizing that a simpler workflow still has to preserve the truth of the operational task. A faster form would not be a successful product improvement if it hid unsaved changes, treated an exception as a clear completion, or removed a required check. That connected the prototype, the guardrails, and the launch message: speed matters only when coordinators can trust what the product records.

## What I will carry forward

In future product work, I will define the user problem and decision rule before asking AI to generate a solution, test unhappy paths alongside the core journey, and prepare adoption and support while the team builds. I will report what the evidence supports, mark uncertainty, and keep the next investment conditional on what we learn.

This reflection is drafted from the documented project work for Saad to review in his own voice. The project used supplied classroom data and AI assistance. It includes a working mock prototype and proposed experiment/GTM plans. It does not claim independently conducted research, an executed A/B test, a production launch, or achieved business impact.
