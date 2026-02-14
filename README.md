# CO2 & GDP Dashboard

A Quarto dashboard analyzing the relationship between CO2 emissions and GDP across countries.

## Project Structure

- **co2-gdp_db_quarto_sol.qmd** - Main Quarto dashboard source file
- **co2-gdp_db_quarto_sol.html** - Rendered HTML dashboard (auto-generated)
- **pyproject.toml** - Python project dependencies

## Getting Started

### Prerequisites

- Python 3.12
- [uv](https://github.com/astral-sh/uv) package manager
- [Quarto](https://quarto.org/)

### Setup

1. **Initialize the Python environment:**
   ```bash
   uv venv --python 3.12
   ```

2. **Activate the environment:**
   ```bash
   source .venv/bin/activate  # On macOS/Linux
   .venv\Scripts\activate     # On Windows
   ```

3. **Install dependencies:**
   ```bash
   uv pip install -r pyproject.toml
   ```e .

## Building the Dashboard

```bash
quarto render co2-gdp_db_quarto_sol.qmd
```

This generates the HTML dashboard in `co2-gdp_db_quarto_sol.html`.

## Deployment

### GitHub Pages

This project is configured for automatic deployment to GitHub Pages via GitHub Actions.

**Setup:**

1. Push this repository to GitHub
2. Go to your repository **Settings → Pages**
3. Under "Build and deployment", select:
   - **Source:** GitHub Actions
   - Deploy should happen automatically on push to `main` branch

The dashboard will be published at: `https://<your-username>.github.io/<repository-name>/`

**How it works:**
- Every push to the `main` branch triggers the `.github/workflows/publish.yml` workflow
- The workflow:
  - Sets up Python 3.12
  - Installs project dependencies via `uv`
  - Renders the Quarto file to HTML
  - Deploys the output to GitHub Pages

No manual build steps needed - just push and the site updates automatically!

## Data Requirements

The project expects the following data structure in the `data/` directory:
- `co2_gdp/co2_gdp_country.csv` - Country-level CO2 and GDP data
- `natural_earth/110m_cultural/ne_110m_admin_0_countries.shp` - Ge
- **plotly** - Interactive visualizations
- **python-dotenv** - Environment variable management

## Notes

- The dashboard renders as a static HTML file with interactive Plotly visualizations
- No Shiny server is required - the output is pure HTML with JavaScript interactivity via Plotly

## License

[Add license information if appl and CSV reading
- **plotly** - Interactive visualizations
[Add author information if applicable]
