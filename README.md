# graphify — evolution workspace

A [thearc](https://github.com/micmurawski/thearc) workspace for the [Graphify](https://github.com/Graphify-Labs/graphify)
agent configuration: its skill, the `AGENTS.md` / `CLAUDE.md` sections, and the Claude and Codex hooks.

`main` is the current release. Epoch 0 imports Graphify 0.9.68 exactly as it was installed for the
FastAPI project the sessions run on. Each epoch then:

1. runs coding tasks on FastAPI with Claude Code, Codex, Pi and OpenCode, all using the current release;
2. reflects on those sessions — which instructions helped or hurt, with ratings in `journal.jsonl`;
3. curates one candidate per harness (`candidate/epoch-<n>/<harness>`), and merges them (`merge/<id>`);
4. releases the merged candidate (`release/<version>`, with `RATINGS.md`) and moves `main` to it.

| Path | What |
| --- | --- |
| `agent.json` | name and version |
| `skills/`, `context/`, `hooks.jsonc` | the configuration; `<!-- res_… -->` markers name each section |
| `owned_hooks.jsonc` | hook commands this agent owns when installed |
| `journal.jsonl` | every change (with its reason) and every rating (with its reflection) |
| `RATINGS.md` | on release branches: each section's ratings |
