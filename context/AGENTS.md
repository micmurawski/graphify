## graphify <!-- res_7d540630d9c3da46710b4fca -->

This project has a knowledge graph at graphify-out/ with god nodes, community structure, and cross-file relationships.

When the user types `/graphify`, use the installed graphify skill or instructions before doing anything else.

Rules:
- For focused tasks with known source files or symbols, inspect those directly. When navigation context is needed to resolve uncertain dependencies, architecture, or file relationships, run `graphify query "<question>"` if graphify-out/graph.json exists. Use `graphify path "<A>" "<B>"` for relationships and `graphify explain "<concept>"` for focused concepts, qualifying ambiguous symbols by file. These return a scoped subgraph, usually much smaller than GRAPH_REPORT.md or raw grep output.
- If Graphify requires approval, is blocked, or returns no useful context, continue with permitted source reads; do not make graph access a prerequisite for the task or repeat blocked queries.
- Dirty graphify-out/ files are expected after hooks or incremental updates and alone are not a reason to skip graph navigation. Respect explicit requests not to use Graphify. When diagnosing stale or incorrect graph output, inspect sources and graph artifacts directly rather than relying on the graph as authoritative context.
- When using the graph for broad navigation, start with graphify-out/wiki/index.md if it exists. Read graphify-out/GRAPH_REPORT.md only for broad architecture review or when query/path/explain do not surface enough context.
- After modifying code, run `graphify update .` only for an explicit graph-maintenance deliverable, an established repository maintenance requirement, or a concrete need for current graph data; otherwise defer refresh to separate maintenance. Run it once after the final edits. Before refreshing, record existing graph artifact changes and preserve pre-existing work. Review the resulting diff, including generated artifacts and community labels, and report material generated-file churn and warnings in the final handoff.
