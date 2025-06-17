[![MseeP.ai Security Assessment Badge](https://mseep.net/pr/skyworkai-mureka-mcp-badge.png)](https://mseep.ai/app/skyworkai-mureka-mcp)



<div class="title-block" style="text-align: center;" align="center">

![export](https://raw.githubusercontent.com/SkyworkAI/Mureka-mcp/refs/heads/master/assets/mureka_mcp.png)

[![Discord Community](https://raw.githubusercontent.com/SkyworkAI/Mureka-mcp/refs/heads/master/assets/discord_mureka.svg)](https://discord.com/invite/nwu9ANqAf5)
[![Twitter](https://raw.githubusercontent.com/SkyworkAI/Mureka-mcp/refs/heads/master/assets/x_mureka.svg)](https://x.com/Mureka_AI)
[![PyPI](https://raw.githubusercontent.com/SkyworkAI/Mureka-mcp/refs/heads/master/assets/pypi_mureka.svg)](https://pypi.org/project/mureka-mcp)

</div>
<p align="center">
  Official Mureka Model Context Protocol (MCP) server that enables interaction with powerful lyrics, song and bgm generating APIs. This server allows MCP clients like <a href="https://www.anthropic.com/claude">Claude Desktop</a>, <a href="https://github.com/openai/openai-agents-python">OpenAI Agents</a> and others to generate lyrics, song and background music(instrumental).
</p>

## Quickstart with Claude Desktop

1. Get your API key from [Mureka](https://platform.mureka.ai/apiKeys).
2. Install `uv` (Python package manager), install with `curl -LsSf https://astral.sh/uv/install.sh | sh` or see the `uv` [repo](https://github.com/astral-sh/uv) for additional install methods.
3. Go to Claude > Settings > Developer > Edit Config > claude_desktop_config.json to include the following:

```
{
    "mcpServers": {
        "Mureka": {
            "command": "uvx",
            "args": [
                "mureka-mcp"
            ],
            "env": {
                "MUREKA_API_KEY": "<insert-your-api-key-here>",
                "MUREKA_API_URL": "https://api.mureka.ai",
                "TIME_OUT_SECONDS":"300"
            }
        }
    }
}
```

Then restart the Claude app and see 4 MCP tools available in the window, indicating successful loading
<div class="title-block" style="text-align: left;">
<img src="https://raw.githubusercontent.com/SkyworkAI/Mureka-mcp/refs/heads/master/assets/img.png" width="400">
</div>

## Optional features
You can add the `TIME_OUT_SECONDS` environment variable to the `claude_desktop_config.json` to set the timeout period for song or bgm generation waiting(Default 60s).

## Example usage

⚠️ Warning: Mureka credits are needed to use these tools.
Try asking Claude:
- "Please create a song for my daughter Jessica to wish her a happy birthday and play it"
<div class="title-block" style="text-align: left;">
<img src="https://github.com/SkyworkAI/Mureka-mcp/blob/master/assets/demo.jpeg?raw=true" width="400">
</div>

- "Please generate lyrics about Christmas"
- "Please generate a song based on the lyrics just now"
- "Please generate background music suitable for playing in the coffee shop"
<div class="title-block" style="text-align: left;">
<img src="https://github.com/SkyworkAI/Mureka-mcp/blob/master/assets/demo1.jpeg?raw=true" width="400">
</div>

[bgm 1 download](https://github.com/SkyworkAI/Mureka-mcp/raw/407ad955ab29c61e81b5d374e492ef8b1353c2f3/assets/16567807049729-9pi6MDiVqTavVUdjf54fmW.mp3)

[bgm 2 download](https://github.com/SkyworkAI/Mureka-mcp/raw/407ad955ab29c61e81b5d374e492ef8b1353c2f3/assets/16567807049729-D7WVCcxp77Prm8b15HSX1G.mp3)

## Troubleshooting

Logs when running with Claude Desktop can be found at:

- **Windows**: `%APPDATA%\Claude\logs\mcp-server-Mureka.log`
- **macOS**: `~/Library/Logs/Claude/mcp-server-Mureka.log`

## Quickstart with Openai agents sdk
Install Agents SDK
```
pip install openai-agents
```
Run example: openapi_agents_example/main.py

Key is required to be filled in: 
```
MUREKA_API_KEY = "<insert-your-api-key-here>"
```
After running, you can see the composition process in the console
<div class="title-block" style="text-align: left;">
<img src="https://raw.githubusercontent.com/SkyworkAI/Mureka-mcp/refs/heads/master/assets/openai_1.jpeg" width="400">
</div>
<div class="title-block" style="text-align: left;">
<img src="https://raw.githubusercontent.com/SkyworkAI/Mureka-mcp/refs/heads/master/assets/openai_2.jpeg" width="400">
</div>
