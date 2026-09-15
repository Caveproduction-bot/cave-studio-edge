# Setting up Cave Studio Edge

Setup takes about two minutes. You need Windows, iCUE 5.47 or later, and a CORSAIR
XENEON EDGE.

## 1. Add the widget to your XENEON EDGE

1. Get **Cave Studio Edge** from Elgato Marketplace. iCUE installs it for you.
2. In iCUE, open your **XENEON EDGE** and go to the **Widgets** page.
3. Add **Cave Studio Edge** to a screen and give it the whole screen (the largest size).

The clock, tasks, work sessions, colour themes and basic media controls work straight
away.

## 2. Install the free Cave Studio Edge Bridge

The bridge is a small program that lets the dashboard reach Windows. It powers:

- volume, mute, microphone mute and switching sound output
- album artwork, the progress bar and switching between media apps
- CPU, GPU, RAM and network stats
- the Windows notification count
- Show desktop, the display-mode button, swiping between pages, and Open iCUE

Without it, those parts of the dashboard show a dash (—).

1. Download **CaveStudioEdgeBridge-Setup.exe** from
   <https://github.com/Caveproduction-bot/cave-studio-edge/releases>.
2. Double-click it. If Windows shows "Windows protected your PC", click **More info**,
   then **Run anyway**. The installer is not code-signed, which is why Windows asks.
3. After a few seconds a message says the bridge is installed and running.

The bridge starts automatically whenever you sign in to Windows, and uses almost no
resources. You only need to install it once. Run a newer installer to update it.

## 3. Swiping between pages and the display-mode button

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
- **Options** has colour themes, the clock format, Movie Mode brightness, Open iCUE and
  Reset all data.

## Troubleshooting

**Parts of the dashboard show "—" or say the bridge is needed.**
The bridge isn't running. Restart your PC. If that doesn't fix it, run the installer
again.

**Swiping moves the dashboard but the page doesn't change.**
Set Previous Display Screen and Next Display Screen in iCUE Screen Setup (step 3).

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
