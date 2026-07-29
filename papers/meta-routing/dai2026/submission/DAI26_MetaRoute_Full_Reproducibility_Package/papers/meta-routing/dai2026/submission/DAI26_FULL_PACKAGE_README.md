# DAI 2026 Full Submission Package

This archive contains only files needed for the DAI 2026 Industry Track
MetaRoute-Bench submission and reproducibility artifact.

## Contents

- `README.md`, `LICENSE`, `pyproject.toml`, `requirements.txt`, `run_all.sh`
- `src/metarouter/`: benchmark, policies, simulator, evaluator, and CLI
- `tests/`: unit tests for the meta-routing implementation
- `experiments/README.md` and `experiments/meta-routing/dai2026/`
- `results/README.md`, `results/meta-routing/README.md`, and
  `results/meta-routing/dai2026/`
- `output/hf_dataset/README.md`, `output/hf_dataset/data/meta-routing/README.md`,
  and `output/hf_dataset/data/meta-routing/dai2026/`
- `benchmarks/README.md` and operational benchmark notes
- `papers/README.md`, `papers/meta-routing/README.md`, and
  `papers/meta-routing/dai2026/`
- `blog/dai2026-metaroute-bench.md`

The package intentionally excludes unrelated AAAI 2027, ORACLE 2026, cache,
temporary build, and local environment files.

## Reproduce

From the unpacked repository root:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -e ".[dev]"
metarouter-benchmark --seeds 30 --output results/meta-routing/dai2026/main
python experiments/meta-routing/dai2026/run_ablations.py
python experiments/meta-routing/dai2026/plot_results.py
python experiments/meta-routing/dai2026/check_paper_results.py
pytest -q
```

Submission-ready upload files are under `papers/meta-routing/dai2026/submission/`.
