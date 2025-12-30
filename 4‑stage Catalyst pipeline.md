# Architectural-Representation-SQL-
High‑level architecture , (4‑stage Catalyst pipeline) / Operator‑level architecture (Logical → Optimized → Physical) / End‑to‑end execution pipeline (Mermaid flow)
```mermaid
flowchart LR
    A[Parsed Logical Plan] --> B[Analyzed Logical Plan]
    B --> C[Optimized Logical Plan]
    C --> D[Physical Plan]
```
