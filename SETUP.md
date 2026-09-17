# Setting up Cave Studio Edge

Setup takes about two minutes. You need Windows, iCUE 5.47 or later, and a CORSAIR
XENEON EDGE.

## 1. Add the widget to your XENEON EDGE

1. Get **Cave Studio Edge** from Elgato Marketplace. iCUE installs it for you.
2. In iCUE, open your **XENEON EDGE** and go to the **Widgets** page.
3. Add **Cave Studio Edge** to a screen and give it the whole screen (the largest size).

The clock, tasks, work sessions, colours and the CPU and GPU readings all work straight
away, with nothing else installed.

## 2. Choose your colours in iCUE

Cave Studio Edge is coloured from iCUE, in the same place as every other widget.

1. In iCUE, open your **XENEON EDGE**, go to **Widgets** and select **Cave Studio Edge**.
2. Under **Cave Studio Edge Personalization**, set **Theme Preset** to Blue, Green,
   Yellow, Orange or Red.
3. To use your own colours instead, set **Theme Preset** to **Custom colours**. The
   dashboard then follows **Accent Color**, **Text Color** and **Background**, and the
   colours you set in **Pages Personalization** (including **Theme per Page**).
4. **Widget Transparency** always applies.

The dashboard changes as you pick. On one of the five presets the colour pickers are
ignored on purpose, so a page's own colours cannot quietly replace the theme you chose.

Whatever you choose is checked for readability and nudged if a combination would be
hard to read, so the dashboard never ends up unreadable.

## 3. Where the CPU, GPU and RAM readings come from

These are found for you and need no setup. **Options → System readings** always names
the source behind each figure, so you can see what was found. If you would rather
choose, select **Cave Studio Edge** under **Widgets** in iCUE and use **System
Readings**:

- **CPU Source**, **GPU Source**, **RAM Source**: each starts on **Automatic**. Change
  one to **Manual** and pick from the sensors on your PC in the row below it.
- The sensor row is only read when its Source says **Manual**. iCUE keeps showing the
  last sensor you picked even after you go back to Automatic, which is why that row
  says "only used when Manual".
- Only the reading you change is affected; the rest stay automatic.
- If a sensor you picked is no longer there, that reading goes back to Automatic.

iCUE has no sensor for system RAM on most PCs, and none at all for network speed, so
those two come from the bridge in the next step. A reading with no source shows **N/A**
and a short note saying where to set it.

## 4. Install the free Cave Studio Edge Bridge

The bridge is a small program that lets the dashboard reach Windows. It powers:

- volume, mute, microphone mute and switching sound output
- album artwork, the progress bar and switching between media apps
- the RAM and network readings
- the Windows notification count
- Show desktop, the display-mode button, swiping between pages, and Open iCUE

Without it, those parts of the dashboard say so. Tasks, work sessions, the clock,
colours and the CPU and GPU readings do not need it.

1. Download **CaveStudioEdgeBridge-Setup.exe** from
   <https://github.com/Caveproduction-bot/cave-studio-edge/releases>.
2. Double-click it. If Windows shows "Windows protected your PC", click **More info**,
   then **Run anyway**. The installer is not code-signed, which is why Windows asks.
3. After a few seconds a message says the bridge is installed and running.

The bridge starts automatically whenever you sign in to Windows, and uses almost no
resources. You only need to install it once. Run a newer installer to update it.

## 5. Swiping between pages and the display-mode button

Cave Studio Edge uses the keyboard shortcuts **you** set in iCUE, so they match however
you already use your XENEON EDGE.

1. In iCUE, open your **XENEON EDGE** and go to **Screen Setup**.
2. Click **Add Keystroke** next to each of these and press a shortcut you don't use
   anywhere else:
   - **Switch Display Mode**: used by the display-mode button under the notification bell
   - **Previous Display Screen**: swipe right on the dashboard
   - **Next Display Screen**: swipe left on the dashboard

Shortcuts such as Ctrl + Alt + Shift + F10, F11 and F12 work well because nothing else
uses them. If a shortcut isn't set, the dashboard tells you when you try to use it.

## Using it

- **Tasks:** tap **ADD TASK**. Start typing a title and past tasks are suggested. Tap
  the date for a calendar. Pick a duration or type one, such as "45 min" or "2h".
- **Work sessions:** tap ▶ on a task to start its timer. Tap **END SESSION** when you're
  done; the session is saved and the task is ticked off.
- **Switch Sound** moves to your next sound output. **Sound Source** lets you pick one.
- **Movie Mode** dims the whole dashboard. Tap anywhere to bring it back.
- **Options** has the clock format, Movie Mode brightness, which network adapter the
  network reading measures, Open iCUE and Reset all data. Colours are in iCUE (step 2).

## Troubleshooting

**Parts of the dashboard say the bridge is needed.**
The bridge isn't running. Restart your PC. If that doesn't fix it, run the installer
again.

**A reading shows "N/A".**
Nothing on this PC reports it. For CPU, GPU or RAM, set a source in iCUE under
**Widgets → Cave Studio Edge → System Readings** (step 3). For the network reading,
install the bridge (step 4) and, if you have several connections, pick the adapter in
**Options → Network adapter**.

**Swiping moves the dashboard but the page doesn't change.**
Set Previous Display Screen and Next Display Screen in iCUE Screen Setup (step 5).

**Two browser tabs are playing but I can only control one.**
Browsers report all their tabs to Windows as a single media source. Media playing in
different apps (for example Spotify and a browser) can be switched between.

**The notification bell has no number.**
Some Windows setups don't allow apps to read the notification count. The bell still
opens your notifications.

## Removing the bridge

1. Find **CaveStudioEdgeBridge-Setup.exe** (usually in your Downloads folder).
2. Hold **Shift**, right-click it, and choose **Copy as path**.
3. Press **Windows key + R**, paste, type a space and `--uninstall` after it, then press
   **Enter**.
4. Confirm. The bridge is stopped and removed, and no longer starts with Windows.

## Help

Questions or problems: <https://github.com/Caveproduction-bot/cave-studio-edge/issues>
