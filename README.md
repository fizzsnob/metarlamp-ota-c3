# metarlamp-ota-c3 — OTA host for the **ESP32-C3** METAR Lamp

Signed firmware image + manifest for the **ESP32-C3** build (sketch
`METARLightworksC3-N-Number`).

- `firmware.json` — version manifest the lamp polls (GitHub API / raw).
- `firmware.img` — RSA-4096 / SHA-256 signed image (512-byte signature prepended),
  verified on-device against the embedded public key.

**Deliberately separate** from
[metarlamp-ota](https://github.com/fizzsnob/metarlamp-ota) (ESP32 / ESP32-S3): the C3 is
RISC-V, so flashing an S3/Xtensa image to it would brick it. Each architecture pulls only
its own repo. Signed with the **same key** as the S3 repo; published by `tools/release-c3.sh`.
