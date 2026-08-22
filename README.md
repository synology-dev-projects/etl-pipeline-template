# `etl-pipeline-template`

Standardized template and blueprint for building, testing, and deploying Dockerized ETL data pipelines across the **Quant System** ecosystem.

---

## 🎯 Design Goals

1. **Standardized Pipeline Structure**:
   - Provides boilerplates for scheduled cron extraction, data cleansing, and Oracle database upserts via `common-lib`.
2. **Deterministic Dependency Management**:
   - Uses `requirements.in` and `pip-tools` (`pip-compile`) to generate pinned `requirements.txt` for reproducible Docker image builds.
3. **CI/CD Integration**:
   - Includes standard GitHub Actions workflows for automated Docker image compilation and deployment to Synology NAS Docker Engine.
4. **Verification Utilities**:
   - Includes `verify.sh` to run static linting, typing, and test suites prior to pushing.

---

## 🛠️ Usage

To initialize a new pipeline:
1. Clone or instantiate from this template.
2. Define data extractors in `src/`.
3. Leverage `common-lib` connectors for database persistence (`write_to_oracle_upsert`).
4. Configure scheduled runs in Docker Compose or Kubernetes cron jobs.