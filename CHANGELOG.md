# Changelog

## 1.0.0 — first release

First release of Cave Studio Edge on Elgato Marketplace.

### Widget

- **Tasks:** due dates from a tap-to-pick calendar, durations from presets (15 min to
  16h) or typed, priorities, and suggestions from previously saved tasks as you type.
  A warning appears before saving a task already scheduled for the same day, with the
  choice to update that task or rename the new one. Delete with Undo, a calendar that
  filters by day, and totals for open and completed tasks, sessions, hours worked and
  today.
- **Work sessions:** start the timer from any task, with its duration as the goal and
  its name under the timer. The timer flashes for a minute when time is up and keeps
  counting. Pause and resume, timed breaks with optional reminders, and End Session to
  save the session and tick the task off. Ticking a task off by hand adds its planned
  time to hours worked. Timestamps keep the timer accurate through restarts, sleep and
  iCUE reloads.
- **Session history:** date, start and end times, breaks, paused time, total and the
  linked task or project, with delete behind a confirmation.
- **Media:** title, artist, app, artwork, a draggable progress bar,
  previous/play/pause/next and volume. When two apps are playing, the controls can
  switch between them.
- **System:** live CPU, GPU, RAM and network speeds with history graphs.
- **Quick controls:** Mute, Mic, Switch Sound (next output), Sound Source (pick an
  output), Movie Mode (dims the dashboard), Options.
- **Clock panel:** date, 12 or 24-hour clock, Windows notification count, Show desktop,
  and a button that switches the XENEON EDGE display mode.
- **Options:** five colour themes (Blue, Green, Yellow, Orange, Red), each checked for
  readability; clock format; Movie Mode brightness; Open iCUE; a link to the Tom's Cave
  shop; and Reset all data behind a second confirmation.

### Companion bridge

- Cave Studio Edge Bridge runs on 127.0.0.1:47140 and refuses requests from websites.
- The installer stops any running copy, waits for the port to be free, starts the new
  bridge and only reports success once it answers. It starts with Windows and can be
  removed with `--uninstall`.
