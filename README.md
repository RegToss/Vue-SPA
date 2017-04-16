# Vue2.0仿饿了么webapp单页应用
<hr>
声明: 代码源于 <a  href="https://github.com/ustbhuangyi">黄毅</a>老师在慕课网上的教学视频，我自己重现了vue2.0版本，喜欢的童鞋可以去支持老师的课程：http://coding.imooc.com/class/74.html
<hr>
演示地址：http://vuejssellapp.t.imooc.io/#!/

![演示.png](http://upload-images.jianshu.io/upload_images/4670483-9a21e2ae16ea6ac6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<hr>
##依赖工具：
- vue-cli
- express
- vue-resource
- vue-router
- vue-infinite-scroll
- stylus
- webpack

<hr>

##安装：
1、安装node：http://nodejs.cn/download/ 
     git：https://git-scm.com/downloads

2、从我的仓库复制代码：
> $ git clone https://github.com/RegToss/Vue-SPA.git

3、安装vue脚手架工具vue-cli:
> $npm install vue-cli -g

4、进入代码根目录安装依赖：
> $ npm install --save-dev

5、运行命令：
> $ npm run dev

6、发布代码：
> $ npm run build



发布完代码后会生成dist目录，保存着项目的所有可运行的代码。
      
注意不能直接打开index.html运行，需要开启http server运行代码。
直接运行我写好的配置文件就可以运行代码：
> $ node prod.server.js

打开浏览器输入localhost:9000看效果。

<hr>
也可以在本地服务器部署你的代码，以nginx为例：

下载地址：http://nginx.org/en/download.html

解压nginx到指定目录：f:/nginx。
在命令行进入f:/nginx目录下运行：
> $ start nginx

开启nginx。

1、默认配置的端口号是80，打开浏览器输入：localhost:80，如果出现welcome to nginx则端口80可以使用。否则需要修改默认端口号。

打开nginx/conf下的nginx.conf配置文件，查看默认监听端口号并修改为：
```
 server {
        listen      8088;
}
```
在浏览器输入localhost:8088即可正常访问。

2、修改默认路径为指定的地址，即可打开我们的页面,将server中的location修改为：
> location / {
            root     F:/Vue/vue-app/dist; //你的dist地址
            index    index.html;
 }

刷新浏览器即可访问vueapp内容。



(完)
