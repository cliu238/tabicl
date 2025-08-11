# 📚 How to Run TabICL vs XGBoost Comparison on Google Colab

## Quick Start (3 Steps)

### Step 1: Upload Notebook to Colab
1. Go to [Google Colab](https://colab.research.google.com/)
2. Click **File → Upload notebook**
3. Upload either:
   - `tabicl_xgboost_comparison_colab.ipynb` (basic version)
   - `tabicl_xgboost_advanced_comparison_colab.ipynb` (advanced version with proper TabICL)

### Step 2: Connect to Runtime
1. Click **Connect** button in top-right corner
2. Wait for runtime to initialize
3. (Optional) For faster execution: **Runtime → Change runtime type → GPU**

### Step 3: Run the Notebook
1. Click **Runtime → Run all** 
2. Or run cells one by one with **Shift+Enter**

---

## Detailed Instructions

### Option A: Direct GitHub Loading (Recommended)

1. Go to [Google Colab](https://colab.research.google.com/)
2. Click **File → Open notebook**
3. Select **GitHub** tab
4. Enter URL: `https://github.com/cliu238/tabicl`
5. Select the notebook you want to run

### Option B: Manual Upload

1. Download the notebook from your local machine
2. Go to [Google Colab](https://colab.research.google.com/)
3. Click **File → Upload notebook**
4. Choose the `.ipynb` file
5. Click **Open**

### Option C: From Google Drive

1. Upload notebook to your Google Drive
2. Go to Google Drive
3. Right-click the notebook file
4. Select **Open with → Google Colaboratory**

---

## What Happens When You Run

### First Cell (Setup)
```
🚀 Starting TabICL vs XGBoost Comparison Setup...
============================================================
📦 Cloning repository...
✅ Repository cloned!
📁 Working directory: /content/tabicl
📦 Installing required packages...
✅ Basic packages installed
📦 Installing TabICL...
✅ TabICL installed successfully!
📊 Checking data files...
✅ Data file found!
============================================================
✅ Setup complete! Ready to proceed.
```

The notebook will automatically:
1. Clone the GitHub repository with data
2. Install all required packages (xgboost, scikit-learn, tabicl, etc.)
3. Verify data files exist
4. Set up the environment

### Subsequent Cells
- Load and preprocess the VA dataset
- Create model wrappers
- Run comparisons
- Generate visualizations
- Show statistical results

---

## Runtime Requirements

### Basic Notebook
- **RAM**: 4-8 GB (standard Colab is fine)
- **Runtime**: ~10-15 minutes total
- **GPU**: Not required

### Advanced Notebook
- **RAM**: 8-12 GB (may need Colab Pro for large experiments)
- **Runtime**: ~20-30 minutes total
- **GPU**: Recommended for faster TabICL inference

---

## Troubleshooting

### Issue: "TabICL installation failed"
**Solution**: The notebook has automatic fallback to KNN. Continue running - it will still work.

### Issue: "Data file not found"
**Solution**: The setup cell will clone the repository. Make sure it completes successfully.

### Issue: "Out of memory"
**Solutions**:
1. **Runtime → Factory reset runtime**
2. Reduce batch sizes in the code
3. Use Colab Pro for more RAM

### Issue: "Disconnected from runtime"
**Solution**: Click **Reconnect** and re-run from the last completed cell

### Issue: "Package import errors"
**Solution**: Re-run the setup cell to reinstall packages

---

## Expected Output

### Performance Metrics
```
🎯 Evaluating In-Domain Performance...
============================================================

📍 Site: AP
----------------------------------------
Training XGBoost...
  XGBoost - Acc: 0.7234, F1: 0.6891, Time: 2.34s
Training TabICL...
  TabICL  - Acc: 0.7156, F1: 0.6823, Time: 1.89s
  🏆 Winner: XGBoost (+0.0078)
```

### Visualizations
- Domain transfer matrices (heatmaps)
- Performance comparison bar charts
- Statistical significance plots
- Few-shot learning curves (advanced version)

### Final Report
```
================================================================================
               TABICL VS XGBOOST: FINAL COMPARISON REPORT
================================================================================

📊 DATASET OVERVIEW:
  • Total samples: 7,582
  • Number of features: 169
  • Number of classes: 34
  • Number of sites: 6
  
📈 OVERALL PERFORMANCE SUMMARY:
  In-Domain:
    • XGBoost: 0.7234
    • TabICL:  0.7156
    
  Cross-Domain:
    • XGBoost: 0.6123
    • TabICL:  0.6489
    
💡 KEY INSIGHTS:
  1. TabICL shows better domain robustness
  2. XGBoost excels in single-domain scenarios
  3. TabICL requires no hyperparameter tuning
```

---

## Save Results

### To Google Drive
The notebook includes an optional cell at the end:
```python
save_results = input("Save results to CSV? (y/n): ")
```
Enter 'y' to save results to your Google Drive.

### Download Locally
1. Files will be in `/content/tabicl/comparison_results/`
2. Click folder icon in left sidebar
3. Navigate to the folder
4. Right-click files → Download

---

## Tips for Best Results

1. **Run cells sequentially** first time to ensure proper setup
2. **Use GPU runtime** for advanced notebook (faster TabICL)
3. **Don't skip the setup cell** - it installs critical dependencies
4. **Be patient** with domain analysis cells - they train multiple models
5. **Check the visualizations** - they provide key insights

---

## Which Notebook to Use?

### Basic Version (`tabicl_xgboost_comparison_colab.ipynb`)
✅ Use if you want:
- Quick comparison
- Standard metrics
- Basic domain analysis
- Faster execution

### Advanced Version (`tabicl_xgboost_advanced_comparison_colab.ipynb`)
✅ Use if you want:
- Proper TabICL implementation
- Few-shot learning analysis
- Domain adaptation experiments
- Interpretable predictions
- More comprehensive evaluation

---

## Questions?

The notebooks are self-contained with explanatory markdown cells. Each section explains what it's doing and why. Just follow along and run the cells in order!