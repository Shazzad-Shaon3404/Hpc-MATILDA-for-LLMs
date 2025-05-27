# Hpc-MATILDA-for-LLMs
![HPC MobaXterm Setup](https://drive.google.com/uc?export=view&id=11Igi8Q8qfuhT5UM3dX9_P7WrQs16xKKa)

#  HPC & LLM Setup Guide

Welcome to this repository! This guide will help you get started with accessing a High-Performance Computing (HPC) cluster and running Large Language Models (LLMs) using Jupyter Notebook or JupyterLab.

---

##  What This Repository Covers

- ✅ **HPC Access Setup Guide**  
  Step-by-step instructions to install and use MobaXterm for accessing your university’s HPC system.

- ✅ **HPC Connection Setup**  
  Visual and written guide to initiate SSH sessions, upload files, and interact with the HPC environment.

- ✅ **Running LLMs on HPC via Jupyter**  
  Instructions on how to launch and run Jupyter Notebook or JupyterLab in the HPC environment to fine-tune and run LLMs (e.g., CodeT5, GraphCodeBERT).

---
Lets Go(-_-)
<p style="color:red"><strong>This guide explains how to configure and access a High-Performance Computing (HPC) environment using MobaXterm.</strong></p>


---

### So, firstly, Download MobaXterm

Download and install **MobaXterm** (a Windows SSH client with built-in X server):

- 📥 [Download MobaXterm Home Edition (Installer)](https://mobaxterm.mobatek.net/download-home-edition.html)

---

### 🔐 Step 2: Connect to HPC

1. **Open MobaXterm**
2. Click on `Session` > `SSH`
3. Fill in the following:
   - **Remote host**: `hpc-login-p01.oakland.edu` *(or your university's HPC login node)*
   - **Specify username**: `your_netid`
4. Click **OK** to save and connect.

---

### 📦 Step 3: Upload Dataset or Files

You can upload files via:
- MobaXterm’s built-in **SCP browser** (left panel after connecting), or
- Use the command line after downloading from Google Drive:

```bash
# Example: Download a Google Drive file directly using gdown (if available)
pip install gdown
gdown --id 11Igi8Q8qfuhT5UM3dX9_P7WrQs16xKKa
