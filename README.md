## xiaolu_mcp_ha

- [English](README.en.md)
- [中文](README.md)

Homeassistant MCP server for 小陆同学，直连小陆同学官方服务器。

[在 HACS 中添加此仓库](https://my.home-assistant.io/redirect/hacs_repository/?owner=LuwuDynamics&repository=xiaolu_mcp_ha&category=integration)

### 插件能力介绍
#### 1.HomeAssistant自身作为mcp server 以websocket协议直接对接小陆同学服务器，无需中转
#### 2.在一个实体里同时选择多个API组（HomeAssistant自带控制API、用户自己配置的MCPServer）并将它们一起代理给小陆同学
#### 3.支持同时配置多个实体

---
### 功能演示

- [接入演示视频](https://www.bilibili.com/video/BV1XdjJzeEwe)
- [控制电视演示（通过自定义script实现）](https://www.bilibili.com/video/BV18DM8zuEYV)
- [HomeAssistant、LLM、MCP、小陆同学的进阶教程](https://www.bilibili.com/video/BV1SruXzqEW5)

---
 
### 安装方法：

确保Home Assistant中已安装HACS

1.打开HACS, 搜索 xiaolu 或 xiaolu_mcp_ha

2.下载插件

3.重启Home Assistant.

### 配置方法：

[设置 > 设备与服务 > 添加集成] > 搜索"Mcp" >找到MCP Server for Xiaolu

下一步 > 请填写小陆同学MCP接入点地址、选择需要的MCP > 提交。

注意llm_hass_api 复选框里  Assist 就是ha自带的function，其他选项是你在HomeAssistant里接入的其他mcp server（可以在这里直接代理给小陆同学）

配置完成！！！稍等一分钟后到小陆同学的接入点页面点击刷新，检查状态。

---

### 调试说明

 1.暴露的工具取决于你公开给Homeassistant语音助手的实体的种类
 
    设置 -> 语音助手 -> 公开
   
 2.尽量使用最新版本的homeassistant，单单看5月版本跟3月版本提供的工具就有明显差异

 3.调试时未达到预期，优先看小陆同学的聊天记录，看看小陆同学对这句指令如何处理的，是否有调用homeassistant的工具。目前已知比较大的问题是灯光控制和音乐控制会和内置的屏幕控制、音乐控制逻辑冲突，需要等服务端支持内置工具选择后可解。
 
 4.如果流程正确的调用了ha内置的function，可以打开本插件的调试日志再去观测实际的执行情况。
