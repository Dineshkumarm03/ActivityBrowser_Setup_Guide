 Activity Browser setup guide (Windows)

This repository documents how to:

- Install Anaconda/Miniconda
- Install **Activity Browser (AB)**
- Import **ecoinvent**
- Install **Brightway2** in a separate environment (for sensitivity analysis)

> **Security note:** Do **not** store credentials (usernames/passwords) in GitHub. Use placeholders like `<your_username>`.

---

## Step 1 — Install Anaconda (or Miniconda)

- On INSA PCs: **Self Service Logiciels (WAPT)** → search **Anaconda Python 3** → install  
- If space is limited: install **Miniconda**

Why: AB is installed via **conda**.

---

## Step 2 — Install Activity Browser (AB)

Official guide: https://github.com/LCA-ActivityBrowser/activity-browser/wiki/Installation-Guide

Open **Anaconda Prompt** and run:

```bash
conda config --prepend channels conda-forge

conda create -n ab -c conda-forge activity-browser
# Proceed [y]/n → y

conda activate ab
activity-browser
```

### Update AB

```bash
conda activate ab
conda update activity-browser
```

---

## Step 3 — Import ecoinvent into AB

### Option A — Import directly inside AB (recommended)

1. Open AB
2. **Databases** → **Set up your project with default data**
3. Select **ecoinvent** and **biosphere3**
4. **Login** with `<your_username>` / `<your_password>`
5. Choose version/system model (e.g., **ecoinvent 3.11 consequential**)
6. Start import and wait for completion

### Option B — Download ecoSpold and import manually

1. Log in to https://ecoinvent.org/
2. Go to **Resources**
3. Download the required **ecoSpold02** archive (e.g., *ecoinvent 3.11 consequential ecoSpold02*)
4. Import into AB using the database import function

---

## Step 4 — Install Brightway2 (separate environment)

```bash
conda create --name brightway2 python=3.9
# Proceed [y]/n → y

conda activate brightway2
pip install brightway2

python -c "import brightway2 as bw; print(bw.__version__)"
```

---

## Troubleshooting

- **Conda not found:** reinstall Anaconda/Miniconda or fix PATH
- **Activation fails:** `conda env list`
- **AB won’t launch:** `conda activate ab` then `activity-browser`, read error; try `conda update --all`
- **ecoinvent import fails:** verify access rights + correct version/system model

---

**Footer signature:** Dineshkumar Muniyappan, Life cycle assessment researcher
