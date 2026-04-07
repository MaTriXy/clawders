# 🦷 Claw Code

An open, community-maintained **agent harness** built on top of OpenClaw. Claw Code lets you run OpenClaw as a standalone CLI tool with full control over prompts and configuration — no GUI required.

> 📺 [Watch the talk](https://www.youtube.com/live/RpFh0Nc7RvA)

---

## What is Claw Code?

Claw Code is a lightweight wrapper around OpenClaw that exposes its capabilities through a simple command-line interface. It is designed to be:

- **Minimal** — no Electron, no browser, just a binary + your terminal
- **Flexible** — swap model providers, override system prompts, configure hooks
- **Hackable** — built in Rust, easy to extend

---

## Prerequisites

- [Rust toolchain](https://rustup.rs) (latest stable)
- A model provider with an API token (MiniMax recommended for free tier)

---

## Building from Source

```bash
# Clone the repository
git clone https://github.com/ultraworkers/claw-code.git ~/src/claw-code
cd ~/src/claw-code/rust

# Build the project
cargo build --workspace

# The binary will be at:
# target/debug/claw
```

---

## Running Claw Code

```bash
# Make a prompt request
./claw prompt "summarize this repository"

# Create a file
./claw prompt "create /tmp/test.txt with 30 random numbers, 3 digits each, with emojis on each line"
```

### Adding a Shell Alias

Add this to your `~/.zshrc` or `~/.bashrc` for convenience:

```bash
alias claw="~/src/claw-code/rust/target/debug/claw $@"
```

---

## Environment Variables

Set these in your shell profile before running Claw Code:

```bash
# MiniMax example (free tier)
export ANTHROPIC_AUTH_TOKEN="sk-cp-your_token_here"
export ANTHROPIC_BASE_URL="https://api.minimax.io/anthropic"
```

| Variable | Required | Description |
|----------|----------|-------------|
| `ANTHROPIC_AUTH_TOKEN` | Yes | Your API token from the model provider |
| `ANTHROPIC_BASE_URL` | No | Override the API endpoint (defaults to Anthropic) |

---

## Related Resources

| Resource | Link |
|----------|------|
| UltraWorkers Claw Code | [github.com/ultraworkers/claw-code](https://github.com/ultraworkers/claw-code) |
| Clawders Root Guide | [github.com/tomerb3/clawders](../README.md) |
| Oh My Claude Code | [github.com/Yeachan-Heo/oh-my-claudecode](https://github.com/Yeachan-Heo/oh-my-claudecode) |

---

<p align="center">
  <strong>Happy clawing! 🦷</strong>
</p>
