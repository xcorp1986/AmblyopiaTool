# 网站信息无障碍
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/gemgin/AmblyopiaTool/pulls)
[![GitHub stars](https://img.shields.io/github/stars/gemgin/AmblyopiaTool.svg?style=social&label=Stars)](https://github.com/gemgin/AmblyopiaTool)
[![GitHub forks](https://img.shields.io/github/forks/gemgin/AmblyopiaTool.svg?style=social&label=Fork)](https://github.com/gemgin/AmblyopiaTool)

交流QQ群：41977413

## 前言

　　为了体现政府提供公共服务的公平、公正、均等化的要求，保障弱势群体获得政府公众服务的权利，我国政府近年一直致力于推动信息无障碍技术在各个领域的应用，先后制定《无障碍环境建设条例》、《网站设计无障碍技术要求》、《网站设计无障碍评级测试方法》等相关法规及行业标准。在建设服务型政府的大环境之下，信息无障碍服务成为政府主厅提高公众服务水平、扩大公众服务范围的新亮点。

## 项目介绍

　　TTS技术基于ScanSoft_MeiLing语音库，提供整套网站信息无障碍服务模块：十字光标、纯文本、文字放到专用阅读屏（简体，繁体和拼音）、高对比阅读配色器、文字放大缩小、网页放大缩小、全程语音实时朗读等，支持服务治理、监控和追踪，努力为政府网站无障碍改造解决方案。

### 信息无障碍工具条界面
![信息无障碍工具条界面](doc/%E6%97%A0%E9%9A%9C%E7%A2%8D%E5%B7%A5%E5%85%B7%E6%9D%A1%E7%95%8C%E9%9D%A2.png)

### 信息无障碍核心技术
![信息无障碍核心技术](doc/%E4%BF%A1%E6%81%AF%E6%97%A0%E9%9A%9C%E7%A2%8D%E6%A0%B8%E5%BF%83%E6%8A%80%E6%9C%AF.jpg)

### 信息无障碍改造流程
![信息无障碍改造流程](doc/%E6%97%A0%E9%9A%9C%E7%A2%8D%E6%9C%8D%E5%8A%A1%E6%B5%81%E7%A8%8B.jpg)

### 信息无障碍辅助工具部署步骤

    以海南人民政府网站为例，官网地址：http://www.hi.gov.cn/code/html

- 1.将canyou文件夹放到 ```http://www.hi.gov.cn``` 站点指向的服务器目录下，保证```http://www.hi.gov.cn/canyou/```能够被访问到即可。

- 2.添加js.将下面一段js放在首页模板区间任意位置即可。一般网站头部和尾部都是模版区。建议放在网站每个页面的```</body>```之前
```
     <script type="text/javascript">
         function ShowDetail() {
             if (window.top.document.getElementById("canyou_toolbar_div")) {
                 return false;
             }
            var url = "?url=" + document.location.href; window.scrollTo(0, 0);
            location_href('canyou/default.html' + url);
        }
        function location_href(url) { location.href = url }
    </script>
```
- 3.在首页位置添加链接，确保红色加粗的不变。可以使用任何html标签。确保该链接放在页面的易发现位置。链接代码如下：
```
   <a title="盲人朋友在线浏览按住shift+1键"  onmousedown="ShowDetail()">信息无障碍通道</a>。
```
- 4.修改```canyou/default.html```中```cysrc="http://wza.canyou168.com/"```为```cysrc="http://www.hi.gov.cn/" ```

- 5.部署的域名发过来，进行授权。

> 测试部署是否成功

   在浏览器中输入地址或通过单击原网站头部无障碍操作条中的链接即可完成对网站的信息无障碍化访问。

### 成功案例

- 广东省网上办事大厅 [http://www.gdbs.gov.cn/portal/index.do](http://www.gdbs.gov.cn/portal/index.do "广东省网上办事大厅")

- 深圳市福田区残疾人联合会 [http://ftcl.szft.gov.cn](http://ftcl.szft.gov.cn "深圳市福田区残疾人联合会")

- 深圳市罗湖区残疾人联合会 [http://www.lhdpf.com](http://www.lhdpf.com "深圳市罗湖区残疾人联合会")

- 海南省残疾人联合会 [http://www.hidpf.org.cn](http://www.hidpf.org.cn "海南省残疾人联合会")

- 海南残疾人劳动就业服务中心 [http://www.hicjrjy.org](http://www.hicjrjy.org "海南残疾人劳动就业服务中心")

- 海南特殊教育信息网 [http://www.hktjw.org](http://www.hktjw.org "海南特殊教育信息网")

- 陕西省环保厅 [http://www.snepb.gov.cn](http://113.140.66.226:8111 "陕西省环保厅")
 

### 演示站点

- 工具条灰色模版 [http://wza.canyou168.com](http://wza.canyou168.com "工具条灰色模版")

- 工具条蓝色模版 [http://wza.canyou168.com/pro](http://wza.canyou168.com/pro "工具条蓝色模版")

