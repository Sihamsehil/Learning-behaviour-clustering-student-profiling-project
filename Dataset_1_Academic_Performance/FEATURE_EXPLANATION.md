# Dataset 1: Academic Performance

Academic performance dataset grouping records, module averages, semester margins, evaluation types (EMD/TP indicators), and derived performance indicators. Sources are kept independent because they do not necessarily track the same students across datasets.

\---

## Files Included \& Descriptions

* **`dataset1\_academic\_performance\_dataset.xlsx`**: The primary master file combining all core features, raw tracking data, build statistics, and data mapping into individual spreadsheet tabs.
* **`dataset1\_academic\_core\_clustering.csv`**: Contains pre-processed, imputed, and normalized numerical features optimized specifically for profiling and clustering tasks.
* **`dataset1\_academic\_extended\_raw\_support.csv`**: Contains the raw data before full normalization, retaining raw attendance percentages and individual structural marks where available.
* **`dataset1\_academic\_build\_summary.csv`**: Record tracking log detailing file origin metadata, row processing extraction counts, and final consolidated counts.
* **`dataset1\_academic\_imputation\_log.csv`**: Technical audit trail indicating features containing missing elements and the specific statistical noise/median strategy used to substitute them.

\---

## Feature Explanations 

### Metadata \& Provenance

* **`source\_dataset`**: The name of the specific original file or system from which the row was extracted (`annual\_deliberation\_y1`, `anonymized\_attendance\_tp\_emd`, `final\_students\_scores`, or `ensia\_performance\_prediction`).
* **`local\_student\_id`**: Anonymous identifier specific to each source registry used to reference students safely.
* **`year\_level`**: Academic level or year group assignment (e.g., `Y1`, `Y2`, or `Unknown`).

### Core Performance Metrics

* **`academic\_avg\_20`**: Overall academic year performance evaluation score mapped on a standard /20 scale.
* **`semester1\_avg\_20`**: Calculated academic average specific to the first semester term (out of 20).
* **`semester2\_avg\_20`**: Calculated academic average specific to the second semester term (out of 20).
* **`course\_grade\_mean\_20`**: The mathematical mean of individual courses/modules mapped to a standard /20 scale.
* **`course\_grade\_std\_20`**: Standard deviation of individual course marks; tracks performance volatility across subjects.
* **`course\_grade\_min\_20`**: Minimum module grade recorded for the student within that term window.
* **`course\_grade\_max\_20`**: Maximum module grade recorded for the student within that term window.
* **`course\_count`**: Total count of active modules or course grades mapped for the student record row.

### Academic Standing \& Volatility Metrics

* **`failed\_course\_count\_est`**: Estimated number of modules that fell strictly below the passing threshold of 10/20. *(Only exists in Core dataset)*.
* **`failed\_course\_rate`**: The ratio of courses with scores below 10/20 relative to the total active course count.
* **`strong\_course\_rate`**: Proportion of modules where the student achieved high proficiency benchmarks ($\\ge 14/20$).
* **`low\_performance\_rate`**: Proportion of critical underperformance fields falling short of baseline metrics ($< 8/20$).
* **`performance\_consistency\_index`**: A specialized scale where 1 indicates absolute uniform marks, and decreasing values point to higher inter-course grade discrepancies.
* **`academic\_risk\_score`**: Calculated probability indicator measuring historical metrics (weak mean averages, high failure shares, and extreme performance volatility).

### Data Integrity \& Imputation Indicators

* **`missing\_raw\_values\_count`**: Total tally of attribute metrics missing from original source file processing.
* **`missing\_core\_features\_before\_imputation`**: Granular counter of targeted core analysis metrics missing prior to running replacement routines. *(Only exists in Core dataset)*.
* **`was\_imputed`**: Boolean toggle flag (`True`/`False`) flagging whether core feature records required synthetic backfilling to run modeling. *(Only exists in Core dataset)*.

### 

### 

### 

### Extended Component Assessment Fields

> \*\*Note on availability\*\*: These metrics are raw properties located \*\*only\*\* in the Extended Raw Support file/tab. They are exclusively populated for the row subsets originating from the `anonymized\_attendance\_tp\_emd` dataset; they appear as empty `NaN` for all other source records.

* **`attendance\_rate\_raw`**: Percentage value tracking physical or active class registration attendance.
* **`tp\_score\_20\_raw`**: Evaluation metrics representing practical lab assignments (*Travaux Pratiques*) evaluated out of 20.
* **`emd\_score\_20\_raw`**: Performance metrics evaluating main term examination sittings (*Examen Major de la Délibération*) evaluated out of 20.
* **`self\_academic\_level\_10\_raw`**: Subjective student self-assessment value representing independent capability tracking evaluated out of 10.

