# KernelScope

**Observing the evolution of operating systems through open data.**

KernelScope is an open analytics platform that tracks global operating system adoption using multi-source data aggregation, statistical modeling, and machine learning forecasting.  

The platform provides a transparent and reproducible view of the OS ecosystem through an interactive dashboard, automated data pipeline, and predictive analytics.

## Features

### Global OS Market Share

- Aggregated OS usage from multiple public datasets.
- Weighted and normalized for reliable consensus metrics.

### Timeline Explorer

- Interactive historical analysis of OS adoption trends.
- Animated charts with drill-down details for each OS.

### Geographic OS Map

- Regional OS usage visualization.
- Hover tooltips and country-level breakdowns.

### Linux Ecosystem Insights

- Distribution share estimates.
- Linux growth prediction using multi-signal indicators.

### Forecasting

- Machine learning forecasts for OS adoption trends.
- Includes Windows, macOS, Linux, ChromeOS predictions.
- Confidence intervals for all predictions.

### Source Transparency

- Every metric is traceable back to underlying datasets.
- Weighted aggregation with reliability scoring.

## Dashboard Capabilities

- Interactive filters for OS selection, region, and time range.
- Responsive layout for desktop, tablet, and mobile.
- Animated charts with smooth transitions.
- Drill-down panels for deeper analytics.
- Nord-theme colors for a consistent dark UI.

## Architecture

The platform runs entirely on GitHub infrastructure:

```
Data Sources
    ↓
Aggregation Pipeline
    ↓
Statistical Modeling
    ↓
Forecasting Models
    ↓
Static Dashboard (GitHub Pages)
```

Automation is handled via **GitHub Actions**, which update datasets and regenerate analytics daily.

## Data Sources

KernelScope aggregates data from multiple sources including:

- StatCounter
- Steam Hardware Survey
- Developer Surveys (GitHub, Stack Overflow)
- Vendor Shipment Reports (Dell, Lenovo, System76, etc.)
- Linux ecosystem signals (ISO downloads, mirror stats, kernel updates)

## Forecast Models

The platform includes **time-series forecasting models** to estimate future OS adoption trends:

- Prophet (Facebook/Meta open-source library)
- ARIMA
- Custom Linux Growth Predictor (multi-signal weighted model)

## Repository Structure

```
data/
├─ raw/               # Raw input datasets from sources
├─ processed/         # Normalized, aggregated, and forecast data

scripts/
├─ fetch_sources.py   # Scripts to pull raw data
├─ aggregate.py       # Aggregation and weighted consensus
├─ forecast_os.py     # ML forecast models
├─ linux_growth.py    # Linux growth predictor

web/
├─ index.html         # Dashboard entry point
├─ styles.css         # Nord-theme styles
├─ charts.js          # Interactive chart logic
├─ map.js             # Geographic visualization
├─ drilldown.js       # Drill-down panel logic

.github/workflows/
├─ update.yml         # Daily automation workflow
```

## Local Development

Clone the repository:

```
git clone https://github.com/SilentGlasses-Labs/kernelscope.git
cd kernelscope
```

Install Python dependencies:

```
pip install -r requirements.txt
```

Run the pipeline locally:

```
python scripts/fetch_sources.py
python scripts/aggregate.py
python scripts/forecast_os.py
python scripts/linux_growth.py
```

Serve the dashboard locally (optional):

```
# Using Python HTTP server
cd web
python -m http.server 8000
```

## Live Dashboard

The public dashboard is hosted via **GitHub Pages**:

```
https://SilentGlasses-Labs.github.io/kernelscope
```

## Project Goals

KernelScope aims to provide:

- Transparent OS analytics.
- Reproducible research.
- Open datasets and interactive visualizations.
- Community contributions and collaboration.

## License

MIT License – see `LICENSE` file for full details.

## Contributions

Contributions are welcome! Ideas for expansion include:

- Mobile OS analytics
- Server OS adoption trends
- Additional forecasting models
- New regional or platform data sources
- Interactive scenario simulations for Linux adoption

## Acknowledgments

Thanks to the public data sources and open-source ecosystem that make projects like KernelScope possible.  
Special thanks to contributors of StatCounter, Steam, GitHub surveys, and Linux community telemetry.
