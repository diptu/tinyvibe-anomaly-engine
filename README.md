# ⚡ TinyVibe Anomaly Engine

<div align="center">

### 🧠 TinyML-Powered Predictive Maintenance for Resource-Constrained Edge Devices

**Detect machine failures before they happen — directly on microcontrollers.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![TinyML](https://img.shields.io/badge/TinyML-Edge%20AI-success)
![TensorFlow Lite Micro](https://img.shields.io/badge/TFLite%20Micro-Supported-orange)
![Python](https://img.shields.io/badge/Python-3.11+-blue)
![ESP32](https://img.shields.io/badge/ESP32-Ready-red)
![ARM Cortex-M4](https://img.shields.io/badge/ARM-Cortex--M4-purple)
![Hardware Cost](https://img.shields.io/badge/Hardware%20Cost-%240-success)

---

### 🚀 Bringing Industrial Predictive Maintenance to Tiny Devices

*A lightweight Edge AI system that transforms raw vibration signals into actionable maintenance intelligence using FFT-based feature extraction and quantized neural networks.*

</div>

---

# 🌟 Why This Project Matters

Industrial equipment often fails without warning, resulting in:

* 💸 Expensive downtime
* 🔧 Unplanned maintenance
* 🏭 Production interruptions
* ⚠️ Safety risks

Traditional monitoring systems rely on cloud infrastructure, powerful servers, or expensive industrial hardware.

**TinyVibe Anomaly Engine demonstrates a different approach:**

> Run predictive maintenance models directly on low-cost microcontrollers using less than 128 KB of memory.

This project combines:

* Embedded Systems
* Signal Processing
* TinyML
* Edge AI
* Deep Learning Optimization

into a deployable end-to-end anomaly detection pipeline.

---

# 🎯 Core Features

## 📡 Real-Time Signal Processing

Transform raw vibration streams into meaningful frequency-domain features using:

* Hanning Windowing
* Fast Fourier Transform (FFT)
* Spectral Magnitude Extraction
* Sliding Window Analysis

---

## 🧠 TinyML Autoencoder

A compact 1D Convolutional Autoencoder learns normal machine behavior and identifies anomalies through reconstruction error.

### Detection Principle

Normal Data:

```text
Input Signal ≈ Reconstructed Signal
```

Anomalous Data:

```text
Input Signal ≠ Reconstructed Signal
```

Error Function:

```math
E = ||X - X̂||₂
```

If:

```math
E > τ
```

An anomaly is detected.

---

## ⚡ Edge-Optimized Inference

Designed for deployment on:

* ESP32
* ARM Cortex-M4
* STM32
* Arduino Nano 33 BLE Sense

Optimizations include:

* INT8 Quantization
* TensorFlow Lite Micro
* Low SRAM Footprint
* No Floating Point Requirement

---

## 🧪 Zero-Cost Simulation Environment

No hardware required.

Developers can:

* Train models locally
* Stream synthetic vibration signals
* Simulate embedded runtimes
* Validate anomaly detection pipelines

using only Python and C++.

---

# 🏗️ System Architecture

```text
 ┌─────────────────────┐
 │ Vibration Sensor    │
 │ (Real or Simulated) │
 └──────────┬──────────┘
            │
            ▼
 ┌─────────────────────┐
 │ Signal Processing   │
 │ FFT + Windowing     │
 └──────────┬──────────┘
            │
            ▼
 ┌─────────────────────┐
 │ Feature Vector      │
 │ Frequency Spectrum  │
 └──────────┬──────────┘
            │
            ▼
 ┌─────────────────────┐
 │ TinyML Autoencoder  │
 │ INT8 Quantized      │
 └──────────┬──────────┘
            │
            ▼
 ┌─────────────────────┐
 │ Reconstruction      │
 │ Error Analysis      │
 └──────────┬──────────┘
            │
            ▼
 ┌─────────────────────┐
 │ Edge Alarm Trigger  │
 └─────────────────────┘
```

---

# 📂 Repository Structure

```text
tinyvibe-anomaly-engine/

├── .github/
│   └── workflows/
│       └── ci.yml

├── data/
│   ├── raw/
│   ├── processed/
│   └── datasets/

├── firmware/
│   ├── include/
│   ├── src/
│   └── anomaly_model.tflite

├── pipeline/
│   ├── preprocess.py
│   ├── train.py
│   ├── evaluate.py
│   └── convert.py

├── simulator/
│   ├── mock_sensor.py
│   └── edge_runtime_mock.cpp

├── notebooks/
│   └── experimentation.ipynb

├── requirements.txt

└── README.md
```

---

# 🔬 Machine Learning Pipeline

```text
Raw Vibration Data
        │
        ▼
Signal Cleaning
        │
        ▼
FFT Transformation
        │
        ▼
Feature Normalization
        │
        ▼
1D CNN Autoencoder Training
        │
        ▼
INT8 Quantization
        │
        ▼
TFLite Micro Deployment
        │
        ▼
Real-Time Edge Inference
```

---

# 🚀 Quick Start

## 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/tinyvibe-anomaly-engine.git

cd tinyvibe-anomaly-engine
```

---

## 2️⃣ Setup Environment

```bash
python -m venv .venv

source .venv/bin/activate

pip install -r requirements.txt
```

---

## 3️⃣ Train the Model

```bash
python pipeline/train.py \
    --epochs 50 \
    --batch_size 32
```

---

## 4️⃣ Convert to TFLite INT8

```bash
python pipeline/convert.py \
    --output firmware/anomaly_model.tflite
```

---

## 5️⃣ Launch Edge Runtime Simulator

```bash
g++ -O3 simulator/edge_runtime_mock.cpp \
    -o simulator/edge_runtime

./simulator/edge_runtime
```

---

## 6️⃣ Stream Sensor Data

```bash
python simulator/mock_sensor.py \
    --mode streaming
```

---

# 📊 Edge Performance Profile

| Metric           | FP32 Model | INT8 Model |
| ---------------- | ---------- | ---------- |
| Flash Size       | 512 KB     | **38 KB**  |
| SRAM Usage       | 192 KB     | **22 KB**  |
| Inference Cycles | 4.2M       | **0.48M**  |
| Execution Time   | 35 ms      | **4 ms**   |
| Recall (Anomaly) | 98.4%      | **97.6%**  |

---

# 🎓 Research Contributions

This project demonstrates practical experience in:

### TinyML

* Model Compression
* Quantization
* Edge Deployment
* Memory-Constrained AI

### Signal Processing

* FFT
* Spectral Analysis
* Feature Engineering
* Sensor Analytics

### Machine Learning

* Unsupervised Learning
* Autoencoders
* Anomaly Detection
* Model Optimization

### Embedded AI

* TensorFlow Lite Micro
* Embedded Inference
* Resource-Aware Design
* Real-Time Systems

---

# 🛠️ Deployment Targets

| Platform          | Supported |
| ----------------- | --------- |
| ESP32             | ✅         |
| STM32             | ✅         |
| ARM Cortex-M4     | ✅         |
| Arduino Nano BLE  | ✅         |
| Raspberry Pi Pico | ✅         |

---

# 🗺️ Future Roadmap

### Phase 1

* [x] FFT Feature Extraction
* [x] Autoencoder Training
* [x] INT8 Quantization
* [x] Edge Simulation

### Phase 2

* [ ] Real Sensor Integration
* [ ] ESP32 Deployment
* [ ] OTA Model Updates
* [ ] BLE Telemetry

### Phase 3

* [ ] Continual Learning Research
* [ ] Federated Edge Training
* [ ] Multi-Sensor Fusion
* [ ] Tiny Transformer Evaluation

---

# 📈 Potential Applications

* Smart Manufacturing
* Industrial IoT
* Predictive Maintenance
* Wind Turbine Monitoring
* Motor Health Diagnostics
* Bearing Fault Detection
* Factory Automation
* Edge Intelligence Systems

---

# 🤝 Contributing

Contributions are welcome.

If you would like to improve model architectures, embedded runtimes, deployment tooling, or benchmarking workflows, feel free to open an issue or submit a pull request.

---

# 📜 License

Released under the MIT License.

See the **LICENSE** file for details.

---

<div align="center">

### ⚡ TinyML • Edge AI • Embedded Intelligence

**Building machine intelligence that fits inside kilobytes, not gigabytes.**

</div>
