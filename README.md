#### node.js基础

#### 一、简介

简单来说node.js就是运行在服务端的javascript。node.js是一个基于Chrome javascript运行时建立的一个平台。node.js是一个事件驱动I/O服务端javascript环境，基于Google的V8引擎，V8引擎执行javascript的速度非常快，性能非常好。

- 查看你使用的版本`$ node -v`

- 第一个程序

  打开终端，键入node进入命令交互模式，可以输入一条代码语句后立即执行并显示结果，例如：

  ```javascript
  $ node 
  > console.log('hello world')
  hello world
  ```

#### 二、安装配置

node.js安装包及源码下载地址：`https://nodejs.org/en/download/`

检测PATH环境变量是否配置了node.js。打开命令cmd，输入“path”，看环境中是否包含了node.js。

#### 三、node.js创建第一个应用

在我们创建node.js第一个应用前，我们来了解下node.js应用是由哪几个部分组成的：

- 引入require模块：我们可以使用require指令来载入node.js模块。
- 创建服务器：服务器可以监听客户端的请求，类似于Apache、Nginx等HTTP服务器。
- 接收请求与响应请求：服务器很容易创建，客户端可以使用浏览器或终端发送HTTP请求，服务器接收请求后返回响应数据。

##### 创建node.js应用

###### 1.引入require模块

我们使用require指令来载入http模块，并将实例化的http赋值给变量http。

```javascript
var http = require('http')
```

###### 2.创建服务器

接下来我们使用http.creatrServer()方法创建服务器，并使用listen方法绑定8888端口。函数通过request、response参数来接收和响应数据。

在你的项目的根目录下创建一个叫server.js的文件，并写入以下代码：

```javascript
var http = require('http')

http.createServer(function(require,response){
  /**
   *  发送http 头部
   *  HTTP 状态值：200：OK
   *  内容类型：text/plain
   */
  response.writeHead(200,{'Content-Type': 'text/plain'})
  /**
   *  发送响应数据“hello world”
   */
  response.end('hello world\n')
}).listen(8888)

console.log('server running at http://127.0.0.1:8888')
```

打开cmd，进入到你所在项目的根目录下，执行：`node server.js`代码，接下来访问http://127.0.0.1:8888 你会看到写着hello world的页面。