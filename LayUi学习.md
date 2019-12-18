# LayUi笔记



## 使用方法

创建项目并引用layui文件到资源文件下

需要引用的HTML页面中需要引入以下资源文件

```html
<link rel="stylesheet" href="resources/layui/css/layui.css">
<script src="resources/layui/layui.js"></script>
```



## 图标(icon)

样式说明

- 基本样式		layui-icon
	 主题样式          layui-icon-rate		
  - [列表](https://www.layui.com/doc/element/icon.html)

使用方式1：使用字符实体

```html
<i class="layui-icon">&#xe6c9;</i>
```

使用方式2：使用样式

```html
<i class="layui-icon layui-icon-rate"></i>
```



## 按钮(button)

样式说明

- 基本样式		layui-btn
- 主题样式
  - 原始按钮    	layui-btn-primary
  - 百搭按钮          layui-btn-normal
  - 暖色按钮          layui-btn-warm
  - 警告按钮          layui-btn-danger
  - 禁用按钮          layui-btn-disabled
- 大小样式
  - 大型按钮   	layui-btn-lg
  - 小型按钮          layui-btn-sm
  - 迷你按钮          layui-btn-xs
- 圆角样式          layui-btn-radius
- 按钮组              layui-btn-group            (只能加在layui-btn的父标签上，紧凑排列)
- 按钮容器          layui-btn-container       (只能加在layui-btn的父标签上，松散排列)
- 流体样式          layui-btn-fluid               (宽度自适应)

使用方式

```html
<button type="button" class="layui-btn layui-btn-primary">原始按钮</button>
<button type="button" class="layui-btn">默认按钮</button>
<button type="button" class="layui-btn layui-btn-normal">百搭按钮</button>
<button type="button" class="layui-btn layui-btn-warm">暖色按钮</button>
<button type="button" class="layui-btn layui-btn-danger">警告按钮</button>
<button type="button" class="layui-btn layui-btn-disabled">禁用按钮</button>
```

```html
<button type="button" class="layui-btn layui-btn-lg">大型按钮</button>
<button type="button" class="layui-btn">默认按钮</button>
<button type="button" class="layui-btn layui-btn-sm">小型按钮</button>
<button type="button" class="layui-btn layui-btn-xs">迷你按钮</button>
```

```html
<button type="button" class="layui-btn layui-btn-radius">圆角按钮</button>
```

```html
<div class="layui-btn-group">
    <button type="button" class="layui-btn">增加</button>
    <button type="button" class="layui-btn ">编辑</button>
    <button type="button" class="layui-btn">删除</button>
</div>
```

```html
<div class="layui-btn-container">
  <button type="button" class="layui-btn">按钮一</button> 
  <button type="button" class="layui-btn">按钮二</button> 
  <button type="button" class="layui-btn">按钮三</button> 
</div>
```

```html
<button type="button" class="layui-btn layui-btn-fluid">流体按钮</button>
```

点击事件的注册

```js
layui.use(['jquery'],function(){
      var $=layui.jquery;
      $(".layui-btn").click(function(){
            alert($(this).text());
      });
})
```



## 导航菜单(navbar)

前置引入

```js
layui.use(['element'],function(){
     
})
```

样式说明

- 基本样式		
  - 导航栏		layui-nav
  - 选项卡             layui-nav-item             (加在layui-nav的子标签下)
  - 子选项卡         layui-nav-child             (加在layui-nav-item的子标签下)
- 选中样式                layui-this                      (加在layui-nav-item或layui-nav-child同标签上)
- 垂直样式                layui-nav-tree               (加在layui-nav同标签上)

使用方式

```html
<ul class="layui-nav">
        <li class="layui-nav-item"><a href="">最新活动</a></li>
        <li class="layui-nav-item layui-this">
          <a href="javascript:;">产品</a>
          <dl class="layui-nav-child">
            <dd><a href="">选项1</a></dd>
            <dd><a href="">选项2</a></dd>
            <dd><a href="">选项3</a></dd>
          </dl>
        </li>
        <li class="layui-nav-item"><a href="">大数据</a></li>
        <li class="layui-nav-item">
          <a href="javascript:;">解决方案</a>
          <dl class="layui-nav-child">
            <dd><a href="">移动模块</a></dd>
            <dd><a href="">后台模版</a></dd>
            <dd class="layui-this"><a href="">选中项</a></dd>
            <dd><a href="">电商平台</a></dd>
          </dl>
        </li>
        <li class="layui-nav-item"><a href="">社区</a></li>
</ul>
```



## 面包屑(breadcrumb)

样式说明

- 基本样式 			layui-breadcrumb

附加属性

- 自定义分割符		lay-separator

使用方式

```html
<span class="layui-breadcrumb" lay-separator="—">
  <a href="">首页</a>
  <a href="">国际新闻</a>
  <a href="">亚太地区</a>
  <a><cite>正文</cite></a>
</span>
```



## 选项卡(tab)

前置引入

```js
layui.use(['element'],function(){
     
})
```

样式说明

- 基本样式		
  - 选项卡             layui-tab
  - 选项卡标题      layui-tab-title
  - 选项卡内容      layui-tab-content
  - 选项卡内容项  layui-tab-item
- 主题样式
  - 简洁风格		layui-tab-brief
  - 卡片风格          layui-tab-card
- 选中样式
  - 标题选中		layui-this     	(加在 layui-tab-title的子标签上)
  - 启动显示          layui-show       (加在 layui-tab-item的标签上)

附加属性

- 允许关闭           lay-allowclose        (加在layui-tab的标签上)

使用方式

```html
<div class="layui-tab" lay-allowclose="true">
  <ul class="layui-tab-title">
    <li class="layui-this">网站设置</li>
    <li>用户管理</li>
    <li>权限分配</li>
    <li>商品管理</li>
    <li>订单管理</li>
  </ul>
  <div class="layui-tab-content">
    <div class="layui-tab-item layui-show">
      1. 高度默认自适应，也可以随意固宽。
      <br>2. Tab进行了响应式处理，所以无需担心数量多少。
    </div>
    <div class="layui-tab-item">内容2</div>
    <div class="layui-tab-item">内容3</div>
    <div class="layui-tab-item">内容4</div>
    <div class="layui-tab-item">内容5</div>
  </div>
</div>
```



## 进度条(progress)

样式说明

- 基本样式		layui-progress
- 进度条             layui-progress-bar
- 进度条颜色      
  - 红色		layui-bg-red		（加在layui-progress-bar的标签上）
  - 橙色         layui-bg-orange
  - 绿色         layui-bg-green
  - 蓝色         layui-bg-blue
  - 黑色         layui-bg-cyan 
- 大小                 layui-progress-big     (加在layui-progress的标签上)

附加属性

- 进度			lay-ercent (百分数)	  (加在layui-progress-bar的标签上)
- 显示进度          lay-showpercent       (加在layui-progress的标签上)

使用方式

```html
<div class="layui-progress  layui-progress-big" lay-showpercent="true">
  <div class="layui-progress-bar layui-bg-red" lay-percent="40%"></div>
</div>
```



## 面板(panel)

前置引入

```js
layui.use(['element'],function(){
     
})
```

样式说明

- 卡片面板
  - 基本样式
    - 面板容器		layui-card
    - 卡片标题          layui-card-header
    - 卡片内容          layui-card-body
- 折叠面板
  - 基本样式
    - 面板容器		layui-collapse
    - 折叠项             layui-colla-item
    - 标题                 layui-colla-title
    - 内容                 layui-colla-content
    - 默认展开          layui-show
  - 附加属性
    - 手风琴折叠      lay-accordion

使用方式

```html
 <div class="layui-card">
     <div class="layui-card-header">标题</div>
     <div class="layui-card-body">内容</div>
 </div>
```

```html
<div class="layui-collapse" lay-accordion="">
        <div class="layui-colla-item">
          <h2 class="layui-colla-title">layui 更适合哪些开发者？</h2>
          <div class="layui-colla-content layui-show">
            <p>所有层次的服务端程序员。</p>
          </div>
        </div>
        <div class="layui-colla-item">
          <h2 class="layui-colla-title">为什么前端工程师多不愿意用 Bootstrap 框架？</h2>
          <div class="layui-colla-content">
            <p>因为不适合。</p>
          </div>
        </div>
      </div>
```



## 栅格(grid)

样式说明

- 基本样式		layui-row
- 等分设置
  - 移动设备划分		layui-col-xs6         	(最后的数字为1~12)
  - 平板设备划分		layui-col-sm6
  - 桌面划分		        layui-col-md6
- 列间隙              layui-col-space1
- 列偏移              layui-col-md-offset4
- 流体布局          layui-fluid

使用方式

```html
<div class="layui-fluid">
            <fieldset class="layui-elem-field layui-field-title">
              <legend>流体容器（宽度自适应，不固定）</legend>
            </fieldset>
            <div class="layui-row">
              <div class="layui-col-sm3">
                <div class="grid-demo">25%</div>
              </div>
              <div class="layui-col-sm3">
                <div class="grid-demo">25%</div>
              </div>
              <div class="layui-col-sm3">
                <div class="grid-demo">25%</div>
              </div>
              <div class="layui-col-sm3">
                <div class="grid-demo">25%</div>
              </div>
            </div>
          </div>
```



## 徽章(badge)

样式说明

- 基本样式
  - 点		layui-badge-dot
  - 自定义     layui-badge
  - 边框         layui-badge-rim
- 颜色
  - 橙色         layui-bg-orange           (还有更多)

使用方式

```html
<span class="layui-badge-dot layui-bg-orange"></span>
```

```html
<span class="layui-badge">6</span>
<span class="layui-badge layui-bg-cyan">青</span>
```

```html
<span class="layui-badge-rim">Hot</span>
```



## 时间线(timeline)

样式说明

- 基本样式
  - 时间线			layui-timeline
  - 时间线项                 ayui-timeline-item
  - 时间线图标             layui-timeline-axis
  - 时间线内容容器      layui-timeline-content
  - 时间线文本              layui-text
  - 时间想项标题          layui-timeline-title

使用方式

```html
<ul class="layui-timeline">
                <li class="layui-timeline-item">
                  <i class="layui-icon layui-timeline-axis"></i>
                  <div class="layui-timeline-content layui-text">
                    <div class="layui-timeline-title">2018年，layui 5.0 发布。并发展成为中国最受欢迎的前端UI框架（期望）</div>
                  </div>
                </li>
                <li class="layui-timeline-item">
                  <i class="layui-icon layui-timeline-axis"></i>
                  <div class="layui-timeline-content layui-text">
                    <div class="layui-timeline-title">2017年，layui 里程碑版本 2.0 发布</div>
                  </div>
                </li>
                <li class="layui-timeline-item">
                  <i class="layui-icon layui-timeline-axis"></i>
                  <div class="layui-timeline-content layui-text">
                    <div class="layui-timeline-title">2016年，layui 首个版本发布</div>
                  </div>
                </li>
                <li class="layui-timeline-item">
                  <i class="layui-icon layui-timeline-axis"></i>
                  <div class="layui-timeline-content layui-text">
                    <div class="layui-timeline-title">2015年，layui 孵化</div>
                  </div>
                </li>
                <li class="layui-timeline-item">
                  <i class="layui-icon layui-anim layui-anim-rotate layui-anim-loop layui-timeline-axis"></i>
                  <div class="layui-timeline-content layui-text">
                    <div class="layui-timeline-title">更久前，轮子时代。维护几个独立组件：layer等</div>
                  </div>
                </li>
              </ul>
```



## 表格(table)

样式说明

- 基本样式
  - 表格		layui-table	(加在table标签上)

附加属性

- 边框
  - 行边框	lay-skin="line"
  - 列边框     lay-skin="row"
  - 无边框     lay-skin="nob"
- 大小
  - 大		 lay-size="lg"
  - 小		 lay-size="sm"

使用方式

```html
<table class="layui-table" lay-skin="line" lay-size="lg">
                <colgroup>
                  <col width="150">
                  <col width="150">
                  <col width="200">
                  <col>
                </colgroup>
                <thead>
                  <tr>
                    <th>人物</th>
                    <th>民族</th>
                    <th>出场时间</th>
                    <th>格言</th>
                  </tr> 
                </thead>
                <tbody>
                  <tr>
                    <td>贤心</td>
                    <td>汉族</td>
                    <td>1989-10-14</td>
                    <td>人生似修行</td>
                  </tr>
                  <tr>
                    <td>张爱玲</td>
                    <td>汉族</td>
                    <td>1920-09-30</td>
                    <td>于千万人之中遇见你所遇见的人，于千万年之中，时间的无涯的荒野里…</td>
                  </tr>
                  <tr>
                    <td>Helen Keller</td>
                    <td>拉丁美裔</td>
                    <td>1880-06-27</td>
                    <td> Life is either a daring adventure or nothing.</td>
                  </tr>
                  <tr>
                    <td>岳飞</td>
                    <td>汉族</td>
                    <td>1103-北宋崇宁二年</td>
                    <td>教科书再滥改，也抹不去“民族英雄”的事实</td>
                  </tr>
                  <tr>
                    <td>孟子</td>
                    <td>华夏族（汉族）</td>
                    <td>公元前-372年</td>
                    <td>猿强，则国强。国强，则猿更强！ </td>
          </tr>
     </tbody>
</table>
```



## 动画(animate)

样式说明

- 基本样式			layui-anim

附加属性

- 动画类型			

使用方式