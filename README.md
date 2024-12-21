# Bioinformatics_analysis

Bioinformatics software defect analysis：Are we there yet?

## 主要文件

1. Bioinformatics Software
    * C++：放置基于C/C++开发的生信软件源代码
    * Python：放置基于Python开发的生信软件源代码
    * R：放置基于R开发的生信软件源代码
2. Report
    * C++：放置SonarQube导出的基于C/C++的生信软件缺陷问题及指标
    * Python：放置SonarQube导出的基于Python的生信软件缺陷问题及指标
    * R：放置SonarQube导出的基于R的生信软件缺陷问题及指标
3. Figure
    * 分析的结果图
4. Code
    * C++：插件
    * R：sonarR包

## Usage
### R
1. Clone this repository or download the source code.

   ```bash
   git clone https://github.com/paulospx/sonarR.git
   ```

2. Navigate to the project directory.

   ```bash
   cd sonarR
   ```

3. Install the required dependencies.

   ```bash
   Rscript -e 'install.packages("data.table")'
   Rscript -e 'install.packages("lintr")'
   Rscript -e 'install.packages("devtools")'
   Rscript -e 'install.packages("roxygen2")'
   ```
   
4. 在 R 控制台或 RStudio 中启动 R，并加载 sonarR 包。

   ```R
   devtools::load_all(".")
   ```
