# Answers

## Q1: How to run
Download index.html and open it in any modern browser. No installation required. I tested it in Chrome and Firefox.

## Q2: Stack & design choices
I picked vanilla JavaScript to avoid build tooling overhead for something this small.

Two design decisions:
(a) I made the timer text 80px+ so it's readable across the room during actual work sessions - the whole point of a pomodoro timer is to glance at it.
(b) I put settings below the timer rather than in a modal because a modal adds friction and this app is used repeatedly - quick access matters.

## Q3: Responsive & accessibility
At 360px wide, the layout tightens padding and reduces the timer font to 60px so it still fits cleanly on a small screen. At 1440px, the app stays centered in a single column with a 480px max width, so the timer remains the focal point.

For accessibility, I used aria-live on the timer so screen readers announce countdown changes. I skipped a full skip-link because it's a single-region page and the tab order is already logical.

## Q4: AI usage
Copilot was used to scaffold the Web Audio API beep, which is fiddly, and the localStorage date-check logic.

One thing changed: Copilot initially generated the audio with a fixed gain that was too loud and didn't fade out, so the gain envelope was adjusted to ramp down over 0.3s so it doesn't startle you mid-deep-work.

## Q5: Honest gap
The settings inputs don't validate well. You can type 0 or a negative number and break things.

With more time, I'd add min/max attributes and a validation message before letting bad values through.