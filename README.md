## wavely
## nuclei模版管理工具
由于没找到一款比较好用的poc管理器，便自己开发了这个。
### POC管理器
- 实现nuclei poc管理的桌面应用
- 支持`MacOS`、`Windows`和`Linux`操作系统
- 使用nuclei v3检测引擎
- 兼容yamlv2和yamlv3 nuclei template
- 实现多任务、并行扫描

# 使用
## poc模版导入
### 手动导入
#### macos
对于MacOS和Linux，初次打开App会在家目录生成模版文件夹
``` bash
ls /Users/$USER/.wavely/templates # macos
ls /home/$USER/.wavely/templates    # linux
```
#### windows
会在wavely.exe的同级目录下创建.wavely/templates，将poc放入此文件夹中

#### 导入
如下图所示
![main](imgs/13.png)
### App指定路径导入
![alt text](imgs/14.png)
### 模版管理
![main](imgs/1.png)

### 扫描
选择thinkphp的poc进行扫描
![main](imgs/2.png)
扫描结果
![main](imgs/3.png)
可复制扫描结果
###  编辑nuclie模版
编辑模版
![main](imgs/8.png)
匹配请求包
![main](imgs/9.png)
匹配响应包
![main](imgs/10.png)
### 添加Nuclei模版
![main](imgs/11.png)

### App设置
主题
![main](imgs/4.png)

代理
![main](imgs/5.png)

扫描
![main](imgs/6.png)

模版导入
![main](imgs/7.png)
## 关于

邮箱：hsmcool@qq.com