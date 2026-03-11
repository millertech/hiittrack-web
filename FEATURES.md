# HIIT Track — Features

## Workout Timer

- **One-tap start** — Large circular START button gets you moving instantly
- **3-2-1-GO countdown** — Animated countdown with audio cues before your workout begins
- **Visual progress ring** — Circular progress indicator shows time remaining in each interval
- **Interval progress bar** — See which interval you're on (e.g., "Interval 3 of 10")
- **Phase display** — Clear "WORKOUT" / "REST" / "GET READY" / "COMPLETE" indicators
- **Pause & resume** — Pause your workout at any time; paused time is tracked separately
- **Manual advance** — Optional manual control to skip to the next interval
- **Stop with confirmation** — End early with a confirmation dialog; progress is always saved

## Real-Time Intensity Tracking

- **Accelerometer-based intensity** — Uses device motion data at 50Hz to measure workout effort in real time
- **Live intensity meter** — Color-coded bar (green → yellow → orange → red) during workout intervals
- **Dynamic max scaling** — Intensity scale automatically adjusts if you exceed the default 10-point range
- **Per-second data capture** — Second-by-second intensity recorded for every interval
- **Per-interval breakdown** — Average and peak intensity stored for each workout round

## Exercise Tagging

- **"What did you just do?"** — During rest periods, tap to label the exercise you just completed
- **14 built-in exercise types** — Jumping Jacks, Burpees, High Knees, Mountain Climbers, Squats, Lunges, Push-ups, Plank, Sprinting, Bicycle Crunches, Box Jumps, Jump Rope, Kettlebell Swings, and Other
- **Custom exercise list** — Add, remove, and reorder exercises in Settings
- **Top 8 shown during workout** — Only your most-used exercises appear in the quick-select grid
- **Persistent selection** — Last selected exercise is remembered between rounds

## Configurable Settings

- **Workout interval** — 10 to 180 seconds (default 30s)
- **Rest interval** — 10 to 180 seconds (default 30s)
- **Total workout time** — 5 to 60 minutes in 5-minute increments (default 30 min)
- **Manual interval restart** — Toggle auto-advance vs. manual "Next" control
- **Reset to defaults** — One-tap restore of all settings

## Workout History

- **Persistent storage** — All workouts saved via Core Data
- **Completion status** — Completed vs. partial workouts clearly badged
- **Per-workout stats** — Workout/rest intervals, total duration, average intensity, interval count
- **Mini intensity chart** — Small bar chart preview on each history row showing per-round intensity
- **Swipe to delete** — Remove old workouts with a swipe gesture
- **Tap for details** — Full workout detail view with charts and insights

## Workout Detail & Analytics

- **Intensity by Round chart** — Bar chart with average intensity per round, colored by exercise type, with peak markers
- **Exercise breakdown** — Grouped cards for each exercise type used, with round count, average intensity, and mini sparkline
- **Tap to drill down** — Each exercise group opens a detailed sheet with:
  - Intensity over time (single-interval line chart or multi-interval overlay)
  - Per-round analysis with expandable disclosure groups
  - AI-generated insights
  - Actionable exercise-specific tips

## AI-Powered Workout Insights

- **Exercise-specific analysis profiles** — Each of the 14 exercise types has a unique analysis profile with expected intensity patterns, ideal ranges, and coefficient-of-variation thresholds
- **Intensity level analysis** — Compares your average intensity to the ideal range for each exercise
- **Consistency analysis** — Detects if your form was too steady (missing explosiveness) or too variable (losing rhythm)
- **Fatigue detection** — Compares first-half vs. second-half intensity to identify drop-off
- **Progression tracking** — Across multiple rounds of the same exercise, detects building momentum or progressive fatigue
- **Rep estimation** — For rep-based exercises (squats, push-ups, burpees), estimates rep count from intensity peaks
- **Cadence analysis** — For explosive exercises, calculates average seconds-per-rep
- **Exercise variety scoring** — Rewards using multiple exercise types in a single workout
- **Strongest exercise identification** — Highlights your highest-intensity exercise
- **Personalized tips** — Context-aware recommendations per exercise (e.g., "Focus on breathing steadily" for planks, "Push for 80-90% effort" for sprinting)

## Audio & Haptics

- **Countdown beeps** — Tick sounds during the 3-2-1 countdown
- **GO tone** — Distinct sound when the workout begins
- **Interval warning beeps** — Audio cues during the final 3 seconds of each work/rest interval
- **Phase transition sound** — Audio feedback when switching between workout and rest
- **Completion celebration** — Fanfare sound when the workout is finished
- **Haptic feedback** — Light, medium, heavy, success, and warning haptics at appropriate moments
- **Silent mode support** — Audio plays even when the device is in silent mode

## Workout Summary

- **End-of-workout summary** — Shows all completed intervals as scrollable cards with exercise icons and intensity bars
- **Overall stats** — Average intensity, peak intensity, and total intervals at a glance
- **Done to dismiss** — Single tap returns to the home screen

## Accessibility

- **VoiceOver support** — Descriptive labels and hints on all interactive elements
- **Accessibility traits** — Headers, buttons, and combined elements properly annotated
- **Dynamic Type** — System font scaling with `.rounded` design
- **High contrast** — White-on-gradient color scheme with distinct phase colors (yellow, green, orange, white)

## Background Handling

- **Auto-pause on background** — Timer pauses when the app leaves the foreground
- **Manual resume** — Tap to resume when returning to the app
- **State preservation** — Workout state maintained across app lifecycle transitions

## Technical Foundation

- **SwiftUI** — Fully declarative UI
- **Core Data** — Persistent workout storage with `NSPersistentContainer`
- **UserDefaults** — Lightweight settings persistence
- **Swift Charts** — Native charting for intensity visualizations
- **CoreMotion** — Accelerometer data collection at 50Hz
- **AVFoundation** — System sound playback
- **UIKit haptics** — `UIImpactFeedbackGenerator` and `UINotificationFeedbackGenerator`
- **iOS 17.0+** / **Xcode 15.0+** / **Swift 5.9+**
