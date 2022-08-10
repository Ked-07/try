#npm基本命令

	##查看npm版本
	npm -v

	##查看npm帮助
	npm help

	##查看npm使用的所有文件夹
	npm help folders

	##查看模块列表
	npm list
 
	##查看node模块的package.json文件夹
	npm view <package>

	##查看包的依赖关系
	npm view <package> dependencies

	##查看包的源文件地址
	npm view <package> repository.url

	##查看包所依赖的Node的版本
	npm view <package> engines

	##查看包的安装路径

		查看当前包
		npm root

		查看全局包
		npm root -g

	##更改包内容后进行重建
	npm rebuild <package>

	##检查包是否已经过时

		此命令会列出所有已经过时的包，可以及时进行包的更新
		npm outdated

	##访问npm的json文件夹

		一个npm包是包含了package.json的文件夹，package.json描述了这个文件夹的结构。访问npm的json文件夹的方法如下
		npm help json
		此命令会以默认的方式打开一个网页，如果更改了默认打开程序则可能不会以网页的形式打开。

	##检验包名是否已存在

		发布一个npm包的时候，需要检验某个包名是否已存在
		npm search <package>

	##创建package.json

		会引导你创建一个package.json文件，包括名称、版本、作者这些信息等
		name（名称）和version（版本）时必须的，main（入口文件）默认为index.js。
		npm init

#npm管理命令

	##更新 npm

		更新至最新的版本：
		npm install npm@latest -g

		更新至即将发布的版本：
		npm install npm@next -g

#npm配置项

	##安装位置配置

		设置为当前位置
		npm config set prefix
		npm config set cache

		更改npm全局模块默认安装位置
		npm config set prefix "\nodejs\node_global"

		更改cache默认安装位置 
		npm config set cache "\nodejs\node_cache"

		查看目录配置
		npm config list
	##registry 配置

		查看当前registry 配置
		npm config get registry

		切换镜像的工具
		npm install nrm -g

		镜像设置
		-直接设置
		nrm use taobao

		-测试速度
		nrm test npm

		-临时设置
		npm i -g express --registry https://registry.npm.taobao.org

		- 设置淘宝镜像：
		npm config set registry https://registry.npm.taobao.org

		- 设置官方镜像：
		npm config set registry https://registry.npmjs.org

		开源镜像: http://npm.taobao.org/mirrors
		Node.js 镜像: http://npm.taobao.org/mirrors/node
		alinode 镜像: http://npm.taobao.org/mirrors/alinode
		phantomjs 镜像: http://npm.taobao.org/mirrors/phantomjs
		ChromeDriver 镜像: http://npm.taobao.org/mirrors/chromedriver
		OperaDriver 镜像: http://npm.taobao.org/mirrors/operadriver
		Selenium 镜像: http://npm.taobao.org/mirrors/selenium
		Node.js 文档镜像: http://npm.taobao.org/mirrors/node/latest/docs/api/index.html
		NPM 镜像: https://npm.taobao.org/mirrors/npm/
		electron 镜像: https://npm.taobao.org/mirrors/electron/
		node-inspector 镜像: https://npm.taobao.org/mirrors/node-inspector/

		-淘宝npm配置
		npm install -g cnpm --registry=https://registry.npm.taobao.org

#本地模块管理

	##安装本地模块
	- 如果你自己的模块依赖于某个包，并通过 node.js 的 require 加载，那么你应该选择本地安装，这种方式也是npm install 命令的默认行为
	npm install <package>

	##获取包的信息
	npm info <package>

	##安装的同时，将信息写入package.json中，若是有package.json文件时，直接使用npm install方法就能够根据dependencies配置安装全部的依赖包
	npm install <package> --save

	##安装的同时，将信息写入package.json中，若是有package.json文件时，直接使用npm install方法就能够根据devDependencies配置安装全部的依赖包
	npm install <package> --save-dev

	##更新本地模块

		更新前需要做的事：
		- 在 package.json文件所在的目录中执行 npm update命令。
		- 执行 npm update 命令。不应该有任何输出。
		npm outdated <package>

		更新：
		npm update <package>

	##卸载本地模块

		如需删除 node_modules 目录下面的包（package）：
		npm uninstall <package>

		从package.json文件中删除依赖：
 		- 生产环境（dependencies）
		npm uninstall --save <package>

 		- 开发环境（devDependencies）
		npm uninstall --save-dev <package>

#全局模块管理

	##安装全局模块
	如果你想将其作为一个命令行工具，那么你应该将其安装到全局。这种安装方式后可以让你在任何目录下使用这个包。比如 grunt 就应该以这种方式安装。
	npm install -g <package>

	##全局安装还需安装命令工具
	npm i -g express-generator
	##更新全局模块

		基本用法：
		npm update -g <package>

		更新全部全局模块：
		npm update -g

	##卸载全局模块
	npm uninstall -g <package>

#终端不常用命令
	##编码格式设成UTF-8
	chcp 65001
