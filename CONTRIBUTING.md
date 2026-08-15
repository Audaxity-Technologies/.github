# Contributing to Audaxity

Thanks for contributing. This document covers how to structure commits, branches, and pull requests.

## Commit Convention

All commits must follow [Conventional Commits](https://www.conventionalcommits.org/).

**Format:**
```
type: description
```

Optionally, a scope can be included to indicate what part of the codebase the change affects:
```
type(scope): description
```

Keep the description short, in the imperative mood ("add", not "added" or "adds"), and under ~72 characters. Add a longer explanation in the commit body if needed.

### Allowed Types

| Type       | Use for                              |
|------------|---------------------------------------|
| `feat`     | New functionality                     |
| `fix`      | Bug fix                               |
| `docs`     | Documentation changes                 |
| `refactor` | Code restructuring, no behavior change|
| `test`     | Adding or updating tests              |
| `build`    | Build system or dependency changes    |
| `ci`       | CI/CD changes                         |
| `perf`     | Performance improvements              |
| `security` | Security changes                      |
| `chore`    | Maintenance, no source or test change |
| `style`    | Formatting/style, no logic change     |
| `revert`   | Reverting a previous commit           |

### Breaking Changes

If a commit introduces a breaking change, mark it with a `!` after the type/scope, and explain the break in the commit body:

```
feat!: change syllabus mapping API response shape

BREAKING CHANGE: `coverage` is now returned as a percentage (0-100)
instead of a fraction (0-1). Update any consumers accordingly.
```

### Examples

**Good:**
```
docs: establish initial company documentation
feat: add lecture transcription pipeline
fix: handle failed audio uploads
feat(notes): add diagram extraction to structured notes generator
refactor: simplify syllabus-mapping RAG query construction
```

**Bad:**
```
updated files
changes
final version
stuff
```

## Branch Naming

Branch names should follow:
```
type/short-description
```

Using the same `type` values as commits, e.g.:
```
feat/lecture-search-engine
fix/audio-upload-retry
docs/contributing-guide
```

## Pull Requests

- Keep PRs focused on a single change where possible — easier to review, easier to revert if needed.
- PR titles should also follow the Conventional Commits format, since some workflows use squash-merge and the PR title becomes the commit message.
- Include a short description of what changed and why. Link any related issue.
- Make sure CI passes before requesting review.
- Address review feedback with additional commits rather than force-pushing over history mid-review, unless the reviewer asks for a clean-up push.

## Questions

If anything here is unclear, open an issue or ask before submitting — better to check once than to redo a PR.
