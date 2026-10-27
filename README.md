# Listening Station — Chelsea Market (Sennheiser × Qobuz)

An offline loop player for iPad. No WiFi, no text, no images. After one tap the screen is black and the tracks repeat forever. Built from the same idea as Abbey Road v2 (static files, no server), but it plays local files instead of embedded Qobuz streams.

## Files
- `index.html`: the player (setup screen plus a black play screen)
- `sw.js`: service worker that caches the app so it opens offline
- `manifest.webmanifest`, `icon-512.png`: the Home Screen app

## 1. Host it once (needs HTTPS, for setup only)
Service workers only run over HTTPS, so put the folder on any HTTPS static host **one time**: GitHub Pages (`milkshakemedia` org), or a folder on milkshakemedia.nyc. Only the app goes up there. **The audio is never uploaded.**

## 2. Install on each iPad (at the office, on WiFi)
1. Open the URL in Safari → Share → **Add to Home Screen**.
2. Open **the Home Screen icon**, not Safari. It has its own storage, separate from Safari's.
3. Copy the audio into the Files app (AirDrop or Finder → iPad → Files).
4. In the app, tap **Add tracks…** → Browse → pick all of them. Name the files `01-…`, `02-…` to set the order.
5. Turn on Airplane Mode. Force-quit the app, reopen it, and check the track list is still there. This is your offline test.

**Formats:** FLAC (Safari on iOS 11+), ALAC in .m4a, WAV, AIFF. 16/44.1 or 24/48 is the safe range. The app skips any file iOS can't play.

## 3. Lock the iPad down
- Settings → Display & Brightness → **Auto-Lock: Never**. Brightness to minimum.
- Settings → Accessibility → **Guided Access: On**, with a passcode. Start it in the app (triple-click the top button) and turn off Touch and the hardware buttons.
- Settings → Sounds → Headphone Safety → **Reduce Loud Audio**: set a ceiling, then set the volume (iOS ignores volume set inside a web app).
- Airplane Mode on. Do Not Disturb / Focus on. Software updates off.
- Tap **Start loop**. To get back to setup, hold the top-left corner for 4 seconds.

## 4. Gotchas
- **Power:** the A16 iPad has one USB-C port. Wired audio through Apple's adapter means **no charging**. Either recharge every night, or use a USB-C splitter with charging pass-through plus a 3.5 mm jack (test for hum and noise). Confirm the AC power at both stations with Anne.
- **After a reboot or a dead battery**, someone has to tap Start again. iOS won't play audio before a tap.
- **Lossless, not bit-perfect hi-res:** Safari resamples to the iPad's output rate. Don't claim hi-res on signage.
- **Rights:** the files have to be ones you're cleared to play in public, and the venue covers public performance (PRO licensing).

## Install-night checklist (Thu Oct 29, after 8:30p)
- [ ] Both iPads charged, loop loaded, Airplane Mode on, offline reopen tested
- [ ] Guided Access on, passcode written down for Dan and Kenn
- [ ] Volume ceiling set and checked on the actual Sennheisers
- [ ] Headphone cables secured (see "Cable security" below), then a pull test
- [ ] Run for 30 minutes and check every headphone position

## Cable security
- **Strain relief inside the box:** feed the headphone cable through a small hole. Inside, clamp it with a screw-down cable clamp or P-clip, leaving a slack loop before the jack. A pull then stops at the clamp, not the jack. This is Kenn's "fitted nut" idea, done with hardware-store parts.
- **Tether the headphones:** run a vinyl-coated steel security cable (looped ends) from the headband to an eye screw in the frame, so a cut cord doesn't mean stolen cans.
- **Lock the iPad and amp inside** the station, with only the cable hole exposed. That also stops the screen from being touched.

## Headphones: Sennheiser HDB 630 (they're active, not passive)
- The HDB 630 is a wireless ANC headphone. It has to be **powered on to play, even when wired** (USB-C or analog). There's no passive mode. Battery is rated up to 60 hours.
- Before opening each day, check every headphone is on and charged. Turn off auto power-off in the Sennheiser Smart Control app if the setting exists (not confirmed). Plan to charge them overnight.
- **Wired routes:** (a) USB-C straight from the iPad, where the headphone acts as its own DAC up to 24/96. That's one iPad per headphone. Or (b) the included 3.5 mm analog cable into a headphone amp.

## Amp station wiring (Mackie HM-4, one per station)
iPad USB-C → Apple USB-C-to-3.5 mm adapter → 3.5 mm-to-¼" TRS cable → HM-4 input (¼") → 3 of the 4 HM-4 outputs (¼") → 3.5 mm-female-to-¼"-male adapters → HDB 630 analog cables.
The HM-4 includes a 12 V power supply, so it needs an outlet at each station. Set each output knob once, then leave it inside the locked box.
