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
2. Under **Cave Studio Edge Personalization**, pick any **Accent Color**. The rest of the
   dashboard is tuned to match it.
3. For a completely different look, change **Text Color** and **Background Color** too.
4. **Background Transparency** fades the dashboard's background and panels, so the iCUE
   page (its Device Background colour or image) shows through, while text, numbers and
   buttons stay at full strength. It starts at 100%. On a black page background the
   change is subtle, because the dashboard is dark too.

These are the only colour settings Cave Studio Edge uses. iCUE's **Pages Personalization**
(Theme per Page, Widget Text Color, Widget Accent Color, Widget Background, Widget
Transparency) does not change it, on purpose: those settings are what dimmed the
dashboard on a new page and hid its own colour choices.

The dashboard changes as you pick. To go back to the original look, set the colours to
accent **#5D9DD3**, text **#F3F6FA** and background **#070B10** (also listed in the
dashboard's **Options**). For the other ready-made looks, use one of these accents:
green **#5FB58C**, yellow **#D6B45A**, orange **#D98F5A**, red **#D4706B**.

Whatever you choose is checked for readability and nudged if a combination would be
hard to read, so the dashboard never ends up unreadable.

## 3. Where the CPU, GPU, RAM and network readings come from

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
- **Network Source**: **Automatic** measures whichever connection is carrying traffic.
  Choose **Ethernet** or **Wi-Fi** to measure that one. The network box is labelled
  ETHERNET or WI-FI so you can see which is being measured.

iCUE has no sensor for system RAM on most PCs, and none at all for network speed, so
those two come from the bridge in the next step. A reading with no source shows **N/A**
and a short note saying why and where to fix it.

## 4. Install the free Cave Studio Edge Bridge

The bridge is a small program that lets the dashboard reach Windows. It powers:

- volume, mute, microphone mute and switching sound output
- album artwork, the progress bar and switching between media apps
- the RAM and network readings
- the Windows notification count, and opening and closing the notification centre
- Show desktop, the display-mode button, swiping between pages, and Open iCUE

Without it, those parts of the dashboard say so. Tasks, work sessions, the clock,
colours and the CPU and GPU readings do not need it.

1. Download **CaveStudioEdgeBridge-Setup.exe** from
   <https://github.com/Caveproduction-bot/cave-studio-edge/releases/latest>.
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
  done; the session is saved and the task is ticked off. If a session is already running
  and you start a different task, the dashboard asks you to end and log that one first.
- **SESSIONS** lists your logged sessions with the time worked. **CONTINUE** picks one
  back up where it left off; the session running now is shown at the top.
- **Calendar:** tap a day to see its tasks; tap the same day again to add a task on it.
- **Switch Sound** moves to your next sound output. **Sound Source** lets you pick one.
- **Movie Mode** dims the whole dashboard. Tap anywhere to bring it back.
- **Options** has the clock format, Movie Mode brightness, Open iCUE and Reset all data.
  Colours and reading sources are in iCUE (steps 2 and 3).

## Troubleshooting

**Parts of the dashboard say the bridge is needed.**
The bridge isn't running. Restart your PC. If that doesn't fix it, run the installer
again.

**A reading shows "N/A".**
Nothing on this PC reports it. For CPU, GPU or RAM, set a source in iCUE under
**Widgets → Cave Studio Edge → System Readings** (step 3). For the network reading,
install the bridge (step 4). If the note says a connection isn't connected, set
**Network Source** back to Automatic, or to the connection you use (step 3).

**Swiping moves the dashboard but the page doesn't change.**
Set Previous Display Screen and Next Display Screen in iCUE Screen Setup (step 5).

**Two browser tabs are playing but I can only control one.**
Browsers report all their tabs to Windows as a single media source. Media playing in
different apps (for example Spotify and a browser) can be switched between.

**The notification bell has no number.**
Some Windows setups don't allow apps to read the notification count. The bell still
opens your notifications, and tapping it again closes them.

## Removing the bridge

1. Find **CaveStudioEdgeBridge-Setup.exe** (usually in your Downloads folder).
2. Hold **Shift**, right-click it, and choose **Copy as path**.
3. Press **Windows key + R**, paste, type a space and `--uninstall` after it, then press
   **Enter**.
4. Confirm. The bridge is stopped and removed, and no longer starts with Windows.

## Help

Questions or problems: <https://github.com/Caveproduction-bot/cave-studio-edge/issues>
