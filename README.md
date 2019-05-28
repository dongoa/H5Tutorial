# H5知识点整理

# HTML部分
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

## 第七章 标记文字
+ 生成超链接 url支持http,https,ftp,mailto,相对路径，内部id表达式(找不到会找name)
	+ target属性，_blank新窗口打开，_parent父窗框，_self当前窗口打开，_top顶层窗口打开，<frame>在指定窗框中打开
+ 用基本文字元素标记内容
	+ 表示关键词和产品名称 b加粗
	+ 加以强调 em倾斜
	+ 表示外文词与或科技术语 i习惯样式，斜体
	+ 表示不准确或校正 s显示一条删除
	+ 表示重要文字 strong加粗
	+ 添加下划线 u避免使用
	+ 添加小号字体内容 small
	+ 添加上标下标 sub sup
	+ 换行br wbr由浏览器决定，可将长单词分为小节划
	+ 表示输入和输出 code var samp kbd
	+ 使用标题引用、引文、定义和缩写
		+ 表示缩写abbr 虚的下划线
		+ 定义术语 dfn斜体
		+ 引用来自他处的内容 q加引号
		+ 引用其他作品标题 cite斜体
	+ 使用语言元素，一共五个用途是为使用非西方语言提供支持
		+ ruby、rt和rp元素
		+ bdo元素 dir=rtl/ltr表示文字方向。
		+ bdi元素
	+ 其他文本元素
		+ 表示一段一般性内容 span
		+ 突出显示文本 mark黄色背景
		+ 表示添加和删除内容 ins del 他们有两个属性cite解释文档的url，datetime属性用来设置修改时间
		+ 表示时间和日期 time元素，最近的artical元素发布日期，datetime属性格式：http://tools.ietf.org/html/rfc3339

## 第八章 组织内容
组织内容相关的HTML元素，能给与文档更多的结构和含义，大多数为流元素
+ 为什么要对内容分组，因为HTML要求浏览器将连在一起的几个空白字符折算为一个空格。
+ 建立段落 p围绕一个观点或论点，包含共同主题
+ 使用div元素 但是应先使用具有语义重要性的元素，其缺点是别人不了解你的自定义结构HTML文档
+ 使用预先编排好格式的内容 pre元素会保留源文档格式，除非原始格式意义重大，否则则最好不要使用
+ 引用他处内容 blockquote元素，与q元素类似，表示更多的引用，cite属性可以指定引用来源，浏览器会忽略blockquote元素内容格式，可以使用p或hr元素进行组织
+ 添加主题分隔 hr
+ 将内容组织为列表
	+ ol元素 有序列表,type属性1/a/A/i/I,reversed属性表示降序
	+ ul元素 无序列表
	+ li元素 value属性，浏览器会将列表项计数器调为该值
	+ 生成说明列表 dl、dt、dd元素，分别表示说明列表、术语、定义
	+ 生成自定义列表
	+ 使用插图 figure和figcaption元素(必须为figure的第一或者最后一个元素)

## 第九章 文档分节
本章主要是划分内容，将主题和概念分隔开的元素，它们构成语义和呈现分离实践的基础
+ 添加基本标题 h1~h6可以不按顺序使用，容易引起误解
+ 隐藏子标题 hgroup解决子标题问题
+ 生成节 section流元素 chrome等浏览器下section中的h1会和h2大小相同
+ 添加首部和尾部 header footer
+ 添加导航区域 nav
+ 使用artical 一段独立成篇的内容
+ 生成附注栏 aside表示跟周边内容稍微沾一点边的内容
+ 提供联系信息 address视为该article的联系信息
+ 生成详情区域 details元素包含summary元

## 第十章 表格元素
+ 生成基本的表格 table、tr和td，浏览器会调整行与列的尺寸以维持表格的形式
+ 添加标头单元格 th
+ 为表格添加结构
+ 表示表头和表格主题
+ 添加表脚 可以放在tbody之前或tr之后
+ 制作不同规则表格 用到td、th元素、colspan(跨多少列)、rowspan(跨多少行，并且要用在要占据网格左上角那个单元格)属性,重叠最好用CSS来做。
+ 把表头与单元格关联起来 headers属性可以被设置多个th的id属性
+ 为表格添加标题caption元素
+ 处理列colgroup元素和col元素,应用于colgroup上的样式具体程度比较低，不规则单元格计入起始列，无法具体选择，col元素控制更多
+ 设置表格边框 table的border属性

## 第十一章 表单
+ 制作基本表单form input button
+ 配置表单
	+ 配置表单的action属性，说明提交表单时浏览器应该把用户手机数据发送到什么地方
	+ 配置HTTP方法属性，指定用来将表单数据发送到服务器的HTTP方法，GET安全交互，POST不安全交互，参www.w3.org/Provider/Style/URI
	+ 配置数据编码，enctype属性3种
		+ application/x-www-form-urlencoded编码，不能上传文件，编码结果：fave=Apple&name=Adam+Freeman
		+ multipart/form-data编码,用于上传文件到服务器列表
		+ text/plain编码，不规范
	+ 控制表单的自动完成功能
	+ 指定表单反馈信息的目标显示位置target属性，属性值包含\_blank,\_parent,\_self,\_top,<frame>
	+ 设置表单名称 name属性为表单设置一个独一无二的标识符,不如input的name那么重要，只限于DOM
	+ 在表单中添加说明标签label
	+ 自动聚焦到某个input元素 autofocus属性
	+ 禁用单个input元素 disabled属性
	+ 对表单元素编组 fieldset元素
	+ 为fieldset元素添加说明标签 legend元素
	+ 使用button元素 type属性值submit、reset、button
		+ buttontype为submit时，额外属性form、formaction、formenctype、formmethod、formtarget、formnovalidate，都是覆盖操作
		+ 用button元素重置表单
		+ button元素也可以作为一般元素使用，上面的文字可以使用短语元素进行标记
	+ 使用表单外的元素，只需要将其form属性设置为相关form元素的id属性值即可。

## 第十二章 定制input元素
+ 用input元素输入文字
	+ text型input元素可用额外属性：dirname、list、maxlength、pattern、placeholder、readonly、required、size、value
		+ 设定元素大小 maxlength、size
		+ 设置初始值和占位式提示 value、placeholder
		+ 使用数据列表 datalist
		+ 生成只读或禁用的文本框 readonly和disabled属性
		+ 输入密码，服务器收到的是明文密码，应该考虑使用SSL、HTTPS
+ 用input元素生成按钮，type设为submit、reset、button时生成button元素
+ 用input元素为输入数据把关
	+ 用于输入受限数据的input元素的type属性值：checkbox、color、date、datetime、datetime-local、email、month、number、radiobutton、range、tel、time、week、url
	+ 用input元素获取数值，number型input元素可用额外属性，list、min、max、readonly、required、step、value
	+ 用input元素获取指定范围内的数值，range属性
	+ 用input元素获取布尔型输入，checkbox型input元素可用额外属性checked、required、value
	+ 用input元素生成一组固定选项，radio型，checked、required、value
	+ 用input元素获取有规定格式的字符串，email、tel、url型额外属性：list、maxlength、pattern、placeholder、readonly、required、size、value，email型input还有一个multiple属性
	+ 用input元素获取时间和日期，datetime、datetime-local、date、month、time、week，时间戳格式RFC339，参见http://tools.ietf.org/html/rfc3339 ,用于日期input元素的额外属性，list、min、max、readonly、required、step、value
	+ 用input获取颜色值
	+ 用input元素获取搜索用词，和text只是外观有区别
	+ 用input元素生成隐藏的数据项
	+ 用input元素生成图形按钮和分区响应图，image型input元素额外属性，alt、formaction、formenctype、formethod、formtarget、formnovalidate、height、src、width(不设置此值图形将以其本身宽度显示)
	+ 用input元素上传文件，file型input元素可用额外属性accept、multiple(尚无支持)、required

## 第十三章 其他表单元素及输入验证
+ 使用其他表单元素
	+生成选项列表，select元素，name、disabled、form、autofocus、required属性与input类似，size属性显示选项数目，multiple属性可以设置为多选。可以用optgroup元素建立结构。
	+ 输入多行文字，textarea，rows、cols设置大小，wrap:hard/soft换行方式，其他属性与input同名属性相同
	+ 表示计算结果 output属性
	+ 生成公开/私有密钥对，keygen元素
		+ name、disabled、form和autofocus属性与input元素同名属性相同，keytype属性指定生成密钥的算法，challenge属性用来指定一条与公钥一起发送给服务器的密钥管理口令。
		+ 使用输入验证required、min、max、pattern
			+ 确保用户提供了一个值,required,value初始值可以满足
			+ 确保输入值位于某个范围内，min、max
			+ 确保输入值与指定模式匹配，pattern
			+ 确保输入值是电子邮箱或URL，用pattern
			+ 禁用输入验证，form元素的novalidate属性，input或button的formnovalidate属性

## 第十四章 嵌入内容
+ 嵌入图像，不要使用width、height缩放，用途是告诉浏览器图像尺寸
	+ 在超链接里嵌入图像，结合a
	+ 创建客户端分区响应图，map元素，area元素分为两类，第一类是导航到url(相关属性href、alt、target、rel、media、hreflang、type)，第二类是代表区域使用shape和coords属性控制(rect、circle、poly、default)。
+ 嵌入另一张HTML文档，属性包括src、srcdoc、name、width、height、sandbox、seamless(后两种可以独立启用功能，浏览器暂不支持)
+ 通过插件嵌入内容
	+ embed元素
	+ 使用object和param元素
+ object元素的其他用途
	+ 使用object嵌入图像
	+ 使用object创建分区响应图
	+ 将object元素作为浏览器上下文环境
+ 嵌入数字表现形式
	+ 显示进度，progress元素
	+ 显示范围里的值，meter元素，属性包括min、max、low、high、optimum、value、form
+ 其他嵌入元素，之后会深入讨论
	+ 嵌入音频和视频audio、video、source、track
	+ 嵌入图形 canvas

# CSS部分

## 第十五章 理解CSS
+ 浏览器特定厂商前缀  

	浏览器|Chrome、Safari|Opera|Firefox|Internet Explorer
	:-:|:-:|:-:|:-:|:-:
	厂商  |-webkit       |  -o-|  -moz-|  -ms-
+ 盒模型，内容、边框(这两个可见)、内边距、外边距  
块容器：父元素的内容盒子，可以用来限定元素外观。
+ 选择器简明参考

	选择器|说明|CSS版本
	:-:|:-|:-:
	\*|选取所有元素|2
	\<type\>|选取指定类型元素|1
	.\<class\>|选取指定类的元素|1
	#\<id\>|选取id属性为指定值得元素|1
	[attr]|选取定义了attr属性，属性任意的元素|2
	[attr="val"]|选取定义了attr属性，属性值val的元素|2
	[attr^="val"]|选取定义了attr属性，属性值val打头的元素|2
	[attr$="val"]|选取定义了attr属性，属性值val结尾的元素|2
	[attr*="val"]|选取定义了attr属性，属性值包含val的元素|2
	[attr~="val"]|选取定义了attr属性，属性值为多个值，其中一个为val的元素|2
	[attr\|="val"]|选取定义了attr属性，属性值以连字符分隔，第一个为val的元素|2
	\<选择器\>,\<选择器\>|选取同时匹配所有选择器的元素|1
	\<选择器\> \<选择器\>|目标元素为第一个选择器元素后代，匹配第二个选择器|1
	\<选择器\>\><选择器\>|目标元素为第一个选择器元素直接后代，匹配第二个选择器|2
	\<选择器\>+\<选择器\>|目标元素紧跟第一个选择器元素之后，匹配第二个选择器|2
	\<选择器\>~\<选择器\>|目标元素跟在第一个选择器元素之后，匹配第二个选择器|3
	::first-line|选取块级元素文本的首行|1
	::first-letter|选取块级元素文本的首字母|1
	:before\/:after|在选取元素之前或之后插入内容|2
	:root|选取文档中的根元素|3
	:first-child|选取元素的第一个子元素|2
	:last-child|选取元素的最后一个子元素|3
	:only-child|选取元素的唯一一个子元素|3
	:only-of-type|选取属于父元素的特定类型的唯一子元素|3
	:nth-child(n)|选取父元素的第n个子元素|3
	:nth-last-child(n)|选取父元素的倒数第n个子元素|3
	:nth-of-type(n)|选取属于父元素的特定类型的第n个子元素|3
	:nth-last-of-type(n)|选取属于父元素的特定类型的倒数第n个子元素|3
	:enabled|选取已启用的元素|3
	:disabled|选取被禁用的元素|3
	:checked|选取所有选中的复选框和单选按钮|3
	:default|选取默认元素|3
	:valid\/:invalid|选取基于输入验证判定的有效或者无效的input元素|3
	:in-range\/:out-of-range|选取被限定在指定范围之内或者之外的input元素|3
	:required\/:optional|根据是否允许使用required属性选取input元素|3
	:link|选取未访问的链接元素|1
	:visited|选取用户已访问的链接元素|1
	:hover|选取鼠标指针悬停在其上面的元素|2
	:active|选取被用户激活，即将点击的元素|2
	:focus|选取获得焦点的元素|2
	:not(\<选择器\>)|否定选择(选取所有不匹配的元素)|3
	:empty|选取不包含任何子元素或文本的元素|3
	:lang(\<语言\>)|选取lang属性为指定值得元素|2
	:target|选取URL片段标识符指向的元素|3

+ 属性简明参考

## 第十六章 使用CSS选择器I
+ 选择所有元素
+ 复合选择器
	+ 并集选择器，
	+ 后代选择器,空格
	+ 选择子元素
	+ 选择兄弟元素,相邻兄弟\/普通兄弟(在匹配元素之后)
+ 使用伪元素选择器，两种伪元素和伪类
	+ 使用::first-line选择器，匹配文本块的首行
	+ 使用::first-letter选择器，首字母，单冒号浏览器也认伪类向后兼容
	+ 使用:before和:after选择器，生成内容并插入
	+ 使用CSS计数器,使用counter-reset： paracount n othercounter;初始化值,初始化后作为counter属性的值content:counter(paracount,lower-alpha) ". ";后面的格式可以是list-style-type属性支持的任意值，然后设置增量counter-increment:paracount 1;

## 第十七章 使用CSS选择器II
**伪类**跟伪元素一样，不是直接针对文档元素，而是为你基于某些共同特征选择元素提供方便。
+ 使用结构性伪类选择器，根据元素在文档中的位置选择元素，都有一个冒号，可单独或组合使用。
	+ 使用根元素选择器 :root 返回html
	+ 使用子元素选择器
		+ :first-child选择器
		+ :last-child选择器
		+ :only-child选择器
		+ :only-of-type选择器，属于父元素的指定特定类型的唯一子元素
		+ 使用:nth-child选择器，制定一个索引可以匹配特定位置
			+ :nth-child(n)选择父元素的第n个子元素
			+ :nth-last-child(n)选择父元素的倒数第n个子元素
			+ :nth-of-type(n) 选择父元素定义类型的第n个子元素
			+ :nth-last-of-type(n)选择父元素定义类型的倒数第n个子元素
+ 使用UI伪类选择器  
可以根据元素的状态匹配元素
	+ 选择启用或禁用状态的元素 :enabled :disabled,而且不会匹配没有禁用状态的元素
	+ 选择已勾选的元素 :checked
	+ 选择默认元素 :default
	+ 选择有效和无效的input元素 :valid和:invalid
	+ 选择限定范围的input元素 :in-range匹配位于指定范围内的input元素,:out-of-range相反
	+ 选择必须和可选的input元素 :required匹配具有required属性的input元素，:optional相反
+ 使用动态伪类选择器
	+ 使用:link和:visited选择器,visited针对浏览器已访问过的url
	+ 使用:hover选择器
	+ 使用:active选择器，鼠标点击(触摸屏按压)
	+ 使用:focus选择器
+ 其他伪类选择器
	+ 使用否定选择器 :not(\<选择器\>)
	+ 使用:empty选择器 匹配没有定义任何子元素的元素，不好演示
	+ 使用:lang选择器 跟|=属性选择器匹配结果一样
	+ 使用:target选择器，匹配URL**片段标识符**指向的元素。

## 第十八章 使用边框和背景
+ 应用边框样式，三个关键属性border-width、border-style、border-color。
	+ 定义边框宽度border-width:\<长度值(em、px、cm)\>、\<百分数(不支持)\>、thin、medium、thick
	+ 定义边框样式border-style:none、dashed(破折线)、dotted(圆点)、double、groove、inset、outset、ridge、solid。
	+ 为一条边应用边框样式 border-(top/bottom/left/right)-(width/style/color)
	+ 使用border简写属性 border:\<宽度\>\<样式\>\<颜色\>顺序任意
	+ 创建圆角边框 共5个属性 border-(top-left/top-right/bottom-left/bottom-right)-radius border-radius，值为一度长度值或百分数值，最后一个可以为4对
	+ 将图像做边框 border-image-(source/slice/width/outset/repeat),border-image
		+ 切分图像border-image
		+ 控制切分图重复方式border-image-repeat stretch/repeat/round/space,两个值一个水平一个垂直
+ 设置元素的背景  
	+ 设置背景颜色和图像background-repeat属性值:repeat-x/repeat-y/repeat/space/round/np-repeat,只有一个值的话会使用同种样式
	+ 设置背景图片的尺寸 backgournd-size属性值:长度值，百分数，预设值(contain、cover、auto)
	+ 设置背景图像位置background-position:top/left/right/bottom/center
	+ 设置元素的北京附着方式background-attachment属性值：fixed、local、scroll
	+ 设置背景图像的开始位置和剪裁样式background-origin和background-clip:border-box/padding-box/content-box
	+ 使用background简写属性background:color/postion/size/repeat/origin/clip/attachment/image
+ 创建盒子阴影  
box-shadow:hoffset/voffset/blur/spread/color/inset后面4个为可选colorchrome必选
	+ 应用轮廓，轮廓属性outline-(color/offset/style/width)

## 第十九章 使用盒模型
+ 为元素应用内边距 padding-(top/right/bottom/left)
+ 为元素应用外边距 margin-(top/right/bottom/left),display:inline时外边距不会显示
+ 控制元素的尺寸 Width Heihgt min/max-width/height box-sizing:(content-box/padding-box/border-box/margin-box)
	+ 设置一定尺寸的盒子,元素的高度包含内容高度、内外边距、边框值。
	+ 设置最小和最大尺寸
+ 处理溢出内容 overflow-x/y,overflow:auto、hidden、no-content(不支持)、no-display(不支持)、scroll、visible
+ 控制元素的可见性 visible:collapse、hidden、visible,对于不支持此特性的可用display:none。
+ 设置元素的盒类型  
inline、block、inline-block、list-item、run-in、compact(不支持)、flexbox、table(布局相关)、ruby(跟带ruby注释文本布局相关)、none
	+ 认识块级元素，display:block
	+ 认识行内元素,inline会忽略某些属性，如width、height、margin
	+ 认识行内-块级元素，可以应用上面的属性
	+ 认识插入元素，display:run-in
	+ 隐藏元素 display:none
	+ 创建浮动盒 float:left/right/none(元素位置固定)
	+ 阻止浮动元素堆叠 clear:left/right/both/none

## 第二十章创建布局  
推荐框架Blueprint(www.blueprintcss.org)
+ 定位内容  
定位属性：position、left、right、top、bottom(长度、百分数、auto)、z-index
	+ 设置定位类型 positon:static(位置的属性不管用)、relative、absolute、fixed
	+ 设置元素的层叠顺序 z-index
+ 创建多列布局  
多列属性column-count、column-fill(balance\/auto)、column-gap、column-rule、column-rule-color、column-rule-style、column-rule-width、colums、column-span、column-width。
+ 创建弹性盒布局  
-webkit弹性盒属性box-align、box-flex、box-pack
	+ 创建简单的弹性盒
	+ 伸缩多个元素 box-flex数值表示浏览器为其分配的多于空间是其他box-flex的倍数
	+ 处理垂直空间box-align:start/end/strech/center
	+ 处理最大尺寸 box-pack (start、end、center、justify)
+ 创建表格布局  
跟表格布局相关的display属性table、inline-table、table-caption(类似于caption元素)、table-column(类似于col元素)、table-column-group(类似于colgroup元素)、table-header-group(类似于thead元素)、table-row-group(类似于tbody元素)、table-footer-group(类似于tfoot元素)、table-row(类似于tr元素)、table-cell(类似于td元素)

## 第二十一章 设置文本样式
+ 应用基本文本样式
	+ 对其文本 text-align(start/end/left/right/center/justify)、text-justify(auto/none/inter-word/inter-ideograph/inter-cluster/distribute/kashida)
	+ 处理空白 whitespace属性(normal/nowrap/pre/pre-line/pre-wrap)
	+ 指定文本方向 ltr/rtl
	+ 指定单词、字母、行之间的间距letter-spacing/word-spacing/line-height
	+ 控制断词 word-wrap属性(normal/break-word)
	+ 首行缩进 text-indent 长度值/百分数
+ 文本装饰与大小写转换  
text-decoration:none/underline/overline/line-through/blink
text-transform:none/capitalize/uppercase/lowercase
+ 创建文本阴影 text-shadow属性h-shadow/v-shadow/blur/color
+ 使用字体font:\<font-style\>\<font-variant\>\<font-weight\>\<font-size\>\<font-family\>
