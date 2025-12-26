## lab1_5_perspective_transform

现提供若干格线图及棋盘格图，请你使用透视变换，从原图任意选择一个四边形区域，变换为新图中的一个矩形区域。

### 实验要求：

1. **读取原始图像**并分析其尺寸与色彩模式
2. **在原始图像上选择四个点**，构成一个四边形区域（注意：这四个点不要共线，最好有明显特征）
3. **定义目标矩形区域**，确定矩形的四个角点位置
4. **计算透视变换矩阵**并应用正向透视变换，将四边形区域变换为目标矩形，将结果保存为`perspective_result`
5. **计算逆透视变换矩阵**，将`perspective_result`反向变换回原始图像的四边形区域，将结果保存为`inverse_result`
6. **比较并分析**原始图像与反向变换结果`inverse_result`的差异

### 你可能要用到的工具函数原型：

如果你是C++选手：

```cpp
// 读取图像
cv::Mat cv::imread(const cv::String &filename, int flags = 1);

// 计算透视变换矩阵（src：源图像四边形，dst：目标矩形）
cv::Mat cv::getPerspectiveTransform(const cv::Point2f src[], const cv::Point2f dst[], int solveMethod = 0);

// 应用透视变换
void cv::warpPerspective(cv::InputArray src, cv::OutputArray dst,
                         cv::InputArray M, cv::Size dsize,
                         int flags = INTER_LINEAR,
                         int borderMode = BORDER_CONSTANT,
                         const cv::Scalar& borderValue = cv::Scalar());

// 逆矩阵计算
cv::Mat cv::Mat::inv(int method = DECOMP_LU) const;

// 保存图像
bool cv::imwrite(const cv::String &filename, cv::InputArray img);

// 展示图像
void cv::imshow(const cv::String &winname, cv::InputArray mat);
int cv::waitKey(int delay = 0);
```

如果你是Python选手：

```python
# 读取图像
cv2.imread(filename: str, flags: int = ...) -> MatLike

# 计算透视变换矩阵（src：源图像四边形，dst：目标矩形）
cv2.getPerspectiveTransform(src: MatLike, dst: MatLike, solveMethod: int = ...) -> MatLike

# 应用透视变换
cv2.warpPerspective(src: MatLike, M: MatLike, dsize: tuple[int, int], flags: int = ..., ...) -> MatLike

# 逆矩阵计算（可用于反向变换矩阵）
numpy.linalg.inv(a: array_like) -> ndarray
# 或者使用以下方法获取反向变换矩阵
cv2.getPerspectiveTransform(dst: MatLike, src: MatLike, solveMethod: int = ...) -> MatLike

# 保存图像
cv2.imwrite(filename: str, img: MatLike, params: Sequence[int] = ...) -> bool

# 展示图像
cv2.imshow(winname: str, mat: MatLike) -> None
cv2.waitKey(delay: int = ...) -> int
```

**注意**：

1. 源图像的四点选择顺序应与目标矩形的四点顺序一致（通常为左上、右上、左下、右下）
2. 透视变换会改变图像的视角，常用于校正文档、车牌等倾斜图像
3. 在定义目标矩形大小时，建议根据实际需要确定，或者根据源四边形的近似尺寸来确定
4. 可以使用INTER_LINEAR插值方法以保证图像质量

### 实验提示：

1. 对于棋盘格图，可以选择一个棋盘格作为源四边形，将其变换为规则矩形
2. 对于格线图，可以选择一个梯形或平行四边形区域进行校正
3. 可以通过鼠标交互或直接指定坐标的方式选择四点
4. 观察正向变换后，原本不平行的线是否变为平行
5. 分析反向变换后图像与原始图像的差异，思考差异产生的原因

### 实验思考：

1. 透视变换与之前学习的仿射变换有何区别？
2. 在什么场景下透视变换比仿射变换更适用？
3. 如果选择的四边形区域不是凸四边形，会发生什么情况？
4. 如何评估透视变换的准确性和质量？

## 实验完毕后，记得提交修改（命令行中-m后的字符串可自行确定），以供检查：

```bash
git commit -a -m "my work on lab1_5 is done."
```
