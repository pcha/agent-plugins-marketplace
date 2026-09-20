# pcha-plugins Marketplace

A collection of Claude Code and Codex plugins by Pablo Cha.

## Claude Code installation

Add this marketplace to Claude Code:

```bash
claude plugin marketplace add https://github.com/pcha/plugins-marketplace.git
```

Then install plugins:

```bash
claude plugin install android-ai-plugin@pcha-plugins
claude plugin install git-ai-plugin@pcha-plugins
```

The Claude marketplace manifest lives at `.claude-plugin/marketplace.json`.

## Codex installation

Add the marketplace repository and install either plugin:

```bash
codex plugin marketplace add https://github.com/pcha/plugins-marketplace.git
codex plugin add android-ai-plugin@pcha-plugins
codex plugin add git-ai-plugin@pcha-plugins
```

Start a new Codex thread after installation so the plugin skills are discovered.
The Codex marketplace manifest lives at `.agents/plugins/marketplace.json`.

## Available Plugins

| Plugin | Description |
|--------|-------------|
| [android-ai-plugin](https://github.com/pcha/android-ai-plugin) | Skills and commands for Android development with clean architecture, MVVM, DI, and testing |
| [git-ai-plugin](https://github.com/pcha/plugins-marketplace/tree/main/plugins/git-ai-plugin) | Conventional commits, pull requests, branch integration, and Git worktree workflows |

## License

MIT
