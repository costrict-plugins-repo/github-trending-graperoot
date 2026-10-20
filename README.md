# Graperoot — Dual-Graph Context Plugin for Claude Code

Structural code context engine that builds a call graph + dependency graph of your codebase, giving Claude precise file and symbol recommendations before it starts exploring.

## How it works

1. **Graph scan** — Indexes your project's functions, classes, imports, and call relationships
2. **Context retrieval** — When you ask a question, the graph finds the most relevant files and symbols
3. **Pre-injection** — Recommended context is delivered to Claude before it starts working, reducing token usage and improving accuracy

## Install

### Step 1: Install the graperoot package

```bash
pip install graperoot
```

### Step 2: Install the plugin

```bash
claude /plugin install graperoot-plugin
```

Or load locally for testing:

```bash
claude --plugin-dir /path/to/graperoot-plugin
```

## What's included

| Component | Purpose |
|-----------|---------|
| **MCP server** (`mcp-graph-server`) | Provides `graph_continue`, `graph_scan`, `graph_read`, `graph_register_edit`, `fallback_rg` tools |
| **Skill** (`graph-context`) | Teaches Claude the retrieval protocol — call graph tools first, respect confidence levels |

## Requirements

- Python 3.10+
- Claude Code 1.0.33+
- `pip install graperoot` (compiled Cython package — no source files exposed)

## Supported languages

TypeScript, JavaScript, Python, Go, Rust, Java, C, C++, Ruby, PHP, Swift, Kotlin, and more.

## License

Proprietary — distributed as compiled binaries via PyPI.
