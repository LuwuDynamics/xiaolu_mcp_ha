# xiaolu_mcp_ha

[English](README.en.md) | [中文](README.md)

Home Assistant MCP Server，为小陆同学提供直连官方服务器的 WebSocket 接入能力。

[在 HACS 中添加此仓库](https://my.home-assistant.io/redirect/hacs_repository/?owner=LuwuDynamics&repository=xiaolu_mcp_ha&category=integration)

## 功能特性

1. Home Assistant 作为 MCP Server，通过 WebSocket 协议直连小陆同学服务器，无需中转
2. 支持在同一实体中同时选择多个 API 组（Home Assistant 内置控制 API、用户自配置的 MCP Server），统一代理给小陆同学
3. 支持同时配置多个实体

## 安装方法

确保 Home Assistant 中已安装 HACS。

1. 打开 HACS，搜索 `xiaolu` 或 `xiaolu_mcp_ha`
2. 下载并安装插件
3. 重启 Home Assistant

## 配置方法

进入 **设置 > 设备与服务 > 添加集成**，搜索 "Mcp"，找到 **MCP Server for Xiaolu**。

填写小陆同学 MCP 接入点地址，选择所需的 MCP，点击提交。

> **说明：** `llm_hass_api` 复选框中的 Assist 选项为 Home Assistant 内置功能，其余选项为你在 Home Assistant 中接入的其他 MCP Server，可直接代理给小陆同学。

配置完成后，等待约一分钟，前往小陆同学的接入点页面刷新并检查状态。

## 调试说明

1. **工具暴露范围**取决于你在 Home Assistant 语音助手中公开的实体类型。
   - 路径：设置 > 语音助手 > 公开

2. 建议使用最新版本的 Home Assistant，不同版本提供的工具存在明显差异。

3. 若调试结果未达预期，优先查看小陆同学的聊天记录，确认其是否正确调用了 Home Assistant 的工具。目前已知灯光控制和音乐控制可能与内置的屏幕控制、音乐控制逻辑冲突，该问题需等待服务端支持内置工具选择后解决。

4. 若流程正确调用了 HA 内置功能，可开启本插件的调试日志以观测实际执行情况。
