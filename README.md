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

### ⚠️ Important: During the measurements, in the Keithley's parameters, the x-axis needs to be named *VG* (both letters capital) and the y-axis *ID* (also all capital).

The order of the files in the folder is critical. When uploaded, please ensure that they are well ordered by sites and runs in the folder (e.g. in order: Site@1Run1, Site@1Run2, Site@2Run1, Site@2Run2, etc.), especially if the names of files are modified when exported from the Keithley (recommended to leave the files names as default in the Keithley). Also important to verify that only files to be used for the computation are uploaded, and that the number of runs for every sites are consistent. Sites with different number of runs are very likely to produce wrong results.

---

# 🧪 Notebook Descriptions

## 1. 📈 plotting_gui.ipynb
Purpose: Plot every single provided files, regrouped by sites.
(images)
Parameters:
- Measurement Name: the name of the measurement, will be used as label in the to right corner
- Path to Measurement Folder: please write down the path to the folder where the files are stored. You get the path to your folder by clicking the folder icon on the left tool bar in Colab. If your file are stored on your Drive, once you mounted your Drive, a folder named 'drive' should appear. Then navigate in this folder by following drive -> MyDrive, and find the folder where the files are stored. Finally, you can get the path by clicking the three little dots on the right next to your folder and 'copy path'.
- +/-: to add a measurement folder or to remove the last added folder
- Number of sites: the number of sites of the measured chip
- Runs per site: the number of runs per site performed during measurement (every provided measurement folder must have the same runs per site or the resulting plots will be errornous!)
- Site to display: allow to select which site to visualize
- Dual sweep: If the measurements perforemed are forward+backward linear sweeps, ticking this checkbox will only show the forward sweep, while leaving it unticked will show the whole cycle
- Save: ticking this checkbox will save the resulting plots. The path to where the files will be saved has to be provided in 'Save Directory'
- Save Directory: The path to where the files will be saved. If the folder doesn't exist, a new one with the provided name will be created automatically. You need to tick the 'Save' checkbox if you want your files to be saved
- Plot: initialte the plotting. You need to fill all other parameters before plotting
- Save all plots: Save every plots for all sites directly in the folder provided in 'Save Directory'
  
