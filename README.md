# Gemini Enhanced - OpenClaw Skill

Enhanced Gemini CLI with timeout support for OpenClaw - Prevents task hanging with 3-minute timeout wrapper

## 🎯 Overview

The **Gemini Enhanced** skill adds timeout support to the Gemini CLI for OpenClaw, preventing AI tasks from hanging indefinitely.

## ✨ Features

- **⏱️ 3-Minute Timeout**: Automatically terminates tasks after 3 minutes
- **🚫 Prevents Hanging**: Stops tasks from freezing OpenClaw sessions
- **🔧 Easy Integration**: Simple drop-in replacement
- **📊 Performance Monitoring**: Logs execution time

## 🚀 Quick Start

### Installation
```bash
git clone https://github.com/ch3nji4n/openclaw-gemini-enhanced.git
cp -r openclaw-gemini-enhanced /root/.openclaw/workspace/skills/gemini-enhanced
```

### Usage
```bash
# Use gemini-timeout instead of gemini
gemini-timeout "Your query here"
```

## 📁 Project Structure
- `gemini-timeout` - Main timeout wrapper script
- `SKILL.md` - OpenClaw skill documentation
- `README.md` - This file
- `LICENSE` - MIT License

## 🧪 Examples
```bash
# Basic query with timeout
gemini-timeout "Explain quantum computing"

# In scripts
RESPONSE=$(gemini-timeout "$QUERY")
```

## 📄 License
MIT License - see LICENSE file

## 🤝 Contributing
See CONTRIBUTING.md for guidelines.

## 📞 Support
- GitHub Issues: https://github.com/ch3nji4n/openclaw-gemini-enhanced/issues
- OpenClaw Community: https://discord.com/invite/clawd

## Contact
Email: ch3nji4n@gmail.com
