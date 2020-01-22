
## HTML5为什么只需要写!DOCTYPE

HTML5不基于SGML，因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）

而HTML4.01基于SGML，所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型


## 行内元素、块级元素、空(void)元素，分别有哪些？

行内元素有：a b span img input select strong（强调的语气）

块级元素有：div ul ol li dl dt dd h1~h6 p

空元素:br hr img input link meta

## 常见的浏览器内核有哪些？

Blink内核：新版 Chrome、新版 Opera

Webkit内核：Safari、原Chrome

Gecko内核：FireFox、Netscape6及以上版本

Trident内核（又称MSHTML内核）：IE、国产浏览器

Presto内核：原Opera7及以上

## cookies，sessionStorage 和 localStorage 有何区别？

cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）

cookie数据始终在同源的http请求中携带（即使不需要），记会在浏览器和服务器间来回传递

cookie数据大小不能超过4k

cookie 设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭

sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存

sessionStorage和localStorage虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大

localStorage 存储持久数据，浏览器关闭后数据不丢失除非主动删除数据

sessionStorage 数据在当前浏览器窗口关闭后自动删除

## 页面可见性（Page Visibility API） 可以有哪些用途？

通过 visibilityState 的值检测页面当前是否可见，以及打开网页的时间等

在页面被切换到其他后台进程的时候，自动暂停音乐或视频的播放

完成登陆后，无刷新自动同步其他页面的登录状态


## 对浏览器内核的理解？

浏览器内核主要分为两部分：渲染引擎(layout engineer 或 Rendering Engine) 和 JS引擎

渲染引擎负责取得网页的内容进行布局计和样式渲染，然后会输出至显示器或打印机

JS引擎则负责解析和执行JS脚本来实现网页的动态效果和用户交互

最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎

## HTML5有哪些新特性？

新增选择器 document.querySelector、document.querySelectorAll

拖拽释放(Drag and drop) API

媒体播放的 video 和 audio

本地存储 localStorage 和 sessionStorage

离线应用 manifest

桌面通知 Notifications

语意化标签 article、footer、header、nav、section

增强表单控件 calendar、date、time、email、url、search

地理位置 Geolocation

多任务 webworker

全双工通信协议 websocket

历史管理 history

跨域资源共享(CORS) Access-Control-Allow-Origin

页面可见性改变事件 visibilitychange

跨窗口通信 PostMessage

Form Data 对象

绘画 canvas

## HTML5移除了那些元素？

纯表现的元素：basefont、big、center、font、s、strike、tt、u

对可用性产生负面影响的元素：frame、frameset、noframes

## HTML5的离线储存的工作原理以及使用？

原理：

- 用户在线时，保存更新用户机器上的缓存文件
- 当用户离线时，可以正常访离线储存问站点或应用内容

使用：

- 在文档的 html 标签设置 manifest 属性，如 manifest="/offline.appcache"
- 在项目中新建 manifest 文件，manifest 文件的命名建议：xxx.appcache
- 在 web 服务器配置正确的 MIME-type，即 text/cache-manifest

## label标签在表单控件中的2种用法

方法1：

- &lt;label for="mobile"&gt;Number:&lt;/label&gt;
- &lt;input type="text" id="mobile"&gt;

方法2：

- &lt;label&gt;Date:&lt;input type="text"&gt;&lt;/label&gt;

