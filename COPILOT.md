# Using this repo with GitHub Copilot

This project includes a **Copilot repository instruction file** so the Karpathy-inspired behavioral guidelines apply automatically when you use GitHub Copilot in VS Code, JetBrains, or any editor that supports `.github/copilot-instructions.md`.

## In this repository

1. Open the folder in VS Code (or any supported editor) with the GitHub Copilot extension installed.
2. The file [`.github/copilot-instructions.md`](.github/copilot-instructions.md) is committed and read automatically by Copilot — no extra installation steps needed.
3. The guidelines will be applied to Copilot Chat responses and inline suggestions for this project.

## Use the same guidelines in another project

**Recommended:** Copy `.github/copilot-instructions.md` into that project's `.github/` directory (create the folder if needed):

```bash
mkdir -p .github
curl -o .github/copilot-instructions.md \
  https://raw.githubusercontent.com/mtopps/andrej-karpathy-skills/main/.github/copilot-instructions.md
```

Adjust or merge with any existing content as needed.

## Global (personal) instructions in VS Code

You can also apply the guidelines to all your projects via VS Code settings:

1. Open **Settings** (`Cmd/Ctrl + ,`) and search for `github.copilot.chat.codeGeneration.instructions`.
2. Add the contents of `.github/copilot-instructions.md` as a personal instruction entry, or point to the file.

This applies the guidelines globally across every repository you open, without needing a per-project file.

## GitHub Copilot CLI (`gh copilot`)

The `gh copilot suggest` and `gh copilot explain` subcommands do **not** have a persistent instruction mechanism equivalent to the editor integration. There is no file that `gh copilot` reads for behavioral customization.

For one-off use, you can prepend the guidelines as context manually:

```bash
gh copilot suggest "$(cat .github/copilot-instructions.md) --- My actual question here"
```

This is a workaround, not a true skill. For the best experience, use the editor-based Copilot where `.github/copilot-instructions.md` is applied automatically.

## For contributors

When you change the four principles, keep the following files in sync:

- **[`CLAUDE.md`](CLAUDE.md)** — Claude Code per-project instructions
- **[`.cursor/rules/karpathy-guidelines.mdc`](.cursor/rules/karpathy-guidelines.mdc)** — Cursor project rule
- **[`.github/copilot-instructions.md`](.github/copilot-instructions.md)** — GitHub Copilot repository instructions
- **[`skills/karpathy-guidelines/SKILL.md`](skills/karpathy-guidelines/SKILL.md)** — Claude Code plugin skill
