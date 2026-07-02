# xiaolu_mcp_ha

[English](README.en.md) | [中文](README.md)

Home Assistant MCP Server, providing WebSocket access to Xiaolu AI's official server.

[Add this repository to HACS](https://my.home-assistant.io/redirect/hacs_repository/?owner=LuwuDynamics&repository=xiaolu_mcp_ha&category=integration)

## Features

1. Home Assistant acts as an MCP Server, connecting directly to the Xiaolu server via WebSocket protocol without any intermediary
2. Supports selecting multiple API groups within a single entity (Home Assistant built-in control APIs and user-configured MCP Servers), unified and proxied to Xiaolu
3. Supports configuring multiple entities simultaneously

## Installation

Ensure HACS is installed in Home Assistant.

1. Open HACS and search for `xiaolu` or `xiaolu_mcp_ha`
2. Download and install the component
3. Restart Home Assistant

## Configuration

Navigate to **Settings > Devices & Services > Add Integration**, search for "Mcp", and find **MCP Server for Xiaolu**.

Enter the Xiaolu MCP access point address, select the desired MCP, and submit.

> **Note:** The Assist option in the `llm_hass_api` checkbox represents the Home Assistant built-in function. Other options are MCP Servers you have integrated into Home Assistant, which can be directly proxied to Xiaolu.

After configuration, wait approximately one minute, then refresh the access point page in Xiaolu to verify the status.

## Debugging

1. **Exposed tools** depend on the entity types you expose to the Home Assistant voice assistant.
   - Path: Settings > Voice Assistants > Expose

2. Use the latest version of Home Assistant whenever possible, as tool availability varies significantly between versions.

3. If debugging results are unexpected, first check Xiaolu's chat log to verify whether Home Assistant tools are being invoked correctly. A known issue is that lighting and music control may conflict with the built-in screen and music control logic. This will be resolved once the server supports built-in tool selection.

4. If the process correctly invokes HA's built-in functions, enable the plugin's debug log to observe the actual execution details.
