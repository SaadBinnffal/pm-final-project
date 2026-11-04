# Simplified PRD - Guided Compliance Review

**Title:** B1 One-Click Compliance Checklist - guided review before save  
**Author:** Saad Binnffal  
**Status:** Draft  
**Target:** High-Fidelity Prototype  
**Project:** RouteLogic Velocity  
**Context:** 2 engineers + 1 designer + 1 CS lead; four-week, three-account pilot. This artifact is a frontend validation prototype, not a production pilot result.

## 1. THE BIG PICTURE

### Vision

Help frontline fleet coordinators complete required compliance reviews with less friction while preserving explicit review, trustworthy state, and complete records.

### Press Release

RouteLogic Velocity proposes a focused compliance review for coordinators who need to keep a daily dispatch workflow moving. Known driver and vehicle context appears together with the required review choices, so the coordinator can see what remains and record the outcome in one place.

Speed comes from clearer work and reuse of known context, rather than automatic certification. Coordinators explicitly record their reviews, keep exceptions visible, and receive an accurate saved or failed state. The production hypothesis is a 30% reduction from the supplied 14.6-minute baseline, subject to observing the real task and testing a comparable implementation.

### Success Metrics

- **Primary production-pilot hypothesis:** Reduce mean correctly completed compliance-task time by 30%, from 14.6 to at most 10.22 minutes after baseline-definition checks. Include failed/abandoned attempts and overall completion alongside the mean.
- **Product guardrail:** Coordinator Core Dispatch CSAT remains at least 4.1/5 with comparable responses; inspect any deterioration versus a suitable baseline or control.
- **Quality constraint:** Mandatory review and record requirements remain intact. An exception is not reported as a clean completion; data missingness/invalidity must not worsen.
- **Related product outcome:** M3 proposes raising eligible workflow handoff completion from the supplied 31% to 40%; the eligibility denominator must be confirmed.
- **Boundary:** A click-through demo with sample data cannot prove production task-time, retention, or compliance outcomes. The usability target in Eval 3 is a different, limited prototype task.

## 2. THE DETAILS

### User Stories - exactly three

**US1 - Find and confirm the task**  
As a frontline coordinator, I want a focused entry to the required review with known dispatch context, so that I can begin without searching unrelated features.

Acceptance criteria:
- The Daily Overview screen has a clear Start Compliance Review action and identifies sample shift SH-2048.
- The Review screen pre-fills a driver and vehicle only from local sample records; a missing or unrecognized selection is required before a valid save.
- Going back and returning retains entered values during the current page session; refresh resets the prototype, as stated in the interface.

**US2 - Record a truthful review**  
As a coordinator, I want to explicitly record reviewed items and any exception, so that the saved state reflects what I actually reviewed.

Acceptance criteria:
- Both illustrative review confirmations begin unchecked, and no outcome is preselected.
- A required review, driver, vehicle, or outcome left incomplete produces an inline error and no saved receipt.
- Needs Follow-up requires a trimmed note of 10-240 characters and leads to an open-exception state, not clean completion. These are demo rules, not asserted regulatory policy.

**US3 - Trust the save state**  
As a coordinator, I want accurate save feedback and clear draft state, so that I can recover from failure without losing work or confusing edits with a saved record.

Acceptance criteria:
- The local Save Failure scenario fails once, preserves all values, and permits a subsequent successful retry.
- A successful save shows the saved values and stable demo reference DEMO-RVW-2048; edits update this review rather than creating duplicate records.
- After editing a saved value and returning to the overview, show Unsaved Changes and do not imply the edited version is saved or ready for handoff.

### Screens to Build - exactly three

1. **Daily Overview / entry point:** Coordinator workspace shell; shift reference; sample fleet/route context; review status; Start/Resume Review action; a small four-step daily workflow summary. Handoff/reporting are contextual, not additional functional screens.
2. **Compliance Review / feature core:** Known driver/vehicle dropdowns; two unchecked review confirmations; explicit outcome radios; conditional exception note; section progress (context, reviews, outcome); inline errors; back/save actions; save-failure feedback.
3. **Confirmation / outcome:** Saved reference and entered values; clear No Exception or Follow-up Required result; note when relevant; Back to Overview and Edit Review actions. This is one screen with two truthful outcome variants.

The roadmap is a separate Lab 1 artifact, not a fourth prototype screen. Demo scenario controls alter fixtures without adding a screen.

### Functional Requirements - eight measurable rules

1. **FR1 - Known context:** Accept driver and vehicle only from the local fixture lists. Empty or unknown values cannot produce a saved receipt. The initial context is sample dispatch data, not a fetched or AI-generated fact.
2. **FR2 - Explicit review:** Initialize both required review checkboxes to false. Save requires the coordinator to select both; pre-fill never checks or certifies them automatically.
3. **FR3 - Outcome and exceptions:** Require exactly one outcome. Follow-up requires a trimmed 10-240-character note and saves as follow-up; switching to No Exception clears obsolete exception text.
4. **FR4 - Validation:** On an invalid save, show field-specific messages, stay on Review, and create no receipt. Clear a field's error when its value is edited and revalidate on save.
5. **FR5 - Save feedback and recovery:** Simulate save locally. During the brief pending state disable save/back controls. A failure displays no success, retains the entered values, and allows retry; no live persistence is implied.
6. **FR6 - Single logical record:** Use one stable demo review reference per sample shift. Repeated submissions or edits replace the local review object rather than append duplicates.
7. **FR7 - Draft versus saved:** Compare current form values with the last saved review. If they differ, Overview displays Unsaved Changes; keep the old receipt unchanged until a valid new save. Do not label unsaved edits as saved completion.
8. **FR8 - Truthful confirmation:** Show only saved values on Confirmation. The follow-up variant states the exception is open and does not count as clean completion. Remain within the three named screens.

### Smart Behaviors

| Situation | Outcome |
| --- | --- |
| Known dispatch sample exists | Pre-fill its driver/vehicle; leave human review unchecked and outcome blank. |
| Context, required review, or outcome is missing | Show an inline error; remain on Review; do not create a receipt. |
| Follow-up is selected with an inadequate note | Require 10-240 meaningful characters before saving. |
| No Exception replaces a follow-up selection | Clear obsolete exception text and its error. |
| Review sections are valid | Advance section progress; an exception with no valid note does not complete its section. Progress is not certification. |
| Local simulated save fails | Retain inputs, show failure, and permit retry; do not show success. |
| A valid save succeeds | Store one local review and show its exact values and result on Confirmation. |
| Saved review is edited but not saved again | Show an unsaved state on Overview and preserve the previous saved record. |
| Follow-up review is saved | Confirm an open exception, not a clean-completion/handoff-ready claim. |
| Page is refreshed | Reset the session; the prototype does not claim durable storage. |

### Technical Constraints - what not to build

- Use React and useState for UI state; no other React hooks, state library, external APIs, login, backend, database, localStorage, analytics calls, or live notifications.
- Bundle React into self-contained HTML so the exported prototype opens offline without a CDN or build step.
- Use only local fictional driver, vehicle, account, and shift fixtures. A short timer simulates saving; it is not a network request.
- Desktop-tested layout with responsive CSS; no claim of a full mobile coordinator-platform rebuild or mobile-device QA.
- The illustrative review labels and note-length rule are prototype assumptions, not an invented legal checklist or legal advice.

## 3. THE LOGISTICS

### Features Out

- Automatic compliance approval or AI invention of authoritative operational facts.
- B2 generative daily-report population; B4 full coordinator-dashboard rebuild; B7 a new ETA prediction surface; B8 a new executive dashboard.
- B3 handoff wizard and B6 notification/synchronization work in this first prototype.
- B9 PDF generation and B10 a full training module; preserve existing records/capabilities and allow simple field help.
- Authentication, live integrations, file uploads, background sync, durable drafts, and real regulatory certification.

### Edge Cases / Unhappy Paths

- Missing/unknown context: require an allowed selection and block invalid completion.
- Unreviewed required item: keep it visible and block saving.
- Open exception without a note: request the note and keep the outcome unresolved.
- Save failure: preserve the draft, show no success, and allow retry.
- Edit after saving: separate the current draft from the saved version on Overview.
- Duplicate action: retain one local logical record and a stable reference.
- Refresh: reset with an explicit memory-only notice; durable recovery is outside the prototype.
- **Safety / hallucination guard:** Never invent a reviewed document, completed check, saved server record, regulatory approval, or operational result. Prefill known context only; human review and exception status remain explicit.

### Decision Log - exactly two scope-protecting choices

1. **Deterministic context, explicit human review:** Narrow B1's “one-click” wording to a focused review-and-save workflow. Exclude automatic certification and new AI infrastructure; protect record integrity.
2. **One core slice:** Implement B1 plus the low-effort B5 progress support. Keep handoff, notifications, exports, training systems, and workspace redesign outside the first prototype so one task can be tested clearly.

### Evals - exactly three targets

| Eval | Target | Current evidence |
| --- | --- | --- |
| E1 - validation accuracy | 100% correct accept/reject outcomes across 16 deterministic field/outcome fixtures | 16/16 passed in local rule checks; this is prototype logic validation, not a production audit. |
| E2 - trustworthy state | 100% pass for four browser scenarios: invalid-save blocking, failed-save preservation/retry, exception stays open, and unsaved-edit labeling | All four observed in desktop browser QA; the unsaved-edit issue was found, corrected, and rechecked. |
| E3 - prototype task usability | At least 4 of 5 representative coordinators complete the sample review without help in at most 2 minutes | Planned; no user study or timed participant result has been conducted. It does not replace the M3 production-time hypothesis. |

### Actual validation loop and PRD refinement

During browser testing, I saved a review, edited the driver, and returned to Overview without saving. The first version still showed Reviewed without identifying the pending edit. I made FR7 explicit, added an unsaved-state comparison, and verified that Overview now shows Unsaved Changes and keeps the prior receipt intact. This was a real observed prototype gap, not an invented interview or user-test result.

## Builder Hook

Build a working prototype based on this PRD. Use the User Scenario as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity. Implement exactly the three named screens with React useState and local sample data. Preserve all explicit review, exception, save-failure, and unsaved-edit rules; do not introduce a login or external APIs.

## Prototype and screenshots

[Open the self-contained prototype](prototype.html) · [Overview](prototype-overview.jpg) · [Review](prototype-review.jpg) · [Confirmation](prototype-confirmation.jpg) · [Exception variant](prototype-exception.jpg)

Prepared with ChatGPT from supplied classroom materials and the M3 hypothesis. Targets are proposed; fictional fixture values and demo checks are labeled. No measured production improvement or participant usability result is claimed.
