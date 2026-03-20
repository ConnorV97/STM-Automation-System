## STM Automation System for Autonomous Spectroscopy and Drift Correction

This project implements a closed-loop automation system for Scanning Tunneling Microscopy (STM) Experiments, enabling autonomous scanning, bias spectroscopy, and adaptive drift correction under varying temperature and magnetic field conditions.

This system integrates LabVIEW-based instrument control with Python-based image analysis to maintain spatial alignment and enable reproducible characterization of the local density of states (LDOS) in superconducting materials. 

## System Architecture:

STM (Nanonis Controller)
        ↓
LabVIEW (QMH / Producer–Consumer)
        ↓
Experiment Control Logic
        ↓
Data Acquisition (Scans + Spectroscopy)
        ↓
Python Processing Pipeline
    - Flattening / Denoising
    - Phase Correlation Drift Detection
        ↓
Feedback to LabVIEW
        ↓
Updated Scan Frame / Bias Position

## Key Features:

- Automate STM scanning and bias spectroscopy workflows
- Closed-loop drift correction using Fourier phase correlation
- Integration of multiple instruments (STM, temperature controller, magnet power supply)
- Adaptive scan frame and bias position updates after environmental changes
- Modular LabVIEW architecre using Queued Message Handler (QMH)

## Tech Stack 

**Control System**
-LabVIEW (Queued Message Handler, Producer-Consumer loop)

**Instrumentation**
-Nanonis V5 STM Controller
-Unisoku USM-1300 STM
-Lakeshore Model 350 Temperature Controller
-Cryogenic Magnet Power Supply

**Data Processing**
-Python(NumPy, OpenCV, matplotlib, nanonispy2) 

## Drift Correction Method

Image-based drift correction is performed using Fourier phase correlation between sequential STM scans. Processed images (flattened and denoised) are analyzed to extract translational offsets, which are fed back into the control system to update scan and bias coordinates in real-time. 
