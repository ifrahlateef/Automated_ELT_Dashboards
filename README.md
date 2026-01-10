# Media Estate Analytics: Cinema & Sports Revenue Optimization

##  Business Objective
The goal of this project is to synthesize disparate data streams from Cinema and Sports media assets into a unified analytical engine. By normalizing cross-channel data and applying region-specific pricing models, this tool provides stakeholders with a "Single Source of Truth" for total revenue visibility and estate performance.

**Business Value:**
* **Operational Efficiency:** Automated 3-step ETL (Extract, Transform, Load) process replaces manual sheet merging.
* **Data Integrity:** Systematic anomaly detection identifies "noisy" data that would otherwise skew financial forecasts.
* **Strategic Mapping:** Enables regional performance benchmarking through standardized estate mapping.

---

##  The Analytical Pipeline

### Phase 1: Data Ingestion & Schema Normalization
To handle the structural variety in Cinema and Sports datasets, a robust ingestion function was developed to perform:
* **Vertical Aggregation:** Programmatically loading and combining multiple Excel worksheets into a centralized DataFrame.
* **Header Standardization:** Implementing a sanitization layer to handle case sensitivity and strip whitespace, ensuring consistent column referencing across different data versions.
* **Feature Selection:** Automated searching for target variables required for downstream analysis, isolating them from auxiliary metadata.



### Phase 2: Data Hygiene & Anomaly Detection
Before calculation, the data undergoes a "Sanity Check" to ensure statistical validity:
* **Integrity Validation:** Identifying data discrepancies and performing **Anomaly Detection** to flag outliers or illogical entries.
* **Dtype Enforcement:** Auditing column data types to filter out "noisy" or corrupted data (e.g., non-numeric strings in financial fields).
* **Deduplication:** Removing redundant records to prevent the artificial inflation of reach and revenue metrics.

### Phase 3: Feature Engineering & Transformation
The raw data is transformed into a calculation-ready format:
* **Temporal Standardization:** Converting varied date formats into unified **ISO Timestamps** to allow for accurate time-series analysis across media cycles.
* **Numerical Casting:** Ensuring "Sales" and "Volume" metrics are strictly numeric to support mathematical aggregations.
* **Regional Mapping:** Applying a specialized **Region Mapping Dictionary** to categorize the diverse media estate into standardized geographical segments.

### Phase 4: Financial Modeling
The final layer applies business logic to generate KPIs:
* **Cost & Threshold Definition:** Setting operational thresholds and cost parameters to evaluate margin health.
* **Revenue Synthesis:** Applying dynamic pricing models to calculate **Total Revenue** across Cinema and Sports categories.

---

## Key Metrics & Output
| **Metric** | **Description** |
| :--- | :--- |
| **Total Revenue** | Aggregate income across all media types. |
| **Regional Yield** | Performance of the estate mapped by geographical dictionary. |
| **Data Health Score** | Percentage of "Bad/Noisy" data filtered during the hygiene phase. |

---

##  Tech Stack
* **Language:** Python
* **Libraries:** Pandas (Data Manipulation), OpenPyXL (Excel Engine), NumPy (Numerical Processing)
* **Techniques:** Regular Expressions (Header Cleaning), Dictionary Mapping, Time-Series Normalization
