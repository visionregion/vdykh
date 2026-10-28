**English** · [Українська](../hardware-concept.md)

# Device concept

*Version 0.1: concept only, none of the parameters have been tested in practice yet.*

## 1. Principle

The device keeps a conventional acoustic stethoscope chestpiece, because a diaphragm picks up sound from the body surface far better than a bare microphone. Instead of tubing and earpieces, a sealed air chamber with a digital microphone sits behind the diaphragm.

## 2. Acoustics

| Component | Requirements | Notes |
|---|---|---|
| Chestpiece with diaphragm | ⌀ ~45 mm | Adult size; smaller for children |
| Acoustic chamber | Sealed, small volume | Shape and volume to be explored in stage 1 |
| Main microphone | Digital MEMS, I2S/PDM, SNR ≥ 65 dB | e.g. ICS-43434, IM69D130, SPH0645 |
| Noise microphone | MEMS, facing outward | Used to subtract room background noise |

**Frequency range:**
- breath sounds: roughly 100–2000 Hz (wheezes in the lower part, crackles in the upper part);
- heart sounds: roughly 20–200 Hz.

**Recording parameters:** 8–16 kHz, 16–24 bit, mono per microphone.

## 3. Recording-quality sensors

- **Pressure / contact sensor** (FSR or strain gauge): detects whether the chestpiece is pressed firmly enough. Poor contact is the most common cause of bad home recordings.
- **Accelerometer (IMU)**: detects movements that cause artifacts; may also help identify the breathing phase from chest wall motion.

## 4. Electronics

| Component | Stage 1 option | Stage 2 option |
|---|---|---|
| MCU + Bluetooth | ESP32-S3 | Nordic nRF5340 (BLE Audio, LC3) |
| Storage | Built-in flash / microSD | SPI flash 16–64 MB |
| Power | LiPo 300–500 mAh | Same + charge management |
| Charging | TP4056 module / USB-C | USB-C on board |
| Controls | 1 button, RGB LED | Same, possibly a vibration motor |

### Data transfer mode

**Record to memory first, then transfer the file.** Streaming audio over Bluetooth introduces losses and artifacts, and for the doctor quality matters more than real-time delivery. One point is recorded for 15–20 seconds (≈0.5 MB at 16 kHz / 16 bit).

## 5. Enclosure

- Material that withstands disinfection with alcohol-based solutions.
- No gaps or seams where dirt can build up.
- Comfortable grip for placing the device on the front and sides of the chest without help.
- An optional handle attachment for self-recording on the back.

## 6. App (concept)

1. **Step-by-step auscultation points** on a body outline: 6–8 on the front and sides, 4–6 on the back. AR guidance through the camera is possible.
2. **Breathing instructions**: a visual "breathe in, breathe out" rhythm, mouth open.
3. **Automatic quality check** after each point: contact, noise level, clothing friction, heart sounds dominating. Poor quality triggers a retake.
4. **Upload of recordings** to secure cloud storage.
5. **Doctor's view:** listen to each point, spectrogram, markers on suspicious segments, comparison with earlier recordings.

## 7. Audio processing and AI

- Filtering, noise subtraction using the second microphone, normalization.
- Classification of abnormal sounds (wheezes, rhonchi, crackles).
- Open research datasets: ICBHI 2017 Respiratory Sound Database, HF_Lung, SPRSound.
- **Certification will require our own clinical recordings verified by doctors.**

## 8. Known problems and open questions

- **Points on the back** are the most informative for the lungs, but impossible to reach alone. Options: help from a family member, a handle attachment, or a nurse recording at a local clinic.
- **Friction from clothing and chest hair** requires artifact-detection algorithms.
- **Heart sounds** interfere with breath sound analysis at some points.
- **Regulation**: a production device used for diagnosis will be a medical device and will need certification.

## 9. Estimated unit cost

Components at production volumes: roughly **$25–40** per device, excluding enclosure and assembly. The estimate will be refined after stage 2.
