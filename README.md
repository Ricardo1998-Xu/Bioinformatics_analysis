# Bioinformatics_analysis

Bioinformatics software defect analysis：Are we there yet?

## 主要文件

1. Bioinformatics Software
    * C++：基于C/C++开发的生信软件源代码
    * Python：基于Python开发的生信软件源代码
    * R：基于R开发的生信软件源代码
2. Report
    * C++：SonarQube导出的基于C/C++的生信软件缺陷问题及指标
    * Python：SonarQube导出的基于Python的生信软件缺陷问题及指标
    * R：SonarQube导出的基于R的生信软件缺陷问题及指标
3. Figure
    * 分析的结果图
4. Code
    * C++：sonar-cxx-plugin-2.1.3.850.jar
    * R：sonarR包

## Usage
### R-based
更多详细信息参考：
* https://github.com/paulospx/sonarR/tree/main

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

4. 在 R 控制台或 RStudio 中启动 R，并切换至sonarR目录。

   ```R
   setwd("sonarR")
   ```
   
5. 加载 sonarR 包。

   ```R
   devtools::load_all(".")
   ```

6. Run the scanner on your R project directory. The tool will scan your R code in the `Bioinformatics Software/R/cellTree` folder and generate a JSON report named `result.json`.

   ```R
   sonarR::sonarScan(dir="Bioinformatics Software/R/cellTree",outFile = "result.json")
   ```

7. 通过`Code/sonarR/R/updated_result.json`文件修改`result.json`格式，使其能够被SonarQube读取。
   * Linting Rules: 
      -  https://lintr.r-lib.org/reference/linters.html
   * JSON
      - https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/importing-external-issues/generic-issue-import-format/


### Python-based

更多详细信息参考：
* https://github.com/SonarSource/sonarqube

1. 安装SonarQube和Sonar Scanner
   * 前往 SonarQube 官方网站下载社区版或其他适合您需求的版本。
   * https://www.sonarsource.com/zh/products/sonarqube/

2. 启动SonarQube
   * 进入解压目录并启动服务：
     ```
     cd sonarqube-<version>/bin/<your-os>
      ./sonar.sh start
     ```
   * 默认 SonarQube 服务会运行在 http://localhost:9000。
3. 创建项目
   * 点击 Projects > Create Project
   * 输入项目名称和密钥，例如`python_project`。

4. 生成令牌
   * 点击Generate Token 并保存令牌（例如 sqa_123）。

5. 扫描代码
   * 打开本地终端并进入项目目录
   * 运行类似以下命令启动扫描：
      ```
      sonar-scanner.bat -D"sonar.projectKey=A123" -D"sonar.sources=." -D"sonar.host.url=http://localhost:9000" -D"sonar.token=sqa_123"
      ```
      注意将sonar.projectKey 替换为您的项目密钥，sonar.token 替换为您的令牌。


### C/C++-based

更多详细信息参考：
* https://github.com/SonarOpenCommunity/sonar-cxx/tree/master

1. 安装SonarQube和Sonar Scanner
   * 前往 SonarQube 官方网站下载社区版或其他适合您需求的版本。
   * https://www.sonarsource.com/zh/products/sonarqube/
2. 加载插件
   * 将`Code/C++/sonar-cxx-plugin-2.1.3.850.jar`文件移动至SonarQube中的`extensions/plugins/`目录下
3. 启动SonarQube
   * 进入解压目录并启动服务：
     ```
     cd sonarqube-<version>/bin/<your-os>
      ./sonar.sh start
     ```
   * 默认 SonarQube 服务会运行在 http://localhost:9000。
4. 创建项目
   * 点击 Projects > Create Project
   * 输入项目名称和密钥，例如`project`。

5. 生成令牌
   * 点击Generate Token 并保存令牌（例如 sqa_123）。

6. 扫描代码
   * 打开本地终端并进入项目目录
   * 运行类似以下命令启动扫描：
      ```
      sonar-scanner.bat -D"sonar.projectKey=A123" -D"sonar.sources=." -D"sonar.host.url=http://localhost:9000" -D"sonar.token=sqa_123"
      ```
      注意将sonar.projectKey 替换为您的项目密钥，sonar.token 替换为您的令牌。
