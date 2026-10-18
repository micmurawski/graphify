# graphify reference: commit hook and native CLAUDE.md integration <!-- res_4785d300594875c8dade2e39 -->

Load this when the user asked to install the post-commit hook or wire graphify into a project's CLAUDE.md.

## For git commit hook <!-- res_d39259785d642de3c6b2f37f -->

Install a post-commit hook that auto-rebuilds the graph after every commit. No background process needed - triggers once per commit, works with any editor.

```bash
graphify hook install    # install
graphify hook uninstall  # remove
graphify hook status     # check
```

After every `git commit`, the hook detects which code files changed (via `git diff HEAD~1`), re-runs AST extraction on those files, and rebuilds `graph.json` and `GRAPH_REPORT.md`. Doc/image changes are ignored by the hook - run `/graphify --update` manually for those.

If a post-commit hook already exists, graphify appends to it rather than replacing it.

---

## For native CLAUDE.md integration <!-- res_2d71a5b83a3746f72c5ea2ac -->

Run once per project to enable native Graphify integration in Claude Code sessions:

```bash
graphify claude install
```

This writes a `## graphify` section to the local `CLAUDE.md`. After installation, align the generated section with the shared Graphify policy in `AGENTS.md`; use that policy as the authority for source inspection, optional lookups, denial fallback, and refresh timing. No manual `/graphify` needed in future sessions.

```bash
graphify claude uninstall  # remove the section
```
