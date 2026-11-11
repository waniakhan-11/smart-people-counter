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

## Author

Wania Khan  
