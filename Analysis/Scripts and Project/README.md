# README — Template 
# ---------------------------------------------------------------

## 1. Project Overview
```text
Insert a brief description of the project here.
```

## 2. Project Structure
```text
Analysis/
├── Data/
├── Figures/
├── Scripts and Project/
    ├── package_citations.bib
    ├── Quarto_template.qmd
    ├── README.md
    ├── renv/
    ├── renv.lock
    ├── Project.Rproj
    ├── setup.R
├── Tables/
```

## 3. Reproducibility Instructions
To reproduce the analysis:

1. Clone the repository:
```bash
git clone https://github.com/...
```
or download the ZIP file from the repository.

2. Install the required R packages:

Restore the R environment using renv::restore() and load packages (in setup.R) 

All package versions are recorded in renv.lock.


## 4. Data Documentation
```text
Insert a brief description of where the Data comes from, variables and structures. A codebook for larger datasets can be very helpful.
```
## 5. Included Analyses
```text
Insert a brief description of the analysis.
```

## 6. License
```text
This project is licensed under the MIT License. You are free to use, share, and adapt this code with appropriate attribution.  
For more details, see the https://opensource.org/licenses/MIT
```

## 7. Acknowledgments
```text
This project relies on the following R packages: insert packages from package_citations.txt
```
