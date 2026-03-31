📡 AI-Powered LoRa Cognitive Radio Network (CRN)
An Edge-AI Dynamic Spectrum Access (DSA) system that uses a Convolutional Neural Network (CNN) on an RTL-SDR to dynamically allocate sub-channels to LoRa Secondary Users (SUs) while protecting Primary Users (PUs) from interference.

📖 Project Overview
This project implements a Cognitive Radio Central Node (run on a Raspberry Pi or PC) that manages a 1 MHz radio band (865.3 - 866.3)MHz. The band is split into 10 sub-channels of 100KHz each.

The system performs real-time spectrum sensing using an RTL-SDR combined with a Quantized TFLite CNN model. If a Primary User (Legacy Device) transmitting LoRa signals is detected, the AI instantly evicts Secondary Users (IoT nodes) to prevent interference. SUs transmit sensor telemetry (Temperature, Humidity, Gas) over the allocated channels.

✨ Features
🤖 Deep Learning Spectrum Sensing: Real-time IQ data classification using a custom CNN.
⚡ Float16 Quantization: Model optimized using TFLite for deployment on low-power edge hardware (Raspberry Pi).
🔄 Instant Eviction: If the SDR detects a PU, the system instantly transmits a vacate command to the active SU.
📊 Dynamic Terminal Dashboard: Real-time visual display of channel occupancy using emojis and visual metrics.
🧵 Thread Safe LoRa Architecture: SPI bus locks prevent driver crashes during multi-threaded operation.


🛠️ Hardware Requirements
Central Node (Controller): Raspberry Pi or Linux PC.
SDR Hardware: RTL-SDR (RTL2832U).
Control Channel Radio: RFM95x LoRa module connected via SPI.
IoT Nodes (PUs and SUs): Arduinos equipped with LoRa modules.

