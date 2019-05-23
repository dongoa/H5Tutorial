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