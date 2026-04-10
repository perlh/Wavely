
# Wavely — Nuclei POC 管理与漏洞验证工具

🔍 面向安全研究人员的本地化 POC 管理与漏洞验证平台。
- 激活码获取：[Wavely 官方 Wiki](https://github.com/perlh/Wavely/wiki)

![main](imgs/3.3.2/1.png)
![main](imgs/3.3.2/2.png)
![main](imgs/3.3.2/3.png)

###  ✨ 功能一览
- [x] 团队协作：支持 POC 共享与远程 POC 仓库接入（v3.3.0及以上）
- [x] POC 模板管理：增删查改、导入去重（基于 Template ID）
- [x] 多任务扫描：支持多 POC、多目标批量运行，可手动停止任务
- [x] 请求分析与调试：完整请求/响应查看、内置抓包、HTTP 请求重放
- [x] 编辑器体验：主题切换、字体大小调整、YAML 语法检查、Raw 自动解析
- [x] 高级配置：自定义 DNSLog、扫描速率控制、HTTP/HTTPS/SOCKS5 代理、请求超时
- [x] 搜索与过滤：关键词组合搜索、基于 tag/author 的分组过滤、高级搜索与POC重载
- [x] 导入与导出：拖拽 YAML/POC 文件夹快速导入、批量导出 POC、导出扫描统计报告（xlsx、docx）
- [x] 配置持久化：自动保存用户配置，下次启动无需重复设置
- [x] API 测试：支持对接口及带目录路径的目标进行扫描
- [x] 扫描进度与结果：可视化进度展示，支持结果导出
- [x] 跨平台兼容：支持macOS 与 Windows
- [x] 支持原创POC接入，可实现多Wavely客户端同一个POC库，并实现分角色远程管理POC库





###  1、安装指南
##### MacOS
1. 将 `Wavely.app` 拖入「Applications / 应用程序」文件夹
2. 打开终端执行以下命令以移除系统隔离属性：

```bash
sudo xattr -d com.apple.quarantine /Applications/Wavely.app
```

#### Windows
1. 下载最新压缩包并解压
2. 运行 `Wavely-windows-installer.exe` 完成安装

#### 版本升级
> 1. macOS：拖动 `Wavely.app` 覆盖旧的 `Wavely.app` 即可
> 2. Windows：用新的 `Wavely.exe` 覆盖旧的 `Wavely.exe` 即可


### 2、使用说明

#### 2.1 🔐 客户端激活使用
- 激活码作为生成license的key，使用一次后即失效。
- 激活成功后会在本地生成 `license` 文件，该文件即为本机专属的激活密钥。**请妥善保管你的 license。**


| 平台 | 路径 |
|---|---|
|macOS / Linux| ~/.wavely/license |
|Windows| 与 Wavely.exe 同级目录下|

如你之前购买过 Wavely，可直接导入 `license` 文件进行激活：
![alt text](./imgs/3.3.2/15.png)

#### 2.2 POC共享服务部署
[下载Wavely-server程序](https://github.com/perlh/Wavely/releases),按如下图即可运行程序即可。
![alt text](./imgs/3.3.2/17.png)

客户端填写好参数后，启用POC服务即可
![功能页面](imgs/3.3.2/9.png)
### 3、更多页面
POC管理页面
![功能页面](imgs/3.3.2/1.png)
POC任务扫描页面
![功能页面](imgs/3.3.2/2.png)
POC添加
![功能页面](imgs/3.3.2/16.png)
模版编辑
![功能页面](imgs/3.3.2/3.png)
抓包工具
![功能页面](imgs/3.3.2/4.png)
请求重放
![功能页面](imgs/3.3.2/5.png)
工具箱
![功能页面](imgs/3.3.2/6.png)
设置页面
![功能页面](imgs/3.3.2/7.png)
POC远程管理页面
![功能页面](imgs/3.3.2/8.png)

连接POC共享库时，右上角会有标记
![功能页面](imgs/3.3.2/10.png)
左侧可以对标签、作者进行分类，方便快速筛选
![功能页面](imgs/3.3.2/11.png)
高级搜索支持不包含字段
![功能页面](imgs/3.3.2/12.png)
扫描任务支持快捷参数设置，支持设置全局请求头
![功能页面](imgs/3.3.2/13.png)
请求/响应详情，支持记录单个POC发出的所有http请求响应
![功能页面](imgs/3.3.2/14.png)
激活输入框
![功能页面](imgs/3.3.2/15.png)



### 4、常见问题
#### Windows 启动时短暂出现命令框？
✅ 属于正常现象，不影响功能，可放心使用

#### macOS 无法打开 App？
由于未使用 Apple 官方证书签名，可能出现以下提示：
- “已损坏，无法打开”
- “无法验证开发者身份”
- App 图标显示禁止符号

 ✅ 解决方案
方案一（推荐）：
```bash
sudo xattr -d com.apple.quarantine /Applications/Wavely.app
```
方案二：修复执行权限
```bash
chmod 755 /Applications/Wavely.app/Contents/MacOS/Wavely
```
### ⚠️ 免责声明
本工具仅用于合法授权的企业安全建设场景。如需测试本工具的可用性，请自行搭建靶机环境。
- 为避免被恶意使用，本项目收录的 POC 均为漏洞的理论判断，不包含漏洞利用过程，不会对目标发起真实攻击或利用。
- 在使用本工具进行检测时，需确保行为符合当地法律法规，并已取得充分授权。
- 请勿对非授权目标进行扫描；如在使用过程中存在任何非法行为，相关后果由使用者自行承担，项目不承担任何法律或连带责任。


### 📈 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=perlh/wavely&type=Date)](https://star-history.com/#perlh/wavely&Date)

### ❤️ 支持我们
如果 Wavely 对你的工作有所帮助，欢迎通过赞赏支持开发。

微信赞赏码：
<div align="center">
<img src="imgs/wechat_doit2.png" alt="微信赞赏" width="300" />
</div>
你的支持是我们持续维护和迭代的动力，感谢每一位用户 🙏



- 📌 项目地址：[github.com/perlh/Wavely](https://github.com/perlh/Wavely)

- 📩 反馈与激活问题：id_0909186@foxmail.com
