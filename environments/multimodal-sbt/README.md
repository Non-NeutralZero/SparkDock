# Multimodal SBT

A modular Scala SBT project for building and managing Spark applications. This project is preconfigured with Spark 2.4.0 (CDH 6.2.1) and Hive 2.1.1 (CDH 6.2.1)

### Componenets
- **Java**: JDK 8 or higher
- **Scala**: 2.11.12
- **SBT**: 1.6.2 or higher
- **Spark**: 2.4.0 (CDH 6.2.1)

### Build the Project
```bash
sbt compile
```
### Run a Specific Module
The project is organized into three modules:

| **Module**      | **Description**                                                                 |
|------------------|---------------------------------------------------------------------------------|
| **warehouse**   | Handles data warehousing and storage logic.                                     |
| **ingestion**   | Manages data ingestion pipelines (e.g., from external sources).                 |
| **processing**  | Performs data transformations and enrichement.          |

```bash
sbt "project <module-name>" run
```

### **Directory Structure**

```
spark-scala-sbt-project/
├── build.sbt               # SBT build configuration
├── project/                # SBT project metadata
├── warehouse/              # Warehouse module
│   ├── src/main/scala/     
│   └── src/test/scala/     
├── ingestion/              # Ingestion module
│   ├── src/main/scala/     
│   └── src/test/scala/     
├── processing/             # Processing module
│   ├── src/main/scala/     
│   └── src/test/scala/     
```


