# Anomalous-Analytics-AI: Autonomous Traffic Anomaly & Safety System

## Overview
Anomalous-Analytics-AI is an autonomous computer vision system designed to monitor urban roadways and traffic intersections in real time. Rather than simple speed logging, this system actively identifies high-risk traffic anomalies—such as wrong-way driving, stalled vehicles in active lanes, and dangerous roadway obstructions—to reduce accident response times and improve road safety.

Built using Google Antigravity and Python/OpenCV.

## Problem Statement 7: Autonomous Vision & Behavior Understanding
This project strictly fulfills the requirements of PS07 by tracking vehicle entities, analyzing spatial trajectories, and explicitly reporting the **Subject (Who), Action (What), and Timestamp (When)** of an unusual event.

### 1. The Baseline (Normal Behavior)
Vehicles traveling continuously along designated lane vector pathways at standard flow speeds without stopping in active intersections or travel lanes.

### 2. The Anomaly (Unusual Event)
A vehicle trajectory moving against the authorized directional vector (Wrong-Way Driving) OR a vehicle remaining stationary (velocity = 0) within an active lane or intersection box for longer than 15 seconds (Stalled Vehicle / Lane Blockage).

### 3. The Output
The system generates a specific, actionable alert to prevent generic false-positive warnings.
* **Format:** `[ALERT] <Who> engaged in <What> at <When>.`
* **Example:** `[ALERT] Vehicle 3 encroached/stalled in Active Flow Zone A for 15s at Video Timestamp 01:15.`

---

## System Architecture & Data Pipeline
1. **Video Ingestion:** Raw MP4 footage from roadside surveillance feeds (Files strictly <100MB).
2. **Entity Tracking:** Bounding boxes and velocity vectors mapped via YOLO/OpenCV.
3. **Behavior Logic:** Directional vector comparison and stationary time counters calculated over a rolling window.
4. **Agent Orchestration:** Google Antigravity autonomously coordinates the tracking pipeline and alert generation.

---

## Scope Note (10-Hour Hackathon Build)
**Core Build (Completed):**
* Successfully tracks up to 5 vehicle identities simultaneously in a single frame.
* Accurately detects directional vector mismatches (wrong-way) and 15-second stationary breaches.
* Outputs explicit Who/What/When logs for traffic administration review.

**Attempted Stretch Goals (Abandoned for Scope):**
* Attempted to integrate Automatic License Plate Recognition (ALPR) for vehicle identification, but abandoned it to ensure real-time rendering stability and model speed within the 10-hour limit.

---

## Repository Structure
* `/src` - Core Python tracking logic and Antigravity agent configurations.
* `/data` - Compressed traffic test footage (Normal flow and Anomaly scenarios).
* `/docs` - Evaluation rubrics, system architecture diagrams, and presentation notes.

---

## How to Run Locally
1. Clone this repository: `git clone https://github.com/melwinsamuel-0336/Anomalous-Analytics-AI.git`
2. Navigate to the source folder: `cd Anomalous-Analytics-AI/src`
3. Launch the Antigravity agent workspace to initialize the dependencies and execute the tracking pipeline against the sample footage in `/data`.
