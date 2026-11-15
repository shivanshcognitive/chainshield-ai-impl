# chainshield-ai-impl
This is implementation repo of project ChainShield AI

# Guidelines
## GIT Practice : Fork and Pull Request

<img width="940" height="377" alt="image" src="https://github.com/user-attachments/assets/aaf87d10-34f9-4b89-8146-c9a1ff21bce1" />

1. Fork your public repository into their own GitHub accounts.
2. Commit and push changes in their own forks.
3. Submit pull requests to your repository.
4. Respond to your review feedback.


Below is the updated **18-notebook package**, including dataset prefixes for notebooks 03–09. Outputs are generated after successful execution.

| Notebook | One-line purpose | Main activities | Outputs |
|---|---|---|---|
| **00 — Environment and persistence** | Establish a reproducible CPU environment and persistent storage. | Verify dependencies; record package versions; configure Google Drive, shared helpers, logging and recovery. | Verified environment, package freeze, shared utilities, Drive folders and completion record. |
| **01 — Dataset acquisition** | Download and verify the three original datasets. | Acquire pinned versions; check file sizes and hashes; record sources and licensing metadata. | Raw DataCo, India-Nepal and CrisisMMD files; acquisition manifests. |
| **02A — DataCo preparation and EDA** | Prepare and understand shipment data before modeling. | Aggregate items into orders; examine missingness, distributions, correlations and shipping modes; validate eligible features and chronological splits. | Canonical orders, feature/label metadata, splits, readiness report and **5 EDA panels**. |
| **02B — India-Nepal preparation and EDA** | Prepare and analyze India-Nepal’s three text-classification tasks. | Normalize text; inspect identifiers and related-record groups; analyze class/source balance, frequent terms and tokenizer lengths. | Prepared task data, label mappings, group-based splits, readiness report and **12 EDA panels**. |
| **02C — CrisisMMD preparation and EDA** | Prepare CrisisMMD screening and humanitarian classification data. | Reconcile annotations; quarantine conflicts; inspect event/class support; create matched minimal-cleaning and URL/mention-normalized variants. | Prepared variants, annotation provenance, task/shared-view splits, readiness report and **16 EDA panels**. |
| **02D — Cross-dataset validation and handoff** | Verify the three completed preparations and make them available for modeling. | Check completion and integrity; validate preparation evidence; assemble verified files in standard folders while preserving separate datasets and labels. | Validated modeling-input folders, consolidated preparation manifest and readiness report. |
| **03 — DataCo shipment-risk models** | Compare classical models for predicting shipment delay risk. | Fit four controls; evaluate **24** feature/model candidates using inner chronological validation; select and refit one supervised configuration. | Four control models, candidate results, one selected model, development predictions and metrics. |
| **04 — India-Nepal + CrisisMMD text classification** | Select text representations and preprocessing across five tasks. | Fit five controls; evaluate **56** BoW/TF-IDF, n-gram and normalization candidates; inspect sparse vectors; refit five selections. | Five control models, candidate results, five selected models, vocabularies, predictions and metrics. |
| **05 — India-Nepal + CrisisMMD text robustness** | Investigate textual artifacts that could inflate performance. | Audit exact/template similarities; inspect examples; measure sampling coverage; document limitations. | Five task-level robustness audits, similarity/template evidence and summary reports. |
| **06 — India-Nepal + CrisisMMD classical generalization** | Measure classical-model transfer across sources and events. | Train **20** fixed-setting transfer models; verify fold isolation and class support; evaluate held-out domains. | Fold models, manifests, predictions, per-fold metrics and pooled transfer results. |
| **07 — CrisisMMD BiLSTM screening** | Train neural screening of informative disaster reports. | Build the training vocabulary; encode text; train BiLSTM; select a development checkpoint; inspect unknown tokens and learning history. | Vocabulary, model weights, checkpoints, parameter counts, histories, predictions and metrics. |
| **08 — India-Nepal + CrisisMMD DistilBERT classification** | Fine-tune disaster-type and humanitarian classifiers. | Acquire pinned weights; inspect tokens, IDs and masks; fine-tune India-Nepal disaster-type and CrisisMMD humanitarian models. | Verified pretrained assets, two trained models, selected checkpoints, histories, predictions and metrics. |
| **09 — India-Nepal + CrisisMMD neural generalization** | Test neural transfer to held-out sources and events. | Train **16** domain models using fixed settings and epochs; evaluate without held-domain checkpoint selection. | Domain weights, checkpoints, fold predictions/metrics and combined **19-job neural summary**. |
| **10 — Results and explanations** | Compare model performance and explain the supporting evidence. | Generate confusion matrices, ROC/PR, reliability and learning curves; calculate paired group-bootstrap intervals; inspect coefficients and tree importance. | Comparison tables, evaluation figures, uncertainty estimates and explanation records. |
| **11 — Saved-model inference** | Demonstrate predictions from verified saved models. | Reload control, selected and neural models; process examples; demonstrate confidence and domain-review states. | Structured inference examples, model/version details and review decisions. |
| **12 — Error and cascade analysis** | Understand classification failures and screening consequences. | Examine class-specific mistakes; analyze screening errors; measure humanitarian reports suppressed on shared CrisisMMD records. | Error examples, class-level findings and screening-suppression reports. |
| **13 — Verification and recovery** | Check correctness, resource evidence and persistence. | Run fixture tests; review CPU/RAM logs; optionally verify the full archive and checkpoint pairs. | Test results, resource summaries, persistence checks and execution logs. |
| **14 — Research report and export** | Assemble the experiment’s evidence into readable deliverables. | Compile preparation findings, selections, metrics, explanations, figures and limitations; export and bundle evidence. | Illustrated **HTML, PDF and Word reports**, Markdown, structured inventory and evidence ZIP. |

**Execution order:** `00 → 01 → 02A → 02B → 02C → 02D → 03 → … → 14`.

Calibration, frozen final-test evaluation, RAG, LangGraph agents, scenario services and Streamlit remain subsequent implementation work.
