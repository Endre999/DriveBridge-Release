# DriveBridge – guide for testers

*Magyar változat: [TESZTELOKNEK.md](TESZTELOKNEK.md)*

DriveBridge is an Android app that lets you talk to your own AI assistant hands-free while driving. You dictate, the car speakers read the answer aloud, and you control it with the car's media buttons. The conversation stays in your own AI account.

## What you need
- An Android phone running Android 13 or newer, with speech recognition for your chosen language
- A car or headset that plays phone audio over Bluetooth and has media buttons
- A Claude or Grok account
- A browser (or Claude Desktop) once, to add the connector, and mobile internet while driving

## Install
1. Download [DriveBridge-0.11.12.apk](https://github.com/Endre999/DriveBridge-Release/releases/download/drivebridge-reader-v0.11.12/DriveBridge-0.11.12.apk). The [README](README.md) always has the latest link.
2. Allow "Install unknown apps" for your browser or file manager. The exact menu varies by phone, usually under Settings → Apps (or Security). Many phones offer it when you open the file.
3. Open the APK and tap Install. If Google Play Protect warns you, that's expected for apps outside Google Play. Choose *More details* → *Install anyway*.
4. Optional: compare the SHA-256 with the value in the README.

## First launch
Grant microphone and notification permissions, then choose the app language. Your DriveBridge account has no password: you sign in with your email address and a code sent by email, in the app or at https://mcp.pandaonthemoon.io/login.

## Connect your AI client (once)
Connector name `DriveBridge`, URL `https://mcp.pandaonthemoon.io/mcp`.
- **Claude:** Settings → Customize → Connectors → *+ Add* → *Add custom connector*.
- **Grok:** open Connectors and scroll to the bottom of the Featured list to add a custom connector.

The "DriveBridge authorization" page asks for your DriveBridge email address and a 6-digit emailed code. In Claude, set all DriveBridge tools to *Always allow*, and turn this back on if Claude resets it after an update.

## In the car
Connect over Bluetooth and tap **Connect** in DriveBridge. The phone shows a 6-digit code and copies a ready sentence. Paste the sentence into your AI chat and send it. Then use **Play** to dictate and **Next** to send. The code is valid for 5 minutes. You can request a new one after 60 seconds (up to 5 per hour), and a new code invalidates the old one. To end, press **End conversation** twice.

## Updating
Install the new APK over the old one. You don't need to uninstall it.

## Feedback
Just tell your AI assistant, for example: *"Send feedback to the DriveBridge developer: dictation didn't start after the second button press."* It forwards your words directly to the developer. Bugs, ideas, anything are welcome. It helps to include your phone model, Android version, app version, and what happened.

## Privacy
What you say and the answers pass through the DriveBridge server and aren't stored there permanently. Speech-to-text runs on your phone. The conversation stays in your AI account. Transcripts are kept on the phone for 7 days. Feedback reaches the developer together with your account email. See [Privacy](https://www.pandaonthemoon.io/hu/privacy/).
