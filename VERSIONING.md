# Website versioning

The version shown under **IT Specialist** in the sidebar is read from `version.json`.

## Automatic version updates

After any normal code/content change reaches `main`, GitHub Actions automatically updates `version.json` and pushes a version-only commit. No separate version-bump pull request is needed.

- **Patch**: normal edits, fixes, content changes (for example `1.0.0 → 1.0.1`).
- **Minor**: commit message starts with `feat:` or `feat(scope):` (for example `1.0.1 → 1.1.0`).
- **Major**: commit message uses a breaking-change marker such as `feat!:` or `fix!:` (for example `1.1.0 → 2.0.0`).

The workflow ignores changes that only touch `version.json` to avoid repeated bumps. It never runs for feature branches; the website version changes after the edit is merged/pushed to `main`.

## Recommended workflow

1. Make edits on a feature branch.
2. Open and merge a pull request to `main`.
3. The version badge updates automatically after the version workflow completes.

## GitHub setting

In **Settings → Actions → General → Workflow permissions**, allow workflows to have read and write permissions. If branch protection rules prohibit GitHub Actions from pushing to `main`, allow the GitHub Actions bot to update `version.json`, or use a required PR-based version update workflow instead.
