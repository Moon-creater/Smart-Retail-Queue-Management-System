# Smart Retail Queue Management System

An AI-powered computer vision project designed to monitor supermarket billing counters, estimate queue occupancy and recommend the counter with the shortest queue.

## Overview

Long queues at supermarket billing counters can result in increased customer waiting times and an inefficient checkout experience.

This project explores a computer vision-based approach to monitoring multiple billing counters using YOLOv8 and OpenCV.

The system detects people in video frames, divides the billing area into multiple counter regions, estimates the number of people in each region and visually classifies counters based on their occupancy.

## Features

- **Person Detection:** Uses YOLOv8 Nano to detect people in video frames.
- **Counter Segmentation:** Divides the video frame into multiple regions representing billing counters.
- **Queue Occupancy Estimation:** Counts detected people within each counter region.
- **Counter Classification:** Classifies counters as Free, Busy or Crowded using colour-coded indicators.
- **Waiting Time Estimation:** Estimates waiting time using an assumed average billing time per person.
- **Counter Recommendation:** Identifies the counter with the lowest detected occupancy.
- **Temporal Smoothing:** Uses a moving average over recent frames to reduce fluctuations in displayed occupancy.
- **Visual Monitoring:** Generates an annotated output video with counter information and recommendations.

## Technologies Used

- Python
- YOLOv8 Nano
- OpenCV
- Ultralytics
- Matplotlib
- Google Colab
- FFmpeg

## How It Works

1. A supermarket video is provided as input.
2. YOLOv8 detects people in individual video frames.
3. Detected people are assigned to counter regions based on bounding-box centre coordinates.
4. The number of detected people in each region is calculated.
5. Counters are classified according to their detected occupancy.
6. Waiting times are estimated using a fixed assumed service time.
7. Temporal smoothing stabilizes the displayed queue counts.
8. The system recommends the counter with the lowest detected occupancy.
9. OpenCV generates an annotated output video.

## Counter Classification

| Occupancy | Status | Indicator |
|---|---|---|
| 0–2 people | Free | Green |
| 3 people | Busy | Yellow |
| 4+ people | Crowded | Red |

## Demo

A demonstration video of the project is available in the `demo` folder.

## Current Limitations

- Counter regions are currently defined using fixed frame boundaries.
- Queue occupancy is estimated using person detections rather than persistent individual tracking.
- Waiting times are calculated using an assumed average service time.
- The current implementation processes uploaded videos rather than a live CCTV stream.

## Future Improvements

- Integrating object tracking using ByteTrack.
- Implementing customizable counter regions.
- Improving queue detection accuracy.
- Developing more realistic waiting-time prediction.
- Building a real-time monitoring dashboard.
- Integrating customer-facing display screens.

## Project Status

Working prototype with video-based person detection, queue occupancy estimation, counter classification and counter recommendation.

Independent AI/ML and Computer Vision Project.
