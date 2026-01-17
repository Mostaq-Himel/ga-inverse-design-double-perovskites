Genetic Algorithm–Based Inverse Design of Double Perovskite Oxides
Targeting Solar-Relevant Band Gaps Using DFT-Informed Machine Learning
📌 Overview
This project presents a data-driven inverse materials design framework for discovering double perovskite oxides (A₂BB′O₆) with target electronic band gaps suitable for photovoltaic and energy-related applications.
The workflow integrates machine learning (ML) as a fast surrogate model with a genetic algorithm (GA) to efficiently explore large compositional spaces. First-principles DFT calculations (VASP) are used to validate the most promising candidates, ensuring physical reliability and thermodynamic stability.
The methodology significantly reduces the number of expensive DFT calculations while maintaining predictive accuracy, making it suitable for resource-efficient materials discovery.
🎯 Research Objectives
    • Inverse-design double perovskite oxides with target band gaps (1.2–2.0 eV)
    • Ensure thermodynamic stability using formation energy constraints
    • Minimize DFT cost using ML-guided genetic optimization
    • Identify photovoltaic-relevant, lead-free oxide candidates
    • Demonstrate a scalable inverse design pipeline for functional materials
      
🧠 Methodology Overview
1️⃣ Data Collection (DFT-Informed)
    • Precomputed DFT data from Materials Project / OQMD
    • Extracted properties:
        ◦ Band gap (Eg)
        ◦ Formation energy
        ◦ Crystal structures (CIF)
2️⃣ Feature Engineering
    • Composition-based descriptors using matminer
    • Includes:
        ◦ Ionic radii
        ◦ Electronegativity
        ◦ Valence electron count
        ◦ Tolerance and octahedral factors (adapted for double perovskites)
3️⃣ Machine Learning (Forward Models)
    • ML models trained to predict:
        ◦ Band gap
        ◦ Formation energy
    • Algorithms:
        ◦ Random Forest
        ◦ Gradient Boosting (baseline)
    • Models serve as surrogate evaluators inside GA
4️⃣ Genetic Algorithm (Inverse Design Core)
    • Chromosome encoding: [A, B, B′]
    • Fitness function:
        ◦ Penalizes deviation from target Eg
        ◦ Penalizes thermodynamic instability
    • GA operations:
        ◦ Selection
        ◦ Crossover (B/B′ site exchange)
        ◦ Mutation (element substitution)
5️⃣ DFT Validation (VASP)
    • Top 3–10 GA-identified candidates
    • Geometry optimization and band gap calculation
    • Comparison between ML predictions and DFT results
6️⃣ Optional Extensions
    • Active learning loop (ML retraining with new DFT data)
    • Simulated XRD patterns for phase validation
    • Extension to photocatalytic or optoelectronic targets
🔬 Why Double Perovskite Oxides?
    • Structural flexibility (A₂BB′O₆)
    • Wide band gap tunability
    • Lead-free alternatives for solar applications
    • Strong relevance in:
        ◦ Photovoltaics
        ◦ Photocatalysis
        ◦ Energy electronics

📁 Repository Structure
├── data/
│   ├── raw/                # MP / OQMD extracted data
│   ├── processed/          # Cleaned datasets
│
├── features/
│   └── featurization.py    # Descriptor generation
│
├── ml_models/
│   ├── train_bandgap.py
│   └── train_stability.py
│
├── ga/
│   ├── genetic_algorithm.py
│   └── fitness_function.py
│
├── dft_validation/
│   ├── cif_files/
│   └── vasp_inputs/
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_ml_training.ipynb
│   └── 03_ga_inverse_design.ipynb
│
├── results/
│   ├── ga_convergence_plots/
│   └── candidate_materials.csv
│
└── README.md
⚙️ Requirements
Python Libraries
    • pymatgen
    • matminer
    • scikit-learn
    • numpy
    • pandas
    • matplotlib
DFT Software
    • VASP (for validation stage)
    • Access to local machine or HPC recommended
🚀 How to Run
    1. Extract DFT data from Materials Project
    2. Generate descriptors using matminer
    3. Train ML surrogate models
    4. Run GA to inverse-design candidate materials
    5. Validate top candidates using DFT (VASP)
    6. (Optional) Retrain ML and repeat GA (active learning)
📊 Key Outputs
    • ML model performance metrics (MAE, R²)
    • GA convergence behavior
    • Predicted vs DFT-validated band gaps
    • List of stable, solar-relevant double perovskite oxides
🧪 Scientific Contribution
    • Demonstrates inverse design beyond forward ML prediction
    • Shows DFT-efficient optimization using GA
    • Bridges materials science, machine learning, and optimization
📖 Potential Applications
    • Photovoltaic absorbers
    • Photocatalysts
    • Energy-efficient oxide electronics
    • Lead-free functional materials discovery
📌 Citation
If you use this work, please cite or acknowledge this repository.
📬 Contact
For questions, collaboration, or academic discussion, feel free to reach out.

