# RunMinion for Mac (preview)

RunMinion is an AI assistant that does real work for you in your own web apps and files. You
watch it work in a live browser, it asks before anything irreversible, and you can take over at
any time. **[runminion.com](https://runminion.com)**

**Downloads:** [Apple silicon](https://github.com/HaotianHuang/runminion-releases/releases/latest/download/RunMinion-arm64.dmg) · [Intel](https://github.com/HaotianHuang/runminion-releases/releases/latest/download/RunMinion-x64.dmg) · [all releases](https://github.com/HaotianHuang/runminion-releases/releases)

This repository only hosts the downloads and these install notes.


This is an early preview for design partners. It's signed with our Apple Developer ID and
notarised by Apple, so it installs like any other Mac app.

## 1. Download

From [runminion.com](https://runminion.com/#download) or the [latest release](https://github.com/HaotianHuang/runminion-releases/releases/latest), pick the file for your Mac:

| Your Mac | Download |
| --- | --- |
| Apple silicon (M1, M2, M3, M4 …) | `RunMinion-arm64.dmg` |
| Intel | `RunMinion-x64.dmg` |

Not sure? Apple menu → About This Mac → "Chip" says Apple M… or "Processor" says Intel.

Requires macOS 12 Monterey or later.

## 2. Install

1. Open the `.dmg` and drag **RunMinion** into **Applications**.
2. Eject the disk image.

## 3. Open it

Open **RunMinion** from Applications. The first time, macOS checks the app and asks you to
confirm opening something downloaded from the internet. Click **Open**.

(Versions before 0.1.2 weren't notarised and needed System Settings → Privacy & Security →
**Open Anyway**. If you see that message, download the latest version.)

## 4. First run

- **Model key.** Onboarding asks for an API key for the model you want to use: Anthropic
  (Claude), or OpenAI or any OpenAI-compatible endpoint. It's encrypted with a key held in your
  macOS Keychain and only ever sent to that provider.
- **Browser.** RunMinion uses its own browser profile, separate from your everyday Chrome. If Google
  Chrome is installed it uses Chrome; if not, it downloads its own copy of Chromium (about
  150 MB, one time) the first time a task needs a browser.
- **Signing in to your apps.** Sign in once inside RunMinion's browser (Settings → Apps), or use
  **Import sign-ins from your browser** on the same page to copy the sites you tick from Chrome,
  Edge, Brave or Arc. macOS asks you to allow access to that browser's "Safe Storage" key; that's
  how RunMinion reads the sign-ins you chose, and nothing else.
- **Try it safely first.** Settings → Apps → **Demo workspace** gives you four practice apps
  (email, CRM, bookkeeping, a shop) with fake data, so you can see how it works before pointing
  it at real accounts.

## Updating

From 0.1.3, RunMinion updates itself: it checks for a new version every few hours, downloads it
in the background and installs it the next time you quit. To update right away, use **Restart to
update** in Settings → General. You can turn automatic checks off there; they're also off in
privacy mode. A check asks GitHub, where the downloads are hosted, for the latest version. GitHub
sees your IP address and app version, and nothing about your tasks.

On 0.1.2 or earlier, download the new `.dmg` once and replace the app in Applications; your tasks,
settings and sign-ins are kept. Coming from before 0.1.2, macOS may ask once whether RunMinion can
use its Keychain item ("RunMinion Safe Storage"). Click **Always Allow**.

## Where your data lives

Everything stays on your Mac in `~/Library/Application Support/RunMinion` (tasks, replays, audit
log, browser profile). Your model key is in that folder too, encrypted with a key held in the
Keychain. RunMinion has no telemetry. Settings → Privacy & audit has privacy mode, which keeps no
screenshots or replays.

To remove everything, quit RunMinion, delete the app and that folder, and remove the "RunMinion Safe
Storage" item in Keychain Access.

## Feedback

Tell us when a task goes wrong. Each task has an **Export audit** button at the top, which
saves the steps, captions and screenshots so we can see exactly what happened. Look it over
before sending; it contains what was on screen.
