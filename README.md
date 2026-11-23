# Unofficial builds: Waveshare ESP32-S3-Touch-LCD-3.5 / -C

Prebuilt [SquachWatch-CYD](https://github.com/skizzophrenic/SquachWatch-CYD) firmware for the
Waveshare ESP32-S3-Touch-LCD-3.5 / -C, for use until the board support is merged:
https://github.com/skizzophrenic/SquachWatch-CYD/pull/158

These are **community builds, not official releases**. The built-in WiFi/Bluetooth update
does not work for them (official updates are signed by the project's key); flash a newer
image over USB instead. Source: the `waveshare-s3-touch-lcd-35` branch of this fork.

| File | For |
|---|---|
| `squachwatch-waveshare-s3-35-v4-merged.bin` | standard build |
| `squachwatch-waveshare-s3-35-gps-v4-merged.bin` | GPS module on the header (module TX to RXD / GPIO44). Not tested on hardware |

The screen runs at 80 MHz. Torn rows or speckle? Build `waveshare-s3-35-40mhz` from source.

## Flash (one file, offset 0x0)
1. Plug the board in over USB-C. If no port appears, hold BOOT while plugging in.
2. Use a web flasher such as https://espressif.github.io/esptool-js/ (Chrome or Edge): connect,
   flash address `0x0`, choose the .bin, Program.
   Or with esptool: `esptool.py --chip esp32s3 write_flash 0x0 squachwatch-waveshare-s3-35-v4-merged.bin`
3. Press reset. First boot runs the touch calibration.

Wi-fi time: Settings > System > WIFI NETWORKS. Pins and notes: `docs/WAVESHARE-S3-35.md` in the PR.
Checksums are in `SHA256SUMS.txt`.
