# Public Codex Settings

This repo contains the public-safe parts of my Codex CLI configuration.

The `codex/allow-all-rm-autonomy` branch is the fully permissive variant:
it keeps autonomous execution enabled and does not block `rm`.

Included:

- `config.toml`: model, reasoning effort, approval policy, sandbox mode, and enabled features/plugins
- `rules/default.rules`: custom command rules (empty on the permissive branch)

Left out on purpose:

- `auth.json`: contains live auth tokens
- `history.jsonl`, `sessions/`, `log/`, `*.sqlite*`: conversation and runtime state
- machine-specific caches
- private `[projects]` trust entries from the original `config.toml`

## What This Config Does

- `approval_policy = "never"`: commands do not require confirmation
- `sandbox_mode = "danger-full-access"`: filesystem/network are not sandboxed
- `rules/default.rules`: intentionally empty on the permissive branch, so `rm` is allowed

## Reuse

Copy these files into `~/.codex/` if you want the same behavior, then add your own project trust entries if needed.
