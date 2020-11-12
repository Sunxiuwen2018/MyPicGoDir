**Typora配置图床教程**
---
[TOC]
## 一、软件简介
> 1.Typora是一款markdown编辑器
2.PicGo软件是一款自动将本地图片转成链接的工具，可以自动将图片上传网络

## 二、问题介绍
> **疼点**：平常做笔记或写文章，需要插入图片，但typora的图片仅保存在本地，变动图片位置或将文档传给其他人看，就看不到图片了，因此需要解决这个问题，图床就是一种解决方案
**图床工具**：自动将本地图片转成链接的工具，专门用来存放图片，允许你将图片对外连接的网上空间

## 三、环境准备
1. typora  :https://typora.io/#windows
2. node.js :https://nodejs.org/zh-cn/ 
3. picGo :https://github.com/Molunerfinn/PicGo

## 四、结合github搭建图床

### 1. 安装node.js【安装过程省略】【必须先安装node.js】
### 2. 安装picGO 【安装过程省略】
### 3. github上创建仓库，如下图操作即可

![图床配置-github创建仓库01](https://raw.githubusercontent.com/Sunxiuwen2018/MyPicGoDir/main/Picture/%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE-github%E5%88%9B%E5%BB%BA%E4%BB%93%E5%BA%9301.png)

### 4. github上生成token用于picgo有权限连接到github的api接口，如下图操作即可
点击`用户图标` ---> 选择`Settings` ---> 选择`Developer settings` 
保存好token密钥，之后无法看到：4e4d515b9d26d9aa9b9514ce5afec3e309255d5a

![图床配置-github创建token01](https://raw.githubusercontent.com/Sunxiuwen2018/MyPicGoDir/main/Picture/%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE-github%E5%88%9B%E5%BB%BAtoken01.png)

![图床配置-github创建token02](https://raw.githubusercontent.com/Sunxiuwen2018/MyPicGoDir/main/Picture/%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE-github%E5%88%9B%E5%BB%BAtoken02.png)

### 5. 配置picGO，如图
> 官方文档：https://picgo.github.io/PicGo-Doc/zh/guide/config.html
> 

![图床配置-github图床配置01](https://raw.githubusercontent.com/Sunxiuwen2018/MyPicGoDir/main/Picture/%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE-github%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE01.png)

![image-20201112161845108](https://raw.githubusercontent.com/Sunxiuwen2018/MyPicGoDir/main/Picture/image-20201112161845108.png)

- 几点注意：
1. 仓库名处格式严格执行：用户名/仓库名 【不要复制如git@github.com:Sun/MyPicGoDir.git---> Sun/MyPicGoDir】
2. 如需上传到指定目录，需先在仓库中创建该目录，然后配置指定存储路劲处填写如目录`Picture/`
3. github仓库主分支名master有改为main
4. 如果闲上传github太慢可以用cdn加速，在`设定自定义域名`处：https://cdn.jsdelivr.net/gh/用户名/图床仓库名
### 6. Typora中配置picGO

![图床配置-typroa中图床配置01](https://raw.githubusercontent.com/Sunxiuwen2018/MyPicGoDir/main/Picture/%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE-typroa%E4%B8%AD%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE01.png)

![图床配置-typroa中图床配置02](https://raw.githubusercontent.com/Sunxiuwen2018/MyPicGoDir/main/Picture/%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE-typroa%E4%B8%AD%E5%9B%BE%E5%BA%8A%E9%85%8D%E7%BD%AE02.png)

## 五、备注

1. 通过smms来保存图床：https://zhuanlan.zhihu.com/p/137310314
2. 通过码云来保存图床：https://www.cnblogs.com/qtzd/p/12554902.html
3. 如果出现github或者typora上传成功却显示不了图片，需修改hosts文件，复制如下映射关系到hosts文件中，[参考](https://blog.csdn.net/weixin_41279876/article/details/109040379)

```shell
# GitHub Start 
140.82.113.3      github.com
140.82.114.20     gist.github.com
151.101.184.133    assets-cdn.github.com
151.101.184.133    raw.githubusercontent.com
151.101.184.133    gist.githubusercontent.com
151.101.184.133    cloud.githubusercontent.com
151.101.184.133    camo.githubusercontent.com
151.101.184.133    avatars0.githubusercontent.com
199.232.68.133     avatars0.githubusercontent.com
199.232.28.133     avatars1.githubusercontent.com
151.101.184.133    avatars1.githubusercontent.com
151.101.184.133    avatars2.githubusercontent.com
199.232.28.133     avatars2.githubusercontent.com
151.101.184.133    avatars3.githubusercontent.com
199.232.68.133     avatars3.githubusercontent.com
151.101.184.133    avatars4.githubusercontent.com
199.232.68.133     avatars4.githubusercontent.com
151.101.184.133    avatars5.githubusercontent.com
199.232.68.133     avatars5.githubusercontent.com
151.101.184.133    avatars6.githubusercontent.com
199.232.68.133     avatars6.githubusercontent.com
151.101.184.133    avatars7.githubusercontent.com
199.232.68.133     avatars7.githubusercontent.com
151.101.184.133    avatars8.githubusercontent.com
199.232.68.133     avatars8.githubusercontent.com
# GitHub End
```



关注公众号`一个python小白重构生活之路`

![](https://raw.githubusercontent.com/Sunxiuwen2018/MyPicGoDir/main/Picture/%E6%88%91%E7%9A%84%E5%85%AC%E4%BC%97%E5%8F%B7.jpg)

