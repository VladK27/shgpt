# shgpt

Generate bash commands from natural language and run them after confirmation.

## Install

1. Download or clone this repo:

```bash
git clone https://github.com/VladK27/shgpt.git ~/shgpt
# or just put the `shgpt` file anywhere
```

2. Add `shgpt` to your shell.

### Bash

Add to `~/.bashrc`:

```bash
export SHGPT_API_KEY="your-api-key"
export SHGPT_API_URL="https://api.deepseek.com/chat/completions"
export SHGPT_MODEL="deepseek-chat"
alias shgpt="/path/to/shgpt/shgpt"
```

Then reload:

```bash
source ~/.bashrc
```

### Fish

Add to `~/.config/fish/config.fish`:

```fish
set -x SHGPT_API_KEY "your-api-key"
set -x SHGPT_API_URL "https://api.deepseek.com/chat/completions"
set -x SHGPT_MODEL "deepseek-chat"
function shgpt
    /path/to/shgpt/shgpt $argv
end
```

Then reload:

```fish
source ~/.config/fish/config.fish
```

## Usage

```bash
shgpt show processes named gradle
```

The tool asks the LLM for a command, prints it, and waits for your confirmation:

```
$ ps aux | grep gradle
Execute? [y/N]
```

Press `y` + Enter to run it, anything else to cancel.

## Requirements

- Python 3.7+
- Any OpenAI-compatible API key
