# Smart People Counter

A computer vision project that uses YOLO11 and ByteTrack to detect and track people in a video.

## Features
- Person detection using YOLO11n.
- Person tracking using ByteTrack.
- Entry and exit counting using a virtual line.
- Restricted zone monitoring.
- Alerts when a person enters the restricted zone.
- Processed video output.

## Technologies Used
- Python
- OpenCV
- YOLO11 (Ultralytics)
- ByteTrack
- Google Colab

## Project Structure

```text
smart-people-counter/
│
├── Smart_People_Counter.ipynb
├── outputs/
│   └── final_output.mp4
└── README.md
```

## Results

| Metric | Count |
|---|---:|
| Total Entries | 16 |
| Total Exits | 10 |
| Restricted Zone Alerts | 1 |

## Comparison with Manual Counting

The automated YOLO-based people counting system detected **16 entries and 10 exits**. For comparison, the estimated manual count was **18 entries and 11 exits**.

The difference was 2 entries and 1 exit. These differences may occur because some people are temporarily hidden behind others, detection confidence can vary, and the tracking algorithm may lose or change a person's ID. Manual counting can also involve human error.

Overall, the system successfully demonstrated automated entry and exit counting using a virtual line and detected a person entering the restricted zone.

*Note: Manual counts are estimated values and have not been independently verified.*

## How to Run

1. Open the notebook in Google Colab.
2. Install the required libraries.
3. Upload your input video.
4. Run all notebook cells.
5. View the processed video in the `outputs` folder.

---

## YOLO Performance Optimization

### Overview

This experiment evaluates YOLO11 people detection performance by changing the confidence threshold, image size, and model. The experiments were performed using Google Colab with an NVIDIA Tesla T4 GPU.

### Video Information

- Total frames: 371
- Original FPS: 30
- Resolution: 768 × 432
- Duration: 12.37 seconds

### Performance Comparison

| Experiment | Model | Confidence | Image Size | FPS | Total Detections | Estimated MAPE (%) |
|---|---|---:|---:|---:|---:|---:|
| Baseline | YOLO11n | 0.35 | 640 | 75.73 | 4398 | 7.83 |
| Experiment 1 | YOLO11n | 0.45 | 640 | 65.85 | 2963 | 41.41 |
| Experiment 2 | YOLO11n | 0.35 | 960 | 67.34 | 8068 | 69.96 |
| Experiment 3 | YOLO11s | 0.35 | 640 | 71.02 | 4646 | 21.98 |

### Key Observations

1. Increasing the confidence threshold reduced detections and increased the estimated counting error.
2. Increasing image size produced more detections but did not improve the estimated counting error.
3. Changing the model to YOLO11s performed better than Experiments 1 and 2 in estimated MAPE, but did not outperform the baseline.

### Conclusion

The baseline configuration (YOLO11n, confidence 0.35, image size 640) achieved the highest processing speed of 75.73 FPS and the lowest estimated MAPE of 7.83%. It was the best-performing configuration among the tested experiments.

### Evaluation Limitation

The reference counts used for MAPE calculation were illustrative assumptions and were not independently verified through manual counting. Therefore, the MAPE values are preliminary estimates rather than verified accuracy measurements.
