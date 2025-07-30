# 项目概述
Async CosyVoice 项目用于加速 cosyvoice2 新版代码的推理过程，当前仅支持 Linux 系统，并且依赖 vllm 库。以下是该项目的主要特性：

LLM 推理加速：借助 vllm 对 LLM 部分的推理进行加速。

# 环境准备
请使用 Python 3.10.16+的 版本，按以下步骤创建并激活 Conda 环境：

conda create -n cosyvoice2 python=3.10.16 -y
conda activate cosyvoice2
# 使用步骤
1. 克隆 CosyVoice  tag 2.0的项目
git clone https://github.com/FunAudioLLM/CosyVoice.git
cd CosyVoice
git submodule update --init --recursive

# 安装系统依赖
1. conda install -y -c conda-forge pynini==2.1.5（arm架构需要按照这个指引https://zhuanlan.zhihu.com/p/28994837054先安装依赖）
sudo apt-get update
sudo apt-get install sox libsox-dev -y
2. 把本项目中的model.py,cosyvoice.py替换到/CosyVoice-main/cosyvoice/cli/中；把本项目中的llm.py替换到/CosyVoice-main/cosyvoice/llm/中

3. 安装依赖
进入 CosyVoice-main目录，安装所有依赖：

cd CosyVoice-main
pip install -r requirements.txt
4. 下载模型文件
从 https://modelscope.cn/models/iic/CosyVoice2-0.5B 下载 CosyVoice2 - 0.5B 模型文件，并将其保存至 CosyVoice/pretrained_models 目录。


本项目使用的是 vllm == 0.9.0，并开启了 VLLM_USE_V1 = '1'。
