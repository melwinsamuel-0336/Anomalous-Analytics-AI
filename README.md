# Anomalous-Analytics-AI: Campus Harassment Intervention System

## Overview
Anomalous-Analytics-AI is an autonomous computer vision system designed to act as a guardian for campus blind spots. Rather than policing minor infractions, this system actively protects student welfare by identifying spatial encroachment, hazing, and harassment behaviors in real-time.

Built using Google Antigravity and Python/OpenCV.

## Problem Statement 7: Autonomous Vision & Behavior Understanding
This project strictly fulfills the requirements of PS07 by tracking entities, analyzing spatial relationships, and explicitly reporting the **Subject (Who), Action (What), and Timestamp (When)** of an unusual event.

### 1. The Baseline (Normal Behavior)
Students walking past each other in a hallway, or standing in a group with standard conversational distance and open body language.

### 2. The Anomaly (Unusual Event)
A single individual (Subject A) is backed against a predefined "wall zone," while two or more individuals (Subjects B & C) aggressively overlap Subject A's personal bounding space for more than 30 seconds without dispersing.

### 3. The Output
The system generates a specific, actionable alert to prevent generic or false-positive warnings. 
* **Format:** `[ALERT] <Who> engaged in <What> at <When>.`
* **Example:** `[ALERT] Subjects 2 and 3 encroached on Subject 1 (Wall Zone) for 30s at Video Timestamp 14:02.`

---

## System Architecture & Data Pipeline
1. **Video Ingestion:** Raw MP4 footage from campus cameras (Files strictly <100MB).
2. **Entity Tracking:** Bounding boxes mapped via YOLO/OpenCV.
3. **Behavior Logic:** Spatial distance and intersection-over-union (IoU) calculated over a rolling 30-second time window.
4. **Agent Orchestration:** Google Antigravity autonomously coordinates the tracking script and alert generation.

---

## Scope Note (10-Hour Hackathon Build)
**Core Build (Completed):**
* Successfully tracks up to 3 persistent identities in a single frame.
* Accurately calculates spatial overlap and triggers alerts on a 30-second boundary breach.
* Outputs explicit Who/What/When logs for administrative review.

**Attempted Stretch Goals (Abandoned for Scope):**
* Attempted to integrate facial recognition for explicit student ID logging, but abandoned it to ensure baseline tracking stability and respect data privacy constraints within the 10-hour limit.

---

## Repository Structure
* `/src` - Core Python tracking logic and Antigravity agent configurations.
* `/data` - Compressed test footage (Normal and Anomaly scenarios).
* `/docs` - Evaluation rubrics, system architecture diagrams, and presentation notes.

---

## How to Run Locally
1. Clone this repository: `git clone https://github.com/melwinsamuel-0336/Anomalous-Analytics-AI.git`
2. Navigate to the source folder: `cd Anomalous-Analytics-AI/src`
3. Launch the Antigravity agent workspace to initialize the dependencies and execute the tracking pipeline against the sample footage in `/data`.
