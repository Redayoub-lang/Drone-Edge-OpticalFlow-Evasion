# Drone Edge Optical Flow Evasion & Blur Detection Engine

![Python 3](https://img.shields.io/badge/Language-Python%203.10-blue)
![Computer Vision](https://img.shields.io/badge/Domain-Computer%20Vision%20%26%20Edge%20AI-orange)
![Developer](https://img.shields.io/badge/Developer-Ayoub%20Lahmar-brightgreen)

An edge-optimized computer vision pipeline designed for real-time UAV obstacle evasion and optical flow tracking. Evaluates frame sharpness via Laplacian variance \(S_{\text{blur}}\) to immediately discard motion-blurred frames and reduce downstream processing latency on resource-constrained embedded platforms.

Implemented by **Ayoub Lahmar** ([@Redayoub-lang](https://github.com/Redayoub-lang)).

## 📐 Mathematical Formulation

Frame focus quality is computed using the variance of the Laplacian operator \(\nabla^2 I\):

$$
S_{\text{blur}} = \text{Var}\left( \nabla^2 I \right) = \text{Var}\left( \frac{\partial^2 I}{\partial x^2} + \frac{\partial^2 I}{\partial y^2} \right)
$$

Frames evaluated with \(S_{\text{blur}} < \tau\) are dropped immediately to optimize downstream edge processing workloads.

## 💻 Build & Run

```bash
python optical_flow_evasion.py
