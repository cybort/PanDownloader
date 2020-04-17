# PanDownloader
简易的百度网盘下载器，通过分块下载提升百度网盘下载速度

# **和PanDownload没有关系，而且已经基本失效，大家不要盲目和浪费时间在这个项目上了**

使用方法：
```shell
Usage of pandownloader:
  -bduss string
    	BDUSS cookie
  -block uint
    	max block size (default 20971520)
  -chunk uint
    	max chunk size (default 1048576)
  -debug
    	enable debug mode
  -dir string
    	download dir
  -name string
    	download file name
  -size uint
    	concurrent downloads size (default 32)
  -url string
    	url to download, required
```

示例：  
使用默认配置下载
```shell
./PanDownloader-linux-amd64 a_direct_download_link
```
自定义并发下载数量
```shell
./PanDownloader-linux-amd64 -url a_direct_download_link -size 128
```

> 如果需要下载自己网盘中未分享的文件，需要指定BDUSS cookie，可以在浏览器baidu.com的cookie中找到，下载自己网盘内的非分享文件会被百度限制多线程下载的并发数量，所以**下载别人分享的文件时最好不要指定cookie，会影响下载速度**

配置文件：
如果不想每次命令行传参调用，可以使用配置文件：pandownloader.json
```json
{
  "bduss": "",
  "dir": "",
  "size": 32,
  "block": 20971520,
  "chunk": 1048576
}
```

配合使用工具：
1. [EX-百度云盘]

其他开源项目推荐：
1. [Proxyee Down]
2. [BaiduPCS-Go]

[EX-百度云盘]: https://github.com/gxvv/ex-baiduyunpan "导出下载地址脚本"
[Proxyee Down]: https://github.com/proxyee-down-org/proxyee-down "Java多线程分段下载器"
[BaiduPCS-Go]: https://github.com/iikira/BaiduPCS-Go "Go语言百度网盘客户端"
