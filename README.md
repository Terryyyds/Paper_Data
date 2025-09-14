# ZTA Survey Dada Analysis

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 项目概述 | Project Overview

本项目是一个关于零信任架构（Zero Trust Architecture, ZTA）采用情况的综合调查研究分析。通过问卷调查收集数据，运用多种统计分析方法，深入探讨组织对ZTA的认知、态度和采用行为。此 Notebook 存储了论文数据，包含数据清洗、可靠性分析（克朗巴赫α系数）、探索性因子分析（EFA）、描述性统计、相关性分析及方差/卡方分析的完整工作流程与结果。

This project is a comprehensive survey research analysis on Zero Trust Architecture (ZTA) adoption. Through questionnaire data collection and various statistical analysis methods, it explores organizations' cognition, attitudes, and adoption behaviors towards ZTA. This is a notebook storing ZTA thesis data, containing the complete workflow and results for data cleaning, reliability analysis (Cronbach's Alpha), EFA, descriptive statistics, correlation, and variance/chi-square analysis.


## 项目结构 | Project Structure

```
Paper_Data/
├── README.md                          # 项目说明文档
├── ZTA_Analysis.ipynb                 # 主要分析Notebook（原始版本）
├── ZTA_Analysis_executed.ipynb        # 已执行的分析Notebook
├── Cleaned Data-5.20.xlsx             # 清洗后的原始数据
├── Python/                            # Python脚本目录
└── analysis_outputs/                  # 分析结果输出目录
    ├── cleaned_dataset.csv            # 清洗后的数据集
    ├── cronbach_alpha.csv             # 信度分析结果
    ├── efa_summary.json               # 因子分析摘要
    ├── correlation_core.csv           # 相关分析结果
    ├── logit_adopt.txt                # 逻辑回归结果
    ├── mca_Q3_3_*.csv                 # MCA分析结果
    ├── chisq_*.csv                    # 卡方检验结果
    ├── freq_*.csv                     # 频数分析结果
    ├── anova_*.txt                    # ANOVA分析结果
    └── *.png                          # 可视化图表
```
## 研究目标 | Research Objectives

- Analyze organizations' familiarity and awareness levels with Zero Trust Architecture
- Assess organizations' perception of ZTA necessity
- Investigate satisfaction with current security solutions
- Explore relationships between organizational size, industry type, and ZTA adoption
- Identify key factors influencing ZTA adoption

## 数据来源 | Data Source

- **Sample Size**: 64 organizations
- **Data Format**: Excel format (Cleaned Data-5.20.xlsx)
- **Data Collection**: Online questionnaire survey via Qualtrics platform
- **Data Cleaning**: Automated data preprocessing and standardization

## 分析方法 | Analysis Methods

### 1. 数据预处理 | Data Preprocessing
- 缺失值标准化处理
- Likert量表（1-7）和Yes/No问题的自动识别与重编码
- 数据质量检查和清洗报告

### 2. 描述性统计 | Descriptive Statistics
- 人口统计学特征分析
- 组织规模分布（<50, 50-250, 251-500, >500人）
- 行业类型分布（教育、能源、金融、医疗等）
- 核心变量的频数分析

### 3. 信度分析 | Reliability Analysis
- Cronbach's Alpha系数计算
- 量表内部一致性检验

### 4. 探索性因子分析 | Exploratory Factor Analysis (EFA)
- KMO和Bartlett球形度检验
- 主成分分析
- 因子载荷矩阵

### 5. 相关分析 | Correlation Analysis
- ZTA熟悉度、必要性感知、满意度之间的Pearson相关分析
- 散点图矩阵可视化

### 6. 假设检验 | Hypothesis Testing
- **ANOVA**: 不同采纳状态下的组间差异分析
- **卡方检验**: 组织规模、行业类型与ZTA采用的关系

### 7. 回归分析 | Regression Analysis
- **逻辑回归**: 预测ZTA采用概率
- 模型：`adopt_zta ~ 熟悉度 + 必要性 + 满意度 + 规模 + 行业`

### 8. 多重对应分析 | Multiple Correspondence Analysis (MCA)
- 基于多选题数据的降维分析
- 选项共现模式分析

## 结果文件说明 | Output Files Description

| 文件名 | 描述 | Description |
|--------|------|-------------|
| `cleaned_dataset.csv` | 清洗后的完整数据集 | Complete cleaned dataset |
| `cronbach_alpha.csv` | 信度分析结果 | Reliability analysis results |
| `correlation_core.csv` | 核心变量相关矩阵 | Core variables correlation matrix |
| `logit_adopt.txt` | 逻辑回归模型结果 | Logistic regression model results |
| `mca_Q3_3_*.csv` | 多重对应分析结果 | Multiple correspondence analysis results |
| `chisq_*.csv` | 卡方检验交叉表 | Chi-square test contingency tables |
| `freq_*.csv` | 各变量频数分布 | Frequency distributions for variables |
| `anova_*.txt` | ANOVA分析结果 | ANOVA analysis results |
| `*.png` | 可视化图表 | Visualization charts |

## 技术栈 | Technology Stack

- **Python 3.11+**: 主要编程语言
- **Jupyter Notebook**: 交互式数据分析环境
- **Pandas**: 数据处理和分析
- **NumPy**: 数值计算
- **Scipy**: 统计分析和科学计算
- **Scikit-learn**: 机器学习工具
- **Statsmodels**: 统计建模
- **Factor Analyzer**: 因子分析
- **Prince**: 多重对应分析
- **Matplotlib/Seaborn**: 数据可视化
- **Pingouin**: 高级统计分析

## 安装和运行 | Installation and Running

### 环境要求 | Requirements
```bash
pip install pandas numpy scipy scikit-learn statsmodels
pip install factor-analyzer prince pingouin
pip install matplotlib seaborn jupyter
pip install openpyxl  # Excel文件支持
```

### 运行分析 | Running Analysis
```bash
# 启动Jupyter Notebook
jupyter notebook

# 或直接运行已执行的版本
jupyter notebook ZTA_Analysis_executed.ipynb
```

