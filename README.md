# Hi there, I'm Lai, Shi-Han 👋

[![Github](https://img.shields.io/badge/-Github-333?style=flat&logo=Github&logoColor=white)](https://github.com/Han-lai/)
[![Linkedin](https://img.shields.io/badge/-LinkedIn-blue?style=flat&logo=Linkedin&logoColor=white)](https://www.linkedin.com/in/shi-han-lai49975)
[![Gmail](https://img.shields.io/badge/-Gmail-c14438?style=flat&logo=Gmail&logoColor=white)](mailto:sh41bee@gmail.com)
[![Blog](https://img.shields.io/badge/-Blog-brightgreen)](https://hanjobs-com.cms.webnode.tw/)

## Data Engineer | Manufacturing IoT Pipelines & OLAP Data Warehousing

Built production ETL systems processing **50K+ daily CFX protocol messages** from Kafka to S3 using DuckDB in-memory processing with Hive-style partitioning. Implemented configuration-driven Airflow DAGs with dynamic task mapping, achieving **zero-code maintenance** for adding new production lines.

### 💼 What I Do

**Production ETL Pipelines**
- Designed 4-stage ETL orchestration (PreAction → Allocation → Processing → PostAction) handling manufacturing IoT data
- Implemented idempotent DELETE-INSERT strategies and manual Kafka offset commit for exactly-once semantics
- Discovered and documented **5.89x PyArrow memory multiplier** through production testing, encoded in batch calculator
- Built micro-batch processing with dynamic memory optimization for 1KB-500KB message sizes

**Observability & Monitoring**
- Built memory tracking system using tracemalloc + psutil (RSS/VMS/tracemalloc diff monitoring)
- Created Airflow Worker Admin Plugin using FastAPI for remote worker management via SSH
- Implemented comprehensive logging and error tracking for production pipelines

**Data Warehousing & Analytics**
- Designed MSSQL-to-ClickHouse sync pipelines via JDBC Bridge achieving **118K records/sec** throughput (2.1M records in 17.89s)
- Implemented Bronze/Silver layer architecture with 4 analytical views (process variables pivot, task node layer, process instance layer, business event aggregation)
- Built config-driven SeaTunnel pipelines with multi-stage transforms (JsonPath → Replace → Filter → SQL) for IoT sensor data
- Developed Cube.js semantic layer for real-time OEE analytics (Yield Rate × Performance Rate × Utilization Rate)
- Conducted technical evaluations: PySpark vs SeaTunnel, Apache Doris vs ClickHouse (validated with 83GB+ datasets)
- Produced formal selection reports with performance benchmarks and trade-off analysis

**Configuration-Driven Architecture**
- YAML-driven multi-tenant configuration enabling zero-code maintenance
- Dynamic DAG generation from configuration files (auto-create DAGs per factory/production line)
- Environment-agnostic deployment (UT/STG/PRD) through configuration separation

### 🔥 Key Projects

**[aiot_data_repo](./aiot_data_repo)** - CFX Protocol ETL Pipeline
- Kafka → DuckDB → Parquet → MinIO/S3
- 8-layer Hive partitioning, 36 business metrics
- Handles 10K-50K messages/topic/day with memory-optimized micro-batching

**[cfx-clickhouse-cubejs-pipeline](./cfx-clickhouse-cubejs-pipeline)** - Real-time OEE Analytics
- RabbitMQ/Kafka → ClickHouse → Cube.js semantic layer
- OEE calculation: Yield Rate × Performance Rate × Utilization Rate
- Multiple integration patterns: direct, multi-hop, and ETL pipelines

**[mongodb_to_clickhouse_seatunnel](https://github.com/Han-lai/mongodb_to_clickhouse_seatunnel)** - Config-Driven SeaTunnel Pipeline
- MongoDB → SeaTunnel → ClickHouse with Materialized Views
- Multi-stage transforms: JsonPath → Replace → Filter → SQL
- Device health, anomaly summary, and energy efficiency analytics

**[dmp_flowable_etl](./dmp_flowable_etl)** - BPM Data Warehouse
- MSSQL → ClickHouse via JDBC Bridge
- 16 tables, 2.1M records, 118K records/sec throughput
- Bronze/Silver layer with analytical views for process efficiency analysis

**[doris-seatunnel-etl-poc](./doris-seatunnel-etl-poc)** - Technical Selection POC
- Evaluated Apache Doris vs ClickHouse, SeaTunnel vs Airbyte
- 15+ ETL pipeline configurations, 83GB data validation
- Formal selection reports with performance benchmarks

**[mongodb-etl-toolkit](./mongodb-etl-toolkit)** - ETL Runtime Comparison
- 2×2 matrix: PySpark vs SeaTunnel × ClickHouse vs S3
- Technical decision guide with migration paths
- IoT sensor data & CFX protocol message processing

### 💡 Technical Highlights

- **Memory Optimization**: Discovered 5.89x memory multiplier in PyArrow arena allocation (production finding)
- **Performance Tuning**: Migrated from Python jsonpath-ng to DuckDB native JSON functions → 60% CPU reduction, 90% throughput increase
- **Partition Strategy**: Added device_id as partition key → improved query performance for device-specific analysis
- **Error Categorization**: Auto-classify errors into resource/network/data/database/permission/business categories
- **Comprehensive Documentation**: System design docs, operations guides, deployment guides, monitoring guides

### 🎯 Production Mindset

- Idempotent pipeline design for safe backfill scenarios
- Retry strategies with exponential backoff
- Comprehensive error handling and failure notifications
- Configuration-driven architecture for operational flexibility
- Detailed lessons learned documentation from production issues

<br />

### 🛠️ Tech Stack

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Han-lai&layout=compact)](https://github.com/anuraghazra/github-readme-stats)

**Data Engineering & Orchestration**
<br />
<code><img width="10%" src="https://www.vectorlogo.zone/logos/python/python-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/apache_spark/apache_spark-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/apache_kafka/apache_kafka-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/apache_airflow/apache_airflow-ar21.svg"></code>
<br />
<code><img width="10%" src="https://img.shields.io/badge/DuckDB-FFF000?style=flat&logo=duckdb&logoColor=black"></code>
<code><img width="10%" src="https://img.shields.io/badge/dlt-0A0A0A?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cGF0aCBkPSJNMTIgMkw0IDZWMTJMMTIgMTZMMjAgMTJWNkwxMiAyWiIgZmlsbD0id2hpdGUiLz48L3N2Zz4="></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/apache_parquet/apache_parquet-ar21.svg"></code>
<code><img width="10%" src="https://img.shields.io/badge/Cube.js-7A77FF?style=flat&logo=cube&logoColor=white"></code>
<br />

**Databases & Storage**
<br />
<code><img width="10%" src="https://www.vectorlogo.zone/logos/mysql/mysql-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/mongodb/mongodb-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/postgresql/postgresql-ar21.svg"></code>
<code><img width="10%" src="https://clickhouse.com/images/ch_gh_logo_rounded.png"></code>
<br />
<code><img width="10%" src="https://www.vectorlogo.zone/logos/amazon_aws/amazon_aws-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/min-io/min-io-ar21.svg"></code>
<br />

**Observability & Infrastructure**
<br />
<code><img width="10%" src="https://www.vectorlogo.zone/logos/docker/docker-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/elastic/elastic-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/elasticco_kibana/elasticco_kibana-ar21.svg"></code>
<code><img width="10%" src="https://www.vectorlogo.zone/logos/prometheusio/prometheusio-ar21.svg"></code>
<br />
<code><img width="10%" src="https://www.vectorlogo.zone/logos/grafana/grafana-ar21.svg"></code>

---

### 📫 Get in Touch

- 💼 LinkedIn: [Shi-Han Lai](https://www.linkedin.com/in/shi-han-lai49975)
- 📧 Email: sh41bee@gmail.com
- 📝 Blog: [hanjobs-com.cms.webnode.tw](https://hanjobs-com.cms.webnode.tw/)

⚡ **Fun fact**: I have a degree in Marine Science and predicted yellowfin tuna distribution in the Pacific Ocean using General Additive Models and MaxEnt models. Now I apply similar data-driven approaches to manufacturing IoT pipelines!
