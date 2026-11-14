# Day 1: Deterministic Spine & Execution Gating

## Core Mechanisms
1. **The Array Wrapper:** Every node in n8n passes data as an array of JSON objects (`[ { "json": { ... } } ]`). Nodes never pass isolated primitive variables.
2. **Execution Gating:** A downstream node only executes if it receives at least 1 item. If an `IF` node routes 0 items to its TRUE branch, that entire branch remains completely dormant.
3. **Zero-Trust Fallbacks:** Never trust incoming payloads. Use `||` in expressions to prevent silent failures (e.g., `{{ $json.lead_score || 0 }}`).
4. **Audit Trails:** Action nodes should always stamp explicit routing data (`lead_status`, `routing_action`) onto the JSON item.