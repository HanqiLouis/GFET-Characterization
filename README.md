# 📊 Plotting & Analysis GUIs (Google Colab)

This repository contains **3 interactive Google Colab notebooks** for analyzing and visualizing data:

1. **`Plot_all_Runs_GUI.ipynb`** – Plot every individual provided data files of a selected site and show them all on the same plot
2. **`Plot_Average_GUI.ipynb`** – Compute and plot an 'averaged' of every individual provided data files of a selected site
3. **`DP_Boxplot_GUI.ipynb`** – Generate boxplots for all sites

# ⚠️ Disclaimer

The notebooks in this repository are developed for internal use in collaboration with **Nanolab** and **Melexis**.
They are not intended for public or commercial distribution.
Please use them only for personal and authorized analysis purposes.
Do not redistribute, publish, or share the code or data without explicit permission.

---

## 🗂 Repository Structure

---

## 🧾 Requirements

These notebooks are designed for use on **Google Colab** — no installation required.
They can be downloaded individually and directly used in **Google Colab**.

Make sure:
- You're signed into a **Google account** (EPFL accounts have sometimes issues with Google Colab).
- You upload data as needed or connect your Google Drive using the same Google account as the one you use on **Google Colab**.

---

## 📁 Data Preparation

### Where to store files:
- **Option 1**: Create a folder within the Colab environment and upload the files directly. Be careful that the files will be lost when the session is closed.
- **Option 2 (Recommanded)**: Store your files in a folder on Google Drive. Then mount your Drive and navigate to the correct folder. It can also be a shared folder if your are working with multiple collaborators.

To mount Google Drive in Colab, run the first cell of the Notebook and allow Colab to connect to your personal Drive:

```python
from google.colab import drive
drive.mount('/content/drive')
```

### Expected file format:
The GUIs are designed to process and compute the Dirac points of **linear voltage sweeps on the gate (with constant bias between gate and drain)** using the **Keithley**.

⚠️ Important: During the measurements, in the Keithley's parameters, the x-axis needs to be named *VG* (both letters capital) and the y-axis *ID* (also all capital).

The order of the files in the folder is critical. When uploaded, please ensure that they are well ordered by sites in the folder (e.g. site1_run1, site1_run2, site2_run1, site2_run2, etc.), especially if the names of files are modified when exported from the Keithley (recommended to leave the files names as default in the Keithley). Also important to verify that only files to be used for the computation are uploaded, and that the number of runs for every sites are consistent. Sites with different number of runs are very likely to produce wrong results.
