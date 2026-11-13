# Innovation Summit 2026 — Data Atlas Dashboard

Run the Benefits Market Intelligence dashboard locally using the included Form 5500 Parquet files.

## Requirements

- **uv** installed and available in your terminal.
- Internet access for the first run to download Python and the dependencies.

The project uses Python 3.14. uv can download a compatible Python version if needed and creates the local environment automatically. Runtime dependencies are configured in `pyproject.toml`.

## Run

1. Extract the ZIP completely.
2. Open a terminal in **Innovation_Summit_2026-Data_Atlas_Dashboard**, the folder containing `app.py` and `pyproject.toml`.
3. Run:

```bash
uv run streamlit run app.py
```

4. Open **http://localhost:8501** in your browser.

The first run takes longer while uv installs dependencies and the dashboard reads the data. Later runs use the same command. Press **Ctrl+C** in the terminal to stop the dashboard.

No separate `uv sync`, manual virtual environment activation, database setup or data pipeline run is needed.

## Included

| File or folder | Purpose |
|---|---|
| `app.py` | Dashboard entry point |
| `figures/` | Data loading, charts and shared interface code |
| `views/` | Market, Brokers, Opportunity and Accounts views |
| `.streamlit/config.toml` | Dashboard theme and settings |
| `data/exports/` | The three Parquet files used by the dashboard |
| `pyproject.toml` | Runtime dependencies for uv |

Keep the folder structure intact. The data files are loaded locally; the dashboard does not download or rebuild the source filings. External fonts and map assets may still use the internet.

## If it does not start

- **`uv` is not recognized:** install uv, then reopen your terminal.
- **`app.py` cannot be found:** open the terminal in the extracted folder containing `app.py`, not its parent folder or inside the ZIP.
- **A Parquet file cannot be found:** confirm that all three files remain under `data/exports/`.
- **Downloads fail:** check your internet connection and any workplace proxy restrictions.
- **Port 8501 is already in use:** run `uv run streamlit run app.py --server.port 8502`, then open `http://localhost:8502`.
