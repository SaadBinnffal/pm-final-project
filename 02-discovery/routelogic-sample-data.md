# RouteLogic Velocity - Course Sample Data

Source: Product Management Foundations, Module 2, Exercise 1; supplied by the student in the conversation. This is fictional practice collateral, not field research conducted by the student. Typographic dash characters are normalized to ASCII in this copy.

## User research notes

### UXR-01 - Diego, delivery driver, 3 yrs

> To mark a stop delivered I tap through three screens. In the rain, at a doorstep, with a package in one hand. I've started just texting my dispatcher instead.

### UXR-02 - Fleet dispatcher, mid-size 3PL

> I reassign a route and the driver doesn't see it for ten, fifteen minutes. By then they've driven the wrong way. We keep a WhatsApp group as the real system.

### UXR-03 - Elena, driver

> The app crashed mid-route and lost my remaining stops. I had to call the office to read them to me off a screen. Twenty minutes gone.

### UXR-04 - Ops manager, enterprise account

> It does everything, which is the problem. My frontline people use maybe 5% of it and can't find that 5%. We're evaluating a leaner competitor that just does routing well.

### UXR-05 - Sam, driver

> Route optimization sent me down a road that's been closed for months. It doesn't know about traffic or the loading dock round the back. I override it every day.

### UXR-06 - Priti, driver, rural routes

> No signal in half my area and the app is useless offline. Stop list won't load. I screenshot my route every morning as a backup.

### UXR-07 - Warehouse lead

> Proof-of-delivery photos take forever to upload and half fail. Drivers don't know if it worked, so they retake three times.

### UXR-08 - New driver, week 2

> Nobody can onboard on this in a day. There are menus inside menus. I still don't know where 'report a failed delivery' is.

### UXR-09 - Dispatcher, night shift

> Status updates from drivers lag on my dashboard. A stop shows 'in progress' when it was delivered an hour ago. I can't trust the board.

### UXR-10 - Regional manager

> The admin reporting is genuinely powerful, that's why we bought it. But the daily driver experience is dragging down adoption and now renewal is at risk.

### UXR-11 - Driver, 6 yrs

> Every update adds a button. Nothing gets removed. The 'start route' I use 30 times a day is now buried under features I've never touched.

### UXR-12 - Driver focus group (aggregate)

> Five of seven drivers keep a paper manifest 'just in case the app dies.' All seven said speed of the core actions matters more than any new feature.

## Bug reports

### BUG-2031 - Severity: Critical

App crashes mid-route on Android 12/13 when the stop list exceeds ~40 stops; remaining route is lost and must be reloaded from the server.

### BUG-2044 - Severity: Critical

Dispatch reassignments take 8-15 min to propagate to the driver app; no push notification on route change. Drivers act on stale routes.

### BUG-2050 - Severity: High

Offline mode fails to cache the stop list; app shows a blank route with no connectivity. Blocks rural routes entirely.

### BUG-2055 - Severity: High

"Mark delivered" requires 3 taps across 3 screens; no single-tap completion. Top frontline complaint; drives off-platform workarounds.

### BUG-2061 - Severity: High

Proof-of-delivery photo upload fails silently on weak signal (~35% failure); no retry queue, no success confirmation.

### BUG-2068 - Severity: Medium

Route optimization ignores road closures and known access constraints (loading docks, one-way streets); no way to save local overrides.

### BUG-2072 - Severity: Medium

Driver status changes lag 20-60 min on the dispatcher dashboard; "in progress" shown for completed stops.

### BUG-2079 - Severity: Medium

Core actions (Start Route, Mark Delivered) are buried 2-3 levels deep after recent feature additions; no configurable home screen.

### BUG-2085 - Severity: Low

GPS pin drifts up to 200m in dense urban areas, causing incorrect "arrived at stop" auto-detection.

### BUG-2090 - Severity: Low

New-user onboarding tutorial cannot be re-opened after first launch; no in-app help for "report failed delivery."
