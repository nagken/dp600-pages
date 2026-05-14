# DP-600 Reference Architectures

> Canonical Fabric analytics patterns. Memorize the shapes.

## 1. Medallion Lakehouse

```mermaid
flowchart LR
    Sources["Sources: OLTP DB, files, APIs"] --> Pipe[Data Pipeline]
    Pipe --> Bronze[Bronze: raw Delta]
    Bronze --> NB[Notebook PySpark]
    NB --> Silver[Silver: cleansed Delta]
    Silver --> WH[Warehouse / SQL endpoint]
    WH --> Gold[Gold: curated star schema]
    Gold --> SM[Semantic model Direct Lake]
    SM --> PBI[Power BI report]
```

- Bronze keeps raw landing zone; Silver is conformed; Gold is BI-ready.
- All layers in OneLake -> single lake, multi-engine access.

## 2. Real-Time Intelligence

```mermaid
flowchart LR
    IoT[IoT Hub / Event Hubs / Kafka] --> ES[Eventstream]
    ES --> KQL[KQL Database]
    KQL --> RTD[Real-Time Dashboard]
    KQL --> Reflex[Reflex / Activator]
    Reflex --> PA[Power Automate / Teams alert]
```

- Sub-second latency; KQL DB stores hot data with retention policy.
- Reflexes encode "alert when count > X" without code.

## 3. Cross-cloud lake via shortcuts

```mermaid
flowchart LR
    S3["Amazon S3 / GCS / ADLS Gen2"] -.shortcut.-> OL[OneLake folder]
    OL --> SM[Semantic model]
    OL --> NB[Notebook]
    OL --> WH[Warehouse SQL endpoint]
```

- Shortcut = pointer; data stays in source. Egress costs stay outside Fabric.
- Works for ADLS Gen2, Amazon S3, Google Cloud Storage, internal OneLake folders.

## 4. Mirroring for zero-ETL analytics

```mermaid
flowchart LR
    AzSQL[Azure SQL DB] -- CDC stream --> Mir[Mirrored Database]
    Mir --> OLD[Mirrored Delta in OneLake]
    OLD --> SM[Direct Lake semantic model]
    SM --> PBI[Power BI]
```

- Azure SQL DB / Cosmos DB / Snowflake mirrored continuously.
- No Spark / pipeline; analytics stays current automatically.

## 5. Lifecycle: Dev -> Test -> Prod

```mermaid
flowchart LR
    Dev[Workspace Dev] --Git PR--> Repo[(Azure DevOps / GitHub)]
    Repo --PR merge--> Main[main branch]
    Dev --deployment pipeline--> Test[Workspace Test]
    Test --deployment pipeline--> Prod[Workspace Prod]
    VL[(Variable library)] -. parameters .- Test
    VL -. parameters .- Prod
```

- Variable libraries swap connection strings per stage.
- Git tracks item JSON; deployment pipelines move artifacts.

---

[Master Index](00-MASTER-INDEX.md)
