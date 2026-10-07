![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Google Antigravity](https://img.shields.io/badge/Google--Antigravity-Orchestrator-4285F4?style=for-the-badge&logo=google)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
# Anomalous-Analytics-AI: Autonomous Behavior Analysis & Anomaly Detection System

## Overview
Anomalous-Analytics-AI is an autonomous computer vision system designed to read and analyze complex behavioral patterns within a defined environment. Rather than simply logging basic movement, this system actively monitors spatial relationships, interaction durations, and localized anomalies to identify high-risk behaviors or severe deviations from normal activity in real-time.

Built using Google Antigravity and Python/OpenCV.

## Problem Statement 7: Autonomous Vision & Behavior Understanding
This project strictly fulfills the requirements of PS07 by tracking entities, deeply analyzing their spatial behaviors over time, and explicitly reporting the **Subject (Who), Action (What), and Timestamp (When)** of an unusual event.

### 1. The Baseline (Normal Behavior)
Subjects navigating the environment naturally, maintaining standard spatial boundaries, and exhibiting expected, routine activity levels without prolonged disruptions.

### 2. The Anomaly (Unusual Event)
A subject or group of subjects exhibiting irregular behavioral patterns—such as aggressive spatial encroachment, erratic movement paths, or prolonged, unauthorized clustering in a predefined zone for more than 30 seconds without dispersing.

### 3. The Output
The system generates a specific, actionable behavioral alert to prevent generic false-positive warnings. 
* **Format:** `[ALERT] <Who> engaged in <What> at <When>.`
* **Example:** `[ALERT] Subjects 2 and 3 engaged in Spatial Encroachment against Subject 1 for 30s at Video Timestamp 14:02.`

---

## System Architecture & Data Pipeline
1. **Video Ingestion:** Raw MP4 scenario footage (Files strictly <100MB).
2. **Entity Tracking:** Bounding boxes and movement trajectories mapped via YOLO/OpenCV.
3. **Behavioral Logic:** Spatial distance, intersection-over-union (IoU), and time-in-zone counters calculated over a rolling 30-second window to establish intent.
4. **Agent Orchestration:** Google Antigravity autonomously coordinates the tracking pipeline and alert generation.

---

## Scope Note (10-Hour Hackathon Build)
**Core Build (Completed):**
* Successfully tracks persistent identities in a single frame to establish behavioral continuity.
* Accurately calculates spatial overlap and triggers alerts purely based on behavioral deviations over a 30-second timeline.
* Outputs explicit Who/What/When logs for administrative review.

**Attempted Stretch Goals (Abandoned for Scope):**
* Attempted to integrate facial recognition for explicit identity logging, but abandoned it to ensure baseline tracking stability, preserve rendering speed, and respect data privacy constraints within the 10-hour limit.

---

## Repository Structure
* `/src` - Core Python tracking logic and Antigravity agent configurations.
* `/data` - Compressed test footage (Baseline normal vs. Behavioral Anomaly scenarios).
* `/docs` - Evaluation rubrics, system architecture diagrams, and presentation notes.

---

## How to Run Locally
1. Clone this repository: `git clone https://github.com/melwinsamuel-0336/Anomalous-Analytics-AI.git`
2. Navigate to the source folder: `cd Anomalous-Analytics-AI/src`
3. Launch the Antigravity agent workspace to initialize the dependencies and execute the tracking pipeline against the sample footage in `/data`.
