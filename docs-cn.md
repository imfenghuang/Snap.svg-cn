# Snap
### 1. `Snap(...)`
> 创建一个面或包裹已经存在SVG元素，并返回`Element`对象

- 参数
	- 1.1 `Snap(width, height)`    
	  `width` 数值或字符串 面的宽度  
	  `height` 数值或字符串 面的高度  
	
	- 1.2 `Snap(DOM)`
	  `DOM` SVG元素 被包裹进Snap结构的元素
	
	- 1.3 `Snap(array)`  
	  `array` 数组 元素数组（返回元素集合）
	
	- 1.4 `Snap(query)`  
	  `query` 字符串 CSS查询选择器

- 返回值

	`Element` 对象

### 2. `Snap.format(token, json)`
> 把`token`中的未知值，用`json`中的值进行替换，并返回一个格式化后的字符串  

- 参数

	`token` 字符串 需要被格式化的字符串  
	`json` 对象 对象中属性的值将被用于替换

- 用法
	
		// 下述命令将绘制一个相当于矩形形状的路径
	    paper.path(Snap.format("M{x},{y}h{dim.width}v{dim.height}h{dim['negative width']}z", {
	    	x: 10,
	   		y: 20,
	    	dim: {
	    		width: 40,
	    		height: 50,
	    		"negative width": -40
	    	}
	    }));

- 返回值
  
  格式化后的字符串 字符串型

### 3. `Snap.rad(deg)`
> 角度转换为弧度，并返回数值型的弧度值

- 参数

	`deg` 数值 角度值

- 返回值
   
    弧度值 数值型

### 4. `Snap.angle(x1, y1, x2, y2, [x3, y3])`
> 返回两个点或三个点之间的夹角度数

- 参数  

	`x1` 数值 第一个点的 `x` 坐标   
	`y1` 数值 第一个点的 `y` 坐标    
	`x2` 数值 第二个点的 `x` 坐标    
	`y2` 数值 第二个点的 `y` 坐标    
	`x3` 数值 第三个点的 `x` 坐标    
	`y3` 数值 第三个点的 `y` 坐标  

- 返回值  
  角度值 数值型

### 5. `Snap.is(o, type)`
> `Snap` 提供的用于代替 `typeof` 的操作，判断一个值是否是某一类型

- 参数

    `o` 任何对象或原始值  
    `type` 字符串 类型名，如 `string`，`function`，`number` 等

- 返回值

  如果给定的 `o` 是 给定的 `type` 类型，则返回为真 布尔型

### 6. `Snap.snapTo(values, value, [tolerance])`
> 需要调整的值通过给定值调整到给定栅格

- 参数  

	`values` 数组 或 数值 给定值的数组或者栅格每步的数值  
	`value` 数值 需要调整的值  
	`tolerance` 数值 达到距离目标值的最大距离将触发`snap`  

- 返回值  

	调整后的值 数值型

### 7. `Snap.getRGB(color)`
> 把颜色字符串解析为一个RGB对象

- 参数

	`color` 字符串 符合以下格式的颜色值：  

		· 具体颜色值，如red，white 等；
		· #··· 简写的十六进制颜色值，如#000；
		· #······ 全写的十六进制颜色值，如#000000；
		· rgb(···，···，···) 通过rgb表示的颜色值，如黑色，rgb(0, 0, 0)；
		· rgba(···，···，···, ···) 带有透明度的rgb颜色值；
		· rgb(···%，···%，···%)
		· rgba(···%，···%，···%, ···%)
		· hsb()
		· hsba()
		· hsl()
		` hsla()

- 返回值  
	rgb对象 对象 具体格式如下：

		{
			r: 数值
			g: 数值
			b: 数值
			hex: 字符串 HTML颜色值
			opacity: 数值 透明度
			error: 布尔型 如果给定的字符串不能被解析，则为真
		}

### 8. `Snap.hsb(h, s, b)`
> 把HSB值转换为十六进制表示的颜色值

- 参数

	`h` 数值 色相
	`s` 数值 饱和度  
	`b` 数值 具体值或亮度

- 返回值
	
	十六进制表示的颜色值 字符串

### 9. `Snap.hsl(h, s, l)`
>把HSL值转化为十六进制表示的颜色值

 - 参数

	`h` 数值 色相  
	`s` 数值 饱和度  
	`l` 数值 亮度

- 返回值
	
	十六进制表示的颜色值 字符串

### 10. `Snap.rgb(r, g, b)`
>把HSL值转化为十六进制表示的颜色值

 - 参数

	`r` 数值   
	`g` 数值   
	`b` 数值 

- 返回值
	
	十六进制表示的颜色值 字符串

### 11. `Snap.color(clr)`
> 把颜色字符串解析为一个对象

- 参数
	
	`clr` 字符串 具体格式参考 `Snap.getRGB()`

- 返回值
	
	对象 具体格式参考 `Snap.getRGB()`

### 12. `Snap.hsb2rgb(h, s, v)`
> 把一个 `HSB` 颜色值转换成一个 `RGB` 对象

- 参数
	
	`h` 数值型 色调    
	`s` 数值型 饱和度  
	`b` 数值型 亮度

- 返回值  

	`RGB` 对象，格式如下  

		{  
			r 数值型 红色值  
			g 数值型 绿色值
			b 数值型 蓝色值 
			hex 字符型 #······ 格式的颜色值
		}

### 13. `Snap.hsl2rgb(h, s, l)`
> 把一个 `HSL` 值转换成一个 `RGB` 对象

- 参数

	`h` 数值型 色调    
	`s` 数值型 饱和度  
	`l` 数值型 明度

- 返回值  

	`RGB` 对象，格式如下  

		{  
			r 数值型 红色值  
			g 数值型 绿色值
			b 数值型 蓝色值 
			hex 字符型 #······ 格式的颜色值
		}

### 14. `Snap.rgb2hsb(r, g, b)`
> 把一个 `RGB` 值转换成一个 `HSB` 对象

- 参数

	`r` 数值型 红色值  
	`g` 数值型 绿色值  
	`b` 数值型 蓝色值

- 返回值  

	`HSB` 对象，格式如下  

		{  
			h 数值型 色调    
			s 数值型 饱和度  
			b 数值型 亮度
		}

### 15. `Snap.rgb2hsl(r, g, b)`
> 把一个 `RGB` 值转换成一个 `HSL` 对象

- 参数

	`r` 数值型 红色值  
	`g` 数值型 绿色值  
	`b` 数值型 蓝色值

- 返回值  

	`HSL` 对象，格式如下  

		{  
			h 数值型 色调    
			s 数值型 饱和度  
			b 数值型 明度 
		}

### 16. `Snap.parsePathString(parseString)`
> 工具方法，将给定的路径字符串解析为一个路径区段的数组

- 参数 

 	`pathString` 字符串或数组 路径字符串或者路径区段数组，后者将直接返回

- 返回值

	路径区段数组 数组

### 17. `Snap.parseTransforｍString(TString)`
> 工具方法，将给定的变化字符串解析为一个变化数组

- 参数 

	`TString` 字符串或者数组  变化字符串或者变换数组，后者将直接返回

- 返回值  
  
	变化数组 数组

### 18. `Snap.select(query)` 
> 通过 `CSS` 选择器来包裹一个 `DOM` 元素，使其具有 `Elememnt` 的方法

- 参数

	`query` 字符串 元素的 `CSS` 选择器

- 返回值
	
	返回当前元素 元素

### 19. `Snap.selectAll(query)`
> 通过 `CSS` 选择器来包裹多个 `DOM` 元素，使其具有 `Elememnt` 的方法

- 参数

	`query` 字符串 元素的 `CSS` 选择器

- 返回值
	
	返回当前元素 元素


### 20. `Snap.animation(attr, duration, [easing],[callback])`
> 创建一个动画对象

- 参数

	`attr` 对象 最终目标的属性  
	`duration` 数值型 动画持续时间，单位 毫秒
	`easing` 函数 `mina` 缓动函数或用户自定义 
	`callback` 函数 动画结束后执行的回调函数

- 返回值

	动画对象 对象

### 21. `Snap.animate(from, to, setter, duration, [easing], [callback])`
> 通过运行一个函数将动画从一个数值运行到另一个数值

- 参数

	`from` 数值型或数组 数值或者多个数值组成大数组  
	`to` 数值型或数组 数值或者多个数值组成大数组  
	`setter` 函数 接受一个数值参数的函数
	`duration` 数值型 动画持续时间，单位 毫秒
	`easing` 函数 `mina` 缓动函数或用户自定义 
	`callback` 函数 动画结束后执行的回调函数

- 返回值

	`mina` 格式的动画对象 对象 具体如下：
		
		{
			id 字符串 动画id 你可以认为它是只读的
			duration 函数 获取或设置的动画时间
			easing 函数 缓动函数
			speed 函数 获取或设置的动画速度
			status 函数 获取或设置的动画状态
			stop 函数 停止动画
		}

- 用法

		var rect = Snap().rect(0, 0, 10, 10);
		Snap.animate(0, 10, function (val) {
		    rect.attr({
		        x: val
		    });
		}, 1000);
		// 类似于
		rect.animate({x: 10}, 1000);



### 22. `Snap.fragment(varargs)`
> 利用给定元素元素列表或字符串创建一个 `DOM`片段

- 参数

	`varargs` 任意值 `SVG` 字符串

- 返回值
	
	`Fragment`

### 23. `Snap.ajax(...)`
> `Ajax` 的简单实现

- 参数

	`url` 字符串 URL  
	`postData` 对象或字符串 `post` 请求的数据  
	`callback` 函数 回调函数
	`scope` 对象 回调函数的作用域

	或者

	`url` 字符串 URL  
	`callback` 函数 回调函数
	`scope` 对象 回调函数的作用域
	
- 返回值
	
	`XMLHttpRequest`对象


### 24. `Snap.load(url, callback, [scope])`
> 加载外部 `SVG` 文件作为 `Fragment`

- 参数

	`url` 
	`callback`
	`scope`


### 25. `Snap.getElementByPoint(x, y)`
> 返回指定点上最顶层的元素

- 参数
	
	`x` 数值型 点的 `x` 坐标  
	`y` 数值型 点的 `y` 坐标  

- 用法

		Snap.getElementByPoint(mouseX, mouseY).attr({stroke: "#f00"});

### 26. `Snap.plugin(f)`
> `Snap` 插件方法

- 参数

	`f` 函数
 
- 用法 

		Snap.plugin(function (Snap, Element, Paper, global, Fragment) {
		    Snap.newmethod = function () {};
		    Element.prototype.newmethod = function () {};
		    Paper.prototype.newmethod = function () {};
		});



### 27. `Snap.Matrix()`
> 矩阵的构造函数，扩展它有一定风险。创建矩阵请使用 `Snap.matrix`

### 28. `Snap.matrix(...)`
> 实用方法。通过给定的参数返回一个矩阵

- 参数

	`a` 数值型  
	`b` 数值型  
	`c` 数值型  
	`d` 数值型  
	`e` 数值型  
	`f` 数值型  

	或者
		
	`svgMatrix` 

- 返回值

	构建的矩阵 对象



### 29. `Snap.parse(svg)`
> 解析 `SVG` 片段，并且将其转换成 `Fragment`

- 参数

	`svg` 字符串 svg字符串

- 返回值

	`Fragment`




### 30. `Snap.filter.blur(x, [y])`
> 返回 `blur` 滤镜的 `SVG` 字符串

- 参数

	`x` 数值型 水平方向上`blur`的大小 单位 `px`  
	`y` 数值型 水平方向上`blur`的大小 单位 `px`  

- 返回值

	滤镜字符串 字符串

- 用法 
		
		console.log(Snap.filter.blur(5, 10)) // <feGaussianBlur stdDeviation="5,10"/>
		
		var f = paper.filter(Snap.filter.blur(5, 10)),
	    c = paper.circle(10, 10, 10).attr({
	        filter: f
	    });


### 31. `Snap.filter.shadow(...)`
> 返回 `shadow` 滤镜的 `SVG` 字符串

- 参数  

		dx, dy, blur, color, opacity
		或者
		dx, dy, color, opacity // blur默认4
		或者
		dx, dy, color

- 用法

		var f = paper.filter(Snap.filter.shadow(0, 2, 3)),
	    c = paper.circle(10, 10, 10).attr({
	        filter: f
	    });

### 32.`Snap.filter.grayscale(amount)`
> 返回 `graycale` 滤镜的 `SVG` 字符串

- 参数

	`amount` 数值型 0~1之间的数值

### 33. `Snap.filter.sepia(amount)`
> 返回 `sepia` 滤镜的 `SVG` 字符串

- 参数

	`amount` 数值型 0~1之间的数值

### 34. `Snap.filter.saturate(amount)`
> 返回 `saturate` 滤镜的 `SVG` 字符串

- 参数

	`amount` 数值型 0~1之间的数值

### 35. `Snap.filter.hueRotate(angle)`
> 返回 `hueRotate` 滤镜的 `SVG` 字符串

- 参数

	`angle` 数值型 旋转的角度

### 36. `Snap.filter.invert(amount)`
> 返回 `invert` 滤镜的 `SVG` 字符串

- 参数

	`amount` 数值型 0~1之间的数值

### 37. `Snap.filter.brightness(amount)`
> 返回 `brightness` 滤镜的 `SVG` 字符串

- 参数

	`amount` 数值型 0~1之间的数值

### 38. `Snap.filter.contrast(amount)`
> 返回 `contrast` 滤镜的 `SVG` 字符串

- 参数

	`amount` 数值型 0~1之间的数值

----------

### 39. `Snap.path.getTotalLength(path)`
> 以像素为单位，返回指定路径的长度

- 参数

	`path` 字符串 `SVG` 路径字符串

### 40. `Snap.path.getPointAtlength(path, length)`
> 返回给定路径上给定长度的点坐标


### 41. `Snap.path.getSubpath(path, from, to)`
> 返回指定起始、结束为止长度的子路径

- 参数

	`path` 字符串 `SVG` 路径字符串    
	`from` 数值型  长度，单位 `px` 从路径起始点到该段的开始  
	`to` 数值型 长度，单位 `px` 从路径结束点到该段的结束  

- 返回值
	定义该段路径的字符串 字符串

### 42. `Snap.path.findDotsAtSegment(p1x, p1y, c1x, c1y, c2x, c2y, p2x, p2y, t)`
> 实用方法 返回指定曲线上指定位置的坐标点

- 参数

	`p1x` 数值型 曲线第一个点的 `x` 坐标  
	`p1y` 数值型 曲线第一个点的 `y` 坐标    
	`c1x` 数值型 曲线第一个锚的 `x` 坐标   
	`c1y` 数值型 曲线第一个锚的 `y` 坐标   
	`c2x` 数值型 曲线第二个锚的 `x` 坐标   
	`c2y` 数值型 曲线第二个锚的 `y` 坐标   
	`p2x` 数值型 曲线第二个点的 `x` 坐标    
	`p2y` 数值型 曲线第二个点的 `y` 坐标   
	`t` 数值型 曲线上的位置 `(0...1)`  
		
- 返回值

		{
			x: 数值型 点的 x 坐标
			y: 数值型 点的 y 坐标
			m:{
				x: 数值型 左边锚的 x 坐标
				y: 数值型 左边锚的 y 坐标
			},
			n:{
				x: 数值型 右边锚的 x 坐标
				y: 数值型 右边锚的 y 坐标
			},
			start:{
				x: 数值型 曲线开始位置的 x 坐标
				y: 数值型 曲线开始位置的 y 坐标
			},
			end:{
				x: 数值型 曲线结束位置的 x 坐标
				y: 数值型 曲线结束位置的 y 坐标
			},
			alpha: 数值型  该点在曲线上切线的角度
		}

### 42. `Snap.path.bezierBBox(...)`
> 使用方法 返回指定贝塞尔曲线的边界盒子

- 参数

	`p1x` 数值型 曲线第一个点的 `x` 坐标  
	`p1y` 数值型 曲线第一个点的 `y` 坐标   
	`c1x` 数值型 曲线第一个锚的 `x` 坐标   
	`c1y` 数值型 曲线第一个锚的 `y` 坐标   
	`c2x` 数值型 曲线第二个锚的 `x` 坐标   
	`c2y` 数值型 曲线第二个锚的 `y` 坐标   
	`p2x` 数值型 曲线第二个点的 `x` 坐标    
	`p2y` 数值型 曲线第二个点的 `y` 坐标   

	或者  

	`bez` 数组 贝塞尔曲线6个点的坐标数组  
	
- 返回值
	
	边界盒子 对象

		{
			x: 盒子左上角顶点的 x 坐标
			y: 盒子左上角顶点的 y 坐标
			x2: 盒子右下角顶点的 x 坐标
			y2: 盒子右下角顶点的 y 坐标
			width: 盒子的宽度
			height: 盒子的高度
		}

### 43. `Snap.path.isPointInsideBBox(bbox, x, y)`
> 实用方法 返回是否给定点在指定盒子当中

- 参数

	`bbox` 字符串 边界盒子  
	`x` 字符串 点的 `x` 坐标   
    `y` 字符串 点的 `y` 坐标

- 返回值

	布尔型 

### 44. `Snap.path.isBBoxIntersect(bbox1, bbox2)`
> 实用方法 返回两个盒子是否相交

- 参数

	`bbox1` 字符串 第一个盒子  
	`bbox2` 字符串 第二个盒子

- 返回值

	布尔型

### 45. `Snap.path.intersection(paht1, path2)`
> 实用方法 找出两条路径相交的坐标

- 参数

	`path1`  
	`path2`

- 返回值

		[
			{
				x: 数值型 点的 x 坐标
				y: 数值型 点的 y 坐标
				t1: 数值型 路径1片段的 t 值
				t2: 数值型 路径2片段的 t 值
				segment1: 数值型 路径1片段的顺序号
				segment2: 数值型 路径2片段的顺序号
				bez1: 数组 路径1片段的贝塞尔曲线的8个点坐标表示
				bez2: 数组 路径2片段的贝塞尔曲线的8个点坐标表示
			}
		]

### 46. `Snap.paht.isPointInside(path, x, y)`
> 实用方法 返回给定点是否在指定闭合路径内部

- 参数  

	`path` 字符串 路径字符串  
	`x` 数值型 给定点的横坐标
	`y` 数值型 给顶点的纵坐标
	
- 注意 `fill` 模式不影响这个方法的结果

- 返回值

	布尔型

### 47. `Snap.path.getBBox(path)`
> 实用方法 返回指定路径的边界盒子

- 参数

	`path` 字符串 路径字符串

- 返回值

	盒子边界信息对象 对象
	具体如下  

		{
			x 数值型 盒子左上角顶点横坐标
			y 数值型 盒子左上角顶点纵坐标
			x2 数值型 盒子右下角顶点横坐标
			y2 数值型 盒子右下角顶点纵坐标
			width 数值型 盒子宽度
			height 数值型 盒子高度
		}


### 48. `Snap.path.toRelative(path)`
> 实用方法 将指定路径的坐标点转换为相对值

- 参数

	`path` 字符串 路径字符串

- 返回值
	
	转换成相对值的路径字符串 字符型

### 49. `Snap.path.toAbsolute(path)`
> 实用方法 将指定路径的坐标点转换成绝对值

- 参数 

	`path` 字符串 路径字符串

- 返回值
	
	转换成绝对值的路径字符串 字符型

### 50. `Snap.path.toCubic(pathString)`
> 实用方法 将指定路径转换为一个新的所有片段用三次贝塞尔曲线表示的路径

- 参数 

	`pathString` 字符串 或 数组 路径字符串或者 片段数组

- 返回值

	路径片段数组 数组

### 51. `Snap.path.map(path, matrix)`
> 将指定路径字符串按住矩阵进行转换

- 参数 

	`path` 字符串 路径字符串
	`matrix` 对象 矩阵 详见 `Matrix`

- 返回值

	转换后的路径字符串 字符串

----------
# Set
----------
### 1. `Set.push()`
> 添加一个元素到集合

- 返回值

	添加的元素 `Element`

### 2. `Set.pop()`
> 从集合中删除一个元素

- 返回值

	删除的元素 `Element`

### 3. `Set.forEach(callback, thisArg)`
> 为集合中的每一个元素执行给定的函数，如果函数返回 `false`,则停止循环

- 参数

	`callback` 函数 需要执行的函数  
	`thisArg` 对象 `callback`的上下文对象

- 返回值

	集合对象 对象

### 4. `Set.aniamte(...)`
> 给集合中的每一个元素同步执行动画
- 用法

		
		// 对集合中的所有元素执行半径为10的动画
		set.animate({r: 10}, 500, mina.easein);
		// or
		// animate first element to radius 10, but second to radius 20 and in different time
		// 给第一个元素执行半径为10动画时间为500毫秒的动画，但是给第二个元素执行半径为20动画时间为1500毫秒的动画
		set.animate([{r: 10}, 500, mina.easein], [{r: 20}, 1500, mina.easein]);

### 5. `Set.bind(...)`
> 指定如何处理特定属性时应用到一个集合

- 参数

	`attrs` 字符串 属性名
	`callback` 函数 需要执行的函数

	或者

	`attrs` 字符串 属性名
	`element` 元素 对集合中指定的元素应用指定的属性


	或者

	`attrs` 字符串 属性名
	`element` 元素 对集合中指定的元素应用指定的属性
	`eattr` 字符串 attribute on the element to bind the attribute to

### todo

- 返回值
	
	集合对象 对象	
			
### 6. `Set.clear()`
> 移除结合中的所有元素

### 7. `Set.splice(index, count, [insertion])`
> 从集合中移除一定范围的 `element`

- 参数

	`index` 数值型 待删除的位置
	`count` 数值型 待移除的 `element` 数量
	`insertion...` 对象 待插入的 `element` // 替换移除的元素

### 8. `Set.exclude(element)`
> 从集合中移除指定`element`

-  参数

	`element` 对象 待移除的 `elment`

- 返回值

	是否移除 布尔值

----------
# Matrix
----------

### 1. `Matrix.add(...)`
> 将指定的矩阵添加到现有的矩阵当中

- 参数

	`a` 数值型  
	`b` 数值型  
	`c` 数值型  
	`d` 数值型  
	`e` 数值型  
	`f` 数值型  

	或者

	`martix` 对象 

### 2. `Matrix.invert()`
> 返回当前矩阵翻转后的矩阵

- 返回值

	返回当前矩阵翻转后的矩阵 对象


### 3. `Matrix.clone()`
> 返回当前矩阵的克隆矩阵

- 返回值

	返回当前矩阵的克隆矩阵 对象

### 4. `Matrix.translate(x, y)`
> 变换矩阵 偏移

- 参数

	`x` 数值型 水平方向的偏移距离  
	`y` 数值型 垂直方向的偏移距离

### 5. `Matrix.scale(x, [y], [cx], [cy])`
> 变换矩阵 缩放

- 参数

	`x` 数值型 水平方向的偏移距离  
	`y` 数值型 垂直方向的偏移距离

### 6. `Matrix.rotate(a, x, y)`
> 变换矩阵 旋转

- 参数

	`a` 数值型 旋转的角度 deg  
	`x` 数值型 指定旋转点的横坐标  
	`y` 数值型 指定旋转点的纵坐标  

### 7. `Matrix.x(x, y)`
> 返回指定点经过矩阵变换后的 `x` 坐标

### 8. `Matrix.y(x, y)`
> 返回指定点经过矩阵变换后的 `y` 坐标

### 9. `Matrix.determinant(x, y)` // determinant 行列式
> 找出指定矩阵的行列式

- 返回值

	行列式 数值型

### 10. `Matrix.split()`
> 分割矩阵为基本变换

- 返回值

	具体格式如下：
		
		dx : 数值型  x 方向偏移大小
		dy : 数值型  y 方向偏移大小
		scaleX : 数值型  x 方向缩放大小
		scaleY : 数值型  y 方向缩放大小
		shear : 数值型  剪切
		rotate : 数值 旋转角度
		isSimple : 布尔值 是否可以通过简单转换来表示
		
		
### 11. `Matrix.toTransformString()`
> 返回指定矩阵的变换字符串

- 返回值 

	变换字符串 字符型

----------
# Element

----------

### 1. `Element.node(x, y, width, height, refX, refY)`
> 提供一个 `DOM` 对象的引用，以便利用户进行事件处理或其它处理

- 用法
		
		// 在坐标点10，10处画一个半径为10的圆，同时绑定点击事件，点击后填充为红色
		var c = paper.circle(10, 10, 10);
		c.node.onclick = function () {
		    c.attr("fill", "red");
		};

### 2. `Element.type(tstr)`
> 给定元素的 `SVG` 标签名

### 3. `Element.attr(...)`
> 获取或设置元素的属性

- 参数

	`param` 字符串 属性名  
	`params` 对象 包含键值对的属性对象

- 返回值
	
	属性值 字符串型 或者 当前元素 `Elememt`

- 用法

		el.attr({
		    fill: "#fc0",
		    stroke: "#000",
		    strokeWidth: 2, 
		    "fill-opacity": 0.5,
		    width: "*=2" 
		});
		console.log(el.attr("fill")); // #fc0

### 4. `Element.getBBOX()`
> 返回指定元素的边界框描述

- 返回值
	元素的边界框描述，具体如下：
	

		{
			cx: 数值型 中心点 x 坐标
			cy: 数值型 中心点 y 坐标
			h: 数值型 高
			height:	数值型 高
			path: 字符串 指定元素的路径命令
			r0:	数值型 完全封闭的盒子圆半径
			r1: 数值型 能闭合的最小圆半径
			r2: 数值型 能闭合的最大圆半径
			vb: 字符串 作为视窗盒子的命令
			w: 数值型 宽
			width: 数值型 宽
			x2: 数值型 右边的 x 左边
			x: 数值型 左边的 y 左边
			y2: 数值型 右边的 x 左边
			y: 数值型 左边的 y 左边
		}

### 5. `Element.transform(tstr)`
> 获取或设置指定元素的变换

- 参数
	
	`tstr` 字符串 Snap或SVG格式的变化字符串  
- 返回值
	
	当前元素 `Element`  
	或者  
	对象 具体描述如下	
		
		{
			string： 字符串 转换字符串
			globalMatrix: 矩阵 应用在当前元素或者其父元素上的变化矩阵
			localMatrix: 矩阵 只应用在当前元素的变化矩阵
			diffMatrix: 矩阵 全局与本地矩阵之间不同的差异矩阵
			global: 字符串 全局变化字符串
			local: 字符串 当前变化字符串
			toString: 函数 返回当前属性的字符串
		}	 


### 6. `Element.parent()`
> 返回当前元素的父元素  

- 返回值

	当前元素的父元素 `element`

### 7. `Element.append(el)`
> 把指定的元素添加到当前元素的末尾。 `el` 作为子元素添加到 `Element` 内部的最后面

- 参数

	`el` 元素 或 集合 需要添加的元素

- 返回值

	父元素 `element`

### 8. `Element.add()`
> 同 `Element.append(el)`

### 9. `Element.appendTo(el)`
> 把当前元素添加到指定元素的末尾。 `Element` 作为子元素添加到 `el` 内部的最后面

- 参数

	`el` 元素 被添加元素的父元素

- 返回值

	父元素 `element`

### 10. `Element.prepend(el)`
> 把指定元素添加到的前部。 `el` 作为子元素添加到 `Element` 内部的最前面

- 参数

	`el` 元素  需要添加的元素

- 返回值

	父元素 `element`

### 11. `Element.prependTo(el)`
> 把当前元素添加到指定元素的前部。 `Element` 作为子元素添加到 `el` 内部的最前面

- 参数

	`el` 元素  需要添加的元素

- 返回值

	父元素 `element`

### 12. `Element.before(el)`
> 在当前元素前面插入指定元素。 `el` 元素插到 `Element` 前面

- 参数

	`el` 元素 待插入的元素

- 返回值 

	父元素 `element`

### 13. `Element.after(el)`
> 在当前元素后面插入指定元素。 `el` 元素插到 `Element` 后面

- 参数

	`el` 元素 待插入的元素

- 返回值 

	父元素 `element`

### 14. `Element.insertBefore(el)`
> 把当前元素插入到指定元素前面。 `Element` 元素插到 `el` 前面

- 参数

	`el` 元素 待插入的元素

- 返回值 

	父元素 `element`

### 15. `Element.insertAfter(el)`
> 把当前元素插入到指定元素后面。 `Element` 元素插到 `el` 后面

- 参数

	`el` 元素 待插入的元素

- 返回值 

	父元素 `element`

### 16. `Element.remove()`
> 从 `DOM` 移除当前元素

- 返回值

	被移除的元素 元素

### 17. `Element.select(query)`
> 匹配一个 `CSS` 选择器的内嵌元素

- 参数 

	`query` 字符串  CSS 选择器
- 返回值

	选择器查询结果 `Element`

### 18. `Element.select(query)`
> 匹配所有 `CSS` 选择器的内嵌元素

- 参数

	`query` 字符串 CSS 选择器
- 返回值

	选择器查询的结果 集合（`set`）或者 对象

### 19. `Element.asPX(attr, [value])`
> 返回当前元素指定属性的 `px` 值

- 参数

	`attr` 字符串 属性名  
	`value` 字符串 属性值

- 返回值  

	返回查询结果 `element`

### 20. `Element.use()`
> 创建一个连接到当前元素的 `<use>` 元素 

- 返回值

	返回 `<use>` 元素

### 21. `Element.clone()`
> 创建一个当前元素的克隆元素，并插入到当前元素之后

- 返回值

	克隆的元素 `element`

### 22. `Element.toDefs()`
> 移动元素到 `<defs>` 区域

- 返回值

	当前元素 `element`

### 23. `Element.pattern()`
> 已废弃 请使用 `Element.toPattern()`

### 24. `Element.toPattern(x, y, width, height)`
> 利用当前元素创建一个 `pattern` 元素，创建此元素必须指定该元素的矩形区域

- 参数

	`x` 字符串或数值  
	`y` 字符串或数值  
	`width` 字符串或数值  
	`height` 字符串或数值  

- 返回值

	返回 `<pattern>` 元素

- 用法


	可以把 `pattern` 作为 `fill` 属性的值来使用 

		var p = paper.path("M10-5-10,15M15,0,0,15M0-5-20,15").attr({
		        fill: "none",
		        stroke: "#bada55",
		        strokeWidth: 5
		    }).pattern(0, 0, 10, 10),
		    c = paper.circle(200, 200, 100);
		c.attr({
		    fill: p
		});

### 25. `Element.marker(x, y, width, height, refX, refY)`
> 利用当前元素创建一个 `<marker>` 元素，创建此元素必须指定矩形的边界和参考点

- 参数

	`x` 字符串或数值  
	`y` 字符串或数值  
	`width` 字符串或数值  
	`height` 字符串或数值
	`refX` 字符串或数值  
	`refY` 字符串或数值  
	
	`<maker>` 元素需要配合 `marker-start`，`marker-end`，`marker-mid`，`maker` 等属性使用。`marker` 属性可以替换路径上任意的点；`marker-mid` 可以替换路径上除了起始点和结束点意外的任意点
	
- 返回值
	
	返回 `<marker>` 元素 `element`

### 26. `Element.inAnim()`
> 返回一个能够操纵当前元素动画的集合

- 返回值

	对象，具体格式如下：
	
		{
			anim 对象 动画对象
			mina 对象 mina 对象
			curStatus 数值 动画状态，0-1，0表示刚刚开始，1表示刚刚结束
			status 函数 获取或设置动画的状态
			stop 函数 停止动画
		}

### 27. `Element.stop()`
> 停止当前元素的所有动画

- 返回值

	当前元素 `element`

### 28. `Element.animate(attrs, duration, [easing], [callback])`
> 当前元素运动指定属性的动画

- 参数

	`attrs`  对象 目标属性的键值对  
	`duration` 数值 动画持续时间 单位 毫秒  
	`easing` 函数 `mina` 函数或用户自定义缓动函数  
	`callback` 函数 动画执行完毕的回调函数  

- 返回值

	当前元素 `element`

### 29. `Element.data(key, [value])`
> 增加或取回指点键名的键值

- 参数

	`key` 字符串 存储数据关键字  
	`value` 任意值 存储的值

- 返回值

	如果 `value` 参数存在，则将对应 `key` 键值设为 `value`；如果 `value` 参数不存在，则获取对应 `key` 已经存在的数据

- 用法

		for (var i = 0, i < 5, i++) {
		    paper.circle(10 + 15 * i, 10, 10)
		         .attr({fill: "#000"})
		         .data("i", i)
		         .click(function () {
		            alert(this.data("i"));
		         });
		}

### 30. `Element.removeData([key])`
> 移除当前元素指定关键字的值，如果不指定关键字，则移除当前元素所有 `data` 数据

- 参数

	key 字符串 关键字
- 返回值

	当前元素 `element`


### 31. `Element.outerSVG()`
> 返回当前元素的 `SVG` 代码，类似于 `HTML` 中的 `outerHTML`

- 返回值
	
	当前元素的 `SVG` 代码

### 32. `Element.toString()`
> 参考 `Element.outerSVG()`

### 33. `Element.innerSVG()`
> 返回当前元素内容的 `SVG` 代码，类似于 `HTML` 中的 `innerHTML`


- 返回值
	
	当前元素内容的 `SVG` 代码


### 33. `Element.addClass(value)`
> 给 `Element` 添加指定的 `Class`

- 参数

	`value` 字符串 `class` 名或者多个用空格隔开的 `class` 名

- 返回值

	原元素 `element`

### 34. `Element.removeClass(value)`
> 给 `Element` 移除指定的 `Class`

- 参数

	`value` 字符串 `class` 名或者多个用空格隔开的 `class` 名

- 返回值

	原元素 `element`

### 35. `Element.hasClass(value)`
> 判断一个 `Element` 是否具有某个指定的 `class`

- 参数

	`value` 字符串 `class` 名

- 返回值

	布尔值

### 36. `Element.toggleClass(value, flag)`
> 根据 `flag`，对一个 `Element`，添加或移除 一个或多个 指定的 `class`

- 参数

	`value` 字符串 `class` 名或者多个用空格隔开的 `class` 名  
	`flag` 布尔值 是否增加或移除的标记

- 返回值 

	原`element` `element`




----------
# 事件
----------

### 37. `Element.click(handler)`
> 给指定元素添加指定点击事件

### 38. `Element.unclick(handler)`
> 给指定元素移除指定点击事件

### 39. `Element.dbclick(handler)`

### 40. `Element.undbclick(handler)`

### 41. `Element.mousedown(handler)`

### 42. `Element.unmousedown(handler)`

### 43. `Element.mousemove(handler)`

### 44. `Element.unmousemove(handler)`

### 45. `Element.mouseout(handler)`

### 46. `Element.unmouseout(handler)`

### 47. `Element.mouseover(handler)`

### 48. `Element.unmouseover(handler)`

### 49. `Element.mouseup(handler)`

### 50. `Element.unmouseup(handler)`

### 51. `Element.touchstart(handler)`

### 52. `Element.untouchstart(handler)`

### 53. `Element.touchmove(handler)`

### 54. `Element.untouchmove(handler)`

### 55. `Element.touchend(handler)`

### 56. `Element.untouchend(handler)`

### 57. `Element.touchcancel(handler)`

### 58. `Element.untouchcancel(handler)`

### 59. `Element.hover(f_in, f_out, [incontext], [ocontent])`

### 60. `Element.unhover(f_in, f_out)`

### 61. `Element.drag(onmove, onstart, onend, [mcontent], [scontent], [econtent])`

# todo

### 62. `Element.getTotalLength()`

### 63. `Element.getPointAtLength(legnth)`

### 64. `Element.getSubpath(from, to)`


----------

# `Fragment`
----------

### 1. `Fragment.select()`
> 参考 `Element.select()`

### 2. `Fragment.selectall()`
> 参考 `Element.selectall()`	


----------
# `Paper`
----------

### 1. `Paper.el(name, attr)`
> 在 `Paper` 中创建一个给定名字和属性的元素

- 参数

	`name` 字符串   
	`attr` 对象 

- 返回值

	当前元素 `element`

- 用法
		
		// 三种不同创建方式
		var c = paper.circle(10, 10, 10); 

		var c = paper.el("circle").attr({
		    cx: 10,
		    cy: 10,
		    r: 10
		});
		
		var c = paper.el("circle", {
		    cx: 10,
		    cy: 10,
		    r: 10
		});


		// 创建超链接
		var a = paper.el("a",{
			"xlink:href":"https://google.com"
		})
		a.add(c) 

### 2. `Paper.rect(x, y, width, height, [rx], [ry])`
> 绘制矩形

- 参数 

	`x` 数值型 左上角顶点 `x` 坐标  
	`y` 数值型 左上角顶点 `y` 坐标  
	`width` 数值型 宽度  
	`height` 数值型 高度  
	`rx` 数值型 水平圆角半径 默认值 `0`  
	`ry` 数值型 垂直圆角半径 默认值 `0` 或者 `rx` 	


- 返回值 

	创建的矩形 对象

### 2. `Paper.circle(x, y, r)`
> 绘制圆

- 参数

	`x` 原点 `x` 坐标  
	`y` 原点 `y` 坐标  
	`r` 半径

- 用法

		// 绘制一个圆心在 50，50 半径为40的圆
		var c = paper.circle(50, 50, 40);

- 返回值

	绘制的圆 对象

### 3. `Paper.image(src, x, y, width, height)`
> 把图片绘制到面上

- 参数

	`src` 图片的 `URI` 地址   
	`x` `x` 偏移位置  
	`y` `y` 偏移位置   
	`width` 图片的宽   
	`height` 图片的高

- 返回值

	图片元素 对象
	
	或者

	图片类型的 `Snap Element` 对象 
	
- 用法

		var c = paper.image("apple.png", 10, 10, 80, 80);
		// 图片资源可以使用外链？跨域？
	
### 4. `Paper.ellipse(x, y, rx, ry)`
> 绘制一个椭圆

- 参数

	`x`
	`y`
	`rx`
	`ry`

- 返回值

	绘制的椭圆 对象

- 用法

		var c = paper.ellipse(50, 50, 40, 20);

### 5. `Paper.path([pathString])`
> 利用给定的路径字符串创建一个 `<path>` 元素

- 参数

	`pathString` 字符串 `SVG`格式的路径字符串

# 补充Todo

- 用法
		
		// 绘制一条线段
		var c = paper.path("M10 10L90 90");
	
### 6. `Paper.g([varargs])`
> 创建一组元素
- 参数
	
	`varargs` 嵌套在组内的元素


- 返回值

	一组元素 对象

- 用法 

		var c1 = paper.circle(),
	    c2 = paper.rect(),
	    g = paper.g(c2, c1); // note that the order of elements is different

		或者
	
		var c1 = paper.circle(),
    	c2 = paper.rect(),
    	g = paper.g();
		g.add(c2, c1);

### 7. `Paper.group()`
> 参考 `Paper.g([varargs])`

### 8. `Paper.svg(x, y, ,width, height, vbx, vby, vbw, vbh)`
> 创建一个嵌套的 `SVG` 元素

- 参数
 
	`x` 数值型 元素的 `X`    
	`y` 数值型 元素的 `Y` 
	`width` 数值型 元素的宽度  
	`height` 数值型 元素的高度 
	`vbx` 数值型 元素的视图盒的 `X`   
	`vby` 数值型 元素的视图盒的 `Y` 
	`vbw` 数值型 元素的视图盒的宽度 
	`vbh` 数值型 元素的视图盒的高度  

- 返回值

	`svg` 元素 对象

### 9. `Paper.mask()`
> 表现与 `Paper.g()`，除了它是 `mask` 

- 返回值

	`mask` 元素 对象

### 10. `Paper.ptrn(x, y, ,width, height, vbx, vby, vbw, vbh)`
> 表现与 `Paper.g()`，除了它是 `pattern` 


- 参数
 
	`x` 数值型 元素的 `X`    
	`y` 数值型 元素的 `Y` 
	`width` 数值型 元素的宽度  
	`height` 数值型 元素的高度 
	`vbx` 数值型 元素的视图盒的 `X`   
	`vby` 数值型 元素的视图盒的 `Y` 
	`vbw` 数值型 元素的视图盒的宽度 
	`vbh` 数值型 元素的视图盒的高度  

- 返回值

	`pattern` 元素 对象

### 11. `Paper.use(...)`
> 创建一个 `<use>` 元素

- 参数

	`id` 字符串 链接到元素的 `id`
	
	或者 
	
	`id` `element` 需要连接的元素

- 返回值

	`<use>` 元素 对象

### 12. `Paper.text(x, y, text)`
> 绘制一个文字字符串

- 参数

	`x` 数值型 坐标的 `x`  
	`y` 数值型 坐标的 `y` 
	`text` 字符串或者数组 需要绘制的文字字符串 或者 通过 `<tspan>` 分开的嵌套的字符串数组

- 返回值

	`text` 元素 对象

- 用法

			var t1 = paper.text(50, 50, "Snap");
			var t2 = paper.text(50, 50, ["S","n","a","p"]);
			// Text path usage
			t1.attr({textpath: "M10,10L100,100"});
			// or
			var pth = paper.path("M10,10L100,100");
			t1.attr({textpath: pth});  

### 13. `Paper.line(x1, y1, x2, y2)`
> 绘制一条线

- 参数

	`x1` 数值型 开始位置的 `x` 坐标  
	`y1` 数值型 开始位置的 `y` 坐标  
	`x2` 数值型 结束位置的 `x` 坐标  
	`y2` 数值型 结束位置的 `y` 坐标

- 返回值

	`line` 元素  对象

- 用法

		var t1 = paper.line(50, 50, 100, 100);

### 14. `Paper.polyline(...)`
> 绘制折线

- 参数

	`points` 数组 数个点的坐标的数据  
	`varargs`  数个点的坐标

- 返回值

	`polyline` 元素 对象

- 用法

		var p1 = paper.polyline([10, 10, 100, 100]);
		var p2 = paper.polyline(10, 10, 100, 100);

### 15. `Paper.polygon(...)`
> 绘制多边形 

- 参数 
	
	参考 `Paper.polyline(...)`

### 16. `Paper.gradient(gradient)`
> 创建一个渐变元素 // 渐变元素作为其他图形的 `fill` 属性的填充

- 参数

	`gradient` 字符串 渐变描述
	
	线性渐变描述具有如下格式： `<type>(<coords>)<color>`。其中，`<type>` 分为 线性（`liner`） 和 径向（`radial`）。`L`, `R` 是绝对坐标地址，`l`，`r`是相对坐标地址。线性用`x1, y1, x2, y2` ； 径向 `cx, cy, r, fx, fy`，`fx, fy`是可选的相对于圆心的焦点。颜色用破折号连接，如`#fff-#000-#0f0`，每个颜色都可以有偏移，可以使用 `:` 标记，如`#fff:15-#000-#0f0`

- 返回值

	`gradient` 元素 对象

- 用法

		var g = paper.gradient("l(0, 0, 1, 1)#000-#f00-#fff");
		var g = paper.gradient("L(0, 0, 100, 100)#000-#f00:25-#fff");
		var g = paper.gradient("r(0.5, 0.5, 0.5)#000-#fff");
		paper.circle(50, 50, 40).attr({
		    fill: g
		});

### 17. `Paper.toString()`
> 返回 `Paper` 的 `SVG` 代码

- 返回值

	返回 `Paper` 的 `SVG` 代码 字符串

### 18. `Paper.clear()`
> 移除所有子节点，除了 `<defs>`


### 19. `Paper.filter(filstr)`
> 创建一个 `<filter>` 元素

- 参数

	`filstr` 字符串  `filstr` 滤镜相关的SVG字符串片段

- 返回值

	`element`  对象

- 注意： 推荐将 `filter` 使用在一个空的 `SVG` 元素上

- 用法

		var f = paper.filter(''),
	    c = paper.circle(10, 10, 10).attr({
	        filter: f
	    });	




----------

# mina

### 1. `mina(a, A, b, B, get, set, [easing])`
> 基本动画所需的数值

- 参数
	
	`a`    
	`B`  
	`b`    
	`B`  
	`get`  
	`set`    
	`easing` 缓动函数 默认：`mina.linear`

- 返回值

	动画描述符 对象

		{
			id	字符串 动画id
			start 字符串   
			end 字符串
			b 字符串
			s 字符串 动画状态（0...1)
			dur 字符串 动画持续时间
			spd 字符串 动画速度
			get 
			set
			easing 缓动函数 默认：`mina.linear`
			duration
			stop
			pause
			resume
			update 
		}

### 2. `mina.time()`
> 返回当前时间 相当于
> 
	function (){
		return (new Date).getTime()
	}  

### 3. `mina.getById(id)`
> 返回指定 `id` 的动画

- 参数 

	`id` 字符串 动画 `id`

### 4. `mina.linear(n)`
> 默认缓动

- 参数 

	`n` 数值型 0...1

### 5. `mina.easeout(n)`

### 6. `mina.easein(n)`

### 7. `mina.easeinout(n)`

### 8. `mina.backin(n)`

### 9. `mina.backout(n)`

### 10. `mina.elastic(n)`

### 11. `mina.bounce(n)`
# Snap
### 1. `Snap(...)`
> 创建一个面或包裹已经存在SVG元素，并返回`Element`对象

- 1.1 `Snap(width, height)`    
  `width` 数值或字符串 面的宽度  
  `height` 数值或字符串 面的高度  

- 1.2 `Snap(DOM)`
  `DOM` SVG元素 被包裹进Snap结构的元素

- 1.3 `Snap(array)`  
  `array` 数组 元素数组（返回元素集合）

- 1.4 `Snap(query)`  
  `query` 字符串 CSS查询选择器

### 2. `Snap.format(token, json)`
> 把`token`中的未知值，用`json`中的值进行替换，并返回一个格式化后的字符串  

- 参数

	`token` 字符串 需要被格式化的字符串  
	`json` 对象 对象中属性的值将被用于替换

- 用法
	
		// 下述命令将绘制一个相当于矩形形状的路径
	    paper.path(Snap.format("M{x},{y}h{dim.width}v{dim.height}h{dim['negative width']}z", {
	    	x: 10,
	   		y: 20,
	    	dim: {
	    		width: 40,
	    		height: 50,
	    		"negative width": -40
	    	}
	    }));

- 返回值
  
  格式化后的字符串 字符串型

### 3. `Snap.rad(deg)`
> 角度转换为弧度，并返回数值型的弧度值

- 参数

	`deg` 数值 角度值

- 返回值
   
    弧度值 数值型

### 4. `Snap.angle(x1, y1, x2, y2, [x3, y3])`
> 返回两个点或三个点之间的夹角度数

- 参数  

	`x1` 数值 第一个点的 `x` 坐标   
	`y1` 数值 第一个点的 `y` 坐标    
	`x2` 数值 第二个点的 `x` 坐标    
	`y2` 数值 第二个点的 `y` 坐标    
	`x3` 数值 第三个点的 `x` 坐标    
	`y3` 数值 第三个点的 `y` 坐标  

- 返回值  
  角度值 数值型

### 5. `Snap.is(o, type)`
> `Snap` 提供的用于代替 `typeof` 的操作，判断一个值是否是某一类型

- 参数

    `o` 任何对象或原始值  
    `type` 字符串 类型名，如 `string`，`function`，`number` 等

- 返回值

  如果给定的 `o` 是 给定的 `type` 类型，则返回为真 布尔型

### 6. `Snap.snapTo(values, value, [tolerance])`
> 需要调整的值通过给定值调整到给定栅格

- 参数  

	`values` 数组 或 数值 给定值的数组或者栅格每步的数值  
	`value` 数值 需要调整的值  
	`tolerance` 数值 达到距离目标值的最大距离将触发`snap`  

- 返回值  

	调整后的值 数值型

### 7. `Snap.getRGB(color)`
> 把颜色字符串解析为一个RGB对象

- 参数

	`color` 字符串 符合以下格式的颜色值：  

		· 具体颜色值，如red，white 等；
		· #··· 简写的十六进制颜色值，如#000；
		· #······ 全写的十六进制颜色值，如#000000；
		· rgb(···，···，···) 通过rgb表示的颜色值，如黑色，rgb(0, 0, 0)；
		· rgba(···，···，···, ···) 带有透明度的rgb颜色值；
		· rgb(···%，···%，···%)
		· rgba(···%，···%，···%, ···%)
		· hsb()
		· hsba()
		· hsl()
		` hsla()

- 返回值  
	rgb对象 对象 具体格式如下：

		{
			r: 数值
			g: 数值
			b: 数值
			hex: 字符串 HTML颜色值
			opacity: 数值 透明度
			error: 布尔型 如果给定的字符串不能被解析，则为真
		}

### 8. `Snap.hsb(h, s, b)`
> 把HSB值转换为十六进制表示的颜色值

- 参数

	`h` 数值 色相
	`s` 数值 饱和度  
	`b` 数值 具体值或亮度

- 返回值
	
	十六进制表示的颜色值 字符串

### 9. `Snap.hsl(h, s, l)`
>把HSL值转化为十六进制表示的颜色值

 - 参数

	`h` 数值 色相  
	`s` 数值 饱和度  
	`l` 数值 亮度

- 返回值
	
	十六进制表示的颜色值 字符串

### 10. `Snap.rgb(r, g, b)`
>把HSL值转化为十六进制表示的颜色值

 - 参数

	`r` 数值   
	`g` 数值   
	`b` 数值 

- 返回值
	
	十六进制表示的颜色值 字符串

### 11. `Snap.color(clr)`
> 把颜色字符串解析为一个对象

- 参数
	
	`clr` 字符串 具体格式参考 `Snap.getRGB()`

- 返回值
	
	对象 具体格式参考 `Snap.getRGB()`

### 12. `Snap.hsb2rgb(h, s, v)`

### 13. `Snap.hsl2rgb(h, s, l)`

### 14. `Snap.rgb2hsb(r, g, b)`

### 15. `Snap.rgb2hsl(r, g, b)`

### 16. `Snap.parsePathString(parseString)`
> 工具方法，将给定的路径字符串解析为一个路径区段的数组

- 参数 

 	`pathString` 字符串或数组 路径字符串或者路径区段数组，后者将直接返回

- 返回值

	路径区段数组 数组

### 17. `Snap.parseTransforｍString(TString)`
> 工具方法，将给定的变化字符串解析为一个变化数组

- 参数 

	`TString` 字符串或者数组  变化字符串或者变换数组，后者将直接返回

- 返回值  
  
	变化数组 数组

### 18. `Snap.select(query)` 
> 通过 `CSS` 选择器来包裹一个 `DOM` 元素，使其具有 `Elememnt` 的方法

- 参数

	`query` 字符串 元素的 `CSS` 选择器

- 返回值
	
	返回当前元素 元素

### 19. `Snap.selectAll(query)`
> 通过 `CSS` 选择器来包裹多个 `DOM` 元素，使其具有 `Elememnt` 的方法

- 参数

	`query` 字符串 元素的 `CSS` 选择器

- 返回值
	
	返回当前元素 元素


### 20. `Snap.animation(attr, duration, [easing],[callback])`
> 创建一个动画对象

- 参数

	`attr` 对象 最终目标的属性  
	`duration` 数值型 动画持续时间，单位 毫秒
	`easing` 函数 `mina` 缓动函数或用户自定义 
	`callback` 函数 动画结束后执行的回调函数

- 返回值

	动画对象 对象

### 21. `Snap.animate(from, to, setter, duration, [easing], [callback])`
> 通过运行一个函数将动画从一个数值运行到另一个数值

- 参数

	`from` 数值型或数组 数值或者多个数值组成大数组  
	`to` 数值型或数组 数值或者多个数值组成大数组  
	`setter` 函数 接受一个数值参数的函数
	`duration` 数值型 动画持续时间，单位 毫秒
	`easing` 函数 `mina` 缓动函数或用户自定义 
	`callback` 函数 动画结束后执行的回调函数

- 返回值

	`mina` 格式的动画对象 对象 具体如下：
		
		{
			id 字符串 动画id 你可以认为它是只读的
			duration 函数 获取或设置的动画时间
			easing 函数 缓动函数
			speed 函数 获取或设置的动画速度
			status 函数 获取或设置的动画状态
			stop 函数 停止动画
		}

- 用法

		var rect = Snap().rect(0, 0, 10, 10);
		Snap.animate(0, 10, function (val) {
		    rect.attr({
		        x: val
		    });
		}, 1000);
		// 类似于
		rect.animate({x: 10}, 1000);



### 22. `Snap.fragment(varargs)`
> 利用给定元素元素列表或字符串创建一个 `DOM`片段

- 参数

	`varargs` 任意值 `SVG` 字符串
- 返回值
	
	`Fragment`



### 23. `Snap.ajax(...)`
> `Ajax` 的简单实现

- 参数

	`url` 字符串 URL  
	`postData` 对象或字符串 `post` 请求的数据  
	`callback` 函数 回调函数
	`scope` 对象 回调函数的作用域

	或者

	`url` 字符串 URL  
	`callback` 函数 回调函数
	`scope` 对象 回调函数的作用域
	
- 返回值
	
	`XMLHttpRequest`对象


### 24. `Snap.load(url, callback, [scope])`
> 加载外部 `SVG` 文件作为 `Fragment`

- 参数

	`url` 
	`callback`
	`scope`


### 25. `Snap.getElementByPoint(x, y)`
> 返回指定点上最顶层的元素

- 参数
	
	`x` 数值型 点的 `x` 坐标  
	`y` 数值型 点的 `y` 坐标  

- 用法

		Snap.getElementByPoint(mouseX, mouseY).attr({stroke: "#f00"});

### 26. `Snap.plugin(f)`
> `Snap` 插件方法

- 参数

	`f` 函数 
- 用法 

		Snap.plugin(function (Snap, Element, Paper, global, Fragment) {
		    Snap.newmethod = function () {};
		    Element.prototype.newmethod = function () {};
		    Paper.prototype.newmethod = function () {};
		});



### 27. `Snap.Matrix()`
> 矩阵的构造函数，扩展它有一定风险。创建矩阵请使用 `Snap.matrix`

### 28. `Snap.matrix(...)`
> 实用方法。通过给定的参数返回一个矩阵

- 参数

	`a` 数值型  
	`b` 数值型  
	`c` 数值型  
	`d` 数值型  
	`e` 数值型  
	`f` 数值型  

	或者
		
	`svgMatrix` 

- 返回值

	构建的矩阵 对象



### 29. `Snap.parse(svg)`
> 解析 `SVG` 片段，并且将其转换成 `Fragment`

- 参数

	`svg` 字符串 svg字符串

- 返回值

	`Fragment`




### 30. `Snap.filter.blur(x, [y])`
> 返回 `blur` 滤镜的 `SVG` 字符串

- 参数

	`x` 数值型 水平方向上`blur`的大小 单位 `px`  
	`y` 数值型 水平方向上`blur`的大小 单位 `px`  


- 返回值

	滤镜字符串 字符串

- 用法 

		var f = paper.filter(Snap.filter.blur(5, 10)),
	    c = paper.circle(10, 10, 10).attr({
	        filter: f
	    });


### 31. `Snap.filter.shadow(...)`

- 参数  

		dx, dy, blur, color, opacity
		或者
		dx, dy, color, opacity // blur默认4
		或者
		dx, dy, color

- 用法

		var f = paper.filter(Snap.filter.shadow(0, 2, 3)),
	    c = paper.circle(10, 10, 10).attr({
	        filter: f
	    });

### 32.`Snap.filter.grayscale(amount)`

### 33. `Snap.filter.sepia(amount)`

### 34. `Snap.filter.saturate(amount)`

### 35. `Snap.filter.hueRotate(angle)`

### 36. `Snap.filter.invert(amount)`

### 37. `Snap.filter.brightness(amount)`

### 38. `Snap.filter.contrast(amount)`


----------

# snap路径操作
----------


### 39. `Snap.path.getTotalLength(path)`
> 以像素为单位，返回指定路径的长度

- 参数

	`path` 字符串 `SVG` 路径字符串

### 40. `Snap.path.getPointAtlength(path, length)`
> 返回给定路径上给定长度的点坐标


### 41. `Snap.path.getSubpath(path, from, to)`
> 返回指定起始、结束为止长度的子路径

- 参数

	`path` 字符串 `SVG` 路径字符串    
	`from` 数值型  长度，单位 `px` 从路径起始点到该段的开始  
	`to` 数值型 长度，单位 `px` 从路径结束点到该段的结束  

- 返回值
	定义该段路径的字符串 字符串

### 42. `Snap.path.findDotsAtSegment(p1x, p1y, c1x, c1y, c2x, c2y, p2x, p2y, t)`
> 实用方法 返回指定曲线上指定位置的坐标点

- 参数

	`p1x` 数值型 曲线第一个点的 `x` 坐标  
	`p1y` 数值型 曲线第一个点的 `y` 坐标    
	`c1x` 数值型 曲线第一个锚的 `x` 坐标   
	`c1y` 数值型 曲线第一个锚的 `y` 坐标   
	`c2x` 数值型 曲线第二个锚的 `x` 坐标   
	`c2y` 数值型 曲线第二个锚的 `y` 坐标   
	`p2x` 数值型 曲线第二个点的 `x` 坐标    
	`p2y` 数值型 曲线第二个点的 `y` 坐标   
	`t` 数值型 曲线上的位置 `(0...1)`  
		
- 返回值

		{
			x: 数值型 点的 x 坐标
			y: 数值型 点的 y 坐标
			m:{
				x: 数值型 左边锚的 x 坐标
				y: 数值型 左边锚的 y 坐标
			},
			n:{
				x: 数值型 右边锚的 x 坐标
				y: 数值型 右边锚的 y 坐标
			},
			start:{
				x: 数值型 曲线开始位置的 x 坐标
				y: 数值型 曲线开始位置的 y 坐标
			},
			end:{
				x: 数值型 曲线结束位置的 x 坐标
				y: 数值型 曲线结束位置的 y 坐标
			},
			alpha: 数值型  该点在曲线上切线的角度
		}

### 42. `Snap.path.bezierBBox(...)`
> 使用方法 返回指定贝塞尔曲线的边界盒子

- 参数

	`p1x` 数值型 曲线第一个点的 `x` 坐标  
	`p1y` 数值型 曲线第一个点的 `y` 坐标   
	`c1x` 数值型 曲线第一个锚的 `x` 坐标   
	`c1y` 数值型 曲线第一个锚的 `y` 坐标   
	`c2x` 数值型 曲线第二个锚的 `x` 坐标   
	`c2y` 数值型 曲线第二个锚的 `y` 坐标   
	`p2x` 数值型 曲线第二个点的 `x` 坐标    
	`p2y` 数值型 曲线第二个点的 `y` 坐标   

	或者  

	`bez` 数组 贝塞尔曲线6个点的坐标数组  
	
- 返回值
	
	边界盒子 对象

		{
			x: 盒子左上角顶点的 x 坐标
			y: 盒子左上角顶点的 y 坐标
			x2: 盒子右下角顶点的 x 坐标
			y2: 盒子右下角顶点的 y 坐标
			width: 盒子的宽度
			height: 盒子的高度
		}

### 43. `Snap.path.isPointInsideBBox(bbox, x, y)`
> 实用方法 返回是否给定点在指定盒子当中

- 参数

	`bbox` 字符串 边界盒子  
	`x` 字符串 点的 `x` 坐标   
    `y` 字符串 点的 `y` 坐标


### 44. `Snap.path.isBBoxIntersect(bbox, bbox2)`
> 实用方法 返回两个盒子是否相交

### 45. `Snap.path.intersection(paht1, path2)`
> 实用方法 找出两条路径相交的坐标

- 参数

	`path1`  
	`path2`

- 返回值

		[
			{
				x: 数值型 点的 x 坐标
				y: 数值型 点的 y 坐标
				t1: 数值型 路径1片段的 t 值
				t2: 数值型 路径2片段的 t 值
				segment1: 数值型 路径1片段的顺序号
				segment2: 数值型 路径2片段的顺序号
				bez1: 数组 路径1片段的贝塞尔曲线的8个点坐标表示
				bez2: 数组 路径2片段的贝塞尔曲线的8个点坐标表示
			}
		]

### 46. `Snap.paht.isPointInside(path, x, y)`
> 实用方法 返回给定点是否在指定闭合路径内部

- 注意 `fill` 模式不影响这个方法的结果


### 47. `Snap.path.getBBox(path)`
> 实用方法 返回指定路径的边界盒子

### 48. `Snap.path.toRelative(path)`
> 实用方法 将指定路径的坐标点转换为相对值

### 49. `Snap.path.toAbsolute(path)`

### 50. `Snap.path.toCubic(pathString)`
> 实用方法 将指定路径转换为一个新的所有片段用三次贝塞尔曲线表示的路径

### 51. `Snap.path.map(path, matrix)`
> 将指定路径字符串按住矩阵进行转换








----------
# Set
----------
### 1. `Set.push()`

### 2. `Set.pop()`

### 3. `Set.forEach(callback, thisArg)`

### 4. `Set.aniamte(...)`

- 用法

		// animate all elements in set to radius 10
		set.animate({r: 10}, 500, mina.easein);
		// or
		// animate first element to radius 10, but second to radius 20 and in different time
		set.animate([{r: 10}, 500, mina.easein], [{r: 20}, 1500, mina.easein]);


### 5. `Set.bind(...)`

### 6. `Set.clear()`

### 7. `Set.splice(index, count, [insertion])`
> 从集合中移除一定范围的 `element`

- 参数

	`index` 数值型 待删除的位置
	`count` 数值型 待移除的 `element` 数量
	`insertion...` 对象 待插入的 `element` // 替换移除的元素
### 8. `Set.exclude(element)`
> 从集合中移除指定`element`

-  参数

	`element` 对象 待移除的 `elment`

- 返回值

	是否移除 布尔值

----------
# Matrix

### 1. `Matrix.add(...)`
> 将指定的矩阵添加到现有的矩阵当中

- 参数

	`a` 数值型  
	`b` 数值型  
	`c` 数值型  
	`d` 数值型  
	`e` 数值型  
	`f` 数值型  

	或者

	`martix` 对象 

### 2. `Matrix.invert()`
> 返回当前矩阵翻转后的矩阵

- 返回值

	返回当前矩阵翻转后的矩阵 对象


### 3. `Matrix.clone()`
> 返回当前矩阵的克隆矩阵

- 返回值

	返回当前矩阵的克隆矩阵 对象

### 4. `Matrix.translate(x, y)`
> 变换矩阵

- 参数

	`x` 数值型 水平方向的偏移距离  
	`y` 数值型 垂直方向的偏移距离

### 5. `Matrix.scale(x, [y], [cx], [cy])`
> 变换矩阵

- 参数

	`x` 数值型 水平方向的偏移距离  
	`y` 数值型 垂直方向的偏移距离

### 6. `Matrix.rotate(a, x, y)`

### 7. `Matrix.x(x, y)`

### 8. `Matrix.y(x, y)`

### 9. `Matrix.determinant(x, y)` // determinant 行列式
> 找出指定矩阵的行列式

- 返回值

	行列式 数值型

### 10. `Matrix.split()`
> 分割矩阵为基本变换

- 返回值

	具体格式如下：
		
		dx : 数值型  x 方向偏移大小
		dy : 数值型  y 方向偏移大小
		scaleX : 数值型  x 方向缩放大小
		scaleY : 数值型  y 方向缩放大小
		shear : 数值型  剪切
		rotate : 数值 旋转角度
		isSimple : 布尔值 是否可以通过简单转换来表示
		
		
### 11. `Matrix.toTransformString()`
> 返回指定矩阵的变换字符串

- 返回值 

	变换字符串 字符型









----------


# Element

### 1. `Element.node(x, y, width, height, refX, refY)`
> 提供一个 `DOM` 对象的引用，以便利用户进行事件处理或其它处理

- 用法
		
		// 在坐标点10，10处画一个半径为10的圆，同时绑定点击事件，点击后填充为红色
		var c = paper.circle(10, 10, 10);
		c.node.onclick = function () {
		    c.attr("fill", "red");
		};

### 2. `Element.type(tstr)`
> 给定元素的 `SVG` 标签名

### 3. `Element.attr(...)`
> 获取或设置元素的属性

- 参数

	`param` 字符串 属性名  
	`params` 对象 包含键值对的属性对象

- 返回值
	
	属性值 字符串型 或者 当前元素 `Elememt`

- 用法

		el.attr({
		    fill: "#fc0",
		    stroke: "#000",
		    strokeWidth: 2, 
		    "fill-opacity": 0.5,
		    width: "*=2" 
		});
		console.log(el.attr("fill")); // #fc0

### 4. `Element.getBBOX()`
> 返回指定元素的边界框描述

- 返回值
	元素的边界框描述，具体如下：
	

		{
			cx: 数值型 中心点 x 坐标
			cy: 数值型 中心点 y 坐标
			h: 数值型 高
			height:	数值型 高
			path: 字符串 指定元素的路径命令
			r0:	数值型 完全封闭的盒子圆半径
			r1: 数值型 能闭合的最小圆半径
			r2: 数值型 能闭合的最大圆半径
			vb: 字符串 作为视窗盒子的命令
			w: 数值型 宽
			width: 数值型 宽
			x2: 数值型 右边的 x 左边
			x: 数值型 左边的 y 左边
			y2: 数值型 右边的 x 左边
			y: 数值型 左边的 y 左边
		}

### 5. `Element.transform(tstr)`
> 获取或设置指定元素的变换

- 参数
	
	`tstr` 字符串 Snap或SVG格式的变化字符串  
- 返回值
	
	当前元素 `Element`  
	或者  
	对象 具体描述如下	
		
		{
			string： 字符串 转换字符串
			globalMatrix: 矩阵 应用在当前元素或者其父元素上的变化矩阵
			localMatrix: 矩阵 只应用在当前元素的变化矩阵
			diffMatrix: 矩阵 全局与本地矩阵之间不同的差异矩阵
			global: 字符串 全局变化字符串
			local: 字符串 当前变化字符串
			toString: 函数 返回当前属性的字符串
		}	 


### 6. `Element.parent()`
> 返回当前元素的父元素  

- 返回值

	当前元素的父元素 `element`

### 7. `Element.append(el)`

### 8. `Element.add()`

### 9. `Element.appendTo(el)`

### 10. `Element.prepend(el)`

### 11. `Element.prependTo(el)`

### 12. `Element.before(el)`

### 13. `Element.after(el)`

### 14. `Element.insertBefore(el)`

### 15. `Element.insertAfter(el)`

### 16. `Element.remove()`

### 17. `Element.select(query)`
> 匹配一个 `CSS` 选择器的内嵌元素

- 参数 

	`query` 字符串  CSS 选择器
- 返回值

	选择器查询结果 `Element`

### 18. `Element.select(query)`
> 匹配所有 `CSS` 选择器的内嵌元素

- 参数

	`query` 字符串 CSS 选择器
- 返回值

	选择器查询的结果 集合（`set`）或者 对象

### 19. `Element.asPX(attr, [value])`
> 返回当前元素指定属性的 `px` 值

- 参数

	`attr` 字符串 属性名  
	`value` 字符串 属性值

- 返回值  

	返回查询结果 `element`

### 20. `Element.use()`
> 创建一个连接到当前元素的 `<use>` 元素 

- 返回值

	返回 `<use>` 元素

### 21. `Element.clone()`
> 创建一个当前元素的克隆元素，并插入到当前元素之后

- 返回值

	克隆的元素 `element`

### 22. `Element.toDefs()`
> 移动元素到 `<defs>` 区域

- 返回值

	当前元素 `element`

### 23. `Element.pattern()`
> 已废弃 请使用 `Element.toPattern()`

### 24. `Element.toPattern(x, y, width, height)`
> 利用当前元素创建一个 `pattern` 元素，创建此元素必须指定该元素的矩形区域

- 参数

	`x` 字符串或数值  
	`y` 字符串或数值  
	`width` 字符串或数值  
	`height` 字符串或数值  

- 返回值

	返回 `<pattern>` 元素

- 用法


	可以把 `pattern` 作为 `fill` 属性的值来使用 

		var p = paper.path("M10-5-10,15M15,0,0,15M0-5-20,15").attr({
		        fill: "none",
		        stroke: "#bada55",
		        strokeWidth: 5
		    }).pattern(0, 0, 10, 10),
		    c = paper.circle(200, 200, 100);
		c.attr({
		    fill: p
		});

### 25. `Element.marker(x, y, width, height, refX, refY)`
> 利用当前元素创建一个 `<marker>` 元素，创建此元素必须指定矩形的边界和参考点

- 参数

	`x` 字符串或数值  
	`y` 字符串或数值  
	`width` 字符串或数值  
	`height` 字符串或数值
	`refX` 字符串或数值  
	`refY` 字符串或数值  
	
	`<maker>` 元素需要配合 `marker-start`，`marker-end`，`marker-mid`，`maker` 等属性使用。`marker` 属性可以替换路径上任意的点；`marker-mid` 可以替换路径上除了起始点和结束点意外的任意点
	
- 返回值
	
	返回 `<marker>` 元素 `element`

### 26. `Element.inAnim()`
> 返回一个能够操纵当前元素动画的集合

- 返回值

	对象，具体格式如下：
	
		{
			anim 对象 动画对象
			mina 对象 mina 对象
			curStatus 数值 动画状态，0-1，0表示刚刚开始，1表示刚刚结束
			status 函数 获取或设置动画的状态
			stop 函数 停止动画
		}

### 27. `Element.stop()`
> 停止当前元素的所有动画

- 返回值

	当前元素 `element`

### 28. `Element.animate(attrs, duration, [easing], [callback])`
> 当前元素运动指定属性的动画

- 参数

	`attrs`  对象 目标属性的键值对  
	`duration` 数值 动画持续时间 单位 毫秒  
	`easing` 函数 `mina` 函数或用户自定义缓动函数  
	`callback` 函数 动画执行完毕的回调函数  

- 返回值

	当前元素 `element`

### 29. `Element.data(key, [value])`
> 增加或取回指点键名的键值

- 参数

	`key` 字符串 存储数据关键字  
	`value` 任意值 存储的值

- 返回值

	如果 `value` 参数存在，则将对应 `key` 键值设为 `value`；如果 `value` 参数不存在，则获取对应 `key` 已经存在的数据

- 用法

		for (var i = 0, i < 5, i++) {
		    paper.circle(10 + 15 * i, 10, 10)
		         .attr({fill: "#000"})
		         .data("i", i)
		         .click(function () {
		            alert(this.data("i"));
		         });
		}

### 30. `Element.removeData([key])`
> 移除当前元素指定关键字的值，如果不指定关键字，则移除当前元素所有 `data` 数据

- 参数

	key 字符串 关键字
- 返回值

	当前元素 `element`


### 31. `Element.outerSVG()`
> 返回当前元素的 `SVG` 代码，类似于 `HTML` 中的 `outerHTML`

- 返回值
	
	当前元素的 `SVG` 代码

### 32. `Element.toString()`
> 参考 `Element.outerSVG()`

### 33. `Element.innerSVG()`
> 返回当前元素内容的 `SVG` 代码，类似于 `HTML` 中的 `innerHTML`


- 返回值
	
	当前元素内容的 `SVG` 代码


### 33. `Element.addClass(value)`
> 给 `Element` 添加指定的 `Class`

- 参数

	`value` 字符串 `class` 名或者多个用空格隔开的 `class` 名

- 返回值

	原元素 `element`

### 34. `Element.removeClass(value)`
> 给 `Element` 移除指定的 `Class`

- 参数

	`value` 字符串 `class` 名或者多个用空格隔开的 `class` 名

- 返回值

	原元素 `element`

### 35. `Element.hasClass(value)`
> 判断一个 `Element` 是否具有某个指定的 `class`

- 参数

	`value` 字符串 `class` 名

- 返回值

	布尔值

### 36. `Element.toggleClass(value, flag)`
> 根据 `flag`，对一个 `Element`，添加或移除 一个或多个 指定的 `class`

- 参数

	`value` 字符串 `class` 名或者多个用空格隔开的 `class` 名  
	`flag` 布尔值 是否增加或移除的标记

- 返回值 

	原`element` `element`




----------
# 事件
----------

### 37. `Element.click(handler)`
> 给指定元素添加指定点击事件

### 38. `Element.unclick(handler)`
> 给指定元素移除指定点击事件

### 39. `Element.dbclick(handler)`

### 40. `Element.undbclick(handler)`

### 41. `Element.mousedown(handler)`

### 42. `Element.unmousedown(handler)`

### 43. `Element.mousemove(handler)`

### 44. `Element.unmousemove(handler)`

### 45. `Element.mouseout(handler)`

### 46. `Element.unmouseout(handler)`

### 47. `Element.mouseover(handler)`

### 48. `Element.unmouseover(handler)`

### 49. `Element.mouseup(handler)`

### 50. `Element.unmouseup(handler)`

### 51. `Element.touchstart(handler)`

### 52. `Element.untouchstart(handler)`

### 53. `Element.touchmove(handler)`

### 54. `Element.untouchmove(handler)`

### 55. `Element.touchend(handler)`

### 56. `Element.untouchend(handler)`

### 57. `Element.touchcancel(handler)`

### 58. `Element.untouchcancel(handler)`

### 59. `Element.hover(f_in, f_out, [incontext], [ocontent])`

### 60. `Element.unhover(f_in, f_out)`

### 61. `Element.drag(onmove, onstart, onend, [mcontent], [scontent], [econtent])`

# todo

### 62. `Element.getTotalLength()`

### 63. `Element.getPointAtLength(legnth)`

### 64. `Element.getSubpath(from, to)`


----------


# `Fragment`

### 1. `Fragment.select()`
> 参考 `Element.select()`


### 2. `Fragment.selectall()`
> 参考 `Element.selectall()`	








----------

# `Paper`

### 1. `Paper.el(name, attr)`
> 在 `Paper` 中创建一个给定名字和属性的元素

- 参数

	`name` 字符串   
	`attr` 对象 

- 返回值

	当前元素 `element`

- 用法
		
		// 三种不同创建方式
		var c = paper.circle(10, 10, 10); 

		var c = paper.el("circle").attr({
		    cx: 10,
		    cy: 10,
		    r: 10
		});
		
		var c = paper.el("circle", {
		    cx: 10,
		    cy: 10,
		    r: 10
		});


		// 创建超链接
		var a = paper.el("a",{
			"xlink:href":"https://google.com"
		})
		a.add(c) 

### 2. `Paper.rect(x, y, width, height, [rx], [ry])`
> 绘制矩形

- 参数 

	`x` 数值型 左上角顶点 `x` 坐标  
	`y` 数值型 左上角顶点 `y` 坐标  
	`width` 数值型 宽度  
	`height` 数值型 高度  
	`rx` 数值型 水平圆角半径 默认值 `0`  
	`ry` 数值型 垂直圆角半径 默认值 `0` 或者 `rx` 	


- 返回值 

	创建的矩形 对象

### 2. `Paper.circle(x, y, r)`
> 绘制圆

- 参数

	`x` 原点 `x` 坐标  
	`y` 原点 `y` 坐标  
	`r` 半径

- 用法

		// 绘制一个圆心在 50，50 半径为40的圆
		var c = paper.circle(50, 50, 40);

- 返回值

	绘制的圆 对象

### 3. `Paper.image(src, x, y, width, height)`
> 把图片绘制到面上

- 参数

	`src` 图片的 `URI` 地址   
	`x` `x` 偏移位置  
	`y` `y` 偏移位置   
	`width` 图片的宽   
	`height` 图片的高

- 返回值

	图片元素 对象
	
	或者

	图片类型的 `Snap Element` 对象 
	
- 用法

		var c = paper.image("apple.png", 10, 10, 80, 80);
		// 图片资源可以使用外链？跨域？
	
### 4. `Paper.ellipse(x, y, rx, ry)`
> 绘制一个椭圆

- 参数

	`x`
	`y`
	`rx`
	`ry`

- 返回值

	绘制的椭圆 对象

- 用法

		var c = paper.ellipse(50, 50, 40, 20);

### 5. `Paper.path([pathString])`
> 利用给定的路径字符串创建一个 `<path>` 元素

- 参数

	`pathString` 字符串 `SVG`格式的路径字符串

# 补充Todo

- 用法
		
		// 绘制一条线段
		var c = paper.path("M10 10L90 90");
	
### 6. `Paper.g([varargs])`
> 创建一组元素
- 参数
	
	`varargs` 嵌套在组内的元素


- 返回值

	一组元素 对象

- 用法 

		var c1 = paper.circle(),
	    c2 = paper.rect(),
	    g = paper.g(c2, c1); // note that the order of elements is different

		或者
	
		var c1 = paper.circle(),
    	c2 = paper.rect(),
    	g = paper.g();
		g.add(c2, c1);

### 7. `Paper.group()`
> 参考 `Paper.g([varargs])`

### 8. `Paper.svg(x, y, ,width, height, vbx, vby, vbw, vbh)`
> 创建一个嵌套的 `SVG` 元素

- 参数
 
	`x` 数值型 元素的 `X`    
	`y` 数值型 元素的 `Y` 
	`width` 数值型 元素的宽度  
	`height` 数值型 元素的高度 
	`vbx` 数值型 元素的视图盒的 `X`   
	`vby` 数值型 元素的视图盒的 `Y` 
	`vbw` 数值型 元素的视图盒的宽度 
	`vbh` 数值型 元素的视图盒的高度  

- 返回值

	`svg` 元素 对象

### 9. `Paper.mask()`
> 表现与 `Paper.g()`，除了它是 `mask` 

- 返回值

	`mask` 元素 对象

### 10. `Paper.ptrn(x, y, ,width, height, vbx, vby, vbw, vbh)`
> 表现与 `Paper.g()`，除了它是 `pattern` 


- 参数
 
	`x` 数值型 元素的 `X`    
	`y` 数值型 元素的 `Y` 
	`width` 数值型 元素的宽度  
	`height` 数值型 元素的高度 
	`vbx` 数值型 元素的视图盒的 `X`   
	`vby` 数值型 元素的视图盒的 `Y` 
	`vbw` 数值型 元素的视图盒的宽度 
	`vbh` 数值型 元素的视图盒的高度  

- 返回值

	`pattern` 元素 对象

### 11. `Paper.use(...)`
> 创建一个 `<use>` 元素

- 参数

	`id` 字符串 链接到元素的 `id`
	
	或者 
	
	`id` `element` 需要连接的元素

- 返回值

	`<use>` 元素 对象

### 12. `Paper.text(x, y, text)`
> 绘制一个文字字符串

- 参数

	`x` 数值型 坐标的 `x`  
	`y` 数值型 坐标的 `y` 
	`text` 字符串或者数组 需要绘制的文字字符串 或者 通过 `<tspan>` 分开的嵌套的字符串数组

- 返回值

	`text` 元素 对象

- 用法

			var t1 = paper.text(50, 50, "Snap");
			var t2 = paper.text(50, 50, ["S","n","a","p"]);
			// Text path usage
			t1.attr({textpath: "M10,10L100,100"});
			// or
			var pth = paper.path("M10,10L100,100");
			t1.attr({textpath: pth});  

### 13. `Paper.line(x1, y1, x2, y2)`
> 绘制一条线

- 参数

	`x1` 数值型 开始位置的 `x` 坐标  
	`y1` 数值型 开始位置的 `y` 坐标  
	`x2` 数值型 结束位置的 `x` 坐标  
	`y2` 数值型 结束位置的 `y` 坐标

- 返回值

	`line` 元素  对象

- 用法

		var t1 = paper.line(50, 50, 100, 100);

### 14. `Paper.polyline(...)`
> 绘制折线

- 参数

	`points` 数组 数个点的坐标的数据  
	`varargs`  数个点的坐标

- 返回值

	`polyline` 元素 对象

- 用法

		var p1 = paper.polyline([10, 10, 100, 100]);
		var p2 = paper.polyline(10, 10, 100, 100);

### 15. `Paper.polygon(...)`
> 绘制多边形 

- 参数 
	
	参考 `Paper.polyline(...)`

### 16. `Paper.gradient(gradient)`
> 创建一个渐变元素 // 渐变元素作为其他图形的 `fill` 属性的填充

- 参数

	`gradient` 字符串 渐变描述
	
	线性渐变描述具有如下格式： `<type>(<coords>)<color>`。其中，`<type>` 分为 线性（`liner`） 和 径向（`radial`）。`L`, `R` 是绝对坐标地址，`l`，`r`是相对坐标地址。线性用`x1, y1, x2, y2` ； 径向 `cx, cy, r, fx, fy`，`fx, fy`是可选的相对于圆心的焦点。颜色用破折号连接，如`#fff-#000-#0f0`，每个颜色都可以有偏移，可以使用 `:` 标记，如`#fff:15-#000-#0f0`

- 返回值

	`gradient` 元素 对象

- 用法

		var g = paper.gradient("l(0, 0, 1, 1)#000-#f00-#fff");
		var g = paper.gradient("L(0, 0, 100, 100)#000-#f00:25-#fff");
		var g = paper.gradient("r(0.5, 0.5, 0.5)#000-#fff");
		paper.circle(50, 50, 40).attr({
		    fill: g
		});

### 17. `Paper.toString()`
> 返回 `Paper` 的 `SVG` 代码

- 返回值

	返回 `Paper` 的 `SVG` 代码 字符串

### 18. `Paper.clear()`
> 移除所有子节点，除了 `<defs>`





### 19. `Paper.filter(filstr)`
> 创建一个 `<filter>` 元素

- 参数

	`filstr` 字符串  `filstr` 滤镜相关的SVG字符串片段

- 返回值

	`element`  对象

- 注意： 推荐将 `filter` 使用在一个空的 `SVG` 元素上

- 用法

		var f = paper.filter(''),
	    c = paper.circle(10, 10, 10).attr({
	        filter: f
	    });	




----------

# mina

### 1. `mina(a, A, b, B, get, set, [easing])`
> 基本动画所需的数值

- 参数
	
	`a`    
	`B`  
	`b`    
	`B`  
	`get`  
	`set`    
	`easing` 缓动函数 默认：`mina.linear`

- 返回值

	动画描述符 对象

		{
			id	字符串 动画id
			start 字符串   
			end 字符串
			b 字符串
			s 字符串 动画状态（0...1)
			dur 字符串 动画持续时间
			spd 字符串 动画速度
			get 
			set
			easing 缓动函数 默认：`mina.linear`
			duration
			stop
			pause
			resume
			update 
		}

### 2. `mina.time()`
> 返回当前时间 相当于
> 
	function (){
		return (new Date).getTime()
	}  


### 3. `mina.getById(id)`
> 返回指定 `id` 的动画

- 参数 

	`id` 字符串 动画 `id`

### 4. `mina.linear(n)`
> 默认缓动

- 参数 

	`n` 数值型 0...1

### 5. `mina.easeout(n)`

### 6. `mina.easein(n)`

### 7. `mina.easeinout(n)`

### 8. `mina.backin(n)`

### 9. `mina.backout(n)`

### 10. `mina.elastic(n)`

### 11. `mina.bounce(n)`
