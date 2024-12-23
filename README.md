# Bioinformatics Analysis

**Bioinformatics Software Defect Analysis: Are we there yet?**

## Overview
This repository provides resources and tools for analyzing defects in bioinformatics software developed in C++, Python, and R. It includes source code, scanning methods, reports, and high-resolution figures for research purposes.

---

## Main Contents

### 1. Bioinformatics Software
- **C++**: Source code of bioinformatics software developed in C/C++.
- **Python**: Source code of bioinformatics software developed in Python.
- **R**: Source code of bioinformatics software developed in R.

### 2. Code
- **C++**: Plugins for C/C++ analysis.
- **R**: Methods for scanning R software source code.

### 3. Figure
- High-resolution figures used in the paper.

### 4. Report
- **C++**: Defect reports and metrics for C/C++ bioinformatics software exported from SonarQube.
- **Python**: Defect reports and metrics for Python bioinformatics software exported from SonarQube.
- **R**: Defect reports and metrics for R bioinformatics software exported from SonarQube.

### 5. Results.xlsx
- Detection results for bioinformatics software.

### 6. Developer's Information.xlsx
- Relevant information about software developers.

---

## Usage

### R-based Analysis

More details: [sonarR](https://github.com/paulospx/sonarR/tree/main)

1. Clone this repository or download the source code:

   ```bash
   git clone https://github.com/Ricardo1998-Xu/Bioinformatics_analysis.git
   ```

2. Navigate to the project directory:

   ```bash
   cd Code/sonarR
   ```

3. Install the required dependencies:

   ```bash
   Rscript -e 'install.packages("data.table")'
   Rscript -e 'install.packages("lintr")'
   Rscript -e 'install.packages("devtools")'
   Rscript -e 'install.packages("roxygen2")'
   ```

4. Start R in the terminal or RStudio and set the working directory to `sonarR`:

   ```R
   setwd("Code/sonarR")
   ```

5. Load the `sonarR` package:

   ```R
   devtools::load_all(".")
   ```

6. Run the scanner on your R project directory. The tool will scan your R code in the `Bioinformatics Software/R/cellTree` folder and generate a JSON report named `result.json`:

   ```R
   sonarR::sonarScan(dir="Bioinformatics Software/R/cellTree", outFile="result.json")
   ```

7. Modify the `result.json` file format to be compatible with SonarQube using the file at `Code/sonarR/R/updated_result.json`.
   - **Linting Rules**: [linters](https://lintr.r-lib.org/reference/linters.html)
   - **JSON**: [Generic Issue Import Format](https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/importing-external-issues/generic-issue-import-format/)

---

### Python-based Analysis

More details: [SonarSource SonarQube](https://github.com/SonarSource/sonarqube)

1. Install SonarQube and Sonar Scanner:
   - Download the community edition or a version suitable for your needs from the [SonarQube website](https://www.sonarsource.com/products/sonarqube/).

2. Start SonarQube:

   ```bash
   cd sonarqube-<version>/bin/<your-os>
   ./sonar.sh start
   ```

   The service will run at [http://localhost:9000](http://localhost:9000).

3. Create a Project:
   - Navigate to **Projects > Create Project**.
   - Enter a project name and key, e.g., `python_project`.

4. Generate a Token:
   - Click **Generate Token** and save it (e.g., `sqa_123`).

5. Scan the Code:
   - Open a terminal and navigate to the project directory.
   - Run the scanner:

     ```bash
     sonar-scanner.bat -D"sonar.projectKey=A123" -D"sonar.sources=." -D"sonar.host.url=http://localhost:9000" -D"sonar.token=sqa_123"
     ```

     Replace `sonar.projectKey` with your project key and `sonar.token` with your token.

---

### C/C++-based Analysis

More details: [Sonar C++ Plugin](https://github.com/SonarOpenCommunity/sonar-cxx/tree/master)

1. Install SonarQube and Sonar Scanner:
   - Download the community edition or a version suitable for your needs from the [SonarQube website](https://www.sonarsource.com/products/sonarqube/).

2. Load the Plugin:
   - Move the `Code/C++/sonar-cxx-plugin-2.1.3.850.jar` file to the `extensions/plugins/` directory in your SonarQube installation.

3. Start SonarQube:

   ```bash
   cd sonarqube-<version>/bin/<your-os>
   ./sonar.sh start
   ```

   The service will run at [http://localhost:9000](http://localhost:9000).

4. Create a Project:
   - Navigate to **Projects > Create Project**.
   - Enter a project name and key, e.g., `project`.

5. Generate a Token:
   - Click **Generate Token** and save it (e.g., `sqa_123`).

6. Scan the Code:
   - Open a terminal and navigate to the project directory.
   - Run the scanner:

     ```bash
     sonar-scanner.bat -D"sonar.projectKey=A123" -D"sonar.sources=." -D"sonar.host.url=http://localhost:9000" -D"sonar.token=sqa_123"
     ```

     Replace `sonar.projectKey` with your project key and `sonar.token` with your token.

---

## Versions Used
- **R**: 4.4.1
- **SonarQube**: 10.6.0.92116
- **C/C++ Plugin**: 2.1.3.850

---

## License
This project is licensed under the MIT License. See the [LICENSE](https://github.com/Ricardo1998-Xu/Bioinformatics_analysis/blob/main/LICENSE) file for details.
