# Pixlpal L2 firmware releases

This repository holds only the firmware releases for the Pixlpal L2. There is no source code here.

Pixlpal L2 devices and the Pixlpal phone app read the latest release from this repository to update the firmware,
over Wi-Fi or Bluetooth.

Each release needs:

- A tag that is the firmware version, for example `v0.0.2`, the same as `version.txt` in the build.
- The asset `PIXLPAL-L2.bin`, the signed application image that `build_release.sh` makes (`build_release/PIXLPAL-L2.bin`).
- No storage (`spiffs.bin`) image: Pixlpal's storage holds each user's installed apps and files, which an image would erase.

The device installs only images built for the Pixlpal L2 and signed with Meterbit's release key, and rolls back if a
new image does not run normally. An image that is not signed this way is refused.

The same `PIXLPAL-L2.bin` also updates a Pixlpal from a USB drive: copy it to the drive's root folder, plug the drive in
and switch Pixlpal on, then press the knob when the screen offers the update.
