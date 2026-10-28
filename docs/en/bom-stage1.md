**English** · [Українська](../bom-stage1.md)

# Stage 1 components: proof of concept

*Goal of this stage: within 2–4 weeks and on a small budget, find out whether a home recording of breath sounds can be good enough for a doctor.*

Prices are approximate, in US dollars, and can vary a lot between shops.

## Parts list

| # | Component | Qty | Approx. price | Purpose |
|---|---|---|---|---|
| 1 | Ordinary mechanical stethoscope (chestpiece with diaphragm) | 1–2 | $10–25 | Acoustic base; the chestpiece is cut off the tubing |
| 2 | ESP32-S3 DevKit board | 1 | $8–15 | Microcontroller + Bluetooth |
| 3 | Digital I2S MEMS microphone (e.g. INMP441, ICS-43434, SPH0645) | 2–3 | $3–8 each | Main mic + noise mic + spare |
| 4 | microSD card module + 4–16 GB card | 1 | $3–6 | Storing recordings |
| 5 | LiPo battery 3.7 V, 300–500 mAh | 1 | $4–8 | Power |
| 6 | USB-C charging module (TP4056 with protection) | 1 | $1–3 | Battery charging |
| 7 | FSR force sensor (e.g. FSR402) | 1 | $3–7 | Monitoring chestpiece pressure |
| 8 | Accelerometer/IMU (e.g. MPU-6050 or LSM6DS3) | 1 | $2–5 | Motion detection |
| 9 | Button, RGB LED, resistors | — | $2 | Controls and status |
| 10 | Silicone tubing ⌀ 5–8 mm, sealant, hot glue | — | $3–5 | Acoustic coupling between chestpiece and microphone |
| 11 | Breadboard, wires, connectors | — | $5 | Assembly |
| 12 | 3D-printed enclosure (PETG) | 1 | $5–15 | Comfortable grip (can come later) |

**Total: roughly $50–120**, depending on the tools and spare parts you already have.

## Tools

- Soldering iron, solder, flux
- Multimeter
- Access to a 3D printer (optional at the start)
- Headphones with good low-frequency response, for listening to recordings

## Software

- Arduino IDE or PlatformIO / ESP-IDF for ESP32-S3 firmware
- Audacity or Sonic Visualiser for listening and spectrograms
- Python (numpy, scipy, librosa) for analysing recordings and comparing variants

## Stage 1 experiments

1. **Acoustic coupling variants:** microphone directly in the chestpiece vs. through a short piece of tubing; different chamber volumes.
2. **Microphone comparison:** which one gives the best signal-to-noise ratio in the 100–2000 Hz range.
3. **Noise subtraction** with the second microphone: TV on, conversation, a running fan.
4. **Effect of pressure:** how quality depends on how firmly the device is pressed (FSR data).
5. **Blind comparison with a doctor:** the doctor listens with a regular stethoscope and to prototype recordings from the same points, and checks whether they hear the same picture.

**Stage outcome:** recordings from several points on volunteers, the doctor's assessment of quality, and a decision on the stage 2 architecture.

> Volunteer recordings are not published in this repository without their written consent and de-identification. See [DISCLAIMER.md](../../DISCLAIMER.md).
