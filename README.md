# devbox-dotfiles
Your portable workstation: Dev Container + dotfiles that bootstrap linting, testing, and CLI ergonomics. One command, identical setup, fewer surprises.

# devbox-dotfiles

Reproducible dev environment for humans: VS Code Dev Containers + Docker + opinionated dotfiles + pre-commit hooks. Clone, “Open in Dev Container,” ship. No more “works on my machine.”

## Why
- Consistent toolchains across macOS/Linux
- One command to onboard teammates
- Built-in lint/test hooks to keep PRs clean

## Quickstart
**Option A — Local (VS Code)**
1. Install Docker (Docker Desktop / OrbStack).
2. Install VS Code + “Dev Containers” extension.
3. `git clone https://github.com/<you>/devbox-dotfiles.git`
4. In VS Code: **Command Palette → Dev Containers: Reopen in Container**.

**Option B — GitHub Codespaces**
- Click **Code → Create codespace on main**. That’s it.

> Tip: This repo intentionally tracks `.vscode/settings.json` and `extensions.json` so everyone opens the same editor with the same extensions.

## What’s inside (and why)
- **Dotfiles**: sane shell + Git aliases for fast DX.
- **Dev Container config**: lock in OS packages, Node/Python toolchains, and editor extensions.
- **pre-commit**: run formatters/linters before bad code hits your branch.
- **GitHub Actions (optional)**: mirror CI checks to what runs locally.

> Public repo = public standards: no secrets, no tokens. Use `.env` locally; never commit it.

## Customize
- **Editor**: tweak `.vscode/settings.json`; add extensions to `.vscode/extensions.json`.
- **CLI tools**: add packages in `Dockerfile` (apt/brew-like) or post-create scripts.
- **Hooks**: edit `.pre-commit-config.yaml` to add black/ruff/eslint/prettier/etc.
- **Language runtimes**: pin versions in the devcontainer image to eliminate drift.

## FAQ
**Can I use this for non-VS Code editors?**  
Yes. The container standardizes tooling; use your editor over the devcontainer’s volume.

**Secrets?**  
Put them in local `.env` files or your Codespaces/CI secrets. Never commit credentials.

## Roadmap
- [ ] Add `/devcontainer/devcontainer.json` + `Dockerfile`
- [ ] Add `.pre-commit-config.yaml` and sample hooks
- [ ] Add `scripts/bootstrap.sh` for local dotfile install
- [ ] Add GitHub Actions template (lint/test)

---

If this saved you setup time, ⭐ the repo. If it didn’t, open an issue and we’ll make it better. (DX > yak-shaving.)

