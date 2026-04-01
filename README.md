# Basic Statistics Projects

Extra activities, practice problems, and mini-projects for a **Statistics 1** course.  
This repository focuses on **core statistical concepts** and **data visualization** using **Excel** and a small **Python (Jupyter) simulation**.

---

## Contents (Repository Files)

- **Jupyter Notebook**
  - `statistics_activity_2.ipynb` — Monte Carlo simulation (fair die throws) to compare theoretical vs experimental probabilities
- **Excel Projects / Activities**
  - `project 2.1.xlsx`
  - `project 2.2.xlsx`
  - `project 3.xlsx`
  - `STATISTICS - project - 4.xlsx`
- **Presentation**
  - `Statistics_Extra_Activities_Presentation.pptx`
- **Image**
  - `statistics_project_4_chart.png`

---

## Topics Covered

- Descriptive Statistics
- Mean, Median, Mode
- Variance & Standard Deviation
- Probability Basics
- Data Visualization (charts & graphs)

---

## Tools Used

- **Microsoft Excel**
- **Microsoft PowerPoint**
- **Python 3 + Jupyter Notebook/Lab** (for `statistics_activity_2.ipynb`)

---

## How to Use

### Option A: Excel / PowerPoint (No coding)
1. Download or clone the repository.
2. Open the `.xlsx` files in **Microsoft Excel**.
3. Open `Statistics_Extra_Activities_Presentation.pptx` in **PowerPoint**.
4. Complete the activities and update charts/analysis as needed.

### Option B: Run the Jupyter Notebook (Python)
**Requirements**
- Python 3
- Jupyter Notebook or JupyterLab
- `numpy`

**Run locally**
```bash
# 1) (optional) create & activate a virtual environment
python -m venv .venv

# Windows:
.venv\Scripts\activate

# macOS/Linux:
source .venv/bin/activate

# 2) install dependencies
pip install numpy jupyter

# 3) start Jupyter
jupyter notebook
# or
jupyter lab
```

Then open:
- `statistics_activity_2.ipynb`

**What the notebook demonstrates**
- Simulates rolling a fair die **10, 50, and 100 times**
- Prints:
  - theoretical probabilities (1/6 each)
  - Monte Carlo probabilities from the simulation
- Shows how results generally get closer to the theoretical values as trials increase (Law of Large Numbers)

---

## Notes / Known Issues

- There is currently **no** `requirements.txt` or `environment.yml`.  
  The notebook can be run with: `pip install numpy jupyter`.
- If you want, you can add a `requirements.txt` later for easier setup.

---

## License

No license file is included yet. If you want this to be reusable by others, consider adding an open-source license (e.g., MIT).
