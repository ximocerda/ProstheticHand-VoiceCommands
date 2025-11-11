# ProstheticHand-VoiceCommands  
Synthetic Wake-Word Dataset Generator for Voice-Controlled Prosthetic-Hand Systems

---

## Overview

This repository provides a complete and reproducible pipeline for generating a **synthetic voice-command dataset** specifically designed for keyword spotting (KWS) and voice-driven control of a prosthetic hand.  

The dataset is created entirely using **open-source tools**, and the generation workflow runs seamlessly in **Google Colab**, without requiring proprietary APIs or user audio recordings. The notebook synthesizes speech using the HuggingFace **MMS-TTS English** model and applies controlled acoustic perturbations to increase variability and improve robustness.

---

## 🔗 Open in Google Colab

Click the badge below to open and run the notebook directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](Wake_Word_Generator.ipynb)

---

## Features

- ✅ Fully open-source TTS pipeline  
- ✅ Works directly in Google Colab  
- ✅ Four dataset classes optimized for wake-word training  
- ✅ Controlled variability via pitch shift, time-stretching, and noise  
- ✅ Normalized audio (mono, 16 kHz, 2 seconds)  
- ✅ Reproducible synthesis flow  
- ✅ Minimal external dependencies  

---

## Dataset Classes

The generator produces four categories aligned with KWS architectures:

| Class           | Description                                               |
|----------------|-----------------------------------------------------------|
| `hand_grab`     | Wake-word command for closing the prosthetic hand         |
| `hand_release`  | Wake-word command for opening the prosthetic hand          |
| `other_words`   | Distractor phrases to improve model robustness             |
| `background`    | Synthetic noise for negative class modeling                |

Each sample is stored as a `.wav` file under its corresponding directory.

---

## Example Audio Samples

This repository includes optional example audio files illustrating the output of each class:

examples/  
├── hand_grab_example.wav  
├── hand_release_example.wav  
└── other_example.wav  


You can regenerate these files by running the notebook.

---

## Repository Structure

ProstheticHand-VoiceCommands/  
│  
├── Wake_Word_Generator.ipynb # Main notebook (full pipeline)  
├── README.md # Documentation  
├── LICENSE # MIT License  
├── .gitignore # Cleanup rules  
└── examples/ # Optional audio examples (3 files)  


---

## How to Use

1. Clone the repository or open the notebook directly in Colab.
2. Execute each cell in order.  
3. The script will:
   - install required dependencies  
   - load the MMS-TTS model  
   - synthesize audio samples  
   - apply augmentation  
   - normalize duration  
   - save `.wav` files under the `dataset/` directory  
4. After execution, the complete dataset will be available locally in:

dataset/  
├── hand_grab/  
├── hand_release/  
├── background/  
└── other_words/  


---

## Notes on Reproducibility

- All samples are deterministic given identical seeds and synthesis conditions.  
- If you require strict repeatability, uncomment and set:

```python
# np.random.seed(42)
```

The pipeline is fully self-contained; all processing steps happen inside the notebook.

## Citation

If you use this notebook, the generated dataset, or the associated methods in your research, please cite: [TO DETERMINE]

## License

This work is distributed under the terms of the MIT License. See the LICENSE file for details.
