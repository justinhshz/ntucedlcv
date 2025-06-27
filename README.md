# 🏁 NTUCE DLCV 113-2 Final Competition

[![Dev Container](https://img.shields.io/badge/devcontainer-Supported-success?logo=docker&logoColor=white)](https://code.visualstudio.com/docs/devcontainers/containers)
[![Miniconda](https://img.shields.io/badge/Anaconda-Miniconda-44A833?logo=anaconda&logoColor=white)](https://www.anaconda.com/docs/getting-started/miniconda/main)
[![Python Version](https://img.shields.io/badge/Python-3.11.12-3776AB?logo=python&logoColor=white)](https://www.python.org/downloads/release/python-31112/)
[![Ultralytics YOLOv9](https://img.shields.io/badge/Ultralytics-YOLOv9t-4051b5?logo=ultralytics)](https://docs.ultralytics.com/models/yolov9/)
[![PyTorch Version](https://img.shields.io/badge/PyTorch-2.7.0-EE4C2C?logo=pytorch&logoColor=white)](https://pytorch.org/get-started/locally/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Ready-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?logo=github)](LICENSE)

**Vision-based advanced damage classification of columns, beams, and walls.** 📷

## 🔍 Project Overview

This repository provides a complete solution for the NTUCE DLCV 113-2 Final Competition. It focuses on vision-based classification of structural damage across three common structural components.

- 🧱 **Targets**: Columns, Beams, and Walls
- 🧠 **Methods**: Vision-based damage analysis using EfficientNet for classification and YOLO for detection
- 📊 **Outputs**: CSV file with final predictions for submission
- 🔧 **Workflows**: Jupyter Notebooks for training and inference across three structure types

---

## 🚀 Usage Instructions

We offer two recommended execution methods. Please choose according to your development environment and preferences:

---

### ✅ Option 1 (Recommended): Use WSL2 + Docker + Dev Container

This method effectively avoids compatibility issues and package errors on Windows, making it the most stable choice.

#### ▸ Prerequisites (Windows Only)

1. Open PowerShell and run the following command to install WSL2:

   ```bash
   wsl --install
   ```
2. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/) and make sure the Docker Engine is running.
3. Open VSCode and install the `Dev Containers` extension.
4. After installation, press `Ctrl + Shift + P` and select:

   ```
   Dev Containers: Open Folder in Container
   ```

   Choose the folder corresponding to the structure type you want to work on (e.g., `beam/`, `column/`, or `wall/`). Each folder will launch a separate container.
5. The first time you launch it, Docker will automatically build the image and install the conda environment. This process may take some time—please be patient.

---

### 💥 Option 2: Use Local Conda Environment on Windows

If you do not wish to use Docker, you can run the code with a local Anaconda or Miniconda environment.

#### ▸ Create and Activate Conda Environment

```bash
conda create -n JPyDLCV python=3.11.12
conda activate JPyDLCV
conda env update -f environment.yml
```

---

## 📂 Data Preparation

1. Go to the [Group 8](https://drive.google.com/drive/folders/10LvxTu-El4GAFFdjv2wtDrGA4MN3xhgp?usp=drive_link) folder on Google Drive and download the `dlcv.zip` file and extract it. It contains the required folders: `beam/`, `column/`, and `wall/`.
2. The folder structure should look like the following (example: `beam/`; other folders are similar):

```
beam/
├── data/
│   ├── crack_classification/
│   ├── damage_classification/
│   ├── damage_detection/
│   └── test/
└── output/
    ├── crack_classification/
    ├── damage_classification/
    └── damage_detection/
```

3. Place the downloaded data into the corresponding folders in the GitHub repository:

   * `beam/data`: Place all four subfolders (`crack_classification`, `damage_classification`, `damage_detection`, `test`)
   * `beam/output`: Place all three subfolders (`crack_classification`, `damage_classification`, `damage_detection`)
   * Repeat similarly for `column/` and `wall/`

---

## 🧪 Running the Notebooks

Open and execute the following Jupyter Notebooks in order:

> ⚠️ **Note:** When running a Jupyter Notebook for the first time, you might see a prompt asking to install the `ipykernel` package, which is required to run notebooks in the selected Python environment. Simply click `Install` to allow Jupyter to automatically install the necessary kernel, after which the notebook will start running.

Additionally, if you wish to work on multiple structure types (e.g., beam, column, wall), you may open each folder in its own Dev Container. Each container runs in an isolated environment, so multiple models can be trained and tested concurrently without conflict.

### 1. Classify Damage Severity Levels
*Notebook: `damage_classification.ipynb`*

* **To train from scratch:** Click `Run All`
* **To use pre-trained models:** Run the following cells:

  * **_0. Imports & Global Setting_** — execute the first three code cells
  * **_1. Dataset / DataLoader_** — execute the first code cell
  * **_2. Define Model_** — execute all code cells in this section
  * **_5. Prediction & Submission_** — execute all code cells in this section

---
### 2. Detect Damage Types
*Notebook: `damage_detection.ipynb`*

* **To train from scratch:** Click `Run All`
* **To use pre-trained models:** Run the following cells:

  * **_0. Imports & Global Setting_** — execute all code cells in this section
  * **_1. Define Model_** — execute all code cells in this section
  * **_3. Prediction & Submission_** — execute all code cells in this section

---

### 3. Classify Crack Presence
*Notebook: `crack_classification.ipynb`*

* **To train from scratch:** Click `Run All`
* **To use pre-trained models:** Run the following cells:

  * **_0. Imports & Global Setting_** — execute the first three code cells
  * **_1. Dataset / DataLoader_** — execute the first code cell
  * **_2. Define Model_** — execute all code cells in this section
  * **_5. Prediction & Submission_** — execute all code cells in this section

---

### 4. Generate Final Submission File
*Notebook: `final_submission.ipynb`*

* Click `Run All` to generate the final result:

  ```
  output/submission.csv
  ```

---

## ✅ Verified System Configuration

This project has been tested and verified to run smoothly on a system with the following specifications:

* **CPU:** Intel Core i5-14500
* **GPU:** NVIDIA GeForce RTX 4070
* **Operating System:** Windows 11 Pro

If your system meets or exceeds these specifications, you should expect stable performance.
