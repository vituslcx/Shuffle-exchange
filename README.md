# 代码结构说明

本仓库基于 DeepSpeed 源码进行修改，核心改动主要集中在以下几个位置：

```text
deepspeed/
├── runtime/
│   ├── engine.py
│   └── zero/
│       └── stage_1_and_2.py
├── __init__.py
└── ...
```

其中：

* `deepspeed/runtime/zero/stage_1_and_2.py`
  为本仓库的主要算法修改位置，核心同步逻辑在此实现。

* `deepspeed/runtime/engine.py`
  对训练引擎进行了相应适配，使其能够支持修改后的同步流程。

* `deepspeed/__init__.py`
  对初始化接口进行了调整，用于暴露或传递新增的配置参数。

---


# 安装说明

建议在独立 Python 环境中安装本仓库，并使用源码 editable 模式，便于后续继续调试和修改。

## 1. 克隆仓库

```bash
git clone https://github.com/vituslcx/Shuffle-exchange
cd Shuffle-exchange
```

## 2. 安装依赖环境

请确保当前环境中已具备以下基础组件：

* Python
* PyTorch
* CUDA
* NCCL
* 与当前 DeepSpeed 版本兼容的其他依赖

## 3. 源码安装

```bash
pip install -e .
```

安装完成后，代码修改通常可以直接在当前源码目录下生效，适合继续开发和调试。
