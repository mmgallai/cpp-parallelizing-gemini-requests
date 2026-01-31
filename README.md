# Parallel Gemini API Benchmark (ThreadPoolExecutor)

This project benchmarks and accelerates a 2-step AI pipeline:
1) **Image → description** (Gemini)
2) **Description → 3 quiz questions** (Gemini)

Goal: reduce end-to-end latency by parallelizing I/O-bound API calls with Python threads.

## What’s inside
- `notebooks/parallel_gemini_api_benchmark.ipynb` — all experiments, plots, and code
- `report/report.pdf` — full technical report with results + analysis

## Key results
- Serial baseline: ~3.06s per image (100 images)
- Parallel (5 threads): ~4× speedup under free-tier rate limits

## How to run
1) Set your API key as an environment variable:
   - `export GEMINI_API_KEY="YOUR_KEY"`
2) Open the notebook and run all cells.

## Notes
- This repo contains **no production NeuroTrace code**—only the benchmarking pipeline.
- API calls are rate-limited; the notebook includes retry + exponential backoff.
