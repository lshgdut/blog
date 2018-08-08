# 关于nodejs方面的随笔

> 真的是很随性


## chromedriver在内网无法下载或被墙的解决办法

根据实际情况，自己选择

- 如果可以连外网，直接用 [npminstall]
- 如果连不了外网，会麻烦些
	**a. 临时方案**
	
	1. 看错误日志，会有下载链接的，比如`http://chromedriver.storage.googleapis.com/2.40/chromedriver_linux64.zip`, 先公网把文件下载下来
	2. 在下载的目录，根据下载链接，建立相同的目录格式，比如下面的则建个目录`2.40`
	3. 把下载的文件重命名成`chromedriver_linux64.zip`，放到`2.40`目录下
	4. 在下载的目录，用`npx hs`起个http服务器
	3. 切换到新的窗口，配置环境变量 `CHROMEDRIVER_CDNURL=http://127.0.0.1:8080`
	4. 再重新`npm install`就可以了

	**b. 最佳方案**
	
	一两次这样搞可以，多了就麻烦，如果想一劳永逸地解决，可以参考这样的方法
	1. 在自己的电脑，或者在公司统一规划个服务器，常驻个WEB服务，把所需的版本文件下载下来，有条件的话全爬下来
	2. 在`.npmrc`文件或者系统环境变量中加入`CHROMEDRIVER_CDNURL`环境变量的配置，就这样，尽情地 `npm install`


[npminstall]: https://github.com/cnpm/npminstall
