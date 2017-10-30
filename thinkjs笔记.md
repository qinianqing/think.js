## thinkjs学习

### 项目的快速搭建

```
//用npm安装thinkjs
npm install -g think-cli
//如果以前下载过，需要卸载旧的的版本再安装
npm uninstall -g thinkjs
//创建项目
thinkjs new demo
cd demo
npm install
npm start
```

### 项目结构

```
|--- development.js   //开发环境下的入口文件
|--- nginx.conf  //nginx 配置文件
|--- package.json
|--- pm2.json //pm2 配置文件
|--- production.js //生产环境下的入口文件
|--- README.md
|--- src
| |--- bootstrap  //启动自动执行目录 
| | |--- master.js //Master 进程下自动执行
| | |--- worker.js //Worker 进程下自动执行
| |--- config  //配置文件目录
| | |--- adapter.js  // adapter 配置文件 
| | |--- config.js  // 默认配置文件 
| | |--- config.production.js  //生产环境下的默认配置文件，和 config.js 合并 
| | |--- extend.js  //extend 配置文件 
| | |--- middleware.js //middleware 配置文件 
| | |--- router.js //自定义路由配置文件
| |--- controller  //控制器目录 
| | |--- base.js
| | |--- index.js
| |--- service  //服务目录 
| | |--- **.js //用户自己定义的服务
| |--- logic //logic 目录
| | |--- index.js
| |--- model //模型目录
| | |--- index.js
|--- view  //模板目录
| |--- index_index.html
|--- www
| |--- static  //静态资源目录
| | |--- css
| | |--- img
| | |--- js
```

* 一般写的时候就在src里面写代码，app里面的代码是经过src里面的代码编译过的。

* 请求参数一般有两种写法：

  * this.ctx.param("请求的参数")
  * This.get("请求的参数")

* 一个接口一般返回结果的时候，都把返回的结果放在一个对象或者数组里面，只能返回一个，

  用 let self = this; self.success("最后输出的结果")

