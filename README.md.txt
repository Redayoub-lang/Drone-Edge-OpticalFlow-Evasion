# Real-Time Edge Obstacle Evasion Engine via Dense Optical Flow

![C++17](https://img.shields.io/badge/Language-C%2B%2B17-blue)
![OpenCV](https://img.shields.io/badge/Library-OpenCV%204.x-green)
![Developer](https://img.shields.io/badge/Developer-Ayoub%20Lahmar-brightgreen)

A deterministic, ultra-low-latency C++ navigation engine designed for resource-constrained UAV onboard edge hardware (e.g., Raspberry Pi, Jetson Nano). Evaluates motion field expansion via **Farneback Dense Optical Flow** to compute steering vectors without deep learning overhead.

Implemented by **Ayoub Lahmar** ([@Redayoub-lang](https://github.com/Redayoub-lang)) for application to **Jiangsu University (JSU)**.

## 📐 Vector Field Analysis

Pixel displacement vectors \((u, v)\) map to magnitude field \(M(x,y)\) via polar decomposition:
M(x,y) = \sqrt{u(x,y)^2 + v(x,y)^2}
Spatial divergence across camera sub-regions generates a differential steering gradient away from high-density motion expansion zones.

💻 Compilation
g++ -std=c++17 -O3 main.cpp -o FlowEvasion `pkg-config --cflags --libs opencv4`
./FlowEvasion