

***

This repository contains datasets for fine-tuning and evaluating a model designed to detect Java lock contention issues. The goal is to provide developers with an automated tool to identify and help resolve potential concurrency problems in code snippets.

* **Finetune Data.csv**: Contains the dataset for fine-tuning the model.
* **Evaluation Dataset.csv**: Contains a dataset for evaluating the model's performance, with pre- and post-merge code examples from real-world GitHub repositories.

---
## Data Schema

### `Finetune Data.csv`

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `instruction` | `String` | A description of the task for the language model. |
| `input` | `String` | The Java code snippet to be analyzed. |
| `output` | `String` | A detailed analysis of potential lock contention and suggested solutions. |
| `text` | `String` | A combined field containing the instruction, input, and response for model training. |

### `Evaluation Dataset.csv`

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `File` | `String` | The path to the Java file that was changed. |
| `PRE-MERGE` | `String` | The Java code **before** a merge, which contains a lock contention issue. |
| `POST-MERGE`| `String` | The Java code **after** a merge, where the contention issue has been fixed. |
