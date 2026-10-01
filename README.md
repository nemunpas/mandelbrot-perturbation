# Mandelbrot Deep Zoom (WebGPU)

[English](#english) | [日本語](#日本語)

---

<a name="english"></a>
## 🚀 About
A browser-based Mandelbrot set deep zoom demo implemented using **WebGPU** and **Perturbation Theory**. 

🔗 **Live Demo:** https://nemunpas.github.io/mandelbrot-perturbation/

### Why Perturbation Theory?
After hitting precision limits quickly with standard `float` and `DSfloat` implementations, I realized perturbation theory was the only way to go deeper smoothly.

### Key Features
* **CPU & GPU Hybrid**: 
  * Reference orbits are computed on the CPU using JavaScript `BigInt` (480-bit fixed-point arithmetic).
  * Pixel perturbation calculations are parallelized via WGSL fragment shaders.
* **Dynamic Rendering**: 
  * Lowers resolution during interaction for smooth panning/zooming, then automatically re-renders in full HD (1080p) when idle.

---

<a name="日本語"></a>
## 🐾 概要
**WebGPU** と **摂動法（Perturbation Theory）** を使って、ブラウザでサクッと動くマンデルプロ集合の深部ズームデモを作ってみました。

🔗 **デモはこちら:** https://nemunpas.github.io/mandelbrot-perturbation/

### なぜ摂動法？
普通の `float` や `DSfloat` でズームしていくとソッコーで精度限界を迎えて破綻するので、「もう摂動法をやるしかない！」と観念して実装したものです。

### 主な工夫
* **CPU × GPU の分業**: 
  * 基準軌道（Reference Orbit）はJavaScriptの `BigInt`（480bit固定小数点数）で計算。
  * 各ピクセルの摂動計算はWGSL（フラグメントシェーダー）で並列処理。
* **二段構えのレンダリング**: 
  * グリグリ動かしている最中は解像度を落として軽快に動作させ、手を止めると高解像度（1080p）でキレイに再描画。

---

## 📄 License
This project is licensed under the [MIT License](LICENSE).
