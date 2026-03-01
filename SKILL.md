---
name: gemini-enhanced
description: Enhanced Gemini CLI with timeout support for one-shot Q&A, summaries, and generation.
homepage: https://ai.google.dev/
metadata:
  {
    "openclaw":
      {
        "emoji": "♊️⏱️",
        "requires": { "bins": ["gemini", "timeout"] },
        "install":
          [
            {
              "id": "brew",
              "kind": "brew",
              "formula": "gemini-cli",
              "bins": ["gemini"],
              "label": "Install Gemini CLI (brew)",
            },
          ],
      },
  }
---

# Enhanced Gemini CLI with Timeout

Use Gemini in one-shot mode with automatic timeout handling (180 seconds default).

## 🚀 Quick Start

### Basic usage with timeout:
```bash
# Simple query with 180s timeout
gemini-timeout "Your question here"

# Custom timeout (in seconds)
gemini-timeout --timeout 120 "Longer processing question"

# Specify model
gemini-timeout --model gemini-1.5-pro "Complex technical question"
```

### Direct gemini calls (for advanced users):
```bash
# Original gemini CLI (may hang without timeout)
gemini --prompt "Your prompt"

# With manual timeout
timeout 180 gemini --prompt "Your prompt"
```

## ⚙️ Enhanced Features

### 1. **Automatic Timeout**
- Default: 180 seconds (3 minutes)
- Configurable via `--timeout` flag
- Prevents hanging on slow responses

### 2. **Error Handling**
- Timeout detection and clean exit
- Connection error handling
- Graceful degradation

### 3. **Progress Indicators**
- Shows timeout countdown
- Progress dots for long-running queries
- Completion status

## 📋 Usage Examples

### Simple Q&A:
```bash
gemini-timeout "Explain quantum computing in simple terms"
```

### Technical Specifications:
```bash
gemini-timeout "What are your technical specifications including context window and max output tokens?"
```

### Code Generation:
```bash
gemini-timeout --timeout 240 "Write a Python function to sort a list of dictionaries by a specific key"
```

### JSON Output:
```bash
gemini-timeout --output-format json "Return information about planets in our solar system as JSON"
```

## 🔧 Implementation

The enhanced skill wraps the original `gemini` CLI with:

1. **Timeout wrapper**: Uses `timeout` command or background process monitoring
2. **Progress tracking**: Visual feedback during execution
3. **Error recovery**: Clean exit on failures
4. **Result caching**: Optional caching for repeated queries

## ⚠️ Notes

- **Authentication**: First run may require interactive login
- **Network**: Requires internet access to Google AI services
- **Rate Limits**: Subject to Google API rate limits
- **Cost**: Using Gemini API may incur costs

## 🛠️ Troubleshooting

### Common Issues:

1. **Timeout too short**:
   ```bash
   gemini-timeout --timeout 300 "Complex analysis task"
   ```

2. **Authentication required**:
   ```bash
   # Run once interactively
   gemini
   # Follow login prompts, then exit
   ```

3. **Network issues**:
   ```bash
   # Check connectivity
   curl -s https://generativelanguage.googleapis.com/v1beta/models | head -5
   ```

4. **Model not available**:
   ```bash
   # List available models
   gemini --list-extensions | grep -i model
   ```

## 📊 Performance Tips

1. **For simple queries**: Use default 180s timeout
2. **For complex analysis**: Increase to 300s or more
3. **Batch processing**: Consider breaking large tasks
4. **Cache results**: Store frequent queries locally

## 🔄 Integration with OpenClaw

This skill can be used in OpenClaw workflows:

```yaml
# Example workflow configuration
steps:
  - name: Ask Gemini
    skill: gemini-enhanced
    params:
      prompt: "Analyze this text: {{input}}"
      timeout: 180
```

## 🆕 Changelog

- **v1.0**: Initial enhanced version with timeout support
- **v1.1**: Added progress indicators and better error handling
- **v1.2**: Configurable timeout and model selection

---

**Safety Note**: Always review AI-generated content before use. Avoid `--yolo` flag for safety-critical applications.