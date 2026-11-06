# Schiphol Passenger Traffic and COVID-19 - TIL6022

Descriptive analysis of Schiphol monthly passenger traffic (January 1992-August 2026) and Dutch COVID-19 case reports (2020-2022). Research covers long-term development, seasonality, category differences and recovery. The analysis does not identify causal effects.

## Run

1. Open this project folder in VS Code or Jupyter.
2. Select a Python environment (Python 3.12 recommended).
3. Run `python -m pip install -r requirements.txt`.
4. Select the environment as the kernel for `analysis_in_vscode.ipynb`.
5. Restart the kernel and run all cells from the project root. Inputs use `data/`; images use `figure/`; numerical tables use `results/`.
6. Open `Schiphol_Project_Report.ipynb` from the same folder. Images use relative links to `figure/`.

Keep the supplied input snapshots unchanged for reproduction. Source pages can provide newer data that would change the results. Existing output files are overwritten by Run All; manually deleting them first is unnecessary.

## Project files

- `analysis_in_vscode.ipynb`: data checks, calculations and figure exports.
- `Schiphol_Project_Report.ipynb`: written report, including the AI disclosure at the end.
- `Schiphol_Project_Report_pdf.pdf`: final readable report export; regenerate after later report changes.
- `data/`: supplied source files. The analysis uses the Schiphol Excel file and OWID CSV. `COVID-19_uitgevoerde_testen.csv` is not used by this pipeline.
- `figure/`: 15 PNG images used in the report: 13 numbered chart images and two table images. No duplicate category chart or unused image is required.
- `results/`: seven CSV summaries: period-level seasonality, annual seasonal strength, passenger-group recovery, recovery-window sensitivity, baseline sensitivity, leave-one-month-out correlation sensitivity for 2022, and correlations using raw totals/recovery indices with zero-, one- and two-month lags.

## Sources

- Royal Schiphol Group, [Traffic and transport figures](https://www.schiphol.nl/en/schiphol-group/transport-and-traffic-statistics/), local file `data/Monthly_traffic_data_1992-current-2.xlsx`.
- Our World in Data, [Daily new confirmed COVID-19 cases per million people](https://ourworldindata.org/grapher/new-covid-cases-per-million), local file `data/daily-new-confirmed-covid-19-cases-per-million-people.csv`.

Source pages accessed 6 November 2026. Original snapshot download dates are not recorded. No newer input data were substituted during final checking.

## Authors and contributions

- **Jouairia Azzouzi:** Wrote Sections 4.1 and 4.2.
- **Juliette Folkers:** Conducted the analyses, excluding the seasonality analysis.
- **Eline Landman:** Conducted the seasonality analysis.
- **Noud Reijn:** Conducted the analyses, excluding the seasonality analysis.
- **Beria Karabocek:** Conducted and analysed Section 4.3 on passenger group differences.

## Generative AI

All group members used ChatGPT. Noud Reijn also used Codex for report feedback, language and structure, code debugging/refactoring, supporting calculations (including lag comparisons, recovery-window checks and annual seasonal summaries) and exports. See the disclosure at the end of the report for the scope and responsibility statement.

## Additional methods and interpretation

The extensions use the existing pandas, NumPy and Matplotlib dependencies. No extra statistical package is required. A lag pairs cases in month t-lag with passengers in month t. Within-year comparisons stay inside each calendar year. The number of pairs decreases with lag, so differences are exploratory and cannot be interpreted as causal effects. Recovery dates denote the start of the first qualifying run. Comparisons of three versus six months show that recovery rankings depend on the selected definition. The annual seasonality line is a descriptive fit, not a significance test.
