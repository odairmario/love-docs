# love-docs
Desktop tool to handle world, google, and Libreoffice documents

## Development

This project uses [Cocogitto (cog)](https://docs.cocogitto.io/) to enforce [Conventional Commits](https://www.conventionalcommits.org/) and automate changelog generation.

### Commit Types

Every commit message must follow the format:

```
<type>(<optional scope>): <description>
```

Below are all the supported commit types, when to use each one, and examples:

| Type | Description | When to Use | Example |
|------|-------------|-------------|---------|
| 🚀 `feat` | A new feature | When adding new functionality visible to the user | `feat(editor): add PDF export support` |
| 🐛 `fix` | A bug fix | When fixing incorrect behavior or a reported issue | `fix(parser): handle empty document gracefully` |
| ♻️ `refactor` | Code refactoring | When restructuring code without changing its external behavior | `refactor(core): extract validation into separate module` |
| ⚡ `perf` | Performance improvement | When optimizing speed, memory usage, or resource consumption | `perf(renderer): cache parsed templates` |
| 📚 `docs` | Documentation changes | When updating README, doc comments, or any documentation files | `docs: add installation instructions to README` |
| 🎨 `style` | Code style / formatting | When fixing whitespace, formatting, or linting issues (no logic change) | `style: apply rustfmt to all modules` |
| ✅ `test` | Tests | When adding, updating, or fixing test cases | `test(parser): add edge case tests for malformed input` |
| 🏗️ `build` | Build system / dependencies | When changing `Cargo.toml`, build scripts, or external dependencies | `build: upgrade serde to v1.0.200` |
| 👷 `ci` | CI/CD configuration | When modifying GitHub Actions, CI pipelines, or deployment scripts | `ci: add release workflow for Windows builds` |
| 🔧 `chore` | Maintenance tasks | When doing routine tasks that don't modify source or test files | `chore: update .gitignore` |
| ⏪ `revert` | Revert a previous commit | When undoing a previous commit entirely | `revert: revert "feat(editor): add PDF export support"` |

### Breaking Changes

Append `!` after the type (or scope) to indicate a breaking change:

```
feat!: redesign document loading API
refactor(core)!: rename Config to AppSettings
```

### Version Bumping

- **`feat`** commits trigger a **minor** version bump (e.g., `1.0.0` → `1.1.0`)
- **`fix`** commits trigger a **patch** version bump (e.g., `1.0.0` → `1.0.1`)
- **Breaking changes** (`!`) trigger a **major** version bump (e.g., `1.0.0` → `2.0.0`)
- All other types (`docs`, `style`, `test`, etc.) do **not** trigger a version bump on their own, but will appear in the changelog.

