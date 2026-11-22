# Empirical Analysis of Sorting Algorithms

Analysis of Algorithms – Major Assignment

This project measures the running time of four sorting algorithms and compares the results with their theoretical time complexity.

## Algorithms

| Algorithm | Best case | Worst case |
|---|---|---|
| Bubble Sort (no early exit) | O(n²) | O(n²) |
| Selection Sort | O(n²) | O(n²) |
| Insertion Sort | O(n) | O(n²) |
| Merge Sort | O(n log n) | O(n log n) |

## Experiment

- **Input sizes:** N = 5, 10, 50, 100 (arrays {1, 2, ..., N} as given in the assignment).
- **Inputs tested:**
  - Given arrays (already sorted): best case for Insertion Sort.
  - Reverse-sorted arrays {N, ..., 1}: worst case.
- **Timer:** `time.perf_counter_ns()`, reported in microseconds (µs).
- **Runs:** 100 timed runs per size after 10 warm-up runs. Garbage collection is disabled while timing. The slowest 20% of runs are dropped (random system spikes) and the average of the remaining runs is reported.
- **Correctness:** each algorithm is checked against Python's `sorted()` on random lists before timing.

## Files

| File | Description |
|---|---|
| `Sorting_Analysis_Final.ipynb` | Main notebook: implementations, correctness test, timing, graphs, ratio table |
| `results_worst_case.csv` | Average times (µs), reverse-sorted input |
| `results_sorted_input.csv` | Average times (µs), given sorted arrays |
| `graph_worst_case.png` | Time vs N, worst case |
| `graph_sorted_input.png` | Time vs N, sorted input |
| `graph_worst_case_loglog.png` | Worst case on log-log scale |

## How to run

### Option 1: Google Colab (easiest)

1. Open [Google Colab](https://colab.research.google.com/).
2. Choose **File → Upload notebook** and select `Sorting_Analysis_Final.ipynb`.
3. Click **Runtime → Run all**.
4. The tables and graphs appear in the notebook. The CSV and PNG files are saved in the Colab file panel on the left.

### Option 2: On your own computer

1. Install Python 3.8 or newer.
2. Install the libraries:
   ```
   pip install pandas matplotlib jupyter
   ```
3. Start Jupyter:
   ```
   jupyter notebook Sorting_Analysis_Final.ipynb
   ```
4. Click **Run → Run All Cells**.

Note: the notebook uses `display(...)`, which works in Jupyter and Colab but not in a plain Python script.

The last cell of the notebook (zip download) only works in Google Colab and can be skipped when running locally.

## Note on results

Exact times depend on the machine and on the load at the time of the run, so your numbers will differ slightly. The growth trends (for example, about 4x for O(n²) and about 2.3x for O(n log n) when N doubles from 50 to 100) should stay the same.
