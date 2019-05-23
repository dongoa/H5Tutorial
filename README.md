# H5知识点整理
## 第一章 背景知识
### H5的改进
+ 支持在浏览器中直接播放视频和音频
+ 添加canvas，编程从而成为HTML文档第一层次的事情
+ 引入语义Web
+ 权威资料 http://w3c.org http://developer.mozilla.org  

## 第二章 初探HTML
**HTML**是一种标记语言，**元素**是一种用来向浏览器说明文档内容的工具，不同的元素有不同的确切含义。
+ 元素属性
	+ 布尔属性：只需添加属性名
	+ 自定义属性： 必须以data-开头
+ 元素之间的关系：父元素、子元素、后代元素和兄弟元素
+ 元素类型
	+ 元数据元素，用来构建HTML文档的基本结构，以及如何处理文档向浏览器提供信息和指示
	+ 流元素
	+ 短语元素，这两个元素的用途确定一个元素合法的父元素和子元素范围。
+ HTML实体
+ 局部属性：每个元素自己规定的属性
+ 全局属性
	+ accessky属性，设置快捷键，windows下使用alt+Key进行转移焦点。
	+ class属性，
	+ contenteditable属性，让用户修改页面上的内容。
	+ contextmenu属性，目前浏览器不支持。
	+ dir属性，规定元素中文字的方向，ltr从左到右，rtl从右到左。
	+ draggable属性，后面详细讲解
	+ dropzone属性，
	+ hidden属性，隐藏相关元素
	+ id属性,可以使用id属性导航到元素
	+ lang属性，说明元素内容使用的语言，必须有效的ISO语言代码，参阅：http://tools.ietf.org/html/bcp47
	+ spellcheck属性，是否对元素的内容进行拼写检查
	+ style属性，直接在元素身上定义CSS样式
	+ tabindex属性，改变焦点转移顺序
	+ title属性，提供了元素的额外信息

## 第三章 初探CSS
+ 样式的定义方式
	+ 元素内嵌样式
	+ css选择器样式
	+ 使用外部样式表,可以使用@import从一个样式表导入另一个样式表,但是效率上不如多个link。@charset声明编码类型。
+ 样式的层叠和继承
	+ 容易被忽略的两个样式：浏览器样式，用户样式，以chrome为例，用户可以自己添加custom.css。
	+ 样式层叠方式：
		1. 元素内嵌样式
		2. 文档内嵌样式
		3. 外部样式
		4. 用户样式
		5. 浏览器样式
	+ 标记重要样式(important),可以改变层叠次序,凌驾于作者重要属性值上的是用户样式表中定义的重要属性值。、
	+ 根据具体程度和定义次序解决同级样式冲突
		+ 具体程度统计选择器的三类特征：
			1. id值数目
			2. 其他属性和伪类数目
			3. 元素名和伪元素数目  
		评估具体程度时使用a-b-c形式(其中每一个字母以此代表上述三类特征的统计结果)，比较方法按照a、b、c优先级比较来确定具体程度。  
		如果具体程度相同，浏览器根据其位置先后选择所用值，后来者居上。
	+ 继承：如果浏览器在直接相关样式中找不到某个属性值，就会应用于继承机制，使用父元素的这个样式值。
	+ CSS中的颜色,CSS扩展的颜色名：http://www.w3.org/TR/css3-color ,css颜色函数rgb,rgba,hsl(hue,saturaion,lightness),hsla()
	+ CSS中的长度:
		+ 绝对长度：in英尺，cm厘米，mm毫米，pt磅，pc pica
		+ 相对长度：em与元素字号挂钩，ex与元素字体的x高度挂钩，rem与根元素的字号挂钩，px css像素，% 另一属性值的百分比
			+ 像素单位，*参考像素是距读者一臂之遥的像素密度为96dpi的设备上一个像素的视角。*主流浏览器将1像素视为1英尺的1/96
			+ 对于百分比单位，并非所有属性都能用这个单位，还有一点是百分比挂钩的其他属性各不相同。
			+ 目前缺乏支持的CSS相对度量单位，gd 网格挂钩，vw 与视口挂钩， vh视口高度挂钩，vm,ch
			+ 用算式做值 calc()
		+ CSS角度： deg度(取值范围0~360)，grad百分度(取值范围0~400)，rad弧度(取值范围0~6.28)，turn圆周(1turn等于360deg)
		+ CSS时间： s ms
	+ 测试CSS 支持情况
		+ 网站：http://caniuse.com
		+ 测试特性并作出调整的js库：https://modernizr.com/
	+ CSS工具：
		+ 一个很老的工具，通过用户点击生成CSS选择器：https://selectorgadget.com/
		+ LESS改进CSS：http://lesscss.org/
		+ CSS框架


## 第四章 初探JavaScript
+ 读物网站：http://lifehacker.com 书籍： 《JavaScript:The Definitive Guide》,高级 《Pro JavaScript Design Patterns》
+ delete可以删除对象的方法和属性，in检查对象是否具有某个属性。 
+ 显示类型转换： toString，将数值转换为字符串
	+ 数字到字符串转换方法：
		+ toString():十进制，toString(2/8/16)
		+ toFixed(n):以小数点后n位数字形式表示实数
		+ toExponential(n):指数表示法表示数值，尾数小数点前后分别1位和n位
		+ toPrecision(n):n位有效数字表示
	+ 字符串转换数值
		+ Number(<str>) 严格解析整数或实数
		+ parseInt(<str>) 自动忽略非数值
		+ parseFloat(<str>)
+ 内置数组方法：
	+ concat(<otherArray>)合并多个数组
	+ join(<separator>)将数组元素链接为字符串
	+ pop()删除返回最后一个元素
	+ push(<item>)数组当作栈使用，添加数组
	+ reverse()反转数组
	+ shift()删除第一个元素
	+ slice(<start>,<end>)返回子数组
	+ sort()就地对数组排序
	+ unshift(<item>)开头插入数组
+ 处理错误：try...catch Error对象有3个属性message,name,number
+ undefined和null的判断，使用!,全等和相等符号来区分
+ JavaScript库： jQuery

## 第五章 HTML5元素背景知识
+ 语义与呈现分离：HTML5一大主要变化就是元素的语义与元素对其内容呈现结果的影响分开。
+ 元素选用的原则：
	+ 少亦可为多
	+ 别误用元素，如果没有自己所要含义的元素，可以考虑span或div
	+ 具体为佳，一以贯之，如果又元素能恰当表明内容类型，就不需要使用通用元素。
	+ 对用户不要想当然，呈现与语义分离的目的完全是为了让HTML文档更易于程序化处理。
+ 元素速览
	+ 文档和元数据元素
		+ base 设置相对URL基础
		+ body 表示HTML文档内容
		+ DOCTYPE 表示HTML文档开始
		+ head 包含文档的元数据
		+ html 表示文档html的开始
		+ link 定义与外部资源的关系
		+ meta 提供关于文档的信息
		+ noscript 包含浏览器不支持脚本时显示的内容
		+ script 脚本
		+ style css样式
		+ title 设置文档标题
	+ 文本元素，提供基本的结构和含义
		+ a 生成超链接 流类型
		+ abbr 缩略语 
		+ b
		+ br 表示换行
		+ cite 表示其他作品标题
		+ code 计算机代码片段
		+ del 从文档中删除的文字 流类型
		+ dfn 表示术语定义
		+ em 强调文字
		+ i 与周围内容不同的文字
		+ ins 表示加入文档的文字 流元素
		+ kbd 表示用户输入内容
		+ mark 突出显示标记
		+ q 表示引自他处内容
		+ rp 与ruby结合使用，标记括号
		+ rt 与ruby结合使用，标记注音符号
		+ ruby 表示位于表意文字上方或右方的注音符号
		+ s 表示文字已不再准确
		+ samp 表示计算机程序输出内容
		+ small 小号字体内容
		+ span 通用元素，无语义
		+ strong 重要
		+ sub 下标文字
		+ sup 上标文字
		+ time 表示时间或日期
		+ u 不带强调或着重意味标记一段文字
		+ var 表示计算机变量
		+ wbr 可安全换行的地方
	+ 对内容分组
		+ blockquote 表示引自他处大段内容 流元素
		+ dd 用在dl中表示定义
		+ div 通用元素，类似span，是在流元素中的对应物
		+ dl 术语定义说明 流
		+ dt 属于
		+ figcaption figure标题
		+ figure 图片 流
		+ hr 主题转换 流
		+ li 用在ul、ol、menu中，列表项
		+ ol 有序列表 流
		+ p 表示段落 流
		+ pre 表示其格式应被保留的内容 流
		+ ul 无序列表 流
	+ 划分内容
		+ address 表示文档或article联系信息 流
		+ article 表示一段独立的内容 流
		+ aside 表示与周边内容稍有牵涉的内容 流
		+ details 生成一个区域，用户展开可以获得更多细节知识 流
		+ footer 表示尾部 流
		+ h1~h6 标题 流
		+ header 首部
		+ hgroup 组织标题，显示一个 流
		+ nav 有意集中在一起的导航元素 流
		+ section 表示一个重要概念或主题 流
		+ summary 用在details中，表标题或说明 
	+ 制表，HTML5中表格不在控制页面布局
		+ caption 表格标题
		+ col 一列
		+ colgroup 一组列
		+ table 表格 流
		+ tbody 表格主体
		+ td 单元格
		+ tfoot 表脚
		+ th 标题行单元格
		+ thead 标题行
		+ tr 一行单元格
	+ 创建表单
		+ button 提交或重置表单按钮
		+ datalist 提供建议值 流
		+ fieldset 一组表单元素 流
		+ form HTML表单 流
		+ input 输入控件
		+ keygen 生成公钥和私钥
		+ label 表单元素说明标签
		+ legend fieldset说明标签
		+ optgroup 一组相关option元素
		+ option 选项
		+ output 计算结果
		+ select 固定选项
		+ textarea 输入多行文字
	+ 嵌入内容
		+ area 客户端分区响应图的区域
		+ audio 音频资源
		+ canvas 画布 流
		+ embed 用插件在html文档中嵌入内容
		+ iframe 在一个文档中嵌入另一个文档
		+ img 嵌入图像
		+ map 定义客户端分区响应图
		+ meter 嵌入数值在许可范围背景中的图形表示
		+ object 嵌入内容
		+ param 通过object元素传递给插件的参数
		+ progress 嵌入目标进展图形表示
		+ source 媒体资源
		+ svg 结构化矢量内容
		+ track 媒体附加轨道
		+ video 视频资源

## 第六章 创建HTML文档
+ 构筑基本的文档结构，文档元素只有4个，但是任何HTML文档都需要所有这些元素
	+ DOCTYPE元素
	+ html元素，更恰当的名称根元素
	+ head元素，包含文档的元数据，向浏览器提供有关文档内容和标记的信息，脚本和外部资源，必须包含一个title
	+ body元素
+ 用元数据元素说明文档
	+ 文档标题title
	+ 设置相对URL的解析基准，让HTML文档中的相对链接咋此基础上进行解析,其包含两个属性：
		+ href
		+ traget
	+ 用元数据说明文档meta元素，其包含多种用途：
		+ 指定名/值元数据对，使用name，content，元数据名称扩展见：http://wiki.whatwg.org/wiki/MetaExtensions ,可以使用该功能告诉搜索引擎如何对内容分类分级，谷歌指南参见：http://google.com/support/webmasters/bin/topic.py?topic=15260
		+ 声明字符编码，charset="utf-8"
		+ 模拟HTTP标头字段，http-equiv="refersh" content="5;url",作用是让浏览器每隔秒就再次载入页面，加url会载入指定url，meta元素http-equiv有3个值，分别为refresh，default-style指定对应content属性值与同一文档中某个style元素或link元素title属性值相同，content-type，另一种声明HTML页面所用字符编码方法。
+ 定义CSS样式,style元素可以出现在HTML文档的各个部分
	1. 指定样式类型type="text/css"
	2. 指定样式作用范围 scoped浏览器不支持
	3. 指定样式适用的媒体，media属性,media属性的规定设备值
		+ all 用于所有设备
		+ aural 用于语音合成器
		+ braillle 用于盲文设备
		+ handheld 用于手持设备
		+ projection 用于投影机
		+ print 用于打印预览和打印页面
		+ screen 用于计算机显示器屏幕
		+ tty 电传打字机
		+ tv 电视机
		浏览器负责解释，有可能比较随意。并可以使用AND,OR,NOT组合,width配合max-min-使用，media使用的特性包含：width，height，device-width，device-height，resolution，orientation(portrait/landscape)，aspect-ratio,aspect-ratio,device-aspect-ratio,monochrome,color-index,scan(progressive/interlace),grid(0/1)
+ 指定外部资源
	+ 定义了6个局部属性：href，hreflang，media，rel，sizes，type  
		+ link元素rel属性值：alternate，author，help，icon，license，pingback，prefetch，stylesheet，全面介绍：http://iana.org/assignments/link-relations/link-relations.xml
		+ 添加网站标志,默认会载入服务器根目录下的favicon.ico
		+ 预先获取资源
+ 使用脚本元素，建议放在head部分
	+ script元素的局部属性，type,src,defer,async,charset
	+ 定义内嵌脚本，默认情况下，浏览器在页面一遇到脚本就会执行。
	+ 载入外部脚本库，不可用自闭合标签，会被忽略掉。
	+ 推迟脚本执行，defer等页面载入和解析完毕后执行脚本
	+ async异步执行脚本,脚本不再按定义它们的次序执行，不要使用其他脚本函数。

## 第八章 标记文字
+ 生成超链接 url支持http,https,ftp,mailto,相对路径，内部id表达式(找不到会找name)
	+ target属性，_blank新窗口打开，_parent父窗框，_self当前窗口打开，_top顶层窗口打开，<frame>在指定窗框中打开
+ 用基本文字元素标记内容
	+ 表示关键词和产品名称 b
	+ 加以强调 em
	+ 表示外文词与或科技术语