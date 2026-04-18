# skripsi-inference-benchmark

Systematic benchmarking of Post-Training Quantization (PTQ) and 
Quantization-Aware Training (QAT) for YOLO-based object detection 
across heterogeneous edge hardware platforms.

## Research Question

What are the latency, throughput, accuracy, and power trade-offs 
between PTQ and QAT for modern YOLO architectures when deployed 
on heterogeneous edge hardware — specifically Apple Silicon M4, 
CUDA-enabled GPU, and MCU-class processors?

## Hardware Targets

| Platform | Chip | Category |
|---|---|---|
| Mac Mini M4 | Apple M4 (Neural Engine) | ARM / Apple Silicon |
| Lab Workstation | NVIDIA RTX 4060 | CUDA GPU |
| ESP32-S3 Sense | Xtensa LX7 + vector ext | MCU-class |

## Models

- YOLOv8n (Ultralytics baseline)
- YOLOv26n (next-gen, ONNX 11.70MB baseline from RescueVision)

## Optimization Techniques

| Technique | Framework | Status |
|---|---|---|
| FP32 baseline | ONNX Runtime | 🔲 planned |
| FP16 | ONNX Runtime / CoreML | 🔲 planned |
| PTQ INT8 | ONNX Runtime | 🔲 planned |
| QAT INT8 | PyTorch → ONNX | 🔲 planned |
| TFLite INT8 | TensorFlow Lite | 🔲 planned (ESP32) |

## Metrics

- Latency: mean, p95, p99 (ms)
- Throughput: FPS
- Accuracy: mAP@0.5, mAP@0.5:0.95
- Model size: MB
- Power consumption: W (where measurable)

## Experiment Tracking

MLflow for all runs. DVC for dataset and model versioning.

## Related Work

This study extends existing benchmarks (Q-YOLO, QATFP-YOLO, 
YOLOv4-Tiny on RPi5) by covering hardware platforms not previously 
benchmarked: Apple Silicon M4 Neural Engine and ESP32-S3 MCU-class 
deployment, with head-to-head PTQ vs QAT comparison on modern 
YOLO architectures.

## Status

🚧 Sprint 1 in progress — baseline environment setup

## Author

Fatih Jawwad Al-Mumtaz  
Computer Engineering, UNIDA Gontor  
Ponorogo, Indonesia
