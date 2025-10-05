## Loan ML — Loan Recovery Analysis

This repository contains an exploratory data analysis and modeling workflow for loan recovery, implemented in the notebook `Loan_recovery.ipynb`. It includes generated visualizations (distribution plots and a correlation heatmap) and the source dataset `loan-recovery.csv`.

### Project Structure

```
Loan_ML/
  Loan_recovery.ipynb         # Main analysis notebook
  loan-recovery.csv           # Input dataset
  correlation.png             # Correlation heatmap (exported)
  categorical_distributions/  # Saved categorical distribution plots
  dist1.png ... dist6.png     # Other exported figures
  .venv/                      # (Optional) Local Python virtual environment
```

### Quickstart

1) Clone and enter the project directory

```bash
git clone <your-fork-or-repo-url>
cd Loan_ML
```

2) Create and activate a virtual environment (Windows PowerShell)

```powershell
py -3 -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3) Install dependencies

If you already have a `requirements.txt`, install from it. Otherwise install the typical stack used by the notebook:

```powershell
python -m pip install --upgrade pip
pip install jupyter pandas numpy scikit-learn matplotlib seaborn plotly kaleido
```

4) Launch Jupyter and open the notebook

```powershell
python -m jupyter lab
# or
python -m jupyter notebook
```

Open `Loan_recovery.ipynb` and run the cells top-to-bottom.

### Exporting Figures (Plotly + Kaleido)

This project uses Plotly for interactive charts and Kaleido for static image export. To write images (e.g., `fig.write_image("correlation.png")`), ensure Kaleido is installed in the SAME environment used by the notebook kernel.

If you see an error like:

```
ValueError: Image export using the "kaleido" engine requires the Kaleido package
```

then in a notebook cell, run:

```python
%pip install --upgrade kaleido
```

Verify the interpreter path inside the notebook matches your virtual environment:

```python
import sys
print(sys.executable)
```

It should end with `...\\Loan_ML\\.venv\\Scripts\\python.exe` if you are using the local venv.

### Reproducing Results

- Run all cells in `Loan_recovery.ipynb`. The notebook loads `loan-recovery.csv`, performs preprocessing/EDA, and saves plots to the project root and to `categorical_distributions/`.
- If you want to regenerate PNGs, re-run the plotting cells. For Plotly figures, use `fig.write_image(...)` (requires Kaleido as above).

### Dataset

- `loan-recovery.csv` is included for convenience. If you replace it, keep the same schema or adapt the data-loading code in the notebook accordingly.

### Troubleshooting

- Kernel mismatch: If exports fail despite Kaleido being installed, your notebook may be using a different Python than your `.venv`. Switch the Jupyter kernel to the `.venv` interpreter and retry.
- OneDrive paths: If you run into permission or sync conflicts, save outputs to a non-synced path or pause OneDrive syncing while running heavy operations.

### Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

### License

Add a license of your choice (e.g., MIT). If you contribute, please include appropriate license headers.


