引脚形变为一整套例子

graph TD
    A[读取图像路径] --> B[读取图像 read_image]
    B --> C[转灰度图 rgb1_to_gray]
    C --> D[高斯滤波 smooth_image]
    D --> E[阈值分割 threshold]
    E --> F[填充空洞 fill_up]
    F --> G[获取主方向 orientation_region]
    G --> H[获取旋转矩形 smallest_rectangle2]
    H --> I[构造仿射变换矩阵 vector_angle_to_rigid]
    I --> J[图像旋转 affine_trans_image]
    I --> K[区域旋转 affine_trans_region]
    J --> L[获取边界框 smallest_rectangle1]
    K --> L
    L --> M[应用缩进计算 NewR1~NewC2]
    M --> N[生成缩小矩形 gen_rectangle1]
    N --> O[仿射矩阵求逆 hom_mat2d_invert]
    O --> P[ROI映射回原图 affine_trans_region]
    P --> Q[显示原图 dev_display]
    Q --> R[显示ROI dev_display(FinalROI)]
    R --> S[获取ROI中心与面积 area_center]
