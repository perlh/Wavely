## Wavely - Nuclei POC漏洞管理与验证可视化工具
- Wiki（下载与激活）：https://github.com/perlh/Wavely/wiki

![main](imgs/3.2.5/1.png)
![main](imgs/img/11.png)

## ✨ 功能一览
- [x] **POC 模板管理**：支持对 Nuclei POC 模板的增删查改操作
- [x] **跨平台兼容**：已支持 macOS 和 Windows 系统，Linux 版本测试中
- [x] **多任务扫描**：支持多 POC、多目标批量扫描
- [x] **高级配置**：支持自定义 DNSLog 服务器、扫描速率控制及 HTTP/HTTPS/SOCKS5 多协议代理
- [x] **请求分析**：支持查看 POC 匹配时的完整请求/响应数据包
- [x] **编辑器优化**：POC 编辑器支持主题切换和字体大小调整
- [x] **模板导入**：支持一键导入 Nuclei 模板，基于 Template ID 自动去重
- [x] **任务控制**：支持手动停止扫描任务，灵活掌控测试流程
- [x] **配置持久化**：自动保存用户配置，下次启动无需重复设置参数
- [x] **API 测试**：支持对 API 接口及带目录路径的目标进行扫描
- [x] **POC 生成**：提供图形化界面辅助生成简单 POC
- [x] **扫描进度实时显示**：提供可视化进度条展示当前扫描状态
- [x] 扫描结果导出
- [x] **POC 导出**（批量导出） v3.1.7
- [x] **POC 生成优化**：Raw 格式下自动解析模板结构 v3.1.8
- [x] **全局请求头**：支持配置全局请求头（如 Cookie 等） - v3.2.3
- [x] **内置 POC 抓包**：集成抓包工具，可对扫描请求实时抓包，便于 POC 调试 v3.2.3
- [x] **新增高级搜索、重载 POC 功能** v3.2.4
- [x] **新增POC 编辑/添加时可折叠参数、目标与结果面板** v3.2.4  
- [x] **新增任务列表支持增删已选 POC** v3.2.4  
- [x] **新增支持拖拽 YAML 文件或 POC 文件夹快速导入** v3.2.4  
- [x] **新增任务列表支持导出扫描统计报告**（Beta，docx 格式）v3.2.4  
- [x] **新增POC 编辑器支持 YAML 语法检查** v3.2.4

## 1、安装
>  **常见问题**：关于使用与安装的常见疑问，可跳转至 [常见问题](#常见问题) 板块查阅。

### 1.1 MacOS （安装/更新）步骤
将 `Wavely.app` 拖移至 `Applications` 文件夹，然后在终端执行：
``` bash
sudo xattr -d com.apple.quarantine /Applications/Wavely.app 
```

### 1.2 Windows （安装/更新）步骤
- 下载压缩包并解压，运行 Wavely-windows-installer.exe 完成安装。


###  1.3 DNSLOG 设置说明
- 系统默认使用 Nuclei 官方 DNSLog 服务。
- 如需搭建私有 DNSLog 服务器，请参考：[Interactsh 搭建指南](https://github.com/projectdiscovery/interactsh)。


## 2、使用
#### 2.1 注册
Wavely 的注册与激活说明请参阅官方文档：：https://github.com/perlh/Wavely/wiki

#### 2.2 导入 POC（3.2.4及以上）
- 将包含 POC 的文件夹直接拖拽至 Wavely 主窗口，即可自动完成批量导入。

![alt text](imgs/3.2.5/3.png)
![alt text](imgs/3.2.5/7.png)

####  2.3 使用

##### 扫描
![main](imgs/3.2.5/2.png)
##### 抓包
编辑模版
![main](imgs/img/2.png)
抓包管理
![main](imgs/img/3.png)
抓包信息
![main](imgs/3.2.5/5.png)
##### 全局请求头
![main](imgs/img/6.png)
![main](imgs/img/7.png)
全局请求头详细
![main](imgs/3.2.5/6.png)


## 3、证书

软件升级或更新**不会导致许可证（license）丢失**。
但如需进行系统重装、迁移设备等操作，请**务必提前备份 license 文件**。

该文件是您本地的授权凭证，**一旦丢失将无法自动恢复**。若不慎遗失，请通过邮件与我们联系。
#### License 文件位置
- macOS / Linux
位于用户主目录的隐藏配置目录中：
```
bash
cat ~/.wavely/license
```
- Windows
位于 Wavely.exe 所在目录下，与可执行文件同级：
```
Wavely.exe
license
```




## 常见问题
### Windows 启动时闪现命令框
此为正常现象，不会对 App 功能产生任何影响，可放心使用。
###  Macos 无法打开App
因未使用 Apple 证书签名 App，可能出现解除安全验证提示，如**软件显示禁止符号** 、 **无法验证软件身份** 或 **提示已损坏故不能正常打开** ，可参考以下方案解决：

##### 方案1
在终端执行命令：
``` bash
sudo xattr -d com.apple.quarantine /Applications/Wavely.app
```
##### 方案2
执行命令：
``` bash
chmod 755 /Applications/Wavely.app/Contents/MacOS/Wavely
```


# 免责声明
本工具仅面向合法授权的企业安全建设行为，如您需要测试本工具的可用性，请自行搭建靶机环境。 为避免被恶意使用，本项目所有收录的poc均为漏洞的理论判断，不存在漏洞利用过程，不会对目标发起真实攻击和漏洞利用。 在使用本工具进行检测时，您应确保该行为符合当地的法律法规，并且已经取得了足够的授权。请勿对非授权目标进行扫描。 如您在使用本工具的过程中存在任何非法行为，您需自行承担相应后果，我们将不承担任何法律及连带责任。

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=perlh/wavely&type=Date)](https://star-history.com/#perlh/wavely&Date)

# 捐赠
如果 Wavely 对您帮助很大，您可以通过以下方式支持我们：

### 赞赏码赞助
<img src="imgs/wechat_doit2.png" alt="图片描述" width="400" height="400">
<!-- ![main](imgs/sponsor.jpg) -->