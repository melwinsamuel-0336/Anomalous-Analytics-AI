# Interrogation Cheat Sheet: Anomalous-Analytics-AI

## 1. Can it recognize what people/objects are doing?
**The Defense:** "Yes, through spatial relationship analysis. It doesn't just see 'people'—it calculates the Intersection over Union (IoU) of their bounding boxes and measures the duration of their overlap. This allows us to classify complex behaviors like crowding, hazing, or spatial encroachment, rather than just basic movement."

## 2. Does it spot meaningful events?
**The Defense:** "Yes. By intentionally ignoring standard movement and only triggering when predefined behavioral thresholds (like a 30-second localized grouping) are breached, the system filters out baseline noise and strictly alerts on high-risk, meaningful anomalies."

## 3. Can it tell normal from abnormal behavior?
**The Defense:** "Absolutely. Normal behavior is defined in our logic as fluid movement and standard conversational distance. Abnormal behavior is detected when our spatial distance matrix collapses and entities remain locked in a predefined zone beyond the acceptable time limit."

## 4. Does it track the same object across the video?
**The Defense:** "Yes. We use a centroid-tracking approach tied to our YOLO bounding boxes. Once an entity enters the frame, it is assigned a persistent ID (e.g., 'Subject 1'). This ID is maintained as long as the entity remains in the camera's field of view, ensuring our alerts log the exact entities involved."

## 5. Does it find objects accurately?
**The Defense:** "Yes, we utilize YOLO (You Only Look Once) integrated with OpenCV. This provides highly accurate, real-time bounding box generation even in dynamic frames, serving as the stable foundational data layer for our Antigravity behavioral logic."

## 6. Are events detected at the right time?
**The Defense:** "Yes. Our Google Antigravity orchestration agent manages a rolling time window. The exact moment an interaction crosses our 30-second boundary threshold, a precise 'Who, What, When' alert is logged with the corresponding video timestamp, eliminating latency in incident reporting."
