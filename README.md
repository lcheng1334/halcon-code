引脚形变为一整套例子

```mermaid
graph TD
    A[读取图像路径] --> B[读取图像<br>read_image]
    B --> C[转灰度图<br>rgb1_to_gray]
    C --> D[高斯滤波<br>smooth_image]
    D --> E[阈值分割<br>threshold]
    E --> F[填充空洞<br>fill_up]
    F --> G[获取主方向<br>orientation_region]
    G --> H[获取旋转矩形参数<br>smallest_rectangle2]
    H --> I[构建仿射矩阵<br>vector_angle_to_rigid]
    I --> J[图像旋转对齐<br>affine_trans_image]
    I --> K[区域旋转对齐<br>affine_trans_region]
    J --> L[获取对齐后边界框<br>smallest_rectangle1]
    K --> L
    L --> M[根据缩进计算新矩形坐标]
    M --> N[生成缩小矩形 ROI<br>gen_rectangle1]
    N --> O[仿射矩阵求逆<br>hom_mat2d_invert]
    O --> P[ROI 映射回原图<br>affine_trans_region]
    P --> Q[显示原图<br>dev_display]
    Q --> R[显示 ROI 区域<br>dev_display FinalROI]
    R --> S[计算 ROI 面积与中心<br>area_center]

