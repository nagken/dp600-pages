# DP-600 - Implementing Analytics Solutions Using Microsoft Fabric - Visual Study Guide

> Concept-only study aid. No exam questions reproduced. Source PDF (if any) stays local + gitignored.

**Skills outline:** https://learn.microsoft.com/credentials/certifications/resources/study-guides/dp-600

## Master mind map

```mermaid
mindmap
  root((DP-600))
    Plan implement and manage
      Workspaces
        Roles and permissions
        Domains
        Capacity assignment
      Capacity
        F SKUs
        Pause and resume
        Bursting and smoothing
      Lifecycle
        Git integration
        Deployment pipelines
        Variable libraries
      Security and governance
        Sensitivity labels
        Endorsement
        Access through OneLake
    Prepare and serve data
      Ingest
        Pipelines
        Dataflows Gen2
        Notebooks PySpark
        Shortcuts
        Mirroring
      Transform
        Lakehouse and Spark
        Warehouse and T-SQL
        KQL database
        Dataflows Power Query
      Optimize
        V-Order
        Partitioning
        Z-Order
        Statistics
        File compaction
      OneLake
        Single copy
        Shortcuts
        Domains
    Implement and manage semantic models
      Storage modes
        Import
        DirectQuery
        Direct Lake
        Composite
      Modeling
        Star schema
        Relationships
        Calculation groups
      DAX
        Time intelligence
        CALCULATE
        Variables
      Security
        Row-level security
        Object-level security
        Dynamic RLS
      Performance
        Aggregations
        Performance Analyzer
        DAX Studio
        Best Practice Analyzer
    Explore and analyze data
      Visual analysis
        Power BI reports
        Notebooks
        Real-Time Dashboards
      Languages
        DAX
        T-SQL
        PySpark and Spark SQL
        KQL
      Statistical analysis
        Descriptive
        Diagnostic
        Forecasting
      AI features
        Copilot in Fabric
        Quick measures
        Smart narratives
```

## Domain map

```mermaid
flowchart LR
    Master["DP-600 Master Index"]
    D01["Plan implement manage"]
    Master --> D01
    D02["Prepare and serve data"]
    Master --> D02
    D03["Semantic models"]
    Master --> D03
    D04["Explore and analyze"]
    Master --> D04
```

## Domain weights

```mermaid
pie showData
    title DP-600 domain weights
    "Plan implement manage" : 10
    "Prepare and serve data" : 40
    "Semantic models" : 25
    "Explore and analyze" : 25
```

## Recommended study order

```mermaid
gantt
    title Suggested study plan
    dateFormat X
    axisFormat Day %d
    section Plan
    Plan implement manage   :t1, 0, 1d
    Prepare and serve data  :t2, after t1, 4d
    Semantic models         :t3, after t2, 3d
    Explore and analyze     :t4, after t3, 2d
    Cheatsheet and review   :t5, after t4, 1d
```

---

**Next:** open [01-plan-implement-manage.md](01-plan-implement-manage.md)
