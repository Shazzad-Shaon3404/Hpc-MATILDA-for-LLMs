# Hpc-MATILDA-for-LLMs
![HPC MobaXterm Setup](https://drive.google.com/uc?export=view&id=11Igi8Q8qfuhT5UM3dX9_P7WrQs16xKKa)

#  HPC & LLM Setup Guide

Welcome to this repository! This guide will help you get started with accessing a High-Performance Computing (HPC) cluster and running Large Language Models (LLMs) using Jupyter Notebook or JupyterLab.

---

##  What This Repository Covers

- ✅ **HPC Access Setup Guide**  
  Step-by-step instructions to install and use MobaXterm for accessing your university’s HPC system.

- ✅ **HPC LOGIN Setup**  
  Visual and written guide to initiate SSH sessions, upload files, and interact with the HPC environment.

- ✅ **Running LLMs on HPC via Jupyter**  
  Instructions on how to launch and run Jupyter Notebook or JupyterLab in the HPC environment to fine-tune and run LLMs.

---
Lets Go(-_-) <br>
This guide explains how to configure and access a High-Performance Computing (HPC) environment using **MobaXterm**.
---

**HPC Access Setup Guide**
### Step 1: Download MobaXterm

Download and install **MobaXterm** (a Windows SSH client with built-in X server):

- 📥 [Download MobaXterm Home Edition (Installer)](https://mobaxterm.mobatek.net/download-home-edition.html)
![Jupyter LLM on HPC](https://drive.google.com/uc?export=view&id=1-9d6RBBVbpWZh-AdsrkZfnjBxaiRMv2K)

---

### Step 2: Connect to HPC

1. **Open MobaXterm**
2. Click on `Session` > `SSH`
3. Fill in the following:
   - **Remote host**: `hpc-login.oakland.edu` *(or your university's HPC login node)*
   - **click  this--✅--- before the Specify username**: then type `your_netid` *(Example your netid: SamuraiX@oakland.edu so put SamuraiX only)*
4. Click **OK** to save and connect based on the Figure.
![HPC Jupyter Access](https://drive.google.com/uc?export=view&id=1K_rO4MbPJIASB60p-SkIMQYLYGjAU7Rg)

---
**HPC LOGIN Setup**
### Step 1: Connect to LogIN page
1. Run the following SSH command in your terminal or MobaXterm:  `ssh <NetId>@hpc-login.oakland.edu`  write example ( your netid : samuraiX@oakland.edu so you have to write ssh samuraiX@hpc-login.oakland.edu)
2. When prompted, enter your password.
Note: The password will not appear as you type — this is normal. Just make sure to enter it correctly and press Enter.
3. After logging in successfully, you will see a URL — either displayed above or below the login message. Simply copy the URL and paste it into your browser to proceed.
4. After opening the URL in your browser, you will be prompted to set up Duo Two-Factor Authentication.

-First, download the Duo Mobile app on your smartphone. It is available for both iPhone and Android.

-On your laptop, click the option that says “I have downloaded the app”.

-Before proceeding, you must enter your U.S.-based phone number on the website.

-Then, open the Duo Mobile app on your phone, tap `“Add Account”,` and select` “Use QR Code”`.

-`Scan the QR code` shown on your laptop screen using your phone.

-Once the QR code is scanned successfully, your Duo setup is complete. 
- According to the image, you need to click on "Passcode" and select a number between 1 and 3 — just a single digit. For example, if you click 3, you will receive an SMS on your phone. At the same time, the Duo Mobile app will show two options: Approve or Reject. Then type the SMS code based on the second fig. 
Tap Approve to complete the authentication process.
![Duo QR Code Setup](https://drive.google.com/uc?export=view&id=1ftAgu9teK5rDHRnpTCgNhHE0z1Yc_fn4)
![Duo Authentication Example](https://drive.google.com/uc?export=view&id=1LBJxwfPyMVoJPn_YumUi7FBsTmE3Z-gY)

**🎉 Login successful! Welcome to the MATILDA HPCC.**
---
**Running LLMs on HPC via Jupyter**
So now you are in Log in page----- Lets Go for how to download or install jupyter
(base) [s@hpc-login-p01 ~]$ `ls`
 S 

(base) [s@hpc-login-p01 ~]$` cd S`



After logging into the MATILDA HPCC, the `ls`~ symbol indicates you're in` your home directory`. 
Running ls lists the contents of the home directory. In this case, the contents are:
A folder named `S`
---

Then----

# Load conda/anaconda module
module load `miniconda3`    # or `module load conda` depending on your system
`pip install miniconda3`

# Create conda environment (only once)
`conda create -y -n myenv python=3.10`

# Activate it
`conda activate myenv`

# Notebook installation
`pip install jupyter notebook`
after installation press <-- frim your keybord arrow and then press q

---
Then--- 




After logging into the HPC, run the following command to request a GPU node:


1. Command:` srun -t 1-00:00:00 --gres=gpu:1 --pty bash` <br>

   **NOTE: --gres=gpu:1 allocates 1 GPU.


   
You can change it to gpu:2 or gpu:3 to request more GPUs if allowed.**

3. Command: `conda activate myenv`
4. Command:  `jupyter lab --no-browser --ip=0.0.0.0 --port=9000`
5. Open Windows Terminal (not MobaXterm).    --Search windows taskbar and search terminal
6. Run the following command to create an SSH tunnel in  Windows Terminal :  `ssh -N -L 9000:hpc-gpu-p03:9000 samuraix@hpc-login.oakland.edu`<br>
 **NOTE :🔁 Replace samuraiX with your actual NetID.** <br>
**🔐 Enter your password when prompted.**
7. Copy the full URL with the token from Step MobaXtrem based on the Figure (GREEN highlight).
![Project Folder Structure](https://drive.google.com/uc?export=view&id=1H8ZCoVirfx55XJ3ftTlOqmS-rRcxGZOU)


8. Paste it into your browser.

🎉 Boom! JupyterLab is now running on the MATILDA HPCC with GPU support.

![Example Output](https://drive.google.com/uc?export=view&id=1S5Jdj8FBmSMKmbZk4pbYeP5ea_EDP5jp)





 
