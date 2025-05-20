
# QGIS Plugin Installation Guide

This guide will help you install the required software and set up QGIS with PyTorch and Detectron2, and install the custom QGIS plugin.

---

## A. SOFTWARE INSTALLATION

### 1. Install Miniconda

Download and install Miniconda from the link below:

**[Miniconda Download](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe)**

### 2. Install Microsoft C++ Build Tools

1. Go to [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/)
2. Download and install the **Build Tools for Visual Studio**.
3. During installation, select the following:
   - ✅ "C++ build tools" workload  
   - ✅ "MSVC v142 or later"  
   - ✅ "Windows 10 SDK" in the right panel  
4. Restart your PC after installation.

---

## B. QGIS SETUP WITH PyTorch & Detectron2

Open **Anaconda Prompt** and run the following commands:

```bash
conda create --name qgis_ python=3.10
conda activate qgis_
conda install pytorch torchvision torchaudio cpuonly -c pytorch
pip install cython
conda install conda-forge::pycocotools
pip install "git+https://github.com/facebookresearch/detectron2.git"
pip install -r path/to/requirement.txt
conda install -c conda-forge qgis=3.40.3 -y
qgis
```
[Note: requiremen.txt will be provided and copy the path of requirement.txt and it will install all other needed library.]

Now, QGIS will launch. To verify all libraries are installed correctly and working inside QGIS, run the provided test script inside the QGIS Python console:

> **File to run:** `test_library.py`

---

## C. INSTALL QGIS PLUGIN

To install the plugin from a `.zip` file:

1. Go to **Plugins > Manage and Install Plugins**.  
2. Click on **Install from ZIP**.  
3. Choose the zip file (e.g., `map_feature_extraction.zip`).  
4. Click **Install Plugin**.

---

## D. USING PLUGIN

Once installed, follow these steps:

1. Click on the plugin name in the QGIS toolbar.
2. A popup window will open allowing you to **select the feature** to process
3. Drag to draw the **area of interest** on the map canvas.
4. Select a **path to save the TIF** file.
5. Wait for processing to complete. The **post-processed GeoJSON** will automatically be added as a **temporary layer** in QGIS.

---