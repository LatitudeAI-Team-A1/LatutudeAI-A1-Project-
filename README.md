**# Latitude_AI-A1-Project-
# Instance Segmentation for Autonomous Driving  
### Latitude AI Team 1A · Break Through Tech AI Studio

> AI Studio final project with **Latitude AI** exploring how autonomous vehicles can detect and segment objects in urban driving scenes.  

---

## Project Highlights

- Fine-tuned a **Mask R-CNN** instance segmentation model on the **BDD100K** dataset and evaluated cross-dataset generalization on **Cityscapes**.
- Built an end-to-end pipeline covering **data loading, preprocessing, training, evaluation, and visualization** for urban driving scenes.
- Achieved **strong detection performance** and met internal baselines on overall AP and training loss, while identifying a performance gap on **small objects** (e.g., distant pedestrians and traffic signs).
- Demonstrated that a BDD100K-trained model can **generalize reasonably to Cityscapes**, with clear qualitative examples and failure cases.
- Reduced **training latency** by optimizing data pipelines and training configuration, making rapid experimentation more feasible.

---

## Team Members

| Name              | GitHub Handle        | Contributions (high level)                                           |
|-------------------|----------------------|-----------------------------------------------------------------------|
| Aisling Greene    |  @AislingGreene      | Project coordination, modeling pipeline, visualization, README/docs   |
| Rebecca Forman    |   |                      |
| Saanvi Chougule   |   |                   |
| Joseph Boadi      |   |            |
| Juliana Prada     |   |          |
| Malk Khalifa      |   |                                  |
| Emmanuel Fanibi   |   |                 |

---

## Project Overview

### Objective & Scope

Our goal is to build and evaluate an **instance segmentation** system for autonomous driving that can:
1. Detect and segment key road objects (cars, buses, pedestrians, traffic lights, traffic signs, etc.).
2. Operate robustly across varied conditions (day/night, weather, geography).
3. Provide visual and quantitative evidence of performance and generalization across datasets.

We focus on:
- **Training** a model on **BDD100K**.
- **Evaluating** it on both BDD100K and **Cityscapes** to probe domain shift.
- **Documenting** model behavior through metrics, visualizations, and reflection on what worked and what did not.

### Motivation

Human drivers rely on a rich understanding of their surroundings—roads, vehicles, pedestrians, and infrastructure. Autonomous vehicles must replicate (and ideally exceed) this capability. Instance segmentation sits at the core of this perception stack, enabling:
- Precise separation of **individual objects** even when they overlap.
- Better **planning and safety** in dense and complex urban environments.
- More informative signals to downstream modules (tracking, prediction, planning).

### Business Relevance (Latitude AI)

This work directly supports business needs at **Latitude AI**, including: 
- **Accurate planning:** Fine-grained object masks improve handling of complex edge cases (e.g., occluded pedestrians, tight merges).
- **Operational efficiency:** A reusable instance segmentation pipeline accelerates model development and enables quantifiable optimization of perception systems.
- **Risk reduction:** Understanding where the model fails (e.g., small or distant objects) informs data collection and safety validation strategies.

---

## Repository Structure

├── README.md
├── environment.yml / requirements.txt   # Dependencies
├── data/
│   ├── bdd100k/                         # (Not checked in) raw & processed BDD100K
│   └── cityscapes/                      # (Not checked in) raw & processed Cityscapes
├── notebooks/
│   ├── 01_eda.ipynb                     # Exploratory data analysis & visualizations
│   ├── 02_train_maskrcnn.ipynb          # Main training notebook
│   └── 03_evaluation_and_viz.ipynb      # Metrics, tables, qualitative visuals
├── src/
│   ├── datasets/
│   │   ├── bdd100k_dataset.py           # Custom Dataset + transforms
│   │   └── cityscapes_dataset.py        # Dataset wrapper for generalization tests
│   ├── models/
│   │   └── maskrcnn_bdd.py              # Model construction / head replacement
│   ├── engine/
│   │   └── train_eval_loop.py           # Training & evaluation loops
│   └── utils/
│       ├── config.py                    # Hyperparameters, paths
│       ├── visualization.py             # Mask/bbox plotting helpers
│       └── metrics.py                   # AP computation helpers / wrappers
├── docs/
│   ├── figures/
│   │   ├── class_distribution.png
│   │   ├── env_time_of_day_heatmap.png
│   │   ├── quantitative_results.png
│   │   └── qualitative_examples.png
│   └── ai_studio_slides.pdf             # Slide deck export (this project)
└── LICENSE
**
