# ComfyUI

基于节点的 Stable Diffusion 可视化工作流编辑器。

本仓库 fork 自 [comfyanonymous/ComfyUI](https://github.com/comfyanonymous/ComfyUI)，添加了托盘启动功能。

## 环境配置

### 前置条件

- Windows 10/11
- Python 3.10+（推荐使用 Miniconda）
- AMD 显卡（使用 DirectML）

### 安装步骤

1. **创建 Conda 环境**

```bash
conda create -n ComfyUI python=3.10 -y
conda activate ComfyUI
```

2. **安装 PyTorch（AMD DirectML）**

```bash
pip install torch-directml
pip install torchvision torchaudio
```

3. **安装依赖**

```bash
pip install -r requirements.txt
```

4. **安装托盘程序依赖**

```bash
pip install pystray pillow
```

## 启动方式

### 托盘启动（推荐）

运行 `Start_ComfyUI_Tray.bat`，程序将在后台运行，任务栏显示托盘图标。

- **双击图标**：打开浏览器访问 ComfyUI
- **右键菜单**：打开 ComfyUI / 重启服务 / 退出

### 命令行启动

```bash
conda activate ComfyUI
python main.py --directml --listen 0.0.0.0 --port 8188
```

## 开机自启动

将 `Start_ComfyUI_Tray.bat` 的快捷方式放到：

```
%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup
```

## 模型目录

| 类型 | 目录 |
|------|------|
| Checkpoint | `models/checkpoints` |
| VAE | `models/vae` |
| LoRA | `models/loras` |
| ControlNet | `models/controlnet` |
| Embeddings | `models/embeddings` |

## 访问地址

启动后访问：http://localhost:8188

## 参考

- [ComfyUI 官方仓库](https://github.com/comfyanonymous/ComfyUI)
- [ComfyUI 示例](https://comfyanonymous.github.io/ComfyUI_examples/)
- [ComfyUI 文档](https://docs.comfy.org/)
