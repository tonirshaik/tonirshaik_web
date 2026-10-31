# Website versioning

The version shown under **IT Specialist** in the sidebar is read from `version.json`.

## Semantic version rules

- **Patch** (`1.0.0 → 1.0.1`): bug fixes and small corrections. This is the default.
- **Minor** (`1.0.1 → 1.1.0`): new features. Add the `feature` label to the pull request before merging.
- **Major** (`1.1.0 → 2.0.0`): major or breaking changes. Add the `major` label to the pull request before merging.

When a code pull request is merged into `main`, GitHub Actions opens a separate version-bump pull request. The workflow does not commit directly to `main`; merge the generated version PR to publish the new version. Version-bump PRs are excluded from triggering another bump.

## Release flow

1. Make changes on a feature/fix branch.
2. Open a pull request into `main`.
3. Optionally add `feature` or `major`; otherwise the bump is patch.
4. Merge the code PR.
5. Review and merge the generated version-bump PR.
