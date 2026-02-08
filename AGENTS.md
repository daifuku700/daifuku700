# Repository Guidelines

## ルール
- コード内のコメントは英語で、それ以外は日本語を用いて下さい。
- プロジェクトの構成を変更した場合は、この AGENTS.md も新しい構成を記載したものに変更して下さい。

## Project Structure & Module Organization
This repository is a GitHub profile-style project centered on `README.md`.

- `README.md`: primary content (profile text, badges, and embedded stat cards).
- `.github/workflows/grs.yml`: scheduled workflow that regenerates and commits SVG stat cards.
- `LICENSE`: project license metadata.

There is currently no application source directory (`src/`) or test directory (`tests/`).

## Build, Test, and Development Commands
There is no build system in this repository. Use these lightweight checks before opening a PR:

- `cat README.md`: quick content verification.
- `cat .github/workflows/grs.yml`: confirm workflow edits and action inputs.
- `git diff -- README.md .github/workflows/grs.yml`: review exactly what changed.

If you have Markdown lint tooling installed, run it on changed docs (for example, `markdownlint README.md AGENTS.md`).

## Coding Style & Naming Conventions
Follow consistent Markdown and YAML style:

- Use concise headings and short paragraphs in Markdown.
- Prefer simple HTML only when Markdown cannot achieve the same layout (current README uses centered `<div>` blocks).
- Keep workflow YAML indentation at 2 spaces.
- Use descriptive, lower-case workflow filenames in `.github/workflows/` (for example, `grs.yml`).

## Testing Guidelines
No automated test framework is configured. Validation is manual:

- Check Markdown rendering in GitHub preview.
- Verify image links and badge URLs resolve.
- For workflow changes, ensure `workflow_dispatch` remains available for manual runs.

## Commit & Pull Request Guidelines
Recent history uses short, imperative commit messages such as:

- `Update README.md`
- `Refactor README.md layout`
- `Add GitHub Actions workflow to update README cards`

Use the same pattern: `<Verb> <target>` and keep commits focused.

PRs should include:

- A brief summary of what changed and why.
- Linked issue (if applicable).
- Screenshot or rendered preview when modifying `README.md` layout or visuals.
- Notes about workflow impact when editing `.github/workflows/grs.yml`.
