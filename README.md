# 拓扑图可视化
使用了[D3v4.js](https://github.com/d3/d3)库
在给出的[Curved Links](https://bl.ocks.org/mbostock/4600693)例子上修改、增加功能。

## 使用到的js库
- d3-v4
- jQuery

## 使用方法:

    localhost:port[/index.html]?proj.json
    
    
## 拓扑图界面内的操作方式和基本元素解释

### 图中可进行的操作
1. 当点击节点时会隐藏或者显示该节点的ID，同时在Node properties显示出该节点的信息
2. 当点击边时会在Link properties显示出该边的信息
3. 在图中可通过滚轮放大缩小图片

### 按钮的使用
1. 隐藏所有标签：即隐藏所有节点的信息
2. 显示所有标签：即显示所有节点的信息
3. 停止迭代拓扑图：停止拓扑图的迭代，再次点击继续迭代
4. 保存为Json文件：将节点的信息保存到Json中
5. 将svg另存为图片：将svg以图片的形式保存

### Simulation properties
1. Strength：节点间斥力的调节
2. Distance：边长度的调节
3. Iterations：迭代次数的调节

### Note properties
1. Node'ID：表示当前显示节点的ID
2. Color：节点颜色的调节
3. Radius：节点大小的调节

### Link properties
1. Link'ID：表示当前显示边的ID
2. Color：边的颜色的调节
3. Width：边的宽度的调节

## 修改日志：
- 20170717增加了显示/隐藏节点标签功能。
- 20170718增加了显示/隐藏全部节点标签功能、给边增加宽度和颜色的功能、视图缩放功能。
- 20170719增加了以鼠标为中心的缩放功能、点击鼠标选中离点击位置最近的节点功能、边缘限制(点限制在svg的范围内)。
- 20170720增加了链路长度、修改了边缘斥力(直接贴附边缘而不是给一个随机值)。
- 20170721
    - 完成输入文件修改格式的问题(昨天修改格式之后图展不开，一直没找到问题，今早发现是由于link的起点必须用'source'，终点必须用'target')。
    - 增加切换拓扑图功能(还有bug)。
- 20170724
    - 手动暂停迭代固定拓扑
    - 完成切换拓扑图的功能(通过将文件名在url后给出，而不是在js函数参数中给出，每次切换刷新页面)
- 20170725
    - 增加修改节点、边属性功能
    - 增加迭代次数控制
- 20170726 基本完成所有要求
    - 更改修改节点、边属性功能(将表格改为滑动条)
    - 更改试图缩放功能(在svg下新建一个container标签，每次缩放container而不是整个svg，好处是放大时不会覆盖按钮，还自动实现了拖拽)
    - 增加修改Simulation属性功能(包括strength、distance  、iterations)，同样是用滑动条实现改变
    - 增加保存节点坐标功能，由于js无法保存文件，因而将数据写成json格式打印到控制台
- 20170728
    - 修改保存节点坐标功能：将节点坐标保存为文件的功能
- 20170729
    - 增加将svg保存为图片的功能
- 20170730
    - 整理代码，将其按功能切分为若干部分
    - 设置边的id，使点击的时候在滑动条上显示边id
    - 设置边的透明度
- 20170731
    - 利用bootstrap优化整个拓扑图的显示效果
    - 整理README文档，解释页面内的具体使用方式
- 20170801
    - 增加修改点/边透明度的功能
    
### 当前效果图如下：
![img](http://wx2.sinaimg.cn/large/006k2kyGgy1fi323jvgn2g31gw0qf1l4.gif)<br />
若是显示不了[点我](http://wx2.sinaimg.cn/large/006k2kyGgy1fi323jvgn2g31gw0qf1l4.gif)
