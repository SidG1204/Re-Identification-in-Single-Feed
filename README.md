# Re-Identification-in-Single-Feed

This project demonstrates real-time player re-identification in a football match video using object detection and tracking techniques. The goal is to ensure that each player is consistently assigned the same ID throughout the 15-second video, even when players leave the frame and reappear later.

---

## Objective

To simulate a real-world sports analytics use case by:
- Detecting all players in the input video using a YOLOv11-based model.
- Tracking players across frames using DeepSORT.
- Maintaining consistent player IDs even when players leave and re-enter the frame.

---

## Model & Tools Used

- **Object Detection Model**: Fine-tuned YOLOv11 model trained to detect both players and the football.
- **Tracking Algorithm**: DeepSORT (deep appearance descriptors + Kalman filter + Hungarian matching).
- **Framework**: Python (Google Colab)
- **Libraries**:
  - `ultralytics`
  - `opencv-python-headless`
  - `deep_sort_realtime`

---

##  File Structure

```
├── 15sec_input_720p.mp4       # Input match video
├── best.pt                    # YOLOv11 fine-tuned weights
├── output.mp4                 # Final annotated output video
├── ReID_tracking.ipynb        # Full Colab notebook
├── README.md                  # Project documentation
```

---

##  How It Works

1. Load the input video and YOLOv11 detection model.
2. Run detection on each frame (filtering only `player` class).
3. Pass bounding boxes and confidence scores to DeepSORT.
4. DeepSORT assigns persistent player IDs across the video.
5. Save and export the video with bounding boxes and IDs.

> **Note**: We explicitly filter out the `ball` class to avoid misclassification.

---

##  Results

- Players retain consistent IDs throughout the video.
- IDs remain stable even when a player briefly disappears from the frame.
- Output video can be played on any platform (converted to `.mp4` for compatibility).

---

##  Author Note

This project was submitted as part of an internship assignment for LIAT AI, focusing on real-world sports analytics and player re-identification.

---

##  Contact

**Siddhant Garg**  
Email: siddhantgarg962@gmail.com
  
