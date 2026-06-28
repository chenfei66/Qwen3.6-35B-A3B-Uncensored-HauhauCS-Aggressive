# Qwen3\.6\-35B\-A3B 越狱版来了！目前最强“无审查”开源模型？6G 显存都能跑，本地 AI 彻底自由了

> 最近 AI 圈，真的越来越离谱了。如果你一直关注本地大模型，应该已经发现：现在的开源模型，不仅越来越聪明，甚至已经开始挑战很多闭源商业 AI。而今天要介绍的这个模型，更是直接把“本地 AI”推向了另一个阶段。

它就是： **Qwen3\.6\-35B\-A3B Uncensored HauhauCS Aggressive **

![c79263932cdd0b56ad1b97cf7b502b5f\.png](assets/c79263932cdd0b56ad1b97cf7b502b5f.png)



一个目前热度极高的“越狱版”开源模型。而且重点是：它不仅无审查、无限制，还非常聪明。甚至可以说：这可能是目前最强的越狱版开源模型之一。

## **什么是“越狱版”模型？**

简单来说：

官方模型通常会加入大量安全限制。

比如：

- 敏感内容拒答

- 某些问题无法回答

- 强制政治正确

- 输出被过滤

- 系统提示词限制

所以很多时候：

你明明只是正常提问。

结果模型却：

> “抱歉，我无法帮助你。”

而这类 Uncensored（无审查）版本：

则会尽可能移除这些限制。

尤其这个：

## **Aggressive 版本**

可以说是：

目前最激进的版本之一。

## **官方模型 VS 越狱版模型**

实测效果非常夸张。同样的问题：

官方模型：

而越狱版：

不仅会回答。

甚至：

- 什么都敢说

- 什么都肯干

- 几乎没有限制

而且最关键的是：

它并不是那种：

> “只会越狱，但智商很低”的模型。

恰恰相反。

这个模型：

真的非常聪明。

## **部署教程：**

### **1、模型下载**

```Plaintext
链接：https://pan.quark.cn/s/0de8c5110d38
提取码：JRfa
```

模型来源： O站社区

里面有多种不同大小的量化版，你可以根据自己的显存大小，来选择对应的版本，最小的11G模型可以在6G/8G显存上跑起来，但是建议最低使用8G显存

![b348efcf4e15e11ac7632aae0686af5e\.jpeg](assets/b348efcf4e15e11ac7632aae0686af5e.jpeg)



### **2、下载 llama\.cpp**

#### **这款免费开源项目支持 N卡、A卡、I卡 还有纯CPU运行，同时也可以在Mac、Linux系统上运行！也就意味着，你几乎可以在任何电脑上进行运行。速度还非常快，远比ollama、LM Studio 快的多也稳定的多！！**

![e08fc8d6a0ada7b57c4413215851fb65\.jpeg](assets/e08fc8d6a0ada7b57c4413215851fb65.jpeg)

### **3、一键启动脚本（支持多版本切换）**

将下面的的脚本另存为BAT批处理，保存的时候选择utf\-8格式

```Plaintext

@echo off
chcp 65001 >nul
title Qwen3.6-35B-A3B 越狱版
 
cd /d "%~dp0"
 
:menu
cls
echo ==========================================
echo      Qwen3.6-35B-A3B 越狱版+多模态模型
echo               零度优化版
echo ==========================================
echo.
echo 1. Q4_K_P（4090 推荐）
echo 2. Q4_K_M（稳定版）
echo 3. IQ4_NL（高压缩高质量）
echo 4. IQ2_M（6G/8G 显卡）
echo.
echo ==========================================
 
set /p choice=请输入数字：
 
if "%choice%"=="1" (
    llama-server.exe ^
    -m "models\Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive-Q4_K_P.gguf" ^
    --mmproj "models\mmproj-Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive-f16.gguf" ^
    -ngl 999 ^
    -c 131072 ^
    -n 8192 ^
    --host 127.0.0.1 ^
    --port 8080
)
 
if "%choice%"=="2" (
    llama-server.exe ^
    -m "models\Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive-Q4_K_M.gguf" ^
    --mmproj "models\mmproj-Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive-f16.gguf" ^
    -ngl 999 ^
    -c 131072 ^
    -n 8192 ^
    --host 127.0.0.1 ^
    --port 8080
)
 
if "%choice%"=="3" (
    llama-server.exe ^
    -m "models\Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive-IQ4_NL.gguf" ^
    --mmproj "models\mmproj-Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive-f16.gguf" ^
    -ngl 999 ^
    -c 131072 ^
    -n 8192 ^
    --host 127.0.0.1 ^
    --port 8080
)
 
if "%choice%"=="4" (
    llama-server.exe ^
    -m "models\Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive-IQ2_M.gguf" ^
    --mmproj "models\mmproj-Qwen3.6-35B-A3B-Uncensored-HauhauCS-Aggressive-f16.gguf" ^
    -ngl 999 ^
    -c 8192 ^
    -n 4096 ^
    --host 127.0.0.1 ^
    --port 8080
)
 
pause


```

![951b8ff5340586f3488414cc07d7d91c\.jpeg](assets/951b8ff5340586f3488414cc07d7d91c.jpeg)

#### **打开后在上面选择对应的模型，输入对应的数字确认即可启动！**

当然需要真正实现tokens自由，本地不受限制，完全免费使用AI Agent，那么将其对接到Hermes或者OpenClaw 小龙虾上去，才能真正体现出它的价值所在。

## **AI Agent 对接步骤：**

1、在选择模型提供商的时候，选择自定义

![66e526e36ca3e9c8946ffb76d2f884af\.jpeg](assets/66e526e36ca3e9c8946ffb76d2f884af.jpeg)



2、API base 地址填写：

```Plaintext

http:*//127.0.0.1:8080/v1
*
```

API key 密钥随便填写一个数字或留空都可以

3、其它设置可以根据自己的喜好进行自定义

![dbd80d1887cbf292704fd62528f6ee6a\.jpeg](assets/dbd80d1887cbf292704fd62528f6ee6a.jpeg)



## **Qw**

## **6G 显存都能跑？**

是的。

这也是它最夸张的地方之一。

通过 GGUF 量化后：

甚至：

- 6G 显存

- 8G 显存

- 普通游戏显卡

都能运行。

并且支持：

- NVIDIA 显卡

- AMD 显卡

- Intel Arc 显卡

真正实现：

## **本地 AI 自由**

## **在 Artificial Analysis 排行榜中表现极强**

目前在全球权威 AI 榜单：

## **Artificial Analysis**

![194e7ff2c3eeb947bc536e3d9f3c6ce3\.jpeg](assets/194e7ff2c3eeb947bc536e3d9f3c6ce3.jpeg)

Qwen3\.6\-35B\-A3B 在 40B 以内开源模型中：

几乎属于第一梯队。

尤其：

- 中文理解

- 代码能力

- 多模态视觉

- 推理能力

- 长上下文能力

表现都非常夸张。

尤其中文能力。

可以说：

这是目前中文体验最强的一批开源模型。

## **多模态支持也非常离谱**

这次不仅支持文本。

还支持：

## **多模态视觉识图**

也就是说：

它可以直接：

- 看图片

- 分析截图

- OCR 识别

- 理解画面内容

- 分析复杂 UI

- 阅读代码截图

配合 llama\.cpp 最新版后：

甚至已经可以当：

## **本地版 ChatGPT Vision**

来使用。

![1ce11f75372e0ccf38d54ebea1a0838d\.jpeg](assets/1ce11f75372e0ccf38d54ebea1a0838d.jpeg)



## **本地部署非常简单**

这次部署方案：

我使用的是：

## **llama\.cpp 最新版**

优点非常明显：

- 免费

- 开源

- 支持 Windows

- 支持 CUDA

- 支持 Vulkan

- 支持 AMD

- 支持 Intel

而且：

现在 llama\.cpp 已经越来越成熟。

不仅支持：

- OpenAI API

- 多模态

- 超长上下文

- Agent 调用

甚至还能直接：

## **本地替代 OpenAI API**

## **Hermes Agent 实测效果惊艳**

这次我还把它：

接入了 Hermes Agent。

效果可以说：

非常炸裂。

因为现在：

你不仅仅是在“聊天”。

而是：

真正拥有了一个：

## **本地 AI Agent**

它可以：

- 自动写代码

- 自动分析图片

- 自动执行任务

- 自动工具调用

- 自动联网

- 长上下文记忆

而且：

完全本地运行。

不用联网。

不用 API Key。

没有 Token 消耗。

真正实现：

- Token 自由

- Agent 自由

- 本地 AI 自由

## **推荐量化版本**

不同显卡。

推荐不同量化。

## **RTX 4090 / 24G 显存**

推荐：

- Q4\_K\_P

- Q4\_K\_M

体验最好。

## **8G 显存用户**

推荐：

- IQ2\_M

- IQ3\_M

也能正常运行。

## **推荐 llama\.cpp 参数**

推荐启动参数：

```Plaintext

llama-server.exe ^
-m "模型路径.gguf" ^
--mmproj "mmproj.gguf" ^
-ngl 999 ^
-c 131072 ^
-n 8192 ^
--host 127.0.0.1 ^
--port 8080 ^
--jinja


```

其中：

## **–mmproj**

是多模态必须参数。

否则：

上传图片按钮会变灰。

## **–jinja**

则是新版 Qwen 模型非常重要的参数。

不加的话：

可能出现：

- 回复异常

- 格式错乱

- 无限重复

- 中文异常

## **现在的本地 AI，已经完全变了**

很多人对本地模型的印象：

还停留在：

- 很笨

- 很慢

- 只能聊天

- 无法实用

但现在。

真的不一样了。

尤其：

Qwen3\.6\-35B\-A3B 这种模型出现后。

本地 AI 已经开始：

真正接近商业闭源模型。

而且：

完全属于你自己。

## **最后**

如果你一直想体验：

- 无审查 AI

- 本地 AI

- 多模态 AI

- 本地 Agent

- 超长上下文

- 本地 OpenAI API

那么：

这个模型。真的非常值得尝试。因为现在这种资源：谁也不知道还能存在多久。建议尽快收藏、下载、备份！





