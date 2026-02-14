# Sample Quarto Dashboard on the CO2-GDP Dataset

A Quarto dashboard that uses the CO2-GDP dataset to visualize the relationship between CO2 emissions and GDP. Uses Plotly for interactive visualizations.

The app is deployed on GitHub Pages at https://phonosync.github.io/co2-gdp_quarto/

## Data

The dataset is sourced from [Our World in Data – CO2 and Greenhouse Gas Emissions](https://github.com/owid/co2-data/tree/master).

## Setup
[Install Quarto](https://quarto.org/docs/get-started/)

Dependencies are managed with [uv](https://docs.astral.sh/uv/) via `pyproject.toml` and `uv.lock`.

Install uv (if not already installed):
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Create the virtual environment and install dependencies:
```bash
uv sync
```

Building the Dashboard locally:

```bash
quarto render co2-gdp_db_quarto_sol.qmd
```

This generates the HTML dashboard in `co2-gdp_db_quarto_sol.html`.

For interactive development and automatic build upon file change:

```bash
quarto preview co2-gdp_db_quarto_sol.qmd
```

## Deployment on GitHub Pages

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

## Documentation
- [Plotly](https://plotly.com/python/)
- [Quarto Dashboards](https://quarto.org/docs/dashboards/)
- Deployment of Quarto documents to [GitHub Pages](https://quarto.org/docs/publishing/github-pages.html)
- [uv Documentation](https://docs.astral.sh/uv/)

## License

This project is licensed under the [CC BY-NC 4.0](LICENSE) license.
