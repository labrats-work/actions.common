# Claude Context: actions.common

## Repository Overview

Repository for shared GitHub Actions workflows and patterns (infrastructure-agnostic).

**Purpose:** Standardize reusable workflows across the labrats-work organization.

## Project Architecture

```
actions.common/
├── .github/
│   └── workflows/
│       ├── README.md                    # Limitations documentation
│       ├── repo-info.yml                # Get repository info
│       ├── repo-info-test.yml
│       ├── create-repo-issue.yml        # Create issues
│       ├── create-repo-issue-inherit.yml
│       ├── create-repo-issue-inherit-test.yml
│       ├── create-repo-issue-output.yml
│       ├── create-repo-issue-output-test.yml
│       └── verify-contrib-file.yml      # Verify contribution files
└── .git/
```

---

## Available Workflows

| Workflow | Purpose |
|----------|---------|
| `repo-info` | Retrieve repository information |
| `create-repo-issue` | Create issues in repositories |
| `verify-contrib-file` | Verify contribution files exist |

---

## Reusable Workflow Limitations

From GitHub documentation:
- Max 4 levels of nesting
- Max 20 reusable workflows per caller (nested count too)
- Environment variables don't propagate to called workflows
- Private repos can only reference workflows in same repo

---

## Usage Example

```yaml
# In another repo
jobs:
  check:
    uses: labrats-work/actions.common/.github/workflows/repo-info.yml@main
```

---

## Notes for AI Assistants

When working in this repository:

1. **Workflows Only** - Minimal source files, focus on workflows
2. **Reusable Patterns** - Cross-repo GitHub Actions patterns
3. **Limitations** - Respect GitHub's nesting limits
4. **Testing** - Each workflow has a corresponding test workflow

### Common Pitfalls

- Environment variables don't propagate
- Nesting limited to 4 levels
- Max 20 reusable workflows per caller

---

## Last Updated

2026-01-29
