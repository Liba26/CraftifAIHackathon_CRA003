# FloraBot — AI-Powered Plant Disease Classification

FloraBot is an AI-based plant monitoring project that uses computer vision to classify potential plant health conditions from video. It aims to help plant caretakers identify plants that may need closer inspection.

## Problem Statement

Indoor plants in offices, hospitals, and other shared spaces may receive delayed attention because regular manual inspections take time. FloraBot explores AI-assisted monitoring to support earlier identification of potential plant health issues.

## Our Solution

FloraBot uses a trained YOLO11n classification model and a PipeGen-generated video inference pipeline to analyse plant imagery and display predicted plant-health classes.

### Key Features

- Classification across 15 plant-health classes.
- ONNX model integration.
- TensorRT FP32 engine compilation.
- DeepStream-based video inference.
- Video output with predicted classification labels.
- JSON metadata containing classification results and confidence scores.

## Technology Stack

- **AI Model:** YOLO11n Classification
- **Model Format:** ONNX
- **Inference Acceleration:** NVIDIA TensorRT
- **Video Pipeline:** NVIDIA DeepStream and PipeGen
- **Programming and Tools:** Python, C++, Ubuntu on WSL2
- **Hardware Used for Development:** NVIDIA GeForce RTX 4050 Laptop GPU (6 GB VRAM)

## Pipeline Architecture

Input Video → Frame Processing → YOLO11n Classification Model → TensorRT Inference → Class Label Mapping → Video Display and JSON Metadata

## Benchmark Results

Latest PipeGen-reported pipeline benchmark:

| Metric | Result |
|---|---:|
| Reported latency | 4.40 ms |
| Reported throughput | Approximately 227 FPS |
| Reported power | 7.4 W |
| TensorRT engine size | 8.8 MB |

These are reported benchmark values; end-to-end performance may vary with the environment and input.

## Repository Contents

- `flora_bot_best.onnx` — exported classification model.
- `tomato.mp4` — sample video used for pipeline testing.
- `FloraBot-PipeGen-Export.zip` — archive of generated PipeGen pipeline files.

## Current Status

The model has been compiled into a TensorRT FP32 engine, and the generated DeepStream pipeline successfully ran on the sample video and displayed classification results.

Prediction consistency still requires investigation: the test video sometimes receives pepper classifications despite showing tomato plants. Real-world classification accuracy has not yet been established.

## Future Work

- Investigate prediction mismatches and validate model preprocessing.
- Test with diverse real-world plant images and videos.
- Integrate a Raspberry Pi camera for physical deployment.
- Continue developing the FloraBot hardware with an ESP32 for sensor monitoring, motor control, and irrigation.
- Evaluate end-to-end performance on the target hardware.
- Explore alerts and a plant-monitoring dashboard.

## Project Goal

Our goal is to develop FloraBot into a practical AI-assisted plant-monitoring system that helps caretakers identify plants requiring attention.

**Note:** The physical hardware integration and real-world validation are still in progress.
