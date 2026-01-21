# EMG-Controlled Assistive Orthosis for Pediatric Cerebral Palsy

An intelligent wearable device that uses machine learning to classify movement intent from EMG signals, providing adaptive assistance during physical therapy for children with cerebral palsy.

## Project Overview

Children with cerebral palsy (CP) often experience muscle weakness and fatigue during therapy. This orthosis helps by:

1. **Detecting movement intent** from 4 EMG sensors
2. **Classifying movement type** (wrist/elbow flexion/extension)
3. **Providing assistance** when weakness is detected

## System Architecture
```
[4 EMG Sensors] → [Intent Detection] → [Movement Classification] → [Motor Control]
                        ↓                        ↓
                  Binary: Moving?         3-class: Rest/Flex/Extend
                  (all 4 sensors)         (2 sensors each joint)
```

## ML Models

| Model | Input | Output | Architecture | Status |
|-------|-------|--------|--------------|--------|
| Intent Detector | 4 EMG channels | Moving / Not Moving | Linear + BCEWithLogitsLoss | 🔄 In Progress |
| Wrist Classifier | 2 EMG channels | Rest / Flex / Extend | Linear + CrossEntropyLoss | 📋 Planned |
| Elbow Classifier | 2 EMG channels | Rest / Flex / Extend | Linear + CrossEntropyLoss | 📋 Planned |

## Hardware

- **Microcontroller:** ESP32-S3
- **EMG Sensors:** 4x (2 forearm, 2 upper arm)
- **Additional Sensors:** Flex sensors, IMU
- **Actuation:** Motors with wire-pull mechanism

## Project Structure
```
├── data/               # EMG datasets
│   ├── raw/           # Raw recordings
│   └── processed/     # Preprocessed features
├── notebooks/          # Jupyter notebooks for exploration
├── src/                # Source code
│   ├── preprocessing.py   # Signal processing
│   ├── features.py        # Feature extraction
│   ├── models.py          # ML model definitions
│   └── train.py           # Training scripts
├── models/             # Saved trained models
└── results/            # Plots and metrics
```

## Getting Started

### Installation
```bash
git clone https://github.com/Tzekhai2005/cp-orthosis-emg-classifier.git
cd cp-orthosis-emg-classifier
pip install -r requirements.txt
```

### Training
```bash
python src/train.py
```

## Roadmap

- [x] Project setup
- [ ] EMG data collection
- [ ] Signal preprocessing pipeline
- [ ] Intent detection model
- [ ] Wrist classifier
- [ ] Elbow classifier
- [ ] ESP32 deployment
- [ ] Real-time testing

## Author

**Calvin Yap** - Year 2 Biomedical Engineering, Imperial College London

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.