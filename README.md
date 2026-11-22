# Energy for Mac (preview)

Energy is an AI assistant that does real work for you in your own web apps and files. You watch
it work in a live browser, it asks before anything irreversible, and you can take over at any
time.

**[Download the latest version →](https://github.com/HaotianHuang/energy-releases/releases/latest)**

This repository only hosts the downloads and these install notes.

This is an early preview for design partners. It isn't signed or notarised by Apple yet, so macOS
asks you to confirm the first time you open it. That's a one-time step.

## 1. Download

From the [latest release](https://github.com/HaotianHuang/energy-releases/releases/latest), pick the file for your Mac:

| Your Mac | Download |
| --- | --- |
| Apple silicon (M1, M2, M3, M4 …) | `Energy-<version>-arm64.dmg` |
| Intel | `Energy-<version>-x64.dmg` |

Not sure? Apple menu → About This Mac → "Chip" says Apple M… or "Processor" says Intel.

Requires macOS 12 Monterey or later.

## 2. Install

1. Open the `.dmg` and drag **Energy** into **Applications**.
2. Eject the disk image.

## 3. Open it the first time

1. Open **Energy** from Applications. macOS says it can't verify the app — click **Done** (not
   "Move to Trash").
2. Open **System Settings → Privacy & Security**, scroll to the **Security** section, and click
   **Open Anyway** next to the message about Energy. Confirm with your password or Touch ID.
3. Click **Open** in the dialog that follows.

After that, Energy opens normally.

**"Energy is damaged and can't be opened"?** That's the same check being stricter, not real
damage. In Terminal, run:

```bash
xattr -dr com.apple.quarantine /Applications/Energy.app
```

then open it again.

## 4. First run

- **Model key.** Onboarding asks for an API key for the model you want to use: Anthropic
  (Claude), or OpenAI or any OpenAI-compatible endpoint. It's encrypted with a key held in your
  macOS Keychain and only ever sent to that provider.
- **Browser.** Energy uses its own browser profile, separate from your everyday Chrome. If Google
  Chrome is installed it uses Chrome; if not, it downloads its own copy of Chromium (about
  150 MB, one time) the first time a task needs a browser.
- **Signing in to your apps.** Sign in once inside Energy's browser (Settings → Apps), or use
  **Import sign-ins from your browser** on the same page to copy the sites you tick from Chrome,
  Edge, Brave or Arc. macOS asks you to allow access to that browser's "Safe Storage" key; that's
  how Energy reads the sign-ins you chose, and nothing else.
- **Try it safely first.** Settings → Apps → **Demo workspace** gives you four practice apps
  (email, CRM, bookkeeping, a shop) with fake data, so you can see how it works before pointing
  it at real accounts.

## Updating

There's no auto-update yet. Download the new `.dmg` and replace the app in Applications; your
tasks, settings and sign-ins are kept. Because preview builds aren't signed, macOS may ask again
whether Energy can use its Keychain item ("Energy Safe Storage"). Click **Always Allow**.

## Where your data lives

Everything stays on your Mac in `~/Library/Application Support/Energy` (tasks, replays, audit
log, browser profile). Your model key is in that folder too, encrypted with a key held in the
Keychain. Energy has no telemetry. Settings → Privacy & audit has privacy mode, which keeps no
screenshots or replays.

To remove everything, quit Energy, delete the app and that folder, and remove the "Energy Safe
Storage" item in Keychain Access.

## Feedback

Tell us when a task goes wrong. Each task has an **Export audit** button at the top, which
saves the steps, captions and screenshots so we can see exactly what happened. Look it over
before sending; it contains what was on screen.
