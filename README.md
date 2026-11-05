# 第 07 课作业

## 作业 01：观察 MNIST 图片与标签

打开 `01_mnist_images_and_labels.ipynb`，从上到下运行：下载 MNIST，观察数字 0、3、7 的图片及完整 28×28 原始像素矩阵，比较整数标签与 one-hot 向量，并填写末尾的观察题。

沿用课程 Python 环境，需要 `torch`、`torchvision`、`notebook` 和 `ipykernel`。图片显示使用 Pillow（torchvision 的依赖），无需额外安装 matplotlib；本题只使用 CPU。打开 Notebook 后选择对应环境的内核。已有可用环境不需要重新安装 PyTorch。

在本文件夹启动 Jupyter，例如：

```bash
conda activate cv_class
python -m notebook
```

首次运行需要网络，MNIST 自动下载到 `data/`；如果下载中断，网络恢复后重新运行下载单元格。后续运行复用缓存。

填写观察题，重启内核并运行所有单元格，保存 Notebook 和输出后提交。不要提交 `data/`、虚拟环境、训练产物或 `.ipynb_checkpoints/`；这些目录已在 `.gitignore` 中排除。

## 作业 02：替换 CNN，提升 MNIST 准确率

打开 `02_mnist_cnn_improvement.ipynb`。先使用默认的 `MODEL_CHOICE = "baseline"` 跑通完整模板，记录基础模型的测试 accuracy。然后在网上寻找一个更强的 CNN，在空白代码单元格中实现 `predict_better()`，将开关改成 `"better"`，重启内核并运行全部单元格。

两个模型函数都返回一个新建的 `torch.nn.Module`。训练、loss 曲线与测试使用同一套代码；先保持相同的训练参数比较结构，再单独记录其他调参实验。提交来源链接、结构说明、两个模型的 accuracy 对比，以及改进模型运行后的曲线和结果。

本题仍使用同一个课程环境，不需要 matplotlib。默认自动选择 CUDA（可用时）或 CPU；没有 GPU 也能完成。基础模型只有 110 个可训练参数，默认训练 2 个 epoch，预期 accuracy 约在 60% 附近；硬件、软件版本和训练设置变化可能影响结果，不对准确率人为设限。
