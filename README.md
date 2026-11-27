# 神经网络：从零到英雄（中文精讲）

这是一本围绕 Andrej Karpathy 的 **Neural Networks: Zero to Hero** 系列 notebook 编写的中文实践教材。

原课程的讲解主要存在于视频中，仓库里的 notebook 几乎只有可运行的代码；本书的目标是把每个 notebook 里的代码**拆开、讲透**：每一步为什么这样写、张量形状如何变化、梯度从哪里来、输出说明了什么。你可以把它当作课程的配套读物，边看代码边读，也可以脱离视频独立学习。

在线阅读（部署 GitHub Pages 后）：

**https://duandalei.github.io/NN-Zero-To-Hero-CN/**

## 这本书讲什么

全书覆盖原课程的讲座 1–6，对应 7 个 notebook：

| 章节 | 标题 | 对应 notebook |
| ---- | ---- | ------------- |
| 第 1 章 | 从导数到自动微分 | `micrograd_lecture_first_half_roughly.ipynb` |
| 第 2 章 | 训练你的第一个神经网络 | `micrograd_lecture_second_half_roughly.ipynb` |
| 第 3 章 | 二元字符语言模型 | `makemore_part1_bigrams.ipynb` |
| 第 4 章 | 多层感知机语言模型 | `makemore_part2_mlp.ipynb` |
| 第 5 章 | 激活值、梯度与批归一化 | `makemore_part3_bn.ipynb` |
| 第 6 章 | 手写反向传播 | `makemore_part4_backprop.ipynb` |
| 第 7 章 | WaveNet 式卷积语言模型 | `makemore_part5_cnn1.ipynb` |

学习路线是一条清晰的上升曲线：

1. **micrograd（第 1–2 章）**：从标量自动微分出发，手写一个能训练的小型神经网络，理解反向传播的本质。
2. **makemore（第 3–7 章）**：从字符级二元语言模型开始，逐步加入嵌入、多层感知机、批归一化、手写反向传播和卷积结构，最终抵达 GPT 的前夜。

## 项目结构

| 目录 | 说明 |
| ---- | ---- |
| `book/` | 中文正文，每章一个 Markdown 文件 |
| `Image/` | 从原 notebook 输出中提取的图表（matplotlib PNG 与计算图 SVG） |
| `index.html` | docsify 配置，负责把 Markdown 渲染成网页 |
| `_sidebar.md` | 侧边栏目录 |

本站使用 [docsify](https://docsify.js.org/) 构建，配合 GitHub Pages 即可实现类似 GitBook 的在线阅读体验：侧边栏目录、上下章分页、KaTeX 公式、代码复制和字数统计。

## 在线阅读章节

- [第 1 章：从导数到自动微分](https://duandalei.github.io/NN-Zero-To-Hero-CN/#/./book/1.从导数到自动微分.md)
- [第 2 章：训练你的第一个神经网络](https://duandalei.github.io/NN-Zero-To-Hero-CN/#/./book/2.训练你的第一个神经网络.md)
- [第 3 章：二元字符语言模型](https://duandalei.github.io/NN-Zero-To-Hero-CN/#/./book/3.二元字符语言模型.md)
- [第 4 章：多层感知机语言模型](https://duandalei.github.io/NN-Zero-To-Hero-CN/#/./book/4.多层感知机语言模型.md)
- 第 5 章：[激活值、梯度与批归一化](https://duandalei.github.io/NN-Zero-To-Hero-CN/#/./book/5.激活值梯度与批归一化.md)
- 第 6 章：[手写反向传播](https://duandalei.github.io/NN-Zero-To-Hero-CN/#/./book/6.手写反向传播.md)
- 第 7 章：[WaveNet 式卷积语言模型](https://duandalei.github.io/NN-Zero-To-Hero-CN/#/./book/7.WaveNet式卷积语言模型.md)

## 本地预览

docsify 不需要构建，任何静态文件服务器都可以：

```bash
# 方式一：Python 内置服务器
python -m http.server 3000

# 方式二：docsify-cli
npm i docsify-cli -g
docsify serve .
```

然后浏览器打开 `http://localhost:3000`。

## 原课程与致谢

+ 课程主页：[karpathy/nn-zero-to-hero](https://github.com/karpathy/nn-zero-to-hero)
+ 视频播放列表：YouTube 上的 [Neural Networks: Zero to Hero](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ)
+ micrograd：[karpathy/micrograd](https://github.com/karpathy/micrograd)
+ makemore：[karpathy/makemore](https://github.com/karpathy/makemore)

本书正文为原创中文讲解；书中的代码示例来自上述以 MIT 许可证发布的课程仓库，版权归 Andrej Karpathy 所有，详见 [LICENSE](./LICENSE)。

## 代码与输出验证

书中所有代码输出均经过实际运行验证，而不是从原 notebook 直接转抄。主要验证环境：

| 组件 | 版本 |
| ---- | ---- |
| Python | 3.12.16（Anaconda `AI` 环境） |
| PyTorch | 2.14.1 |
| NumPy | 2.5.5 |
| tiktoken | 0.14.0 |

原 notebook 中的部分输出是 Jupyter 会话的历史状态（例如重复执行过训练单元），与从干净环境重新运行的结果不同。本书以实测结果为准，并在相关位置说明差异。

## 说明

+ 原 notebook 基于特定版本的 PyTorch 与 NumPy，个别输出可能随版本变化；本书展示的是上表环境下实测的输出。
+ 本书不逐句翻译视频，而是围绕代码组织讲解，并补充必要的数学背景与工程细节。
+ 欢迎通过 Issue 指出错误或提出改进建议。
