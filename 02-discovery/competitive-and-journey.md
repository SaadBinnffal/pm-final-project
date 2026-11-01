# Competitive Analysis & Journey Map

Module 2 - Exercise 2 - Deliverable 2 | RouteLogic Velocity

## Module 1 context

**Problem hook:** We must protect RouteLogic's largest enterprise account from switching to a leaner competitor by addressing the administrative friction that slows frontline fleet coordination.

**Value proposition:** For frontline fleet coordinators, RouteLogic Velocity will make urgent coordination tasks simpler and faster while keeping advanced enterprise capabilities available, because declining usage and our largest account's competitor trial make restoring operational usefulness an immediate priority.

## Candidate personas and selection

- **Fleet dispatcher:** Coordinates route changes and monitors execution. Delayed reassignment delivery and stale dashboard status prevent a trustworthy shared picture [UXR-02, UXR-09; BUG-2044, BUG-2072].
- **Delivery driver:** Needs to execute routes and record deliveries in field conditions. Crashes, failed offline access, and multi-screen core actions interrupt that work [UXR-01, UXR-03, UXR-06; BUG-2031, BUG-2050, BUG-2055].

**Chosen persona:** Fleet dispatcher. This directly matches the Module 1 focus on urgent coordination and is supported by explicit reassignment and WhatsApp evidence. The driver is a supporting actor; their separate pain is not merged into the dispatcher's role.

## Responses

### Role - who are we solving for?

A frontline fleet dispatcher coordinating route changes and delivery exceptions for a regional delivery fleet.

### Goal - what are they ultimately trying to achieve?

Keep drivers executing the latest route and coordinate exceptions using operational status they can trust.

### Friction - the main moment of misery

A reassigned route takes 8-15 minutes to reach the driver app, with no route-change push notification, so the driver can continue in the wrong direction. Separately, driver status can lag 20-60 minutes on the dispatcher's dashboard. The dispatcher relies on WhatsApp as the real coordination channel [UXR-02, UXR-09; BUG-2044, BUG-2072].

### External tools the user is forced to use

**WhatsApp group**, explicitly reported in UXR-02. Other sample participants use delivery texts, office calls, screenshots, or paper manifests in different contexts; these are not all assumed to be part of this dispatcher's reassignment process. No spreadsheet workaround is established.

### The process - four manual steps

This is a reconstruction to validate, not a complete observed workflow:

1. **Reassign the route in RouteLogic.** Directly reported in UXR-02.
2. **Relay the changed instruction through the WhatsApp group.** Reconstructed from the dispatcher's statement that WhatsApp is the real system; the exact message sequence is not supplied.
3. **Check that the driver received and understood the current instruction through the external conversation.** A proposed reconstruction of the manual confirmation burden; explicit acknowledgement behavior is not documented in the sample.
4. **Reconcile the external conversation with the lagging dashboard.** A reconstruction based on UXR-09 and BUG-2072; direct observation is needed to establish the actual cross-checking steps.

The likely inefficiency is coordinating across two channels without a dependable shared state. That interpretation is supported by the delays and the WhatsApp quote, but the effort and error cost of each reconstructed step remain unmeasured.

### Core frustration - where the process feels most broken

Changing a route in the official system does not establish that the driver is following it, and the board may still show an old status. The dispatcher must bridge the gap outside the product. This creates an adoption and trust risk; managers connect weak frontline usefulness to competitor evaluation and renewal risk [UXR-04, UXR-10], but a causal effect on churn has not been measured.

### The evidence - a quote or behavior from the research

> "I reassign a route and the driver doesn't see it for ten, fifteen minutes. By then they've driven the wrong way. We keep a WhatsApp group as the real system."

Source: UXR-02, fleet dispatcher in the supplied course sample.

> "I can't trust the board."

Source: UXR-09, night-shift dispatcher. BUG-2044 specifies an 8-15 minute reassignment delay; BUG-2072 specifies a separate 20-60 minute dashboard-status delay.

### Journey map - committed file to link

[journey-map.md](journey-map.md) - the four-stage journey, with [PNG visual](journey-map.png) and [one-page PDF](journey-map.pdf).

## Competitive baseline and intended edge

The evidence-backed baseline is the existing RouteLogic experience plus a WhatsApp coordination group. The enterprise account is also evaluating a leaner competitor, but that competitor is unnamed and no independent benchmark is provided. This analysis therefore compares the proposed journey with the documented workaround, without claiming a market-wide speed advantage.

- **Shared route-change record:** Intended to reduce dependence on parallel WhatsApp instructions.
- **Visible receipt and acknowledgement:** Intended to reduce uncertainty about whether the latest route was seen.
- **Trustworthy, timestamped status:** Intended to reduce manual reconciliation with a stale board.

These advantages are hypotheses. They depend on reliable synchronization and driver participation, and require validation before any claim of faster coordination or improved retention.

## How Module 2 updates the Module 1 diagnosis

The sample supports the broad hypothesis that frontline usefulness is failing and confirms an external messaging workaround. It also sharpens the problem: delayed shared state is a central barrier, so visual simplification alone will not restore trust. Enterprise reporting is explicitly valuable [UXR-10]; preserving it while focusing the operational path remains part of the strategy.

## Biggest opportunity gap - cohort-channel reflection

The biggest gap is between changing a route and knowing the driver is acting on it: RouteLogic records the change, but the dispatcher still trusts WhatsApp more than the product's shared state.

## Source and authorship

Based on the supplied [RouteLogic sample data](routelogic-sample-data.md), the [Exercise 1 synthesis](ai-synthesis.md), and the existing Module 1 Problem Hook. These are course examples, not research conducted by the student. Prepared in ChatGPT; proposed actions and internal states are clearly separated from source observations. No repository commit or channel post has been performed by this file's authoring process.
