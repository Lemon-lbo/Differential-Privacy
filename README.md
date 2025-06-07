# Differential Privacy on US Broadband Demographics

## Project Description

This project explores the application of Differential Privacy (DP) to the US Broadband Internet Demographics dataset. The dataset contains sensitive information such as household income, disabilities, and opinions on censorship, making it a prime candidate for privacy-preserving techniques.

The project focuses on protecting individual-level categorical data using randomized response under various privacy budgets (ε). It evaluates how the level of differential privacy affects the accuracy and distribution of protected variables compared to the original data.

## What is Differential Privacy?

Differential Privacy is a formal mathematical framework that provides strong privacy guarantees while allowing useful statistical analysis. It ensures that the inclusion or exclusion of a single individual's data does not significantly affect the output of any analysis, thereby protecting privacy.

### Key Principle:

A mechanism satisfies ε-differential privacy if, for all datasets differing in one record and for all outputs, the probability of any output changes by at most a factor of e^ε.

### Mechanism Used: Randomized Response

- Truth reported with probability:  
  **p = e^ε / (e^ε + k - 1)**  
- Random value reported with probability:  
  **q = 1 / (e^ε + k - 1)**

This mechanism provides plausible deniability to participants while preserving aggregate-level patterns.

## Dataset

- **Name**: [US Broadband Internet Demographics (1997)](https://archive.ics.uci.edu/dataset/126/internet+usage+data) 
- **Source**: Graphics and Visualization Unit, Georgia Tech  
- **Attributes**: 71 (after preprocessing), including demographics, internet usage patterns, and opinions.

## Data Preprocessing
Preprocessed the dataset and categorized attributes based on their role:
Personally Identifiable Information (PII), Quasi-Identifiers (QI), Sensitive Attributes (SA), and Non-Sensitive Attributes (NSA).

This step was crucial because the dataset was not rectangular by default:
- Column names were stored in a separate metadata file.
- Data rows had inconsistent lengths due to missing or extra values.
- Some rows had to be filtered based on column count (e.g., 71 vs. 72).
- The dataset included a unique ID column which was dropped for privacy.

## Experiments

- Applied DP to 11 sensitive attributes under multiple ε values.
- Visualized distributional changes for each attribute.
- Observed that as ε increases, the perturbed distribution converges to the original.
- Quantified utility loss through accuracy metrics and divergence plots.

## Conclusion

The project demonstrates how randomized response can be a simple yet effective method to achieve differential privacy for categorical data. Proper tuning of ε and handling of high-cardinality features are key to balancing privacy and utility.

## Repository Structure

- `Differential_Privacy.pdf` — Final presentation slides summarizing the project
- `DP_Slides/` — Folder containing LaTeX source files and figures used to generate the slides
- `DP_US_dashboard_project.ipynb` — Google Colab notebook containing the full project workflow:
  - Data preprocessing
  - Attribute categorization (PII, QI, SA, NSA)
  - Differential Privacy implementation using randomized response
  - Visualizations and analysis across varying privacy budgets (ε)


## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## Completion Date
This project was originally completed in May 2025.

