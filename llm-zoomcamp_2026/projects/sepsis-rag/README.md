# Sepsis RAG

A retrieval-augmented generation system built over the 2026 Surviving Sepsis Campaign Guidelines.

## Data

**Surviving Sepsis Campaign: international guidelines for management of
sepsis and septic shock 2026**

- **Authors:** Prescott HC, Antonelli M, et al.
- **Journal:** Intensive Care Med (2026)
- **DOI:** https://doi.org/10.1007/s00134-026-08361-1
- **Local file:** `data/surviving-sepsis-campaign-guidelines-2026.pdf` (not tracked in git)

A five-record corpus was manually extracted from the 2026 SSC Guidelines publication and structured as JSON. The extracted records were saved under keys which include `topic`, `recommendation_number`, `recommendation`, `remark`, and `rationale`. These five records were selected because they contain a single recommendation number each. Recommendations sharing a common rationale across multiple numbers cannot be cleanly represented as independent records in this schema.

Cleaning was required because rationale fields span multiple paragraphs, embedding literal newline characters inside JSON string values. Cleaning was performed using Python's replace method to substitute `\n` with a single space. The JSON file was validated using Python's `json.tool`.

## Status

Work in progress.