# ESP32 OTA firmware host

Static hosting for pull-based ESP32 OTA updates.

- `version.txt` — the latest firmware version number (a single integer).
- `firmware.bin` — the current firmware image the device downloads.

The device (see the ESP32_HTTP_OTA sketch) fetches the raw URLs of these two
files over HTTPS, and self-flashes when version.txt is higher than the version
baked into the running firmware.

## Releasing an update
1. Bump `FW_VERSION` in the sketch, rebuild.
2. Copy the new `firmware.bin` here.
3. Set `version.txt` to the new number.
4. Commit and push. Devices update on their next check.
