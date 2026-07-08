# EEG-Mental-State-Analysis-Feedback-System
A MATLAB-based pipeline that reads raw EEG signals, processes them through a bandpass filter, extracts frequency band features using Power Spectral Density (PSD), and classifies the user's mental state. The system features a custom UI window that dynamically displays tailored behavioral feedback based on dominant neural oscillations.

Here is a clean, professional, and scannable `README.md` template tailored perfectly for your script. It outlines the objective, setup, pipeline, and classification logic in a way that makes it look polished for your GitHub repository.

---

# EEG Mental State Analysis & Feedback System

A MATLAB-based pipeline that reads raw EEG signals, processes them through a bandpass filter, extracts frequency band features using Power Spectral Density (PSD), and classifies the user's mental state. The system features a custom UI window that dynamically displays tailored behavioral feedback based on dominant neural oscillations.

---

## 🚀 Features

* **Automated Data Extraction:** Directly extracts time-domain data ($XData, YData$) from pre-saved MATLAB figure files (`.fig`).
* **Signal Preprocessing:** Implements an 8th-order Butterworth Infinite Impulse Response (IIR) bandpass filter ($0.5\text{--}50\text{ Hz}$) to remove DC offset, baseline wander, and high-frequency noise.
* **Spectral Feature Extraction:** Uses Welch’s Overlapped Segment Averaging (`pwelch`) with a Hamming window to compute the Power Spectral Density (PSD).
* **Quantifiable Band Metrics:** Calculates the absolute power for standard neurological bands: Delta, Theta, Alpha, Beta, and Gamma.
* **Dynamic Feedback Interface:** Uses a custom `uicontrol` text container to provide word-wrapped, readable behavioral advice mapped to the user's cognitive state.

---

## 📊 Pipeline Architecture

The script maps the dominant frequency bands to the following cognitive states:

| Brain Wave | Frequency Range | Target Cognitive/Mental States |
| --- | --- | --- |
| **Delta ($\delta$)** | $0.5\text{--}4\text{ Hz}$ | Deep Sleep 😴 |
| **Theta ($\theta$)** | $4\text{--}8\text{ Hz}$ | Drowsy 💤 / Creative State 🧠 (if Alpha is also high) |
| **Alpha ($\alpha$)** | $8\text{--}13\text{ Hz}$ | Relaxed & Meditative 🧘‍♂️ |
| **Beta ($\beta$)** | $13\text{--}30\text{ Hz}$ | Sharp Focus 🎯 / High Stress 😣 (if Gamma spikes) |
| **Gamma ($\gamma$)** | $30\text{--}50\text{ Hz}$ | High Alertness & Peak Cognition 🤓 |

## 🛠️ Requirements & Setup

### Prerequisites

* MATLAB (R2020a or later recommended)
* **Signal Processing Toolbox**

### Running the Code

1. Clone this repository to your local machine:
```bash
git clone https://github.com/yourusername/eeg-mental-state-analysis.git
```
2. Place your target `.fig` file inside the project directory and ensure it is named `high_alert.fig` (or update line 6 of the script to match your filename).
3. Open `eeg_analysis.m` in MATLAB and press **Run**.

