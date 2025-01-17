<h1 align="center">Welcome to headwolf 👋</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-v0.01-blue.svg?cacheSeconds=2592000" />
  <a href="w文档" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
</p>

> Scaffolding for agile development based on Xposed and Sekiro (基于Xposed和Sekiro搭建的敏捷开发的脚手架)

> 借鉴于@[virjar大佬](https://github.com/virjar)的[Sekiro框架](https://github.com/virjar/sekiro)，感谢大佬分享:ok_woman:

### 🏠 [Homepage]()

暂无

### ✨ [Demo]()

暂无

## Features introduction

1. No restart debugging（免重启调试）
2. Configure the framework by the configuration file（由配置文件配置框架）
3. High concurrency design（高并发设计）
4. One-click automatic registration（可选功能：一键自动注册）

## Structure introduction

> 公共类
- **commons** 

  > 统一日志类
  - **Logger**
  
  > 响应线程Task类
  - **Response**
  
> 入口类 
- **entry**

  > Hook第一层入口（包括免重启等功能）
  - **BaseEntry**

  > Hook逻辑入口，由第一层入口加载，包含具体的Hook逻辑
  - **RealEntry**

> 事件处理类 
- **handlers**

  > 基础处理类
  - **BaseHandler**

  > 测试类
  - **KuaishouHandler**
  - **其他**

> 初始化管理类
- **initialization**

  > 基础初始化类
  - **BaseInit**

  > 注册类，管理与Sekiro服务端通信
  - **Register**

> 工具类
- **utils**

  > 类查询助手
  - **ClassesReaderAssistant**

  > 通信助手
  - **CommunicationAssistant**

  > 算法助手
  - **AlgorithmAssistant**

  > 配置文件助手
  - **PropertiesAssistant**

  > XSharedPreferences类助手
  - **PreferenceAssistant**
  
- **Config**

## Description
![相关图示说明](https://github.com/lateautumn4lin/diagrams_dir/blob/master/headwolf_flow.png)

## Install

```sh
step1: git clone https://github.com/lateautumn4lin/headwolf
step2: import project into android studio
step3: run the test project E.g kuaishou
```

## Usage

已实现自动化，省去该步骤 ~~**step1：** 在源码中加入hook app的包名，由于技术lj，没有能够实现自动加载配置文件、后续实现~~

>路径：com.lateautumn4lin.headwolf.entry.BaseEntry

![step1](https://github.com/lateautumn4lin/headwolf/blob/master/sources/step1.png)

**step2：** 在配置文件中配置相应hook项目的信息，包括包名和主页activity，以便于后续打开app时hook到主页activity向sekiro服务端注册

>路径：assets.config

![step2](https://github.com/lateautumn4lin/headwolf/blob/master/sources/step2.png)

**step3：** 开发对应hook app的handlers，参考现有的快手的handler模块

>路径：com.lateautumn4lin.headwolf.handlers下新建

![step3](https://github.com/lateautumn4lin/headwolf/blob/master/sources/step3.png)

已实现自动化，省去该步骤 ~~**step4：** 在Config文件中预先添加handler的实例，没有实现动态添加，后续补充~~

>路径：com.lateautumn4lin.headwolf.Config

![step4](https://github.com/lateautumn4lin/headwolf/blob/master/sources/step4.png)

**案例演示：** 看看实际演示效果！

- group
>也就是Config配置文件中group_pdd/group_kuaishou这两个值，当然你也可以自定义，group_xxxxx开头的就行

- action
>对应的是每个handler的action获取方法

- name
>这个就是在handler方法中指定的query参数了，当然也可以放在post请求的body中

![案例演示](https://github.com/lateautumn4lin/headwolf/blob/master/sources/%E8%B0%83%E7%94%A8%E6%A1%88%E4%BE%8B.png)

## Run tests

**案例测试：** 参考快手的项目

```sh
参考源码中快手和pdd项目的Hook
```

**并发测试：** 采用C:50*1000（总请求） M:1000（并发请求）的方案

![Jmeter并发测试](https://github.com/lateautumn4lin/headwolf/blob/master/sources/Jmeter%E5%B9%B6%E5%8F%91%E6%B5%8B%E8%AF%95.png)

## Author

👤 **lateautumn4lin**

* Website: https://cloudcrawler.club/
* Github: [@lateautumn4lin](https://github.com/lateautumn4lin)

## Show your support

Give a ⭐️ if this project helped you!

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
