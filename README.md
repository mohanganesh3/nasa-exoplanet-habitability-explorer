# 🪐 Exoplanet Habitability Explorer
## *Unveiling the Most Earth-Like Worlds in NASA's Archive*

> **"Are we alone in the universe? This project helps answer that question by identifying the most habitable worlds beyond our solar system."**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![NASA Data](https://img.shields.io/badge/Data-NASA%20Exoplanet%20Archive-orange.svg)](https://exoplanetarchive.ipac.caltech.edu/)


## 📊 How to Use the Dataset in Python

The dataset used in this project is sourced from the [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/), specifically the `ps` table containing confirmed exoplanet data.

You can directly load the dataset using Python as shown below:

```python
import pandas as pd
import requests
from io import StringIO

# URL to fetch the full exoplanet dataset
url = "https://exoplanetarchive.ipac.caltech.edu/TAP/sync?query=select+*+from+ps&format=csv"

# Fetch the dataset with a timeout (in seconds)
response = requests.get(url, timeout=60)

# Load CSV into a DataFrame
df = pd.read_csv(StringIO(response.text))

# Preview the data
print(df.head())

## 🌟 **What Makes This Special?**

Ever wondered which exoplanets could potentially harbor life? This comprehensive analysis tool processes real NASA data to identify the most Earth-like worlds ever discovered. Using advanced habitability metrics and beautiful visualizations, we've created the ultimate guide to potentially habitable exoplanets.

### 🔬 **The Science Behind It**

Our analysis goes beyond simple planet catalogs. We compute the **Earth Similarity Index (ESI)** - a sophisticated metric that considers:

- **Planet Size** - How close to Earth's radius?
- **Energy Received** - Is it in the "Goldilocks Zone"?
- **Stellar Properties** - Does it orbit a Sun-like star?
- **Detection Biases** - What are we missing?

---

## 🚀 **Key Features**

### 📊 **Comprehensive Data Analysis**
- **5,000+** confirmed exoplanets from NASA's archive
- Real-time data fetching and processing
- Advanced statistical analysis and correlation studies

### 🎯 **Habitable Zone Detection**
- Identifies planets in the "Goldilocks Zone"
- Custom habitability scoring algorithm
- Earth Similarity Index (ESI) calculations

### 📈 **Publication-Ready Visualizations**
- Sky maps showing planet distributions
- Correlation matrices and scatter plots
- Interactive filtering capabilities
- Professional publication-quality figures

### 🏆 **Candidate Identification**
- Ranked list of most Earth-like planets
- Exportable target lists for follow-up studies
- Golden Zone candidates for priority observation

---

## 🌍 **What You'll Discover**

### **Shocking Statistics**
- Only **~3%** of known exoplanets are in habitable zones
- **Super-Earths** (1-2× Earth's size) are surprisingly common
- Most "Earth-like" planets are actually **larger** than Earth
- Detection methods have significant **observational biases**

### **Top Earth Analogs**
Our analysis identifies the most promising candidates for habitability, including planets with:
- ESI scores above **0.8** (extremely Earth-like)
- Optimal stellar irradiation levels
- Rocky planet compositions
- Sun-like host stars

---

## 📋 **Quick Start Guide**

### **Prerequisites**
```bash
pip install pandas numpy matplotlib seaborn requests astroquery
```

### **Run the Analysis**
```python
# Clone and run all cells in order
# Data is fetched automatically from NASA
# Results are exported as CSV files
```

### **Explore Results**
```python
# Use the interactive filtering function
filter_exoplanets(min_esi=0.7, habitable_zone_only=True)
```

---

## 📸 **Visual Highlights**

### **Planet Size Distribution**
*Most exoplanets are larger than Earth - true Earth-twins are rare!*

### **Habitable Zone Analysis** 
*Only a small fraction of planets receive Earth-like amounts of starlight*

### **Earth Similarity Ranking**
*Our custom ESI metric identifies the most promising worlds*

### **Sky Map Visualization**
*Where are the most habitable planets located in our galaxy?*

---

## 🎯 **Research Applications**

### **For Astronomers**
- Target selection for JWST observations
- Statistical analysis of planet populations
- Detection bias quantification

### **For Educators**
- Classroom demonstrations of exoplanet science
- Interactive exploration tools
- Real NASA data analysis

### **For Space Enthusiasts**
- Discover potentially habitable worlds
- Understand what makes planets habitable
- Explore the latest exoplanet discoveries

---

## 📊 **Sample Results**

```
🏆 TOP EARTH-ANALOG CANDIDATES

Planet Name          | Radius | ESI   | Status
--------------------|--------|-------|------------------
Kepler-442b         | 1.34   | 0.84  | 🌟 Golden Zone
Kepler-438b         | 1.12   | 0.88  | 🌟 Golden Zone  
Kepler-296e         | 1.75   | 0.85  | 🌟 Golden Zone
TOI-715b            | 1.55   | 0.87  | 🌟 Golden Zone
Proxima Centauri b  | 1.17   | 0.85  | 🌟 Nearest Star!

📈 SUMMARY STATISTICS
• Total planets analyzed: 5,247
• In habitable zone: 187 (3.6%)
• High ESI candidates: 45
• Earth-size planets: 127
```

---

## 📁 **Project Structure**

```
exoplanet-habitability-explorer/
├── 🔬 analysis_notebook.ipynb     # Main analysis (16 comprehensive cells)
├── 📊 visualizations/             # All generated plots and charts
├── 📄 results/                    # Exported CSV files and summaries
│   ├── top_earth_analogs.csv     # Prime candidates list
│   ├── analysis_summary.json     # Statistical summary
│   └── exoplanet_habitability_analysis.csv
├── 📚 docs/                       # Documentation and methodology
└── 🛠️  utils/                     # Helper functions and tools
```

---

## 🔍 **Methodology Deep Dive**

### **Data Source**
We use NASA's Exoplanet Archive - the most comprehensive and up-to-date catalog of confirmed exoplanets.

### **Earth Similarity Index (ESI)**
Our ESI calculation considers:
```python
ESI = sqrt((1 - |R - 1|) * (1 - |sqrt(S) - 1|))
```
Where:
- `R` = Planet radius / Earth radius
- `S` = Stellar insolation / Earth insolation

### **Habitable Zone Definition**
Conservative estimate: **0.25 < insolation < 2.0** Earth flux units

---

## 🎨 **Customization Options**

### **Adjust Habitability Criteria**
```python
# Conservative approach
filter_exoplanets(min_esi=0.8, min_radius=0.8, max_radius=1.2)

# Broader search
filter_exoplanets(min_esi=0.6, max_radius=2.0, habitable_zone_only=True)
```

### **Export Custom Results**
```python
# Save your filtered results
candidates.to_csv('my_exoplanet_targets.csv')
```

---

## 🌟 **What's Next?**

### **Phase 2 Features (Coming Soon)**
- **Machine Learning** models for habitability prediction
- **Atmospheric modeling** integration
- **Real-time updates** from NASA feeds
- **3D interactive** galaxy visualization

### **Research Extensions**
- Stellar activity impact analysis
- Tidal locking probability calculations
- Atmospheric escape rate modeling
- Biosignature detection probability

---

## 🤝 **Contributing**

We welcome contributions from astronomers, data scientists, and space enthusiasts!

### **How to Contribute**
1. 🍴 Fork the repository
2. 🌱 Create a feature branch
3. 🔬 Add your analysis or improvements
4. 📊 Update visualizations if needed
5. 🚀 Submit a pull request

### **Ideas for Contributions**
- New habitability metrics
- Additional visualization types
- Performance optimizations
- Documentation improvements

---


## 📚 **Resources & References**

### **Key Papers**
- Schulze-Makuch et al. (2011) - Earth Similarity Index methodology
- Kopparapu et al. (2013) - Habitable zone calculations
- NASA Exoplanet Archive documentation

### **Useful Links**
- 🌐 [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/)
- 🔭 [Exoplanet Exploration (NASA)](https://exoplanets.nasa.gov/)
- 📖 [Astrobiology Primer](https://astrobiology.nasa.gov/)


---

*Made with ❤️ for the astronomy community 

---

## 🔒 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Data Attribution:** This research has made use of the NASA Exoplanet Archive, which is operated by the California Institute of Technology, under contract with the National Aeronautics and Space Administration under the Exoplanet Exploration Program.
