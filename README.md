# Public Codex Settings

This repo contains the public-safe parts of my Codex CLI configuration.

Included:

- `config.toml`: model, reasoning effort, approval policy, sandbox mode, and enabled features/plugins
- `rules/default.rules`: custom command rules

Left out on purpose:

- `auth.json`: contains live auth tokens
- `history.jsonl`, `sessions/`, `log/`, `*.sqlite*`: conversation and runtime state
- machine-specific caches
- private `[projects]` trust entries from the original `config.toml`

## What This Config Does

- `approval_policy = "never"`: commands do not require confirmation
- `sandbox_mode = "danger-full-access"`: filesystem/network are not sandboxed
- `rules/default.rules`: blocks direct `rm` usage, including `sudo rm`

## Reuse

Copy these files into `~/.codex/` if you want the same behavior, then add your own project trust entries if needed.
