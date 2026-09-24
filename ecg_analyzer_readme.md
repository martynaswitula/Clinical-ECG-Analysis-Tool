# ECG Signal & Stress Analyzer 🫀📈

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-lightgrey.svg)
![SciPy](https://img.shields.io/badge/Signal%20Processing-SciPy-orange.svg)
![Status](https://img.shields.io/badge/Status-Prototype-success.svg)

## Overview

**ECG Signal & Stress Analyzer** is a Python-based desktop application designed to assist medical professionals in the preliminary phase of cardiac analysis. By processing raw ECG (Electrocardiogram) signals, the software automatically detects R-peaks and extracts key physiological parameters to aid in diagnostics.

The tool provides an intuitive graphical interface (GUI) for doctors and administrators to load patient data, visualize the signal, and calculate metrics such as Heart Rate, Heart Rhythm regularity, and estimated psychological stress levels.

## Key Features

* **R-Peak Detection:** Utilizes `SciPy` signal processing (`find_peaks`, `peak_prominences`) to accurately identify R-peaks in the QRS complex.
* **Heart Rate Calculation:** Computes the average pulse rate (BPM) based on R-R intervals.
* **Rhythm Analysis:** Evaluates the regularity of the heart rhythm by analyzing the variance in R-R interval spacing.
* **Stress Level Prediction:** Estimates physiological stress levels (Low, Medium, High) based on heart rate thresholds.
* **Signal Visualization:** Embeds `Matplotlib` plots directly into the Tkinter interface for immediate visual feedback of the raw signal and detected peaks.
* **Data Management & Export:** Allows users to save analysis results directly to a local `.txt` database with timestamps and physician IDs.
* **Role-Based Access Control:** Features a mock login system differentiating between 'Doctor' (analysis access only) and 'Administrator' (user management access).

## Tech Stack

* **Language:** Python
* **GUI Framework:** Tkinter
* **Data & Signal Processing:** Pandas, NumPy, SciPy
* **Visualization:** Matplotlib
* **Image Handling:** Pillow (PIL)

## Installation & Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/martynaswitula/ECG-Stress-Analyzer.git
   cd ECG-Stress-Analyzer
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure you have the `login.txt` file in the root directory. If missing, create one with a default admin account (Format: `Name;Surname;Username;Password;Role`), for example:
   ```text
   Admin;User;admin;admin;Administrator
   ```

4. Run the application:
   ```bash
   python login.py
   ```
   *(Note: The main executable file is currently named `login.py`)*

## Usage Guide

1. Log in using your credentials (use `admin` / `admin` for Administrator access).
2. From the main dashboard, select **"Kliknij i wybierz plik txt"** to load a raw ECG signal (time/voltage format). Sample files (e.g., `sygnal_ekg.txt`) are included in the repository.
3. Check **"Wyświetl załamek R"** to visualize the signal with detected peaks highlighted.
4. Click **"Analizuj"** to proceed to the analysis panel.
5. Select the desired metric (Heart Rate, Stress Level, Rhythm, or Standard Deviation) and click **"Oblicz"**.
6. Save the results to the log by clicking **"Zapisz"**.

## Disclaimer

This software was developed as an academic engineering project. The stress estimation algorithm is simplified for demonstration purposes and the tool is not certified for clinical medical diagnosis. The authentication system uses plain-text local storage and is intended only as a conceptual prototype.