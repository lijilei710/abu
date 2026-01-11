# AbuQuant AI Agent Coding Guide

## 项目结构与核心模块
- **abupy/**：主量化系统代码，包含策略、回测、数据、指标、交易等核心模块。各子目录如 `AlphaBu/`、`BetaBu/`、`CoreBu/` 等分别实现不同的量化功能。
- **abupy_lecture/**：Jupyter Notebook 教程，演示策略开发、回测、机器学习等典型用法。
- **abupy_ui/**：非编程用户的图形界面操作工具，含交互式小部件和演示脚本。
- **ipython/**、**python/**：章节化的 Notebook 示例，配合文档讲解量化分析流程。

## 主要开发与运行流程
- 推荐在 Jupyter Notebook 环境下开发和测试策略，便于交互和可视化。
- 典型工作流：在 `abupy_lecture/` 选择对应主题的 Notebook，按章节逐步运行和修改代码。
- 量化主逻辑和可复用组件集中在 `abupy/`，如需扩展新策略或指标，建议在对应子目录下新建模块。
- 图形界面相关开发请参考 `abupy_ui/`，所有 UI 交互均通过 widget 脚本实现。

## 约定与风格
- 各子模块以 `Bu` 结尾（如 `AlphaBu`、`CoreBu`），代表“部件”或“模块”，便于分层管理。
- 策略、因子、指标等均以面向对象方式实现，便于组合和扩展。
- 数据、回测、交易等流程通过统一接口调用，跨模块通信以参数和对象传递为主。
- 代码注释和文档多为中文，变量名以英文为主，遵循 Python 常规命名。

## 依赖与集成
- 依赖通过 `requirements.txt` 管理，核心依赖为 numpy、pandas、matplotlib、scikit-learn 等。
- 外部数据源和行情接口在 `CrawlBu/`、`RomDataBu/` 等子模块实现，需按需配置。
- 机器学习相关内容集中在 `MLBu/`，与主回测框架解耦。

## 关键文件/目录举例
- `abupy/CoreBu/abupy_core.py`：主流程与核心接口
- `abupy/FactorBuyBu/`、`abupy/FactorSellBu/`：买入/卖出因子实现
- `abupy/IndicatorBu/`：技术指标实现
- `abupy_ui/widget_loop_back.py`：回测界面交互逻辑
- `abupy_lecture/` 下各 Notebook：实战演示与教学

## 其他说明
- 详细操作视频见 `界面操作视频教程/`。
- 代码示例与文档紧密结合，建议先阅读 Notebook 再查阅源码。
- 贡献新模块时请保持 `Bu` 命名风格和分层结构。

---
如有不清楚或遗漏之处，请反馈以便持续完善本说明。