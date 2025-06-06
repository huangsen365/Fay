
<div align="center">
    <br>
    <img src="readme/icon.png" alt="Fay">
    <h1>FAY</h1>
	<h3>Fay数字人框架</h3>
</div>

！！重要通知：我们已经把Fay的三个版本合并成1个，并致力提供更稳定更全面的功能。

我们致力于思考面向终端的数字人落地应用，并通过完整代码把思考结果呈现给大家。Fay数字人框架，向上适配各种数字人模型技术，向下接入各式大语言模型，并且便于更换诸如TTS、ASR等模型，为单片机、app、网站提供全面的数字人应用接口。      
更新日志：https://qqk9ntwbcit.feishu.cn/wiki/UlbZwfAXgiKSquk52AkcibhHngg
文档：https://qqk9ntwbcit.feishu.cn/wiki/JzMJw7AghiO8eHktMwlcxznenIg


## **功能特点**



- 完全开源，商用免责
- 支持全离线使用
- 全时流式的支持
- 自由匹配数字人模型、大语言模型、ASR、TTS模型
- 支持数字人自动播报模式（虚拟教师、虚拟主播、新闻播报）
- 支持任意终端使用：单片机、app、网站、大屏、成熟系统接入等
- 支持多用户多路并发
- 提供文字交互接口、语音交互接口、数字人驱动接口、管理控制接口、自动播报接口、意图接口
- 支持语音指令灵活配置执行
- 支持自定义知识库、自定义问答对、自定义人设信息
- 支持唤醒及打断对话
- 支持服务器及单机模式
- 支持机器人表情输出
- 支持react agent自主决策执行、主动对话（准备升级到MCP协议）
- 支持后台静默启动
- 支持deepseek等thinking llm
- 设计独特的认知模型
- 支持MCP
- 提供配置管理中心

###               

## **Fay数字人框架**

![](readme/chat.png)

![](readme/controller.png)

![](readme/mcp.png)






## **源码启动**


### **环境** 
- Python 3.12
- Windows、macos、linux

### **安装依赖**

```shell
pip install -r requirements.txt
```

### **配置**
+ 仓库已提供默认的 `system.conf` 文件，可按需修改

### **依赖说明**
Fay 需要外部语音识别（ASR）、语音合成（TTS）和大语言模型（LLM）等服务配合使用，上述地址和密钥均在 `system.conf` 中配置。例如：

```ini
ASR_mode = funasr
local_asr_ip = 127.0.0.1
local_asr_port = 10197
gpt_base_url = http://127.0.0.1:5010/v1
gpt_api_key = <your key>
```

若这些服务未启动或网络不可达，启动或交互时可能会在终端看到 `Connection error.` 提示。
请检查 `system.conf` 中 `gpt_base_url` 等设置是否正确，并确保 ASR、TTS 和语言模型服务均已启动并可访问。

### **音频设备问题**
在无声卡环境（如部分 Docker 容器）运行时，`pygame` 初始化音频输出可能导致 `ALSA lib` 报错。框架在代码中自动设置 `SDL_AUDIODRIVER=dummy` 以避免该问题，如仍有报错可手动在启动前设置：

```bash
export SDL_AUDIODRIVER=dummy
```

### **启动**
启动Fay控制器
```shell
python main.py start
```



## **或 Docker 启动**

1. 克隆仓库（已包含默认 `system.conf`，可按需修改）
2. 使用下列命令构建镜像（修改配置后需要重新 build）。Dockerfile 会自动安装构建依赖


```bash
docker build -t fay -f docker/Dockerfile .
```

运行（容器会自动启动 Fay 服务）

```bash
docker run -it --rm -p 5010:5010 -p 5000:5000 -p 10001:10001 -p 10002:10002 -p 10003:10003 fay
```


## **高级玩法**

![](readme/interface.png)



### ***使用数字人（非必须）***

ue: https://github.com/xszyou/fay-ue5

unity：https://qqk9ntwbcit.feishu.cn/wiki/Se9xw04hUiss00kb2Lmci1BVnM9

metahuman-stream（2d）：https://qqk9ntwbcit.feishu.cn/wiki/Ik1kwO9X5iilnGkFwRhcnmtvn3e

duix（android)：https://qqk9ntwbcit.feishu.cn/wiki/Ik1kwO9X5iilnGkFwRhcnmtvn3e()

aibote(windows cpu克隆人)：[‬‍‬‍⁠﻿‍‍‍‌﻿﻿https://qqk9ntwbcit.feishu.cn/wiki/ULaywzVRti0HXWkhCzacoSPAnIg



### ***集成到自家产品（非必须）***
接口：https://qqk9ntwbcit.feishu.cn/wiki/Mcw3wbA3RiNZzwkexz6cnKCsnhh



### **联系**

**交流群及资料教程**关注公众号 **fay数字人**（**请先star本仓库**）

![](readme/gzh.jpg)
