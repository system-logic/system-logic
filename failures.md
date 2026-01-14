### F-01: Tooling vs. Stability Trade-off (Python & Env)

**Context:** Initial setup for the scientific computing stack and development environment.

**Original Assumption:** Use the latest available **Python (3.12)** and standard **venv** to keep the project "bleeding edge" and simple.

**Error / Issue:**

* **Python 3.12:** Encountered stability risks and potential library compatibility lags. Some critical C-extensions in the scientific stack (NumPy/SciPy) are still in the process of optimizing for 3.12, leading to unpredictable behavior.
* **venv:** High manual overhead in managing low-level binary dependencies like **BLAS/LAPACK**. These are critical for NumPy performance, and `pip` does not always handle them optimally for specialized hardware.

**Correction:** Switched to **Python 3.11** (the current "gold standard" for stability) and **Conda/Miniforge** for robust package management.

**Lesson learned:** **"Latest"  "Best"** for production systems.

* Prioritize stability and automated management of binary dependencies over chasing version numbers.
* Don't waste cognitive load on "tool-fighting" (environment issues) when Conda solves it out of the box. Focus on the logic, not the plumbing.