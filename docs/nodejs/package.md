# 包管理文件

package.json 是一个项目的包管理文件（非常重要）

完整的包管理文件 package.json

```js
{
	//项目名称
	//不能有空格、汉字，并且不能与npmjs.org官网的包重名
	"name": "nodejs",
	//项目版本号
	// v3.2.1
	// 3 大版本  我们的代码、ui界面有颠覆性的改变
	// 2 小版本  新增功能，修复bug
	// 1 修复bug、缺陷 提升用户体验
	"version": "1.0.0",
	//项目描述，包含一些关键字、功能描述
	"description": "my first nodejs project",
	//入口文件
	"main": "index.js",
	//快捷启动命令
	"scripts": {
	"test": "echo \"Error: no test specified\" && exit 1"
	},
	//项目的关键字，用于seo优化
		"keywords": [
		"nodejs",
		"express",
		"mysql"
	],
	//作者
	"author": "heinan",
	//版权信息
	"license": "ISC",
	"dependencies":{}
	"devDependencies":{}
}

```

## dependencies 生产环境依赖模块

```js
	npm install --save <package>
```

## devDependencies 开发环境依赖模块

```js
	npm install --save-dev <package>
```

## 发布包的流程

-   添加用户名、密码、邮箱

```cmd
	npm adduser
		- username 输入用户名
		- password 密码
		- email 邮箱
```

-   登录

```cmd
	npm login
		- username 输入用户名
		- password 密码
		- email 邮箱
```

-   发布
    npm publish

注意事项：

-   包名
-   版本号
