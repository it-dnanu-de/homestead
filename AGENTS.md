# Agent instructions for homestead

Only facts that change how you work here.

## Tool / framework
- BanyanCode (built on OpenCode). Config file is `banyancode.json`, not `opencode.json`.
- `.opencode/agent/*.md` defines agent prompts/frontmatter.
- `opencode.json` exists but is minimal (workspace reference only); BanyanCode settings live in `banyancode.json`.

## Agents (text-only, no generation)
- `joat` — primary orchestrator. `mode: primary`.
- Subagents: `coder` (frontend/backend), `planner` (multi-planner allowed), `memory` (embeddings/re-rank: LFM2.5 + Llama Nemotron), `docs`.
- Built-in text roles: `scout`, `researcher` (DuckDuckGo), `reviewer`.
- No image/video/audio generation. Memory uses `.banyancode/` DB + embeddings/re-rank layer.

## Workspace
- Workspace root reference: `~/projects/homestead`.
- `.banyancode/` holds DB/trace. Do not commit `.banyancode/trace/` (deleted from worktree).
- `.opencode/agent/` holds agent definitions.
- This repo is the dev-env config repo (`github.com/it-dnanu-de/homestead`), not the full Homestead server build.

## Workflow
- Direct push to `main` is preferred; PR only when explicitly asked.
- Keep commits focused; stage all relevant config/agent changes together.
- If `banyancode.json` changes, remind to restart BanyanCode.

## What to omit
- Generic coding advice.
- Full file trees; read `banyancode.json` and `.opencode/agent/*.md` for structure.
- Image/video/audio generation instructions (not supported).
