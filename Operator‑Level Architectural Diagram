```mermaid
flowchart TD

    %% High-level pipeline
    A[Parsed Logical Plan] --> B[Analyzed Logical Plan]
    B --> C[Optimized Logical Plan]
    C --> D[Physical Plan]

    %% Parsed
    P1["Project: COUNT(*), SUM(total_population)"]
    P2["Aggregate: BY continent"]
    P3["UnresolvedRelation: population"]

    %% Analyzed
    A1["Project: continent#12, count#45L, sum#46L"]
    A2["Aggregate: count(1), sum(total_population#13)"]
    A3["Relation: population[...]"]

    %% Optimized
    O1["Aggregate: count(1), sum(total_population)"]
    O2["Project: continent, total_population"]
    O3["Relation: population"]

    %% Physical
    X1["Final HashAggregate"]
    X2["Shuffle: hashpartition(continent)"]
    X3["Partial HashAggregate"]
    X4["Scan parquet population"]

    %% Grouping (GitHub-safe)
    subgraph Parsed
        P1
        P2
        P3
    end

    subgraph Analyzed
        A1
        A2
        A3
    end

    subgraph Optimized
        O1
        O2
        O3
    end

    subgraph Physical
        X1
        X2
        X3
        X4
    end
```
