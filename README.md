
## 介绍

网赚游戏是一款基于uniCloud、uni-ad的趣味合成类游戏。

本游戏基本特征如下：
- 玩家通过签到、抽奖等方式赚取金币，使用金币购买低等级猫，将同级别猫合成为更高等级猫；
- 玩家通过努力，可合成分红猫，获取平台分红收益，可提现；
- 金币不足时，玩家可通过观看激励视频广告，获取新的金币；
- 玩家通过邀请好友一起养猫，下线观看激励视频，邀请者可获得激励，可转为现金并在平台提现。


## 体验地址

<!-- #### 应用汇【萌猫成长】已正式上线，下载地址：[萌猫成长](http://www.appchina.com/app/io.dcloud.game.cat) -->


体验包下载地址：[Android安装包](https://mp-3469aac7-a663-4c5d-8ee8-94275f8c09ab.cdn.bspapp.com/cloudstorage/__UNI__GameCat_20230802160607.apk)




###  DCloud网赚游戏交流群，欢迎大家加入！

交流群1：645630288（已满）   <a target="_blank" href="https://qm.qq.com/cgi-bin/qm/qr?k=LzE3YTjyZ0bSVbsYjohkfA3Qzlp5rlMV&jump_from=webapi"><img border="0" src="//pub.idqqimg.com/wpa/images/group.png" alt="DCloud网赚游戏交流群" title="DCloud网赚游戏交流群"></a>

交流群2：711753236   <a target="_blank" href="https://qm.qq.com/cgi-bin/qm/qr?k=UVxKKUluBQUz6xBcYBxJHbaSANFBzjwZ&jump_from=webapi"><img border="0" src="//pub.idqqimg.com/wpa/images/group.png" alt="DCloud网赚游戏2群" title="DCloud网赚游戏2群"></a>

加群时请备注你的DCloud appid，[什么是DCloud appid说明](https://ask.dcloud.net.cn/article/35907)。



游戏界面如下：

![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-01.png)

![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-02.png)



## 项目优势

1. 对于只懂js的开发者，可以独立从事网赚、零撸创业。前端到后端都是js，源码拿走就能用
2. 本项目基于serverless，永远不必担心服务器扛不住、不必为服务器开发技术不到位而操心、不必为运维操心、不必打各种补丁、不必做硬件扩容、不必管ddos攻击...
	这么好的服务器，会很贵吗？答案是：uniCloud的阿里云版完全免费。而腾讯云版的价格也远低于传统云的虚拟机。
3. DCloud提供从技术、到二开（由授权合作伙伴提供二次开发）、到变现、到运营的一条龙创业辅助。

网赚创业，从这里开始！





## 项目构成


前端基于uni-app开发，后端基于[uniCloud](https://uniapp.dcloud.net.cn/uniCloud/README)开发

整个网赚合成游戏，有2个项目，复用同一个uniCloud空间。一个项目是App端，另一个项目是管理端。

管理端面向开发商的运营人员使用，设置游戏参数，查看玩家日志，审批提现等，**admin管理后台是另外插件**，另见：[https://ext.dcloud.net.cn/plugin?id=4102](https://ext.dcloud.net.cn/plugin?id=4102)。

本插件即为App端，面向手机用户使用，功能包括：
- cocos游戏模块：基于cocos开发，主要处理萌猫的新购、合成等，最后编译为html，通过webview组件内嵌到uni-app项目中。
- 账户及邀请裂变系统：基于[uni-id](https://uniapp.dcloud.net.cn/uniCloud/uni-id)的账户体系，登陆注册一应俱全，天然支持裂变分享。
- 广告变现系统：包括开屏、激励视频。激励视频广告，是网赚行业价值链的顶端。详见[uni-ad广告联盟](https://uniad.dcloud.net.cn/)
- 防刷系统：前端代码加密、客户端证书校验、模拟器/root/网络代理识别 [详见](https://uniapp.dcloud.net.cn/api/a-d/rewarded-video?id=%e5%ae%89%e5%85%a8%e6%b3%a8%e6%84%8f)
- 支付结算系统：计算用户收益，及用户的上线收益，支持用户提现、微信自动转账。它基于[uniPay](https://uniapp.dcloud.net.cn/uniCloud/unipay)




#### 【网赚游戏规则说明】：
[https://catgame.dcloud.io/markdown-share-docs/0ca7ade3867d3c5bf43a924f22644aac/](https://catgame.dcloud.io/markdown-share-docs/0ca7ade3867d3c5bf43a924f22644aac/)



#### 【正式商用部署流程(完整版)】：
[http://catgame.dcloud.io/markdown-share-docs/b20819f880bc3ea962e0f38564ea71ab/](http://catgame.dcloud.io/markdown-share-docs/b20819f880bc3ea962e0f38564ea71ab/)



#### 一键更新此插件

一键更新此插件：在项目根目录package.json右键点击，“从插件市场更新”。

> 注意：更新合并时，去掉勾选 `uni_modules` --》 `uni-config` --》 `uniCloud` --》 ... --》 `uni-id`和 `uni-pay`，以及`manifest.json`，防止配置文件被重置，需要重新配置。更新后注意检查其他配置文件。


### 1.7.0版本：新增uni统计2.0，老版本升级更新说明

1. 上传所有云函数和公共模块
2. database右键上传所有DB Schema
3. database右键初始化云数据库，弹框内选择opendb-admin-menus，覆盖选中的表，初始化新增的统计页面和admin端页面完成
4. 在manifest.json
	- uni统计--》勾选uni统计2.0--》启用App平台
	- 源码视图开启debug调试，在uniStatistics节点下新增："debug" : true，[详见文档](https://uniapp.dcloud.net.cn/uni-stat-v2.html#%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B)
	- uni统计相关配置在`uniCloud/cloudfunctions/common/uni-config-center/uni-stat/config.json`文件
	- uni统计需要发行后才有统计数据
5. 如果遇到：`初始化数据库失败。失败详情: 数据表 opendb-admin-menus 数据导入失败：唯一索引 menu_id 值重复，请检查 db_init.json 文件中是否含有与已有数据重复的_id或其他唯一索引字段，修改或删除后重试。`，在uniCloud web控制台删除数据表 opendb-admin-menus，在db_init.json重新初始化`opendb-admin-menus`。
6. 完成以上操作和项目相关配置后，打自定义基座调试。 
7. admin管理后台--》系统管理--》应用管理--》新增应用，填写appid、应用名称等信息
8. 启动uni统计后，何时可以查看报表数据？[详见文档](https://uniapp.dcloud.net.cn/uni-stat-v2.html#%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)




为了方便快速体验此游戏，本文档部署流程分为：**真机体验快速部署流程**（尽量减少各项配置，目的快速完成部署体验此游戏）和**正式商用部署流程**（需要申请各项配置，等待审核周期长），请根据自身需求选择。




## 真机体验快速部署流程


### 1. 开通uniCloud

- 开通uniCloud：本项目是云端一体的，它的云端代码需要部署在uniCloud云服务空间里，需要开通uniCloud。在[https://unicloud.dcloud.net.cn/](https://unicloud.dcloud.net.cn/)登录，按云厂商要求进行实名认证。
- 在uniCloud认证通过后，创建一个服务空间给本项目使用。选择阿里云或腾讯云均可。[参考](https://uniapp.dcloud.net.cn/uniCloud/price)
- 使用HBuilderX 3.1以上版本（最好是最新版），把本项目导入到HBuilderX中，在项目根目录uniCloud上点右键菜单，关联服务空间 -> 选择之前创建的服务空间

#### 2. 开通App一键登陆

App登录分一键登陆和微信登录两种方式。初期体验时在微信申请登录很麻烦，可以先开通一键登陆快速体验。一键登陆是运营商提供的、比短信验证码更方便、更安全、更便宜的方案。[详见](https://uniapp.dcloud.net.cn/univerify)。

- `manifest.json`--》`App模块配置` --》`OAuth（登录鉴权）`--》` 一键登录`，点击后面的`开通配置`
- 在随后打开的web界面中，同意协议，并点击充值按钮充值。如只是测试，可以只充值1元钱。
- 如果你已经确定包名，则可以在web界面点击“添加应用”，提交审核。这个是正式打包必须的。真机运行可以跳过此环节。


#### 3. uni-id里配置一键登录

打开文件 `uniCloud` --》 `cloudfunctions` --》 `common` --》 `uni-config-center` --》 `uni-id`--》 `config.json`，

找到如下节点：`service` --》 `univerify`，填写`appid`。`appid`就是`manifest`里的`appid`。



#### 4. 配置云函数url化

打开uniCloud控制台 [https://unicloud.dcloud.net.cn/](https://unicloud.dcloud.net.cn/)，找到关联该项目的服务空间进入，点击左侧找到云函数下的云函数列表，点击云函数域名绑定。

![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-03.png)

腾讯云，复制默认域名（不含https://）部分。

![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-04.jpg)

阿里云/支付宝小程序云，启用域名，复制域名。

![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-05.jpg)


##### 复制的域名配置在以下两处：

- 在`uniCloud`--》 `cloudfunctions`--》 `common`--》 `globalunit`--》 `utils`--》 `config`--》 `index.js` 里面进行修改，在`data`--》 `globalinfo`--》 `url` 填写复制的域名（注意不能加http或https，**阿里云/支付宝小程序云需添加PATH部分的/http，配置格式例如：url："346xxxxxxxxxxxxxxxxxx9ab.bspapp.com/http"**） 。

- 在`uniCloud`--》 `database`--》 `gameconfig.init_data.json`文件内--》 `url`填写复制的域名。(**阿里云/支付宝小程序云需添加PATH部分的/http，配置格式例如：url："346xxxxxxxxxxxxxxxxxx9ab.bspapp.com/http"**)


![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-06.jpg)


##### 云函数url化配置：
	
本项目需对`hallctrl`、`minectrl`、`teamctrl` 三个云函数url化。

- 阿里云、支付宝小程序云服务空间，配置格式例如：`/http/teamctrl`，目前已默认配置好了，你无需再配置。
- 腾讯云服务空间，则需要分别在以上三个云函数目录下的`package.json`里，更改`cloudfunction-config`下的`path`路径为：/函数名，配置格式例如：`/teamctrl`


#### 5. 初始化数据库、上传云函数
 
方式一：
- 在项目`uniCloud`--》`database`目录，右键选择 “初始化云数据库”。
- 在项目`uniCloud`--》`database`目录，右键选择 “上传所有DB Schema及扩展校验函数”。
- 在项目`uniCloud`--》`cloudfunctions`目录右键，选择 “上传所有云函数、公共模块及actions”。

方式二：
- 在项目`uniCloud`目录右键，选择“运行云服务空间初始化向导”，点击“下一步”，点击“开始部署”。



#### 6. 跨域配置

如运行在iOS上，需解决本地页面跨域问题。

在 [uniCloud web控制台](https://unicloud.dcloud.net.cn/) 跨域配置里添加：**localhost:13131**

![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-07.jpg)



#### 7. 真机运行

到此为止，就可以真机运行跑起来了。这里运行的广告，是测试广告位，不会产生真实收益。

如果你要商用，还得申请各种资质。具体见下一章文档。

注意：
- ios必须制作自定义基座，运行到自定义基座测试，[什么是自定义调试基座及使用说明](https://ask.dcloud.net.cn/article/35115)



## 正式商用部署流程

在完成真机运行的基础之上，可继续如下流程。

### 准备工作

网赚游戏投入运营前，需完成如下准备工作：

首先确定App的应用名称、包名、证书，后续在各个三方服务申请时，都需要包名和证书摘要。并且注意在HBuilderX中打包时，必须使用相同的包名和证书。

应用名称在`manifest`里设置，注意不要包含“游戏”字样，否则上架应用商店时可能会被要求提供游戏版号。请以应用的名义上架。


- 申请软件著作权：开通广告必须要求软著。软著的uni-im群加入链接：[点击加群](https://im.dcloud.net.cn/#/?joinGroup=65d8604c9847e92db03ff828)
- 申请uni-ad：开通增强广告，申请激励视频的广告位，详见[uni-ad官网](https://uniad.dcloud.net.cn)
- 申请一键登录：在 `manifest.json`--》 `App模块配置` --》` OAuth（登录鉴权）`--》 `一键登录`，点击后面的`开通配置`，在打开的web页面添加应用，充值。
- 申请微信登录：在**微信开放平台**申请移动应用，获得的appid和appsecret，用于微信登录、微信分享。[微信开放平台](https://open.weixin.qq.com/)
> 申请要求提供应用官网，如果还是没有官网的同学，可使用**官网模板**插件：[https://ext.dcloud.net.cn/plugin?id=8935](https://ext.dcloud.net.cn/plugin?id=8935)。
> [网赚游戏官网预览地址](https://static-mp-c028af40-3251-4959-9015-24dce394ef82.next.bspapp.com/web/)
> 
> 微信 appid 申请步骤：[https://ask.dcloud.net.cn/article/208](https://ask.dcloud.net.cn/article/208)
>  
> iOS平台微信SDK配置通用链接：[https://ask.dcloud.net.cn/article/36445](https://ask.dcloud.net.cn/article/36445)
> 
- 提现方式有两种选择：微信企业付款到零钱和个人支付宝批量转账方式。**暂时无法开通微信商户支付的用户可选择个人支付宝方式转账**。选择微信提现方式，需要申请微信提现：用于将网赚激励直接打款到手机用户的微信零钱中。在微信商户平台申请，需要完成企业资质认证，在产品中心，开通企业付款到零钱功能：微信官方要求需要有90天注册时长，近30天连续业务流水，并状态良好的账号方可开通。[微信支付商户平台](https://pay.weixin.qq.com/)。
- 小程序和App备案，软著申请等参考[备案专题](https://uniapp.dcloud.net.cn/tutorial/beian.html)，或前往[开发者商店](https://market.aliyun.com/agents/yscdcloud)。


- Android平台快速生成云端证书：从HBuilderX3.2.0及以上版本开始支持服务器生成证书，在[DCloud开发者中心](https://dev.dcloud.net.cn/)，应用管理--》我创建的应用--》选择应用进入--》应用证书管理--》创建证书，收到邮件通知，证书创建成功，可以查看证书详情。
> Android平台云端打包证书使用说明：[https://ask.dcloud.net.cn/article/35985](https://ask.dcloud.net.cn/article/35985)




以上业务都有审核周期，请提前处理。


#### 开通广告所需条件

1. 开通快手广告：需要提供软著和合作授权书（授权书在uni-ad申请后台获取，需要签字盖章上传）
2. 开通优量汇广告：需要上架应用商店和软著
3. 开通穿山甲广告：需要具备公司资质，需要上架和软著
4. 百度百青藤广告联盟：支持开屏、插屏、激励视频广告，请使用HBuilder3.4.0版本以上进行打包
5. 华为广告联盟（Android平台）： 包括开屏、信息流、插屏、激励视频广告，请使用HBuilder3.4.0版本以上进行打包
6. 开通sigmob：无上架要求，无需软著，仅支持激励视频。在uni-AD后台点击申请


> 注： Sigmob属于小型广告联盟，收益偏低。如有条件，还需开通优量汇，快手等广告渠道以便提高收益
> 
> HBuilderX3.4.0+已支持自动配置插屏广告（无需额外开发）。在应用启动或应用后台切到前台的场景时，开屏广告展示过后进入到应用内立即展示插屏广告。您可在uni-ad后台“APP增强广告开屏管理”中配置该功能开启或者关闭。
> 
> 华为广告需开发者在华为应用市场上架，且华为广告目前只展示在华为手机上。华为广告的收益相对较高，但华为广告接入标准较严，如应用不符合平台接入标准会被拒审。
> 
> 为了广告收益最大化，uni-ad建议您的应用至少要开通3家以上广告渠道（能多开就多开），只有开通3家以上广告渠道后优化算法才能有效启动。

网赚游戏开发完成后，需要开通广告，推荐流程为：申请软著 --》 开通快手广告 --》上架应用市场 --》 开通优量汇广告 --》若有公司资质可开通穿山甲广告。



### 配置参数

#### 1. manifest.json配置

完成如下配置：

- 基础配置 --》uni-app应用标识（AppID）点击获取
- App图标配置 --》点击浏览，选择此项目根目录下icon.png图标，或选择一张你自己的应用图标，[应用图标配置注意事项](https://ask.dcloud.net.cn/article/35979)
- App模块配置 --》 OAuth（登录鉴权）--》 勾选微信登录 --》 填写`appid`、`appsecret`、`ios平台通用链接`。
- App模块配置 --》 Share（分享）--》 微信分享 --》 填写`appid`、如需在iOS平台使用还需要配置通用链接，填写`ios平台通用链接`。
- App模块配置 --》 OAuth（登录鉴权）勾选`苹果登录`，[IOS苹果授权登录参考文档](https://ask.dcloud.net.cn/article/36651)。如不发布到Appstore，不需要配置此项
- App常用其他设置  --》 填写关联域Associated Domains  [参考教程](https://ask.dcloud.net.cn/article/36393)。如不发布到Appstore，不需要配置此项
- 源码视图中 --》 `app-plus` --》 `privacy` 设置`服务协议和隐私政策`弹框，将协议链接替换成你自己的。

#### 2. uni-id配置

在项目目录`uniCloud`--》 `cloudfunctions`--》 `common` --》 `uni-config-center`--》 `uni-id`--》 `config.json`文件里：

- 微信登录填写`appid` 、`appsecret`,在微信开放平台查看，[微信开放平台](https://open.weixin.qq.com/)
- 苹果登录需要配置，`app-plus`--》  `oauth`--》  `apple`，填写包名`bundleId`



#### 3. 提现方式配置


提现方式有两种方式：支付宝个人批量转账和微信企业付款到零钱，可自行按需选择。**暂时无法开通微信商户支付的用户可选择个人支付宝方式转账**



**支付宝方式**


- 提现要求：用户需要在app端，在我的页面完成实名认证，在设置页面完成支付宝账号绑定
- 在网赚游戏前端项目
	- `uniCloud`--》`cloudfunctions`--》`common`--》`globalunit`--》`utils`--》`config`--》`index.js`里搜索一下tixiantype，修改配置`tixiantype`下的 `type：zhifubao`（表示支付宝提现方式），修改完成后，上传云函数。
	- 在`uniCloud`--》`database`--》`gameconfig.init_data.json`里搜索一下`tixiantype`，修改配置`type：zhifubao`（表示支付宝提现方式），修改完成后，重新初始化gameconfig云数据库。
	- 若出现索引提示无法初始化，可在[uniCloud web控制台](https://unicloud.dcloud.net.cn/)云数据库下的`gameconfig`，新增记录。若已存在`"_id": "tixiantype"`记录，修改`"type": "zhifubao"`即可。
```js
{
	"_id": "tixiantype",
	"type": "zhifubao"
}
```
- 提现操作，详见[网赚游戏管理后台](https://ext.dcloud.net.cn/plugin?id=4102)




**微信方式**


- 提现要求：用户需要在app端，在我的页面完成实名认证，在提现页面绑定微信
- 在网赚游戏前端项目
	- `uniCloud`--》`cloudfunctions`--》`common`--》`globalunit`--》`utils`--》`config`--》`index.js`里搜索一下`tixiantype`，修改配置`tixiantype`下的 `type：weixin`（表示微信提现方式），修改完成后，上传云函数。
	- 在`uniCloud`--》`database`--》`gameconfig.init_data.json`里搜索一下`tixiantype`，修改配置`type：weixin`（表示微信提现方式），修改完成后，重新初始化gameconfig云数据库。
	- 若出现索引提示无法初始化，可在[uniCloud web控制台](https://unicloud.dcloud.net.cn/)云数据库下的`gameconfig`，新增记录。若已存在`"_id": "tixiantype"`记录，修改`"type": "weixin"`即可。
```js
{
	"_id": "tixiantype",
	"type": "weixin"
}
```



确保已开通微信支付商户，企业付款到零钱功能。
在项目目录`uniCloud`--》 `cloudfunctions`--》 `common`--》`uni-config-center` --》 `uni-pay` --》`config.json`文件内，配置如下：

```js
	{
		"app":{
			"weixin" : {
				"appid" : "wxxxxxxxxxxxxxxx",//公众号id
				"mchid" : "00000000000",//商户id
				"partnerKey" : "xxxxxxxxxxxxxxxxxxxxx"//安全密钥
			}
		}
	}
```



**添加apiclient_cert.p12证书**

微信支付接口中，涉及资金回滚的接口会使用到API证书，包括退款、撤销接口。商家在申请微信支付成功后，收到的相应邮件后，可以按照指引下载API证书，也可以按照以下路径下载：微信商户平台(pay.weixin.qq.com)--》账户中心--》账户设置--》API安全。[更多内容详见](https://pay.weixin.qq.com/wiki/doc/api/tools/mch_pay.php?chapter=4_3)

在 `minectrl`--》 `controller`目录下和 `uni-admin`--》 `controller` 目录下添加从你自己微信商户平台下载的API证书`apiclient_cert.p12`。


教程参考，[微信App支付功能申请](https://uniapp.dcloud.net.cn/api/plugins/payment?id=app%e5%b9%b3%e5%8f%b0%e6%94%af%e4%bb%98%e6%b5%81%e7%a8%8b)

如果在接入过程中遇到问题参考[微信付款到零钱文档](https://pay.weixin.qq.com/wiki/doc/api/tools/mch_pay.php?chapter=14_2)中错误码排查。

对 `uniCloud`--》 `cloudfunctions`目录点右键，上传所有云函数及公共模块。




#### 4. 广告位配置



**激励视频广告位配置**

现在是默认的激励视频测试广告位，广告位标识（adpid）为：1507000689，仅用于测试，不会产生真实收益。

你需要在[uni-ad系统](https://uniad.dcloud.net.cn/)里申请激励视频广告位，获得广告位ID（即：adpid）。

在项目目录`hybrid`--》 `html`--》 `index.html`
- `_adpid`填写激励视频广告位id
- `adpid`填写信息流广告位id（显示于签到弹框下方）

广告后台申请的广告位(adpid)需要自定义基座/云打包/本地打包后生效



**插屏广告位和信息流广告配置**


在项目目录`common`--》 `globalunit.js`，配置如下：

 
 ```html
 
	this.interstitialAdpid = "1111111113";// 插屏广告测试广告位 ：1111111113，仅用于HBuilderX标准基座真机运行测试，不会产生真实收益。
	this.bannerAdpid = "1111111111"; // 我的页面、喵喵团页面，信息流测试广告位：1111111111，仅用于HBuilderX标准基座真机运行测试，不会产生真实收益。
	
```


测试广告位，仅在HBuilderX标准基座中有效，仅用于测试，不会产生收益。

正式商用需要替换成你自己广告后台申请的广告位(adpid)，再自定义基座/云打包/本地打包后生效 


> 注意：未上架的应用，申请开通快手广告后，可申请插屏广告；广点通和穿山甲需要上架后才可开通插屏广告

[详见插屏广告文档](https://uniapp.dcloud.io/api/a-d/interstitial)

教程参考：[uni-ad广告联盟使用指南](https://ask.dcloud.net.cn/article/36769)


#### 5. 激励视频回调配置

激励视频广告可以支持广告服务器到业务服务器的回调，用于业务系统判断是否提供奖励给观看广告的用户。配置服务器回调后，当用户成功看完广告时，广告服务器会访问配置的云函数，通知用户完成观看激励视频。

相对来讲服务器回调将更加安全，可以依赖**广告平台的反作弊机制**来避免用户模拟观看广告完成的事件。[详见](https://uniapp.dcloud.io/api/a-d/rewarded-video?id=callback)


你需要在[uni-ad系统](https://uniad.dcloud.net.cn/)的激励视频广告位，点击**配置激励视频**，出现以下界面，选择服务空间，选择激励视频回调云函数`videocallvack`，保存。


![](https://web-ext-storage.dcloud.net.cn/ext/game/ad-video-secret-1.jpg)


选择已配置好的广告位，展开可查看到`Secret`，如下：


![](https://web-ext-storage.dcloud.net.cn/ext/game/ad-video-secret-2.jpg)


在`uniCloud`--》`cloudfunctions`--》`common` --》`uni-config-center` --》`uni-pay` --》`config.json`文件配置`secret`如下：

```js

{
	"app": {
		"AD":{
			"secret":"XXXXXXXXXXXXXXXXXXXX"//uni-ad 后台开通激励视频回调后生成的 secret
		}
	}
}
```


在`uni-config-center`目录，右键‘上传公共模块’




#### 6. 配置分享下载链接

裂变拉新是必要的传播手段，使用直接`uni-portal`统一发布页，一键式生成统一发布页静态页面，更快，更高效的访问。

- 多版本灵活展示，多平台适配，实时线上更新
- 实时生成当前页面二维码，方便手机扫码访问、下载
- 自动判断浏览器环境进行提示，如：在微信浏览器中会引导用户使用相应的浏览器打开

- 插件地址：uni-portal 统一发布页 [https://ext.dcloud.net.cn/plugin?id=7100](https://ext.dcloud.net.cn/plugin?id=7100)
	
1. 在admin管理端--》升级中心--》制作统一发布页--》填写信息，保存后下载index.html，将此文件上传至前端网页托管（为了不与其他冲突，可新建个目录存放），部署完毕后获得链接
2. 在项目目录`common`--》 `globalunit.js`里面修改`downloadurl`下载地址为上一步得到的网址，配置如下：

 ```html
	this.downloadurl = "xxxxxxxx";//分享地址
```



#### 7. 配置打开应用市场评价


在项目目录`common`--》 `globalunit.js`里配置`iosMarketId`和`androidMarketId`，如下：


 ```html
	this.iosMarketId = "id123456789";//appStore下载地址最后id
	this.androidMarketId = "xxxxxxxxx";//Android上架应用市场的应用包名
```





#### 8. 隐私政策弹框


根据工业和信息化部关于开展APP侵害用户权益专项整治要求，App提交到应用市场必须满足以下条件：

- 应用启动运行时需弹出隐私政策协议，说明应用采集用户数据
- 应用不能强制要求用户授予权限，即不能“不给权限不让用”
- 如不希望应用启动时申请“读写手机存储”和“访问设备信息”权限，请参考：[https://ask.dcloud.net.cn/article/36549](https://ask.dcloud.net.cn/article/36549)


配置弹出“隐私协议和政策”：在项目的`manifest.json`--》 `源码视图`--》 `app-plus`--》 `privacy` 节点，添加以下代码片段，修改文字内容，替换服务协议和隐私政策链接。保存后**提交云端打包生效**。

```js
	"privacy" : {
		"prompt" : "template",
		"template" : {
			"title" : "服务协议和隐私政策",
			"message" : "  请你务必审慎阅读、充分理解“服务协议”和“隐私政策”各条款，包括但不限于：为了更好的向你提供服务，我们需要收集你的设备标识、操作日志等信息用于分析、优化应用性能。<br/>  你可阅读<a href=\"https://ask.dcloud.net.cn/protocol.html\">《服务协议》</a>和<a href=\"https://ask.dcloud.net.cn/protocol.html\">《隐私政策》</a>了解详细信息。如果你同意，请点击下面按钮开始接受我们的服务。",
			"buttonAccept" : "同意",
			"buttonRefuse" : "暂不同意"
		}
	}
```


**隐私权政策协议模板**，可参考[Android平台隐私与政策提示框配置方法](https://ask.dcloud.net.cn/article/36937)文章附件。

**不同细分领域的App隐私政策模板**，可参考使用，[APP隐私政策模板](https://docs.getui.com/templet/)

[Android平台 uni-app(5+ app) 应用上架应用市场合规指南](https://ask.dcloud.net.cn/article/39073)





#### 9. 自动绑定上下级关系


通过发送携带专属邀请码的下载页给同伴或用户安装App，能够自动发展下级好友、以及绑定新用户从属关系。


1. 在`common`--》`globalunit.js`文件配置：

```html
	//裂变分享功能需配置以下几项
		this.domainName = ""; //分销裂变下载页的域名
		this.appName = "萌猫成长"//app名称
		this.share = {
			title:"萌猫成长",//分享标题
			summary:"萌猫成长是一款趣味合成类网赚游戏。",//分享描述
			imageUrl:""//缩略图
		}
	//下载页面信息
		this.about = {
			logo:"",//app-logo
			appName:"萌猫成长",//app名称
			slogan:"趣味合成类网赚游戏",//app-slogan
			version:"1.0.0",//app版本号
			company:""//公司名称
		}
```



2. 下载页前端网页托管方式
	- 分开部署到不同服务空间：新建一个服务空间，开通前端网页托管，用于托管邀请好友下载页。不要和admin后台管理部署到同一个前端网页托管，否则会导致覆盖问题。
	- 部署到同一个服务空间：可以使用不同的基础路径来区分，在猫游戏前端项目--》manifest.json--》h5配置--》运行的基础路径，配置/download/，用于托管下载页面，若是网赚游戏admin管理后台，可配置/admin/，完成配置后操作步骤【6】即可。 [详见](https://uniapp.dcloud.io/uniCloud/hosting?id=host-uni-app)
	![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-10.jpg)
	
3. 在`uniCloud`--》`database`--》`opendb-app-versions.schema.json`，开启读取权限，将read：false改为 **read：true** ，右键'上传此DB schema'

![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-11.jpg)

4. 增加应用版本名称和应用版本号信息，打包app成功后，在admin管理后台--》升级中心--》发布新版。

5. 因浏览器跨域问题，发行H5站点时需[uniCloud web控制台](https://unicloud.dcloud.net.cn/)，`跨域配置`配置安全域名，允许该域名跨域访问云函数服务器。

6. 发行分销裂变下载页：点击`发行`--》`上传网站到服务器`--》点`上传`（未开通前端网页托管需要点击`开通托管`，去[uniCloud web控制台](https://unicloud.dcloud.net.cn/)，`前端网页托管`--》`点击开通`）


**注意事项**

- 本项目需要HBuilderX 3.1.22+ 以上版本
- 配置分销裂变下载页的域名：在[uniCloud web控制台](https://unicloud.dcloud.net.cn/)，`前端网页托管`--》`参数配置`，找到默认域名或者配置网站域名，用默认域名（访问次数有限制），上线**一定要配置自己购买的域名**。



#### 10. 更换素材 

如果你需要把猫素材替换成其他内容（例如：兔子、猪等），在项目根目录下`hybrid` --》 `html` --》 `res`  --》 `raw-assets`下修改图片可更换素材。


**登录页替换‘网赚游戏’图片替换**：

- `static` --》`login` --》`logo.png` ，替换此图片，注意此处只替换了登录页的‘网赚游戏’这几个字
- 如果需要替换整张背景图，`static` --》`login` --》`bg.png` ，替换此背景图片，并在 `pages` --》`login` --》`login.vue` 页面删除第4行和第5行的代码。


**首页进度条加载背景图替换**


在项目根目录下`hybrid` --》 `html` --》 `res` --》`raw-assets`--》`07` 内替换首页进度条加载背景图。


**注意：图片名称、格式、尺寸必须和原图片一致**



#### 11. APP云打包

IOS和Android云打包，配置正确的包名，勾选广告，打包。




## 二次开发

本项目已包含cocos模块，无需申请cocos游戏源码也可部署成功。

如果你需要二开，改动cocos游戏源码，或者获取本项目的图片的psd原图，则需按照以下步骤申请：

-  在[DCloud开发者中心](https://dev.dcloud.net.cn/)，完成账号的企业实名认证。
-  使用在HBuilderX中注册的邮箱，发邮件到uniad@dcloud.io，说明企业是否有此类网赚游戏的成功案例经验做出简单介绍说明，以及公司的具体信息（包含：企业名、法人、联系方式）
-  审核需要3-5个工作日，请耐心等待，会有专人回复邮件，谢谢！




## 其他说明

本项目由DCloud委托大连一家外包公司开发，该公司同时承接二开定制工作。如有二开需求，请加QQ：691878059或1418504531（添加时备注来意）。

DCloud正在寻找更多行业服务商，开发各种基于uniCloud的项目，如论坛、阅读、短视频.... 由DCloud出资，开发完毕后上架插件市场，然后行业合作伙伴可持续接二开的项目。有意成为uniCloud行业服务商的公司或个人可以联系`bd@dcloud.io`。[详见](https://ask.dcloud.net.cn/article/38878)



## 上架必看


- 应用名称不要包含“游戏”、“网赚”字样，否则上架应用商店时可能会被要求提供游戏版号，请以应用的名义上架。
- 大部分应用市场，上架需要提供计算机软件著作权证书，软著中应用名称，与提交的应用名称需要一致。
- 各应用市场上架应用资质未达到的，可先上架谷歌Googlplay商店。谷歌上架注意：不要包含广告相关SDK ，否则很容易被驳回或封禁账号
- 谷歌上架成功后，可申请开通优量汇广告，无需提供软著。



**IOS上架注意：**

- 不要提到网赚游戏，看广告有收益等内容，第一版上架建议先**关闭和广告、红包、赚钱、奖励相关内容**，否则审核会因引导用户看广告，大概率被驳回。
- 上架前，若有第三方微信登录，同时也要求提供苹果登录，可自行替换符合苹果登录的规范按钮， [详见Buttons](https://appleid.apple.com/signinwithapple/button)。



开通广告，可选上架应用渠道包括：应用宝、豌豆荚、小米应用商店、魅族应用市场、安智市场、酷安市场、乐商店、4399、Googleplay、华为、9游、vivo、360、oppo、百度应用市场（只能进行优量汇审核）。

> 建议优先上架：360应用市场、应用宝、百度应用市场、豌豆荚、Googleplay

[Android应用市场上架uni-app(5+App)应用合规指南](https://ask.dcloud.net.cn/article/39073)

[苹果App上架App Store注意事项，避免被拒！](https://ask.dcloud.net.cn/article/36312)



## FAQ：常见问题

1. 登录失败问题，请根据以上文档仔细检查各项登录配置。前端的 `login.js `中，打印登录错误回调信息，看具体原因。
2. 首页加载不了，去[uniCloud web控制台](https://unicloud.dcloud.net.cn/)检查云数据库 `gameconfig` 配置中url是否填写正确。查看hallctrl函数运行日志，将日志信息打包发给我们。
3. 自定义基座调试，一键登录失败，HBuilderX控制台报错：
```js
[本地调试]"[hallctrl]返回结果：" {"code":4001,"message":"errCode: 4001 | errMsg: 获取手机号码失败：uni一键登录 apiKey 不存在"} 
```

解决方案：选择**连接云端云函数**

![](https://web-assets.dcloud.net.cn/ext/moneygame/moneygame-12.jpg)

4. 新增`uni-config-center`，注意事项：如果你是在`cloudfunctions`右键‘上传所有云函数、公共模块及actions’，需要单独在`cloudfunctions`--》`common`--》`uni-config-center` 目录单独上传一次，右键‘上传公共模块’。
5. 本项目代码可以商用，无需为DCloud付费。但您只能在DCloud产品体系内使用本软件及其源码。您不能将源码修改后运行在DCloud产品体系之外的环境，比如客户端脱离uni-app，或服务端脱离uniCloud，或脱离uni-ad。这将违反使用许可协议。
6. 欢迎加入网赚游戏交流群，QQ群号：645630288，加群时请备注你的DCloud appid，[什么是DCloud appid说明](https://ask.dcloud.net.cn/article/35907)。
