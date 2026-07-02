## xiaolu_mcp_ha
- [English](README.en.md)
- [中文](README.md)

Homeassistant MCP server for Xiaolu AI，directly connect to Xiaolu AI official server.

[Add this repository to HACS](https://my.home-assistant.io/redirect/hacs_repository/?owner=LuwuDynamics&repository=xiaolu_mcp_ha&category=integration)

### Capabilities
#### 1.HomeAssistant itself acts as an MCP server and connects directly to the Xiaolu server via the websocket protocol without the need for a proxy.
#### 2.Select multiple API groups (HomeAssistant's build in Intent APIs and user-configured MCPServer) in one entity and proxy them to Xiaolu
#### 3.Support configuring multiple entities at the same time

---
### Function demonstration

- [Access demonstration video](https://www.bilibili.com/video/BV1XdjJzeEwe)
- [Control TV presentation (via custom script)](https://www.bilibili.com/video/BV18DM8zuEYV)
- [HomeAssistant、LLM、MCP、Xiaolu AI advanced tutorials](https://www.bilibili.com/video/BV1SruXzqEW5)

---
 
### Installation：

Make sure HACS is installed in Home Assistant

1.Open HACS and search for xiaolu or xiaolu_mcp_ha

2.Download the component

3.Restart Home Assistant.

### Configuration：

[Settings > Devices & Services > Add Integration] > Search for "Mcp" > Find MCP Server for Xiaolu

Next > Please fill in the Xiaolu MCP access point address, select the required MCP > Submit. 

Note that the Assist in the llm_hass_api checkbox is the HA built-in function, 
and the other options are other MCP servers you had connected in HomeAssistant (you can directly proxy to Xiaolu here)

Configuration is complete! Wait a minute and go to Xiaolu's access point page and click refresh to check the

---

### Debugging Instructions

 1.The tools exposed depend on the type of entity you expose to the HomeAssistant voice assistant
   
 2.Try to use the latest version of HomeAssistant. There are obvious differences in the tools provided by the May version and the March version.

 3.If debugging doesn't work as expected, first check Xiaolu's chat log to see how he handles the command and whether he has a tool that calls HomeAssist. Currently, a major known issue is that lighting and music control can conflict with the built-in screen and music control logic. This will be resolved after the server supports built-in tool selection.
 
 4.If the process correctly calls the built-in function of HA, you can open the debug log of this plug-in to observe the actual execution status.
