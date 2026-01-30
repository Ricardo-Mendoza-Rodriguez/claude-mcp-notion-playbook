# 🤖 Claude MCP + Notion Playbook

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Notion API](https://img.shields.io/badge/Notion-API-black?logo=notion)](https://developers.notion.com/)
[![Claude](https://img.shields.io/badge/Claude-MCP-orange)](https://www.anthropic.com/claude)
[![MCP](https://img.shields.io/badge/MCP-Protocol-blue)](https://modelcontextprotocol.io/)

> **Practical automation playbook**: Connect Claude to Notion using Model Context Protocol (MCP) for intelligent project management with natural language.

Part of the [Building Systems Series](https://github.com/Ricardo-Mendoza-Rodriguez) — practical guides for Data, AI, and Automation.

## ✨ What is this?

A **technical playbook** for connecting Claude (Anthropic's AI assistant) to your Notion workspace via Model Context Protocol. This enables:

**Core Capabilities:**
- 📝 Programmatic page creation and editing
- 🗂️ Database management and automation
- 📊 Automated report generation
- 🔄 Workflow automation for repetitive tasks
- 🎯 Natural language project management

**Technical Approach:**
This playbook provides production-ready configurations, real-world use cases, and troubleshooting patterns for implementing Claude + Notion automation in business environments.

## 🚀 Quick Start

```bash
# 1. Clone this repository
git clone https://github.com/Ricardo-Mendoza-Rodriguez/claude-mcp-notion-playbook.git
cd claude-mcp-notion-playbook

# 2. Get your Notion API Key
# Follow the setup guide in SETUP-GUIDE.md

# 3. Configure MCP server
# Copy example config and add your token
cp config.example.json ~/.config/Claude/claude_desktop_config.json
# Edit with your Notion token

# 4. Restart Claude Desktop and test connection
```

**⚡ Fast Track:** If you're familiar with APIs and CLIs, jump straight to [SETUP-GUIDE.md](./SETUP-GUIDE.md) for technical setup.

## 📚 Documentation

- **[Setup Guide (Complete)](./SETUP-GUIDE.md)** - Step-by-step installation and configuration
- **[Architecture Overview](./ARCHITECTURE.md)** - Technical architecture and system design
- **[Configuration Template](./config.example.json)** - Ready-to-use MCP server config
- **[Use Cases](./USE-CASES.md)** - 8+ real-world automation scenarios
- **[FAQ](./FAQ.md)** - Troubleshooting and common questions
- **[Changelog](./CHANGELOG.md)** - Version history and updates

## 🎯 Use Cases

### Enterprise & Business
```
"Claude, review our Q4 project database and:
1. Update all projects with deadlines this week to 'Urgent'
2. Calculate total hours logged per project
3. Generate billing report for pending invoices"
```

### Technical Teams
```
"Create sprint planning template with:
- User stories with acceptance criteria
- Story points estimation
- Sprint velocity tracking
- Automated daily standup notes"
```

### Personal Productivity
```
"Analyze my completed tasks from last month:
- Identify productivity patterns
- Suggest optimization opportunities
- Create next month's action plan"
```

**→ See [USE-CASES.md](./USE-CASES.md) for 8+ detailed scenarios with implementation patterns**

## 🛠️ Requirements

**Software Dependencies:**
- Notion account (Free/Personal/Business/Enterprise)
- Claude Desktop App or claude.ai account
- Node.js 18+ (for MCP server runtime)
- OS: Windows 10+, macOS 11+, or Linux (Ubuntu 20.04+)

**Technical Prerequisites:**
- Basic terminal/command line familiarity
- Notion API integration setup (guided in docs)
- 15-30 minutes for initial configuration

## 📦 Repository Structure

```
claude-mcp-notion-playbook/
├── README.md                 # Overview and quick start
├── SETUP-GUIDE.md           # Complete installation guide
├── ARCHITECTURE.md          # Technical architecture docs
├── config.example.json      # MCP server configuration template
├── USE-CASES.md             # Real-world implementation patterns
├── FAQ.md                   # Troubleshooting and questions
├── CHANGELOG.md             # Version history
├── CONTRIBUTING.md          # Contribution guidelines
├── PUBLISHING.md            # GitHub publishing guide
└── LICENSE                  # MIT License
```

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Si tienes ideas, mejoras o encontraste un error:

1. Fork este repositorio
2. Crea una rama: `git checkout -b feature/mi-mejora`
3. Haz commit: `git commit -m 'Agrega nueva funcionalidad'`
4. Push: `git push origin feature/mi-mejora`
5. Abre un Pull Request

Ver [CONTRIBUTING.md](./CONTRIBUTING.md) para más detalles.

## 🐛 Reportar Problemas

¿Encontraste un bug? [Abre un issue](https://github.com/TU-USUARIO/claude-mcp-notion/issues) con:
- Descripción del problema
- Pasos para reproducirlo
- Capturas de pantalla (si aplica)
- Tu sistema operativo y versión de Node.js

## ⚠️ Seguridad

**IMPORTANTE**: Nunca compartas tu token de API de Notion. Este repositorio incluye `.gitignore` configurado para prevenir la subida accidental de credenciales.

## 📄 Licencia

Este proyecto está bajo la licencia MIT - ver [LICENSE](LICENSE) para más detalles.

## 🌟 Part of Building Systems Series

This playbook is part of a collection of practical technical resources:

- [**Technical Second Brain**](https://github.com/Ricardo-Mendoza-Rodriguez/building-a-technical-second-brain-on-github) - GitHub as knowledge system
- [**Prompt Engineering Playbook**](https://github.com/Ricardo-Mendoza-Rodriguez/prompt-engineering-playbook) - Practical prompt patterns
- [**n8n Automation Recipes**](https://github.com/Ricardo-Mendoza-Rodriguez/n8n-automation-recipes) - Workflow automation templates
- **Claude + Notion Playbook** ← You are here

## 📄 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

## 🤝 Contributing

Contributions are welcome! See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

Built with ❤️ by [Ricardo Mendoza](https://github.com/Ricardo-Mendoza-Rodriguez) | [LinkedIn](https://www.linkedin.com/in/ricardomendozar) | [Website](https://ricardo-mendoza.com/)

---

⭐ **Found this useful?** Star the repo and share with your network.

📢 **Questions?** Open an [issue](https://github.com/Ricardo-Mendoza-Rodriguez/claude-mcp-notion-playbook/issues) or reach out on LinkedIn.
