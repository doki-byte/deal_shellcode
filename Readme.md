### 前言

分享一个最近折腾了好久的shellcode免杀处理平台，平台采用wails进行打包，windows用户双击即可运行生成所需文件。

目前集成模板15个，后续将增加新的处理模式。

### 环境准备

wails采用webview2运行，当系统不存在时会自动下载

<img src="images/image-20241211232501434.png" alt="image-20241211232501434" style="zoom: 80%;" />

<img src="images/image-20241211232457173.png" alt="image-20241211232457173" style="zoom: 67%;" />

1. 程序采用go生成文件，需要先行安装go环境

2. 设置go环境变量

   ~~~
   go env -w CGO_ENABLED=1
   ~~~

3. 下载go依赖包

   ~~~
   go get github.com/gonutz/ide
   go get github.com/mitchellh/go-ps
   go get golang.org/x/sys
   go get github.com/spf13/cobra
   ~~~

4. 下载gcc

~~~
https://blog.csdn.net/qq_45876765/article/details/132586631
~~~

### 使用教程

下载程序

~~~
https://github.com/doki-byte/deal_shellcode/releases/download/v1.0/ShellCode.rar
~~~

双击打开

![image-20241211231335494](images/image-20241211231335494.png)

上传生成的bin文件

点击处理bin文件

![image-20241211232211811](images/image-20241211232211811.png)

点击编译生成，等待生成完成即可

![image-20241211232233468](images/image-20241211232233468.png)

### 查杀结果

![image-20241211232351810](images/image-20241211232351810.png)

![image-20241211232645708](images/image-20241211232645708.png)

**360部分会报QVM，添加数字证书和资源文件即可**

![image-20241211233130458](images/image-20241211233130458.png)

云传结果

![image-20241211233211353](images/image-20241211233211353.png)
