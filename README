# LLM-SLR-2026: THREAT-LLM evidence base, codebook and persistence protocol

Research artifact for the draft paper *THREAT-LLM: A Lifecycle-Aware Taxonomy and Threat Model for Large Language Model Poisoning with a Cross-Stage Persistence Protocol* (Waqas Ahmed, PhD research on security and trust frameworks for LLMs). The paper is a draft under preparation and is not included here.

Archived on Zenodo. Concept DOI (always the latest version): [10.5281/zenodo.23321265](https://doi.org/10.5281/zenodo.23321265).

## What is in this release (v1.1)

| Folder | Contents |
|---|---|
| `data/` | Search queries (29, with exact search URLs), screening log of 2,049 records (304 included, 246 duplicates, 1,499 excluded), bibliographic metadata of the 304 included studies, 186 secondary studies set aside for snowballing. See `data/README.md` for the schema. |
| `docs/` | Coding codebook v1.0 and the second-coder (inter-rater) protocol |
| `validation/` | Cohen's kappa / Gwet's AC1 / PABAK script with unit tests; adjudication log template |
| `code/` | Cross-stage persistence protocol (Algorithm 2 of the paper): data handling, training, evaluation, analysis, configuration, smoke test |

## What is deliberately not in this release

- **Coding labels** (scope, mechanism, stage, persistence for each study) and the scripts that produce them. They are held back until the independent second coder has returned their sheet, so the second coding stays blind. They will be added in a later version.
- **Abstracts and full texts** of the included studies. Most are copyrighted by their publishers. Use the links in `data/included_studies_metadata.csv`.
- **Experimental results.** The persistence experiment has **not been run**. No attack success rates, persistence ratios or test statistics exist yet.

## Reproducing

```bash
conda env create -f environment.yml && conda activate threat-llm   # or: pip install -r code/requirements.txt
python3 validation/scripts/test_compute_agreement.py              # unit tests for the agreement statistics
cd code && python3 smoke_test.py                                  # pipeline check on a tiny random model (no LLM results)
```

Running the real experiment needs a GPU (a 24 GB card is planned), pinned datasets and the base model; see `code/config.yaml`, which is marked as not yet executed.

## Safety and ethics

The planned backdoor maps a rare trigger string to a fixed, harmless marker string. Use only small open models in an offline, controlled setting. Do not upload poisoned checkpoints to public model hubs.

## Licence

Code: MIT (`LICENSE`). Data and documentation: CC BY 4.0 (`LICENSE-DATA`). Third-party bibliographic metadata remains subject to its sources' terms.

## Citation

See `CITATION.cff`. Cite the concept DOI above unless you need a specific version.

## Status of the wider study

See `CHANGELOG.md`. Pending: second-coder agreement, full-text recoding of the in-scope studies, the five-seed persistence experiment.
