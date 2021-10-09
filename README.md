# script-goldfinger

青龙面板跑金银手指脚本教程（一天差不多1.2元）


## 前言：解放双手，挣点小毛。

注意：推荐一个容器运行1-2个账号，账号多了会限制，可以多容器跑

收益：只看文章的话，跑满每日12000金币（1.2元），被限制阅读另说
每满4000金币（4毛）微信自动提现


![Snipaste_2021-10-09_13-48-52.jpg](https://i.loli.net/2021/10/09/KXhIYFqV3DoPxf5.jpg)


**微信扫二维码，开启金银手指自动阅读文章**

![DrVmjEdWB4peCzc](https://i.loli.net/2021/10/09/DrVmjEdWB4peCzc.jpg)

## 安装青龙面板
```
docker run -dit \
-v $PWD/ql/config:/ql/config \
-v $PWD/ql/db:/ql/db \
-v $PWD/ql/repo:/ql/repo \
-v $PWD/ql/raw:/ql/raw \
-v $PWD/ql/scripts:/ql/scripts \
-v $PWD/ql/log:/ql/log \
-v $PWD/ql/jbot:/ql/jbot \
-v $PWD/ql/ninja:/ql/ninja \
-p 5700:5700 \
-p 5701:5701 \
-e ENABLE_HANGUP=true \
-e ENABLE_TG_BOT=true \
-e ENABLE_WEB_PANEL=true \
--name qinglong \
--hostname qinglong \
--restart always \
whyour/qinglong:latest
```

## 登录青龙面板

浏览器进网址：http://ip:5700

## 开始步骤：

首先打开Charles或Fiddler，开启抓包模式

抓包微信，微信再次扫描二维码，不用操作,自动阅读文章，阅读10S左右就可以返回，看到金币增加200即可,就会看到所需的变量值。


### 上面的TOKEN以及User_Agent的抓取教程：IOS和Android差不多，以Android为例：

```
1、打开抓包,微信进金银手指界面 找有http://apponlie.sahaj.cn的连接
2、点进去他的请求头中token 和 User-Agent
```

![hJuUo2dY9ti5c4F](https://i.loli.net/2021/10/09/hJuUo2dY9ti5c4F.png)


## 添加脚本：

```
主脚本：
ql raw https://raw.githubusercontent.com/KingRan/JD-Scripts/main/wx_jysz.js
定时：0 8-22/1 * * *
```
![UxLAzK84lM6kR3e](https://i.loli.net/2021/10/09/UxLAzK84lM6kR3e.png)

运行脚本后会自动添加阅读任务


## 重要部分：

青龙面板变量填写规则：

![](https://www.juan920.com/wp-content/uploads/2021/10/89a47a9915fa.png)

```
export soy_wx_jysz_token=""
export soy_wx_jysz_User_Agent=""

多个token用 @ 或 # 或 换行 隔开

特别注意：请使用自己的UA，防止被封，一个UA不超过两个token
```


## 运行成功图：

![](https://www.juan920.com/wp-content/uploads/2021/10/3c54ff691157.png)


## 附依赖下载地址：(已经安装青龙自动修复依赖的下面的依赖可以不用管)

[http://shandianpan.com/f/8Oc6](https://www.juan920.com/?golink=aHR0cDovL3NoYW5kaWFucGFuLmNvbS9mLzhPYzY=)

