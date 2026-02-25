# AirHust 视觉实训

欢迎来到AirHUST视觉实训项目。本仓库包含一系列逐步深入的计算机视觉实践任务，适合计算机视觉的入门开发者。

## 项目概览

本项目通过多个实验分支，带你从基础到高级逐步掌握计算机视觉：

### 实验内容
* **lab0:测试环境** - 测试你的各种环境是否正常
  - lab0_test_for_env:测试环境

* **lab1: 图像基础** - 掌握图像处理的基本操作
  
  - lab1_1_read_write_images: 图像读写
  - lab1_2_from_pixels_to_images: 像素级操作
  - lab1_3_flipping_channels: 通道操作
  - lab1_4_spin_around: 图像旋转
  - lab1_5_perspective_transform: 透视变换
  - lab1_6_simple_threshold: 简单阈值分割及轮廓筛选等
  - lab1_7_mask: 基础掩膜操作
  - lab1_8_morphological_process： 基本形态学操作

* **lab2: OpenCV视觉工程** - 构建实际视觉应用
  -  lab2_1_video_stream_processing: 视频流处理
  -  lab2_2_ros_pkg_for_vision 如何封ros包
  
* **lab3: 深度学习相关** - 深度学习在视觉中的应用

### 发布时间表
- ✅ lab0_test_for_env (已发布)
- ✅ lab1_1_read_write_images (已发布)
- ✅ lab1_2_from_pixels_to_images (已发布)
- ✅ lab1_3_flipping_channels (已发布)
- ✅ lab1_4_spin_around (已发布)
- ✅ lab1_5_perspective_transform (已发布)
- ✅ lab1_6_simple_threshold (已发布)
- ✅ lab1_7_mask (已发布)
- 🔄 lab1_8_morphological_process ( 2026.2.26 )
- 🔄 lab2_1_video_stream_processing
- 🔄 lab2_2_ros_pkg_for_vision
  
## 快速开始指南

### 第一步：准备工作

1. **注册GitHub账号**（如果还没有）
   
   - 访问 [github.com](https://github.com) 注册账号

2. **安装必要的软件**
   
   - **Git**: [下载地址](https://git-scm.com/downloads)
   - 根据你的编程语言选择：
     - **Python选手**: Python 3.8+ 和相应的IDE
     - **C++选手**: C++编译器（g++/MSVC）和相应的IDE

### 第二步：Fork本仓库

1. 登录GitHub，访问本仓库页面
2. 点击右上角的 **"Fork"** 按钮
3. 选择你的账户作为目标位置
4. 等待Fork完成，现在你有了自己的副本

### 第三步：克隆仓库到本地

1. 打开终端（Windows用户使用Git Bash或命令提示符）
2. 选择一个合适的工作目录，执行以下命令：

```bash
# 克隆你fork的仓库（替换<your-username>为你的GitHub用户名）
git clone https://github.com/<your-username>/AirHUST_Vision_Tutorial.git

# 进入项目目录
cd AirHUST_Vision_Tutorial

# 将原仓库添加为上游
git remote add upstream https://github.com/FirmamentumX/AirHUST_Vision_Tutorial.git

# 拉取原仓库的所有分支
git fetch upstream

# 同步到本地和副本仓库
git checkout -b 分支名 upstream/分支名
git push origin 分支名
```

### 第四步：配置开发环境

根据你的编程语言选择配置方式：

#### **Python选手：conda环境配置**

1. **安装Miniconda/Anaconda**
   
   ```bash
   # Linux/macOS 下载和安装
   wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
   bash miniconda.sh -b -p $HOME/miniconda3
   source $HOME/miniconda3/bin/activate
   
   # Windows: 从官网下载安装程序 https://docs.conda.io/en/latest/miniconda.html
   ```

2. **创建专用环境**
   
   ```bash
   # 创建名为airhust的Python环境
   conda create -n airhust python=3.8
   
   # 激活环境
   conda activate airhust
   ```

3. **安装依赖包**
   
   ```bash
   pip install opencv-python numpy matplotlib
   
   # 或者使用conda安装
   conda install -c conda-forge opencv numpy matplotlib
   ```

#### **C++选手：OpenCV配置**

1. **安装编译工具**
   
   ```bash
   # Ubuntu/Debian
   sudo apt update
   sudo apt install build-essential cmake git pkg-config
   
   # macOS (使用Homebrew)
   brew install cmake pkg-config
   
   # Windows: 安装Visual Studio 2019/2022 和 CMake
   ```

2. **安装OpenCV依赖**
   
   ```bash
   # Ubuntu/Debian
   sudo apt install libopencv-dev
   
   # macOS
   brew install opencv
   
   # Windows: 从OpenCV官网下载预编译库
   # https://opencv.org/releases/
   ```

3. **配置开发环境**
   
   ```bash
   # 创建CMakeLists.txt模板
   # 参考示例：https://docs.opencv.org/master/db/df5/tutorial_linux_gcc_cmake.html
   ```

### 第五步：查看和切换分支

```bash
# 查看所有分支（包括远程分支）
git branch -a

# 更新原仓库的所有分支
git fetch upstream

# 同步到本地和副本仓库
git checkout -b 分支名 upstream/分支名
git push origin 分支名

# 查看当前所在分支
git branch
```

### 第六步：开始实验

1. **如果分支已有代码结构**：
   
   - 阅读现有的代码和注释
   - 按照要求完成任务
   - 运行代码测试效果

2. **如果分支不存在代码结构，仅有.md或者图片**：
   
   - 创建代码目录和文件
   - 按照文档要求实现功能
   - 参考以下经典的开发结构：

#### **Python开发结构**

```
lab1_1_read_write_images/
├── src/
│   ├── image_io.py          # 主程序文件
│   └── utils.py             # 工具函数
├── data/
│   ├── input/               # 输入图片
│   └── output/              # 输出图片
├── requirements.txt         # 依赖包列表
├── README.md               # 项目说明
└── run.py                  # 运行脚本
```

#### **C++开发结构**

```
lab1_1_read_write_images/
├── src/
│   ├── main.cpp            # 主程序文件
│   ├── image_io.cpp        # 函数实现
│   └── image_io.h          # 配套头文件
├── data/
│   ├── input/              # 输入图片
│   └── output/             # 输出图片
├── CMakeLists.txt          # CMake配置文件
├── README.md               # 项目说明
└── build/                  # 编译目录（建议.gitignore）
```

### 第七步：提交你的工作

```bash
# 查看更改状态
git status

# 添加更改的文件
git add .

# 提交更改
git commit -m "完成lab1_1: 实现了图像读写功能"

# 推送到远程仓库（你的fork）
git push origin lab1_1_read_write_images
```

### 第八步：合并分支（当需要时）

如果后续实验需要基于前一个实验的代码：

```bash
# 切换到目标分支
git checkout labn_2_yyy

# 合并前一个分支的代码
git merge labn_1_xxx

# 解决可能的冲突（如果有）
# 完成合并后提交
git push origin labn_2_yyy
```

## 实验提交要求

1. 每个实验都应当在对应的分支中完成
2. 代码最好要有清晰的注释
3. 提交信息应描述完成的工作
4. 保持代码结构整洁

## 开发小贴士

### **Python选手**

```python
# 检查OpenCV是否正确安装
import cv2
print(f"OpenCV Version: {cv2.__version__}")

# 基本的图像读取和显示
img = cv2.imread("image.jpg")
cv2.imshow("Image", img)
cv2.waitKey(0)
```

### **C++选手**

```cpp
// 基本的OpenCV程序示例
#include <opencv2/opencv.hpp>

int main() {
    cv::Mat img = cv::imread("image.jpg");
    cv::imshow("Image", img);
    cv::waitKey(0);
    return 0;
}
```

### **CMakeLists.txt 示例**

```cmake
cmake_minimum_required(VERSION 3.10)
project(lab1_1)

set(CMAKE_CXX_STANDARD 11)

# 查找OpenCV
find_package(OpenCV REQUIRED)

# 包含头文件
include_directories(${OpenCV_INCLUDE_DIRS})

# 创建可执行文件
add_executable(lab1_1 src/main.cpp)

# 链接OpenCV库
target_link_libraries(lab1_1 ${OpenCV_LIBS})
```

## 需要帮助？

如果在学习过程中遇到问题：

1. 查看实验的详细说明
2. 搜索相关错误信息
3. 向同学或老师请教
4. 在GitHub Issues中提问

---

**祝学习愉快！** 🎉

> 或许部分内容并没有在课上讲过，但相信你也能成功做出来（确信
