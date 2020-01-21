---
title: 阿姆达尔定律 (Amdahl's Law)
date: 2020-01-20T16:00:00Z
path: AmdahlsLaw
author: 阿姆达尔
excerpt: 阿姆达尔定律是一个显示计算任务潜在加速能力的公式。这种能力可以通过增加系统资源来实现，通常用于并行计算中。
tags:
- 定律

---
> 阿姆达尔定律是一个显示计算任务**潜在加速**能力的公式。这种能力可以通过增加系统资源来实现，通常用于并行计算中。它可以预测增加处理器数量的实际好处，然而增加处理器数量会受到程序并行性的限制。

举例说明：如果程序由两部分组成，部分 A 必须由单个处理器执行，部分 B 可以并行运行。那么向执行程序的系统添加多个处理器只能获得有限的好处。它可以极大地提升部分 B 的运行速度，但部分 A 的运行速度将保持不变。

下图展示了一些运行速度的提升潜能的例子：

[![阿姆达尔定律](https://github.com/nusr/hacker-laws-zh/raw/master/images/amdahls_law.png)](https://github.com/nusr/hacker-laws-zh/blob/master/images/amdahls_law.png)

_(图片来源: By Daniels220 at English Wikipedia, Creative Commons Attribution-Share Alike 3.0 Unported,_ [_https://en.wikipedia.org/wiki/File:AmdahlsLaw.svg_](https://en.wikipedia.org/wiki/File:AmdahlsLaw.svg "https://en.wikipedia.org/wiki/File:AmdahlsLaw.svg")_)_

可以看出，50％ 并行化的程序在使用大于 10 个处理单元之后的速度提升收效甚微，而 95％ 并行化的程序在使用超过一千个处理单元之后仍然可以显著提升速度。

随着[摩尔定律](https://github.com/nusr/hacker-laws-zh#%E6%91%A9%E5%B0%94%E5%AE%9A%E5%BE%8B-moores-law)减慢，单个处理器的速度增加缓慢，并行化是提高性能的关键。图形编程是一个极好的例子，现代着色器可以并行渲染单个像素或片段。这也是现代显卡通常具有数千个处理核心（GPU 或着色器单元）的原因。