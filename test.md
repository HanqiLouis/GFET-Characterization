# 📊 Google Colab Plotting & Analysis GUIs 

This repository contains **three interactive Google Colab notebooks** built for analyzing and visualizing Keithley measurement data:

1. **`Plot_all_Runs_GUI.ipynb`** – Plot every individual data file from a selected site and overlay them on a single graph  
2. **`Plot_Average_GUI.ipynb`** – Compute and visualize the average of all individual runs from a selected site  
3. **`DP_Boxplot_GUI.ipynb`** – Generate boxplots summarizing the extracted values (e.g., Dirac Points) across multiple sites

---

## ⚠️ Disclaimer

These notebooks are developed for internal use in collaboration with **Nanolab** and **Melexis**.  
They are **not intended for public or commercial distribution**.

Please use them **only for personal and authorized analysis purposes**.  
**Do not redistribute, publish, or share** the notebooks or associated data without explicit permission.

---

## 🧾 Requirements

These notebooks are meant to be used on **Google Colab** – no local installation is required.

To run them successfully:

- You must be signed in to a **Google account**  
  ⚠️ *Note:* EPFL Google accounts may cause issues with Drive access in Colab. A personal Google account is recommended.

---

## 📁 Data Preparation

### 📂 Where to store your files:

- **Option 1 – Upload in Colab**  
  Upload your files using the folder icon on the left toolbar in Colab.  
  ⚠️ *These files will be lost when the session ends.*

- **Option 2 – Mount your personal Google Drive (Recommended)**  
  Create a folder in your Google Drive and store the data files there.  
  You can also use a shared Drive folder to collaborate with others.

To mount your Google Drive inside Colab, run this code at the top of the notebook:

```python
from google.colab import drive
drive.mount('/content/drive')
```

Once mounted, your Drive content will be accessible under `/content/drive/MyDrive/`.


---

### 📄 Expected File Format

These GUIs are designed to process **linear voltage sweeps on the gate** (with constant bias between gate and drain), measured using the **Keithley**.

Each measurement file must:

- Be a **.xls or .xlsx  file**. 
- Each file must contain a `VG` and a `ID` columns.

> ⚠️ These column names (**VG** and **ID**) must **exactly** match this format (will both letters in uppercase) — otherwise the scripts will fail to parse the data.
> Please make sure that they are named correctly when setting up the parameters in the Keithley.

---

### 📑 File Naming and Ordering

Proper file order in the exported folder is **essential** to ensure proper site/run association. Please make sure that the files are ordered by sites and runs  
Example of correct order: Site@1Run1, Site@1Run2, Site@1Run3, Site@2Run1, Site@2Run2, Site@2Run3, ...  

#### ⚠️ Some Important Notes:

- Recommended to **not modify the name** of the files when exported from the Keithley, as the default naming classify them already in the correct order
- All **sites must have the same number of runs**
- Only include **files intended for processing** (please remove all test runs or duplicate runs)
- Files must be **sorted in the correct order** to ensure proper site/run association.

> ⚠️ Failing to follow this structure will likely result in **incorrect results or script errors**.

---

## 🧪 Notebook Descriptions

### 1. 📈 `Plot_all_Runs_GUI.ipynb`

**Purpose:**  
Plot each individual measurement for a selected site, with **all provided runs displayed together** on a single plot.

---

### ✅ Features and Parameters

- **Measurement Name**  
  - Label that will appear in the top-right corner of the resulting plot.

- **Path to Measurement Folder**  
  - Enter the full path to the folder containing your measurement files.

    👉 To find the path in Colab:
    - Use the file browser (the folder icon on the left sidebar in Colab)
    - If your Drive is mounted, follow `drive > MyDrive` and look for your folder
    - Click on the three little dots on the right of your folder and select **Copy path**
    - The path should look like this (if using Google Drive):  
      `/content/drive/MyDrive/MeasurementExample`

- **+ / – Buttons**  
  - Add a new measurement folder / Remove the last added folder

- **Number of Sites**  
  - The total number of sites measured (e.g. 24, if you folder contains Site@1, Site@2 until Site@24)

- **Runs per Site**  
  - The number of runs performed per site (e.g. 3, if you have Site@1Run1, Site@1Run2, Site@1Run3, then Site@2Run1, Site@2Run2, Site@2Run3, etc.)
  > ⚠️ *This must be the same for all sites across all provided folders*

- **Site to Display**  
  - Select which site to display on the plot (dropdown menu)

- **Dual Sweep**  
  If the measurements are linear dual sweep (forward + backward):
  - **Ticked**: only the **forward sweep** is shown  
  - **Unticked**: both **forward and backward** sweeps are shown

- **Save**  
  - Tick this box to save the generated plot(s) to the folder provided in **Save Directory**

- **Save Directory**  
  - The path to the directory where plots should be saved  
    - If the folder does not exist, it will be **created automatically**
    - This must be set in combination with the **Save** checkbox ticked

- **Plot**  
  - Click this to generate the plot  
  - Make sure all other required parameters are filled first

- **Save All Plots**  
  - Automatically saves **plots for all sites** into the specified `Save Directory`

---



