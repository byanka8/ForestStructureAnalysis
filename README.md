# ForestStructureAnalysis
ML-based forest structure analysis and classification with Random Forest, Decision Tree, and KNN. Created using Google Colab Notebook.

## Overview
The dataset contains information on tree inventory, height, diameter at breast height (DBH), and crown measurements from 30 plots in the Tapajos National Forest, Para, Brazil, collected in September 2010. The plots are categorized into primary forests, selectively logged primary forests, and secondary forests with varying ages and disturbance histories. Out of the 50 x 50-meter plots, eight were in primary forests, eight in logged primary forests, and fourteen in secondary forests. Trees with a diameter of 5 cm or more in early successional stands and 10 cm or more in other stands were measured and identified. DBH was measured to the nearest 0.1 cm, while heights and crown depths were visually estimated using a laser rangefinder. Crown radius was measured in two directions. The Tapajos National Forest is located about 50 km south of Santarem, Pará, along highway BR-163. The study utilizes a comma-separated (.csv) file containing the inventory and biometric measurements of trees.

## Dataset
- Dataset: [Tree Inventory and Biometry Measurements, Tapajos National Forest, Para, Brazil, 2010](https://daac.ornl.gov/VEGETATION/guides/Forest_Inventory_Tapajos.html)
- File name: Tapajos_inventory_data_2010.csv
- Description: Contains tree height, diameter, density, wood density, species composition, and geographic information  
- Key preprocessing steps: 
  - Handling Missing Values
  - Remove Duplicates
  - Feature Selection

## Features / Exploratory Analysis
* *Numerical Distributions:* Histograms revealed that many numerical features, including dbh and ht_total, exhibit right-skewed distributions, typical of forest structures with many small and fewer large trees. density_wood showed a more symmetrical distribution.

* *Categorical Distributions:* Bar plots highlighted that Secondary Forests (SF) represent the majority class in the dataset, indicating an imbalance. The origin analysis showed a prevalence of the "SW" origin point. The plots also identified the most abundant tree families, genera, and species, revealing differences in taxonomic composition across the forest types.

* *Tree Height and Diameter:* Analysis of ht_total and dbh showed that trees in PF and SLF generally have larger heights and diameters with higher variability compared to trees in SF, which are typically smaller and more uniform.

* *Tree Density:* Secondary Forests (SF) displayed the highest average tree density per plot and the greatest variability in density, while PF and SLF had lower, less variable densities.

* *Species Richness:* Selectively Logged Forests (SLF) and Primary Forests (PF) showed slightly higher species richness (number of unique species) compared to Secondary Forests (SF).

* *Family Composition:* The relative abundance of tree families differed across forest types. SF had a higher proportion of certain families like Salicaceae and Urticaceae, whereas PF and SLF had a higher proportion of families like Sapotaceae and Burseraceae.

* *Wood Density:* Trees in PF and SLF exhibited higher average wood densities than those in SF.
  
## Results
Three classification models (Decision Tree, Random Forest, and k-Nearest Neighbors) were trained to predict forest type.

* *Decision Tree:* Achieved 77% accuracy, performing well on SF but struggling with PF and SLF classification. dbh and origin_NE were identified as most important features.

* *Random Forest:* Showed improved performance with 84% accuracy, classifying all three forest types more effectively than the Decision Tree. dbh remained a key feature, along with various tree dimension and origin features.

* *k-Nearest Neighbors (KNN):* Achieved 80% accuracy, performing well on SF but showing limitations in classifying SLF, which was often misclassified as SF. Permutation importance highlighted origin_NE and origin_SW as highly important features.
