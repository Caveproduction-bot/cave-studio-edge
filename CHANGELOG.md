# Changelog

## 1.1.0 — colours and hardware sources move into iCUE

Answers the two points raised in the Elgato Marketplace review of 1.0.0, and the three
raised when 1.1.0 was first reviewed:

- **Colours only, no switches.** The colour settings no longer use iCUE's standard names,
  which made iCUE add its own Custom Style switch that hid the pickers, and the Theme
  Preset dropdown is gone too: iCUE shows Accent, Text and Background Color and
  Background Transparency, and every change shows straight away. Any accent is laid on
  the tuned dark background (the old presets were exactly that), until text or
  background is changed too. Options lists the original colours. The per-page theme
  (Pages Personalization) no longer drives the dashboard as a result.
- **Not dimmed on install.** iCUE fed a new page's 80% Widget Transparency into the old
  `transparency` setting. The new Background Transparency starts at 100% and fades only
  the background; panels, text and controls stay at full strength.
- **Network in iCUE.** System Readings has Network Source: Automatic, Ethernet or
  Wi-Fi. (A live list of adapters was tried first and crashed iCUE.)
- The notifications button opens the Windows notification centre and, pressed again,
  closes it (bridge 1.1.1).
- Deleting a task asks for confirmation first; Undo still follows.
- The dashboard fills the full width of the screen instead of leaving bands at the sides.
- Options no longer has a network adapter picker: Network Source in iCUE covers it.
- Starting a different task while a session has time on it (or choosing another task
  with CHANGE) no longer switches silently: "Already working on a task" offers KEEP
  WORKING or END SESSION.
- Work sessions: each logged session has CONTINUE, which puts it back on the timer; the
  session running now is listed first as Active now with END SESSION; rows show TOTAL
  (time worked) and BREAKS; deleting a session asks in a pop-up; HOURS WORKED matches
  the figure under the task list; the task picker separates upcoming and completed tasks.
- Calendar: a tap on a day lists its tasks and keeps the calendar open; a second tap
  on that day adds a task on it. SHOW TODAY / SHOW ALL switches the task list.
- Larger text in task rows and in every pop-up.

The notes below describe 1.1.0 as first submitted; where they mention Pages
Personalization, the points above replace them.

### Colours are set in iCUE

- The five colour themes and free accent, text and background colour pickers, plus
  widget transparency, are now declared as iCUE widget properties and appear under
  **Widgets → Cave Studio Edge** in iCUE. **Theme Preset** chooses between the five
  palettes and **Custom colours**; on Custom the pickers apply, and because they use
  iCUE's standard colour property names, **Pages Personalization** and **Theme per
  Page** drive the dashboard too.
- Changes made in iCUE apply to the dashboard immediately, and are remembered across
  reloads and iCUE restarts.
- Any colour a user can pick is still run through the WCAG contrast checks and
  corrected before it is applied, so no combination makes the dashboard unreadable.
- The colour swatches have been removed from the dashboard's own Options, which now
  says where the colours live. Nothing else in Options changed.

### CPU, GPU, RAM and network readings

- CPU and GPU now work as soon as the widget is added, with no bridge and nothing else
  installed, by reading iCUE's own Sensors plugin. In 1.0.0 every reading came from the
  companion bridge, which is a separate download, so all four readings were blank for
  anyone who had not installed it.
- Where the bridge is running it is used first, because it measures CPU, GPU and RAM
  the way Windows itself does, so all four readings agree with each other and with Task
  Manager. iCUE's GPU sensor reads the card's own counter, which runs roughly double
  Windows' figure for the same card at the same moment. A sensor chosen by hand in iCUE
  still beats both, for that reading only.
- Sources are detected from the sensor's reported type and kind, never from a sensor
  id, device name or vendor, so detection is the same on Intel and AMD processors and
  on NVIDIA, AMD and Intel graphics. On a PC with more than one GPU, Automatic reads
  every card and shows the busiest, so an idle onboard chip cannot hide the card doing
  the work; the cards are also labelled so they can be told apart when choosing by hand.
- Every reading has a source setting in iCUE (**System Readings**) that starts on
  **Automatic**. A manual choice applies to that reading alone; the others stay
  automatic. A chosen sensor that no longer exists returns to Automatic by itself.
- Sources are worked out again when a sensor appears or disappears and when iCUE
  restarts, without reinstalling or reloading the dashboard.
- The network reading picks a connected Ethernet or Wi-Fi adapter that is carrying
  traffic and skips virtual, VPN, tunnel, loopback and disconnected adapters. The
  adapter can also be chosen by hand in Options.
- A reading with no source shows **N/A** with a one-line note naming the setting that
  fixes it, in the same space as the graph, so no part of the dashboard is left blank
  and unexplained. Missing readings never draw an invented value.
- Options gained a read-only **System readings** line naming the source behind each
  figure, so it is obvious which sensor Automatic found and whether a setting changed
  anything.

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
