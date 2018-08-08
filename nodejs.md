# 关于nodejs方面的随笔

> 真的是很随性


## chromedriver在内网无法下载或被墙的解决办法

以下方法任选其一

- 如果可以连外网，直接用 [npminstall]
- 如果连不了外网，会麻烦些
	1. 看错误日志，会有下载链接的，比如`http://chromedriver.storage.googleapis.com/2.40/chromedriver_linux64.zip`, 先公网把文件下载下来
	2. 在下载的目录，根据下载链接，建立相同的目录格式，比如下面的则建个目录`2.40`
	3. 把下载的文件重命名成`chromedriver_linux64.zip`，放到`2.40`目录下
	4. 在下载的目录，用`npx hs`起个http服务器
	3. 切换到新的窗口，配置环境变量 `CHROMEDRIVER_CDNURL=http://127.0.0.1:8080`
	4. 再重新`npm install`就可以了



[npminstall]: https://github.com/cnpm/npminstall
