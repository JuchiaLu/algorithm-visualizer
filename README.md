# 算法可视化

### (一) 添加自定义颜色功能

官方只支持 patch 元素时的酒红色 和 select 元素时的蓝色，如下图所示的希尔排序：

![](https://raw.githubusercontent.com/JuchiaLu/algorithm-visualizer/master/branding/shellSort1.gif)

有些算法需要将元素分组后进行相应操作， 所有元素同一种颜色，不能不直观的分辨出哪些元素是同一组。

添加自定义颜色功能后希尔排序如下图(绿色和黄色为同一组元素，绿色代表已经排好序，黄色代表等待排序)：

![](https://raw.githubusercontent.com/JuchiaLu/algorithm-visualizer/master/branding/shellSort2.gif)

API 与 官方的 select 风格保存一致, 如二维数组中(一维数组和柱状图类似):

| 函数               | 说明                                            | API                                                    |
| ------------------ | ----------------------------------------------- | ------------------------------------------------------ |
| **setColor**       | set color (`x`, `y`).                           | setColor(string color, int x, int y)                   |
|                    |                                                 |                                                        |
| **setColor**       | set color from (`sx`, `sy`) to (`ex`, `ey`).    | setColor(string color, int sx, int sy, int ex, int ey) |
|                    |                                                 |                                                        |
| **setRowColor**    | set color from (`x`, `sy`) to (`x`, `ey`).      | setRowColor(string color, int x, int sy, int ey)       |
|                    |                                                 |                                                        |
| **setColColor**    | set color from (`sx`, `y`) to (`ex`, `y`).      | setColColor(string color, int y, int sx, int ex)       |
|                    |                                                 |                                                        |
| **removeColor**    | remove color (`x`, `y`).                        | removeColor(int x, int y)                              |
|                    |                                                 |                                                        |
| **removeColor**    | remove color from (`sx`, `sy`) to (`ex`, `ey`). | removeColor(int sx, int sy, int ex, int ey)            |
|                    |                                                 |                                                        |
| **removeRowColor** | remove color from (`x`, `sy`) to (`x`, `ey`).   | removeRowColor(int x, int sy, int ey)                  |
|                    |                                                 |                                                        |
| **removeColColor** | remove color from (`sx`, `y`) to (`ex`, `y`).   | removeColColor(int y, int sx, int ex)                  |
|                    |                                                 |                                                        |

注：这里颜色是绑定到位置而非绑定到元素，如果元素移动后，颜色会保留在原位置, color 的值按 css 写即可 

### (二) 删除 JAVA 和 CPP 支持

jAVA 和 CPP 需要搭建服务端语言环境用来提取可视化命令，删除后把 JS 的服务端提取脚本直接放到本项目，这样便可以将项目直接部署到 GitHub Page 中方便使用。

