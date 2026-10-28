**English** · [Українська](../roadmap.md)

# Roadmap

*Timelines and budgets are approximate and depend on the team and funding.*

## Stage 0: Concept ✅

- Technical concept of the device
- Publishing the project, looking for collaborators
- First conversations with doctors about clinical requirements

## Stage 1: Proof of concept ⏳

**Timeline:** 2–4 weeks · **Budget:** $50–150

- Building a prototype from off-the-shelf modules (ESP32-S3, MEMS microphones, a regular stethoscope chestpiece)
- Experiments with the acoustic chamber and microphones
- First recordings on volunteers
- Blind comparison with conventional auscultation, with a doctor taking part

**Success criterion:** at most points, the doctor hears the same picture in the recording as with a regular stethoscope.

Components: [bom-stage1.md](bom-stage1.md)

## Stage 2: Functional prototype ⬜

**Timeline:** 2–4 months · **Budget:** $2–5k

- Custom PCB based on nRF5340
- 3D-printed enclosure designed for ergonomics
- Basic mobile app: auscultation points, breathing instructions, quality check
- First noise reduction algorithms

## Stage 3: Clinical validation ⬜

**Timeline:** 3–6 months

- Pilot with several family doctors
- Comparison of recordings with conventional auscultation on a larger sample
- Collecting doctor-labelled data for AI training (with patients' informed consent)
- Choosing an approach for points on the back: family help, an attachment, or a nurse

## Stage 4: Pre-production unit ⬜

- Industrial design of the enclosure
- Quality management system (ISO 13485), IEC 62304 documentation for the software
- Preparing for conformity assessment as a medical device
- Finding a manufacturing partner

## Parallel tracks

- **Doctor's app**: listening to recordings, spectrograms, patient history
- **AI analysis**: detecting wheezes, rhonchi, crackles
- **Integration** with the broader AI assistant platform for family doctors
