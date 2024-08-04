# RiotPlayButton [![English](https://img.shields.io/badge/Language-English-blue.svg)](README.md) [![中文](https://img.shields.io/badge/Language-中文-red.svg)](README.zh-CN.md) [![한국어](https://img.shields.io/badge/Language-한국어-red.svg)](README.ko.md)

一个受英雄联盟游戏PLAY按钮启发的可自定义WPF ToggleButton控件

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![.NET](https://img.shields.io/badge/.NET-8.0-blue.svg)](https://dotnet.microsoft.com/download)
[![Stars](https://img.shields.io/github/stars/vickyqu115/riotplaybutton.svg)](https://github.com/vickyqu115/riotplaybutton/stargazers)
[![Issues](https://img.shields.io/github/issues/vickyqu115/riotplaybutton.svg)](https://github.com/vickyqu115/riotplaybutton/issues)

## 项目概述

RiotPlayButton是一个自定义WPF控件，重现了英雄联盟游戏客户端的PLAY按钮。它展示了高级WPF技术，包括自定义形状创建、渐变画笔、动画和高效的XAML设计。

<img src="https://github.com/user-attachments/assets/cc980d89-4479-4c4d-8d6a-d97593e12b3b" width="49%"/>
<img src="https://github.com/user-attachments/assets/033e7a46-c0d2-4f3c-9566-69ec0028f442" width="49%"/>
<img src="https://github.com/user-attachments/assets/218fe98c-dfa8-4eb0-9038-c8f4199f107b" width="49%"/>
<img src="https://github.com/user-attachments/assets/ea15edee-6efd-43c5-b796-226ccb78e89a" width="49%"/>
<img src="https://github.com/user-attachments/assets/4beb7730-cfd5-46fb-9a5e-31075ae0db2d" width="49%"/>
<img src="https://github.com/user-attachments/assets/7d0f803c-c8f7-40e0-a324-7ecc4b75126a" width="49%"/>

## 主要特性和实现
#### 1. 自定义WPF控件开发
- [x] 扩展WPF ToggleButton以实现特殊功能
- [x] 使用纯XAML实现复杂的UI元素

#### 2. 高级XAML技术
- [x] 使用Path和Geometry创建不规则形状
- [x] 利用LinearGradientBrush实现复杂的颜色效果

#### 3. 复杂形状生成
- [x] 使用Polygon创建多点形状
- [x] 实现Cubic Bezier曲线以创建平滑复杂的曲线
- [x] 应用Quadratic Bezier曲线创建简单的曲线形状

#### 4. 动画和交互性
- [x] 使用Jamesnet.WPF Nuget包实现流畅动画
- [x] 交互式鼠标悬停和选中状态效果

#### 5. 性能优化
- [x] 使用裁剪技术实现高效渲染
- [x] 优化XAML结构以提高性能

#### 6. 忠实重现
- [x] 像素级精确重现英雄联盟PLAY按钮
- [x] 注重设计和功能的细节

<img src="https://github.com/user-attachments/assets/0abeddcb-8f4e-4273-82d8-e7c42849ec4e" width="49%"/>
<img src="https://github.com/user-attachments/assets/4feb4e87-dbc2-435a-b5fb-cff1640004f8" width="49%"/>
<img src="https://github.com/user-attachments/assets/f7f97dca-9918-45bc-aa49-5920059728ae" width="49%"/>
<img src="https://github.com/user-attachments/assets/7181da5b-0218-40a7-b1a6-e9ac05b334bf" width="49%"/>
<img src="https://github.com/user-attachments/assets/a3a52292-c9ac-441f-bf5c-9f3dd40823e5" width="49%"/>
<img src="https://github.com/user-attachments/assets/c777c08a-9680-4b6c-97e8-1a1edc5d6fb5" width="49%"/>

## 技术栈
- WPF (Windows Presentation Foundation)
- .NET 8.0
- C#
- Jamesnet.WPF Nuget包

## 入门指南
### 先决条件
- Visual Studio 2022或更高版本
- .NET 8.0 SDK

### 安装和执行
#### 1. 克隆仓库：

```
git clone https://github.com/vickyqu115/riotplaybutton.git  
```

#### 2. 打开解决方案
- [x] Visual Studio
- [x] Visual Studio Code
- [x] JetBrains Rider

<img src="https://github.com/user-attachments/assets/af70f422-7057-4e77-a54d-042ee8358d2a" width="32%"/>
<img src="https://github.com/user-attachments/assets/e4feaa10-a107-4b58-8d13-1d8be620ec62" width="32%"/>
<img src="https://github.com/user-attachments/assets/5ff487f6-55e4-43e1-9abf-f8d419ee6943" width="32%"/>

#### 3. 构建和运行
- [x] 设置启动项目
- [x] 按F5或点击运行按钮
- [x] 推荐使用Windows 11

## 学习资源
- [详细实现文章](https://jamesnet.dev/article/51)
- [YouTube教程](https://bit.ly/40YoVIo)
- [哔哩哔哩教程](https://bit.ly/49L6dXu)

## 贡献
欢迎为RiotPlayButton做出贡献！随时提交问题、创建拉取请求或提出改进建议。

## 许可证
该项目基于MIT许可证分发。有关详细信息，请参阅[LICENSE](LICENSE)文件。

## 联系方式
- 网站：https://jamesnet.dev
- 电子邮件：vickyqu115@hotmail.com, james@jamesnet.dev

使用这个具有高级形状生成技术的吸引人的英雄联盟风格PLAY按钮来增强您的WPF应用程序！
