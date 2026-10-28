**English** · [Українська](README.md)

# Vdykh — an open Bluetooth stethoscope for remote auscultation

> ⚠️ **Research prototype. Not a medical device.** Do not use it for diagnosis or treatment. See [DISCLAIMER.md](DISCLAIMER.md).

**Vdykh** (Ukrainian for "inhale") is a digital stethoscope project. The device connects to a smartphone over Bluetooth and lets people record lung and bronchial sounds at home, so their family doctor can listen to them remotely.

*Working name, may change.*

## Why

Ukraine is short of primary care physicians, especially in rural communities and frontline regions. Pulse, blood pressure, oxygen saturation and even ECG can already be measured at home with consumer devices. What is still hard to pass on to a doctor remotely is what they hear through a stethoscope: crackles, wheezes, diminished breath sounds.

The goal is a low-cost device that lets a patient, or someone in their family, make a good-quality recording by following prompts in an app, so the doctor can listen to it from anywhere.

The project is part of a broader idea: an AI assistant for family doctors, where the AI collects the patient's complaints and readings and the doctor always makes the final decision.

## How it works

```
[Diaphragm] → [MEMS microphone] ─┐
[Noise microphone] ──────────────┼→ [MCU + Bluetooth] → [App] → [Cloud + AI] → [Doctor]
[Contact & motion sensors] ──────┘        ↕
                                    [Flash memory]
```

1. The app shows on a body outline where to place the device and sets the breathing rhythm.
2. The device records 15–20 seconds of sound at each point into its internal memory.
3. The app checks recording quality and asks for a retake if there was noise or poor contact.
4. The recordings go to the doctor together with a spectrogram and markers on suspicious segments.

Details: [docs/en/hardware-concept.md](docs/en/hardware-concept.md).

## Project status

🟡 **Stage 0: concept.** Looking for collaborators and preparing the first prototype.

| Stage | Description | Status |
|---|---|---|
| 0 | Concept and documentation | ✅ |
| 1 | Proof of concept with off-the-shelf modules | ⏳ |
| 2 | Functional prototype on a custom PCB | ⬜ |
| 3 | Comparison with conventional auscultation together with doctors | ⬜ |
| 4 | Pre-production unit | ⬜ |

Details: [docs/en/roadmap.md](docs/en/roadmap.md).

## Repository structure

```
├── README.md                — Ukrainian version
├── README.en.md             — this file
├── LICENSE.md               — terms of use (UA + EN)
├── DISCLAIMER.md            — medical-use disclaimer (UA + EN)
├── CONTRIBUTING.md          — how to contribute + contributor agreement (UA + EN)
└── docs/
    ├── hardware-concept.md  — device concept (UA)
    ├── bom-stage1.md        — stage 1 components (UA)
    ├── roadmap.md           — roadmap (UA)
    └── en/                  — English versions of the documents
        ├── hardware-concept.md
        ├── bom-stage1.md
        └── roadmap.md
```

## Who we are looking for

- **Family doctors, pulmonologists, pediatricians**: to assess recording quality and define clinical requirements
- **Electronics engineers**: circuit design, acoustics, PCBs
- **Mobile developers**: the iOS and Android app
- **Audio processing and ML specialists**: noise reduction, detection of abnormal sounds
- **Industrial designers**: enclosure and ergonomics

Want to get involved? Read [CONTRIBUTING.md](CONTRIBUTING.md) and open an Issue, or get in touch: **visionregion@gmail.com / [LinkedIn](https://www.linkedin.com/in/vitalii-buchyn-88087824)**

Issues and comments in English are welcome.

## Terms of use

At this stage **all rights are reserved**. You may view the materials, discuss them and propose changes, but using, copying or building a device based on these materials requires the author's written permission. An open license may be applied in the future. See [LICENSE.md](LICENSE.md).

---

© 2026 Vitalii Buchyn
