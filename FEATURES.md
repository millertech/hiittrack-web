# HIITTrack — Features

No fluff. Here's what the app does and why it matters.

---

## One-Tap Timer

Big START button. 3-2-1-GO countdown with audio cues. Work and rest intervals that fire every time — no lag, no crashes. Pause, resume, skip ahead, or stop early. Your progress is always saved.

No menus to dig through. No onboarding flow. Open the app and train.

## Real-Time Intensity Tracking

Your phone already has a 50Hz accelerometer. HIITTrack turns it into a real-time intensity meter — no Apple Watch, no chest strap, no wearable required.

- Live color-coded bar (green → yellow → orange → red) during every interval
- Second-by-second intensity recorded per round
- Dynamic scaling that adjusts if you exceed the default range
- Per-interval breakdown: average and peak intensity stored automatically

Just your phone in your pocket. That's it.

## Exercise Tagging

During rest: "What did you just do?" Tap to label each round.

- 14 built-in exercises (Burpees, Sprints, Plank, High Knees, and more)
- Add your own custom exercises in Settings
- Top 8 most-used appear in the quick-select grid — no scrolling
- Last selection remembered between rounds

Every round gets a name. Every name gets analysis.

## Customizable Intervals

Make it yours:

- Work intervals: 10–180 seconds
- Rest intervals: 10–180 seconds
- Total time: 5–60 minutes
- Manual interval control for paced training
- One-tap reset to defaults

No opinions about how you should train. Set your numbers and go.

## Workout History

Every session saved. Swipe to delete what you don't want.

- Completion badges (finished vs. partial)
- Per-workout stats: intervals, duration, intensity, round count
- Mini intensity bar chart on every history row
- Tap any workout for the full detail view

Your data lives on your device. No cloud. No account. No sync.

## Workout Detail & Charts

Tap into any session for the deep dive:

- Intensity-by-round bar chart, colored by exercise type, with peak markers
- Exercise breakdown cards with round count, average intensity, and sparklines
- Drill-down sheets per exercise: line charts, per-round analysis, and AI insights

Built with Swift Charts. Native, fast, no web views.

## AI-Powered Insights

Not generic stats. Exercise-specific analysis profiles for all 14 built-in exercises:

- **Intensity analysis** — Your effort vs. the ideal range for each exercise
- **Consistency scoring** — Too steady (missing explosiveness) or too variable (losing rhythm)?
- **Fatigue detection** — First-half vs. second-half drop-off
- **Progression tracking** — Building momentum or burning out across rounds?
- **Rep estimation** — Approximate rep counts from motion patterns alone
- **Cadence analysis** — Seconds-per-rep for explosive movements
- **Personalized tips** — "Squeeze your glutes and pull your belly button in" for planks, "Push for 80–90% effort" for sprints

All on-device. No data leaves your phone.

## Audio & Haptics

Train by feel, not by staring at your screen:

- Countdown ticks, GO tone, interval warning beeps, phase-change sounds
- Completion celebration fanfare
- Light, medium, and heavy haptic feedback at the right moments
- Works in silent mode

## Accessibility

- Full VoiceOver support with descriptive labels
- Dynamic Type with `.rounded` design
- High-contrast color scheme
- Proper header, button, and element traits

## Technical Details

- SwiftUI — fully declarative
- Core Data — persistent workout storage
- Swift Charts — native charting
- CoreMotion — 50Hz accelerometer
- AVFoundation — audio playback
- UIKit haptics
- 100% on-device — no network calls, no analytics SDKs, no third-party frameworks
- iOS 17.0+ / Xcode 15.0+ / Swift 5.9+
