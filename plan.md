Week 1 — Research + Dataset + Setup

Goal: understand the project and prepare the environment.

Day 1 — Understand ECG basics

Study:

what ECG is
P wave
QRS complex
T wave
heart rate
arrhythmia

Focus especially on the QRS complex, because it’s central to diagnosis.

Quick idea:

P → atrial activity
QRS → ventricular contraction
T → recovery
Day 2 — Study disease classes

Learn common ECG abnormalities:

Normal sinus rhythm
Bradycardia
Tachycardia
PVC
AFib
Arrhythmia

Make notes about what each one looks like.

Day 3 — Download dataset

Best choice:

PTB-XL for final project
MIT-BIH for easier start

Create project folders:

ecg_ai_system/
│
├── data/
├── preprocessing/
├── model/
├── ui/
├── hardware/
└── results/
Day 4 — Install Python libraries

Install everything:

pip install numpy pandas matplotlib scipy tensorflow scikit-learn plotly wfdb

Important package:

wfdb for ECG datasets
Day 5 — Load and visualize data

Write code to load one ECG sample and plot it.

Example:

import matplotlib.pyplot as plt
plt.plot(signal)
plt.show()

Goal:
understand how raw ECG looks.

Day 6 — Research filtering

Study:

bandpass filter
noise removal
baseline drift
Day 7 — Build preprocessing module

Write filtering code:

from scipy.signal import butter, filtfilt

Save cleaned signal.

Week 2 — Signal Analysis

Goal: extract medical features.

Day 8 — QRS detection

Use peak detection:

from scipy.signal import find_peaks

Find R peaks.

This is one of the most important steps.

Day 9 — RR interval

Calculate heartbeat intervals:

rr = np.diff(peaks)
Day 10 — Heart rate

Calculate BPM:

heart_rate = 60 / np.mean(rr)
Day 11 — Feature extraction

Extract:

QRS width
RR interval
peak amplitude
heart rate

Store as features.

Day 12 — Label understanding

Understand dataset labels:

0 = normal
1 = abnormal
2 = PVC
3 = AFib
Day 13 — Prepare train/test split

Split data:

from sklearn.model_selection import train_test_split
Day 14 — Review week

Test everything built so far.

By now you should have:

cleaned ECG
detected peaks
extracted features

That’s excellent progress.

Week 3 — AI Model

Goal: train the brain.

Day 15 — Build first simple model

Start easy:

from sklearn.ensemble import RandomForestClassifier

This helps verify pipeline works.

Day 16 — Evaluate first model

Check:

accuracy
confusion matrix
Day 17 — Upgrade to CNN

Now use deep learning.

Best for ECG:

Conv1D
Day 18 — Build CNN architecture

Example layers:

Conv1D
MaxPooling1D
Flatten
Dense
Day 19 — Train model

Train for 10–20 epochs.

Save model:

model.save("ecg_model.h5")
Day 20 — Test predictions

Check:

prediction = model.predict(new_signal)
Day 21 — Disease classification

Add disease names:

disease_map = {
    0: "Normal",
    1: "PVC",
    2: "AFib"
}

Now the system becomes medically useful.

Week 4 — Interface + Hardware

Goal: make it feel like a real device.

Day 22 — Build screen UI

Use Streamlit (easiest):

pip install streamlit
Day 23 — Create display dashboard

Show:

ECG graph
prediction
disease
heart rate
Day 24 — Add 3D ECG graph

Use Plotly:

import plotly.graph_objects as go

This will look very professional.

Day 25 — Add alert system

Example:

if abnormal:
    print("⚠ Warning")
Day 26 — Treatment suggestion system

Add simple rule-based logic:

if disease == "AFib":
    recommendation = "Consult cardiologist"

Keep it as recommendation, not diagnosis.

Day 27 — Hardware research

Study sensor:

AD8232
Raspberry Pi
Arduino
Day 28 — Hardware integration

Connect sensor output to Python.

Flow:

Sensor → ADC → Python → AI → Screen
Day 29 — Final testing

Test complete flow:

signal
→ filter
→ classify
→ display
Day 30 — Final project presentation

Prepare:

screenshots
architecture diagram
code demo
results
accuracy graph

This is presentation day.