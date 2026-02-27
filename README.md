# GymPanner
### AI-Driven Biomechanical & Physiological Analysis for Musculoskeletal Health Optimization

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#license)
[![Status](https://img.shields.io/badge/Status-Hackathon%20Prototype-orange.svg)](#)

---

## Overview

**GymPanner** is an AI-powered training assistant that combines **pose-based biomechanics** with **camera-based heart-rate sensing** to quantify movement quality and fatigue-related risk during workouts. The project is designed for **biohacking/longevity** contexts where the goal is to improve **musculoskeletal healthspan** through measurable, actionable feedback.

Core capabilities:

- **Pose-based kinematics:** rep detection, range-of-motion (ROM), tempo, stability
- **rPPG heart rate:** fast heart-rate estimation from a phone camera
- **Fatigue-aware scoring:** movement-quality drift + HR signals → readiness/risk cues
- **Interpretable outputs:** clear metrics and visualizations (not a black box)

---

## Key Features

### 1) Biomechanics from Pose Estimation
Using a webcam (or video), GymPanner extracts 2D keypoints and computes:

- **Rep count** (peak/trough detection on joint-angle time series)
- **Range of Motion (ROM)** per rep
- **Tempo** (eccentric/concentric phase durations)
- **Stability metrics** (variance in trunk angle / joint tracking)
- **Rep Quality Score** (weighted composite)

### 2) Phone-Camera Heart Rate (rPPG)
Using a phone rear camera + flashlight (finger-over-lens), the system:

- extracts a PPG-like signal (green channel intensity)
- filters the signal (typical band: ~0.7–4 Hz)
- detects peaks to estimate **heart rate (BPM)**
- optionally computes a basic **HRV proxy** (e.g., RMSSD) from inter-beat intervals

### 3) Fusion: Fatigue & Readiness Heuristics
GymPanner fuses physiological and biomechanical signals to generate:

- **Readiness recommendation:** Train / Maintain / Technique / Deload
- **Fatigue drift flag:** quality degradation across reps
- **Simple risk indicators:** elevated resting HR + movement instability

> Note: the fusion layer is designed to remain interpretable and configurable.

---

## Why This Matters (Biohacking × Longevity)

GymPanner targets **preventive performance**:

- reducing injury risk from fatigue-induced form breakdown
- improving training efficiency via objective movement metrics
- enabling sustainable training habits for long-term joint and muscle health

---

## Tech Stack

- **Python**
- **MediaPipe** (pose estimation)
- **OpenCV** (video I/O, processing)
- **NumPy / SciPy** (signal processing)
- **Streamlit** (optional UI/dashboard)

