# Multi-Agent Debate MCP Server

[![smithery badge](https://smithery.ai/badge/@albinjal/multi-agent-debate-mcp)](https://smithery.ai/server/@albinjal/multi-agent-debate-mcp)

An MCP server implementation that enables structured multi-agent debates between different personas. This server allows multiple AI agents to engage in formal debates with arguments, rebuttals, and judgments across multiple rounds.

## Features

- Register multiple agents with different personas (e.g., "pro", "con", "judge")
- Structured debate flow with organized rounds
- Colorized console output with beautiful terminal display
- Flexible agent IDs beyond just "pro" and "con"
- Automatic verdict tracking with rationale
- Round-based system with configurable progression

## Tool

### multiagentdebate

Facilitates structured multi-agent debates with arguments, rebuttals, and judgments.

**Inputs:**
- `agentId` (string): Unique identifier for the agent (e.g., "pro", "con", "judge")
- `round` (integer): Current debate round number (≥1)
- `action` (string): One of "register", "argue", "rebut", "judge"
- `content` (string, optional): The argument text or verdict content
- `targetAgentId` (string, optional): For rebuttals, specify which agent is being countered
- `needsMoreRounds` (boolean): Whether additional debate rounds are needed

## Usage

The Multi-Agent Debate tool is designed for:
- Structured debates between multiple AI personas
- Formal argumentation with rebuttals and counterpoints
- Multi-round discussions with judgment phases
- Complex decision-making processes requiring multiple perspectives
- Educational debate simulations
- Collaborative problem-solving through adversarial discussion

## Configuration

### Usage with Claude Desktop

Add this to your `claude_desktop_config.json`:

#### Local Development

```json
{
  "mcpServers": {
    "multi-agent-debate": {
      "command": "node",
      "args": ["path/to/multi-agent-debate-mcp/dist/index.js"]
    }
  }
}
```

#### npx

```json
{
  "mcpServers": {
    "multi-agent-debate": {
      "command": "npx",
      "args": [
        "-y",
        "multi-agent-debate-mcp"
      ]
    }
  }
}
```

#### Docker

```json
{
  "mcpServers": {
    "multi-agent-debate": {
      "command": "docker",
      "args": [
        "run",
        "--rm",
        "-i",
        "ghcr.io/albinjal/multi-agent-debate-mcp:latest"
      ]
    }
  }
}
```

### Usage with VS Code

For manual installation, add the following JSON block to your User Settings (JSON) file in VS Code. You can do this by pressing `Ctrl + Shift + P` and typing `Preferences: Open Settings (JSON)`.

Optionally, you can add it to a file called `.vscode/mcp.json` in your workspace. This will allow you to share the configuration with others.

> Note that the `mcp` key is not needed in the `.vscode/mcp.json` file.

For local development:

```json
{
  "mcp": {
    "servers": {
      "multi-agent-debate": {
        "command": "node",
        "args": [
          "path/to/multi-agent-debate-mcp/dist/index.js"
        ]
      }
    }
  }
}
```

For npx installation:

```json
{
  "mcp": {
    "servers": {
      "multi-agent-debate": {
        "command": "npx",
        "args": [
          "-y",
          "multi-agent-debate-mcp"
        ]
      }
    }
  }
}
```

For Docker installation:

```json
{
  "mcp": {
    "servers": {
      "multi-agent-debate": {
        "command": "docker",
        "args": [
          "run",
          "--rm",
          "-i",
          "ghcr.io/albinjal/multi-agent-debate-mcp:latest"
        ]
      }
    }
  }
}
```

## Building

Local development:

```bash
npm install
npm run build
npm start
```

Docker:

```bash
# Build locally
docker build -t multi-agent-debate-mcp .

# Or pull from GitHub Container Registry
docker pull ghcr.io/albinjal/multi-agent-debate-mcp:latest

# Run the container
docker run --rm -i ghcr.io/albinjal/multi-agent-debate-mcp:latest
```

## License

This MCP server is licensed under the MIT License. This means you are free to use, modify, and distribute the software, subject to the terms and conditions of the MIT License. For more details, please see the LICENSE file in the project repository.
