# MCP-UI Integration Skill

A comprehensive Claude skill for creating and rendering interactive UI components in MCP (Model Context Protocol) applications. This skill provides condensed guidance for both server-side creation and client-side rendering of UI resources.

## Overview

This skill dramatically reduces context usage when working with [MCP-UI](https://github.com/idosal/mcp-ui) by distilling ~40,000 tokens of documentation into a focused, ~2,000 token skill file whilst maintaining all essential information.

## What is MCP-UI?

MCP-UI enables dynamic, interactive UI components to be sent from MCP servers and rendered securely in client applications. It supports:

- **Raw HTML** resources for simple interfaces
- **External URLs** rendered in sandboxed iframes
- **Remote DOM** for native component rendering
- **Iframe communication** via postMessage protocol
- **Metadata** for preferred rendering contexts and sizes

## Installation

### Claude Desktop

1. Download the latest `mcp-ui.skill` file from [Releases](../../releases)
2. Open Claude Desktop
3. Go to Settings → Capabilities → Skills
4. Click "Upload Skill" and select the `.skill` file
5. Enable the skill in your settings

### Claude Code CLI

```bash
# Create skills directory if needed
mkdir -p ~/.claude/skills

# Extract the skill file
unzip mcp-ui.skill -d ~/.claude/skills/mcp-ui-integration

# Verify installation
ls ~/.claude/skills/mcp-ui-integration/SKILL.md
```

Restart Claude Code if it's running. The skill will be automatically discovered.

### Claude API

See the [Skills API documentation](https://docs.claude.com/en/api/skills) for programmatic skill management.

## Usage

Once installed, Claude will automatically use this skill when you:

- Ask about MCP-UI resources or UIResourceRenderer
- Request help creating interactive UI components for MCP servers
- Need guidance on iframe communication protocols
- Want to understand Remote DOM rendering
- Ask about MCP-UI best practices or troubleshooting

### Example Prompts

```
"Help me create an MCP-UI resource that displays a form"

"Show me how to render a UIResource in React with custom component library"

"Explain the MCP-UI iframe communication protocol"

"How do I handle asynchronous tool calls from an MCP-UI iframe?"

"What's the best way to auto-resize iframes in MCP-UI?"
```

## What's Included

The skill covers:

- ✅ **Core Concepts** - UIResource structure, MIME types, URI schemes
- ✅ **Server-Side Creation** - TypeScript/Node.js and Ruby examples
- ✅ **Client-Side Rendering** - React and Web Components integration
- ✅ **Communication Protocol** - Complete postMessage examples
- ✅ **Security & Best Practices** - Sandboxing, CSP, validation
- ✅ **Metadata Handling** - Standard and UI-specific metadata
- ✅ **Common Patterns** - Real-world usage examples
- ✅ **Troubleshooting Guide** - Quick solutions to common issues
- ✅ **Quick Reference** - Condensed API overview

## Benefits

### Context Efficiency
- **Before**: ~40,000 tokens of documentation
- **After**: ~2,000 tokens in skill format
- **Savings**: ~95% reduction in context usage

### Always Available
Claude loads the skill automatically when relevant, without you needing to paste documentation or search for examples.

### Up-to-Date
Based on the official [idosal/mcp-ui](https://github.com/idosal/mcp-ui) documentation, ensuring accurate and current information.

## Development

### Building from Source

If you want to modify or rebuild the skill:

1. Clone this repository
2. Edit `SKILL.md` as needed
3. Package it:

```bash
cd mcp-ui-integration
zip -j ../mcp-ui.skill SKILL.md
```

### YAML Frontmatter Requirements

The `SKILL.md` file must start with valid YAML frontmatter:

```yaml
---
name: mcp-ui-integration
description: Guide for creating and rendering interactive UI components in MCP applications. Use when working with MCP-UI resources, UIResourceRenderer, or creating dynamic interfaces for MCP servers.
---
```

**Important requirements:**
- `name` must be lowercase with hyphens only (`[a-z0-9-]+`)
- `description` should clearly explain when to use the skill
- SKILL.md must be in the root of the zip file

## Contributing

Contributions are welcome! To contribute:

1. Fork this repository
2. Create a feature branch
3. Make your changes to `SKILL.md`
4. Test the skill in Claude Desktop or Claude Code
5. Submit a pull request

## Related Projects

- [idosal/mcp-ui](https://github.com/idosal/mcp-ui) - The official MCP-UI library
- [anthropics/skills](https://github.com/anthropics/skills) - Official Claude skills repository
- [Model Context Protocol](https://modelcontextprotocol.io/) - MCP specification

## Supported Hosts

| Host | Rendering | UI Actions | Notes |
|------|-----------|------------|-------|
| Postman | ✅ Full | ✅ Full | Complete support |
| Goose | ✅ Full | ⚠️ Partial | Limited action support |
| Smithery | ✅ Full | ⚠️ Partial | Limited action support |
| MCPJam | ✅ Full | ❌ Not supported | Rendering only |
| VSCode | 🔜 Coming | 🔜 Coming | Planned support |

## Troubleshooting

### Skill not appearing in Claude Desktop
- Verify the `.skill` file is properly formatted
- Check that `name` in frontmatter matches the expected format
- Try re-uploading the skill
- Restart Claude Desktop

### Skill not discovered in Claude Code
- Ensure the skill is in `~/.claude/skills/mcp-ui-integration/`
- Verify `SKILL.md` exists and has valid frontmatter
- Restart Claude Code
- Check console for validation errors

### Need more help?
See the [MCP-UI documentation](https://github.com/idosal/mcp-ui/tree/main/docs) or open an issue in this repository.

## Licence

This skill is based on the [MCP-UI project](https://github.com/idosal/mcp-ui) documentation. The skill packaging and condensation is provided under the MIT Licence.

## Acknowledgements

- **MCP-UI Authors**: [Ido Salomon](https://github.com/idosal) and [Liad Yosef](https://github.com/liadyosef)
- **MCP-UI Project**: https://github.com/idosal/mcp-ui
- **Claude Skills System**: [Anthropic](https://www.anthropic.com)

---

**Made with ❤️ for the Claude community**

*Dramatically reduce context usage when working with MCP-UI*
