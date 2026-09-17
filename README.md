# Cave Studio Edge

A calm, creator-focused dashboard for the **CORSAIR XENEON EDGE**: tasks, work sessions,
media, system stats and quick controls on one 2560×720 touch screen. Made by
[Tom's Cave](https://marketplace.elgato.com/@tomscave) for iCUE 5.47 or later on Windows.

Get it from **Elgato Marketplace**, then install the free bridge below.

## Download the free bridge

**[CaveStudioEdgeBridge-Setup.exe](https://github.com/Caveproduction-bot/cave-studio-edge/releases/latest)**
from the Releases page.

The bridge is a small Windows program that powers audio controls, media details, the RAM
and network readings, the notification count and the screen buttons. It starts with
Windows, talks only to your own PC, and sends nothing to the internet. Tasks, work
sessions, the clock, colours and the CPU and GPU readings all work without it.

Full setup steps: **[SETUP.md](SETUP.md)**

## Features

- **Tasks:** due dates, preset or typed durations, suggestions from past tasks, a
  calendar filter, a warning before double-booking a day, Undo on delete, and totals
- **Work sessions:** start a timer from any task, with a flash when time is up, breaks,
  End Session and history
- **Media:** artwork, progress, transport, volume, and switching between media apps
- **System:** live CPU and GPU from iCUE's own sensors, plus RAM and network from the
  bridge, each with a source you can set in iCUE
- **Quick controls:** mute, mic, Switch Sound, Sound Source, Movie Mode, Show desktop,
  display-mode switching, and swiping between iCUE pages using your iCUE Screen Setup
  shortcuts
- **Colours:** five themes or your own accent, text and background colours and
  transparency, set in iCUE's Widgets settings and Pages Personalization
- **Options:** 12 or 24-hour clock, Movie Mode brightness, network adapter, and
  Reset all data

## Support

Questions and problems: [open an issue](https://github.com/Caveproduction-bot/cave-studio-edge/issues).

- [Privacy](PRIVACY.md): no account, no telemetry, nothing leaves your PC
- [Licence](LICENSE.md)
- [Changelog](CHANGELOG.md)
- [Third-party notices](THIRD-PARTY-NOTICES.md)

CORSAIR, iCUE and XENEON are trademarks of their respective owners. Tom's Cave is not
affiliated with or endorsed by Corsair.

---

## Development

```powershell
npm test                   # unit and structure tests
npm run check              # syntax, iCUE-parser-safe syntax, references, icuewidget validate
npm run preview            # http://127.0.0.1:4174/CaveStudioEdge/  (add ?mock=1 for sample data)
npm run capture            # dist/screens/mock.png at exactly 2560x720 ("live" for real data)
npm run package            # dist/CaveStudioEdge.icuewidget for importing into iCUE
npm run marketplace:media  # the eight 1920x960 store images, from the widget in mock mode
npm run release            # verified submission bundle in release/<version>/
```

```
CaveStudioEdge/scripts/
  views/      presentation only (no fetch, storage or iCUE calls, enforced by a test)
  models/     tasks, task memory, work session, breaks, history, preferences
  services/   the only code that reaches Windows: bridge client, audio, media, telemetry,
              iCUE media and sensor plugins, notifications, desktop, iCUE screen actions,
              links, and the labelled dev mock
  core/       storage, formatting, theme engine with WCAG contrast checks, the iCUE
              style properties and hardware source detection
bridge/       C# companion on 127.0.0.1:47140, plus its installer
```

Bridge: build with the .NET 8 SDK. `bridge\CaveStudioEdgeBridge.Setup` publishes
`CaveStudioEdgeBridge-Setup.exe`, which embeds the published bridge.
