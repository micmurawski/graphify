## graphify <!-- res_4f27e072e20215e9fb87e0c1 -->

This project has a knowledge graph at graphify-out/ with god nodes, community structure, and cross-file relationships.

Rules:
- For open-ended codebase questions (where something lives, how parts relate), first run `graphify query "<question>"` when graphify-out/graph.json exists. When the task already names the file or symbols to change, skip the query and grep/read those targets directly; if a query returns truncated or off-topic nodes (docs, unrelated tests), switch to targeted grep. The graphify hook-guard reminders are advisory and need not be repeated once a query has run or the target is known. Use `graphify path "<A>" "<B>"` for relationships and `graphify explain "<concept>"` for focused concepts. These return a scoped subgraph, usually much smaller than GRAPH_REPORT.md or raw grep output.
- If graphify-out/wiki/index.md exists, use it for broad navigation instead of raw source browsing.
- Read graphify-out/GRAPH_REPORT.md only for broad architecture review or when query/path/explain do not surface enough context.
- After modifying code, run `graphify update .` to keep the graph current (AST-only, no API cost).
