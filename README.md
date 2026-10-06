# ACCREU_Labour_Productivity_Shock_Dataset
This public folder contains country-level datasets describing projected labour productivity losses associated with temperature-related heat and cold exposure. The datasets provide productivity shocks by country, year, climate scenario, quantile, and adaptation scenario.

**Author:** Francesco Colelli, CMCC Foundation ([francesco.colelli@cmcc.it](mailto:francesco.colelli@cmcc.it))
**Produced within:** ACCREU (Assessing Climate Change Risk in EUrope), Horizon Europe
**Version:** 1.0 (2026)

**Public Accelerator folder:** [View ACCREU dataset files](links.html)

## Summary

This dataset contains projected **labour productivity losses** due to temperature-related heat and cold exposure. Shocks are provided by country, year, climate scenario, quantile and adaptation scenario, separately for **high-exposure** and **low-exposure** sectors, with and without adaptation. A regional aggregation for EU NUTS2 regions is also provided for macroeconomic modelling.

The dataset supports analysis of climate impacts on labour productivity at country (ISO3) and EU regional level. It was produced by the CMCC Foundation in the context of the ACCREU project.

## Citation

> Colelli, Francesco. (2026). *Labour Productivity Shock Dataset* (Version 1.0). Zenodo. https://doi.org/10.5281/zenodo.XXXXXXX

## License

- **Data:** This dataset is licensed under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.

## Repository Contents (Metadata only)

This GitHub repository hosts **only** the metadata (this README and the data access page). The data files reside on the IIASA Accelerator platform (see link above).

## Folder Structure (on Accelerator)

```text
CMCC_lab_prod/
├─ lab_prod_shock_ISO3.csv
├─ lab_prod_shock_ISO3_cdd18_cooling.csv
├─ lab_prod_shock_ISO3_hdd18_heating.csv
└─ model_specific_aggregation/
   └─ lab_prod_shock_macromethod_eu_nuts2.csv
```

---

# Dataset Documentation

## 1. Files

| File | Content |
|---|---|
| `lab_prod_shock_ISO3.csv` | Total labour productivity shock by country (heat and cold exposure) |
| `lab_prod_shock_ISO3_cdd18_cooling.csv` | Shock from **heat** exposure only, based on cooling degree days above 18 °C (CDD18) |
| `lab_prod_shock_ISO3_hdd18_heating.csv` | Shock from **cold** exposure only, based on heating degree days below 18 °C (HDD18) |
| `model_specific_aggregation/lab_prod_shock_macromethod_eu_nuts2.csv` | Shock aggregated to EU NUTS2 regions, formatted for macroeconomic modelling |

<!-- TO CONFIRM: is lab_prod_shock_ISO3.csv the combined heat + cold shock? Add the column list of the NUTS2 file. -->

## 2. Variables (ISO3 files)

| Column | Description |
|---|---|
| `ISO3` | ISO 3166-1 alpha-3 country code |
| `country` | Country name |
| `year` | Year of the estimate |
| `rcp` | Climate scenario (Representative Concentration Pathway) |
| `quantile` | Quantile of the estimate distribution (uncertainty range) |
| `ada_scenario` | Adaptation scenario |
| `productivity_%_loss_highexp` | % labour productivity loss, **high-exposure** sectors |
| `productivity_%_loss_lowexp_noada` | % labour productivity loss, **low-exposure** sectors, **without** adaptation |
| `productivity_%_loss_lowexp_ada` | % labour productivity loss, **low-exposure** sectors, **with** adaptation |

## 3. Definitions

| Term | Definition |
|---|---|
| **High-exposure sectors** | Outdoor or physically intensive work: agriculture, forestry, construction and mining. |
| **Low-exposure sectors** | Manufacturing, industry and services not included in the high-exposure sectors. |
| **Adaptation** | Measures that reduce exposure in low-exposure sectors (e.g. indoor cooling), as defined by `ada_scenario`. |
| **CDD18 / HDD18** | Cooling / heating degree days computed against an 18 °C threshold, capturing heat and cold exposure respectively. |

All `productivity_%_loss_*` values are **percentage losses** in labour productivity.

The **effect of adaptation** in low-exposure sectors is:

```text
productivity_%_loss_lowexp_noada − productivity_%_loss_lowexp_ada
```

---

## Notes for Users

- Always keep the `rcp`, `quantile` and `ada_scenario` dimensions when comparing countries or years. Mixing them leads to inconsistent comparisons.
- Percentage losses **cannot be summed** across countries. To aggregate to regions, weight them (e.g. by employment or value added in the corresponding sectors).
- The underlying climate data, exposure-response functions, quantiles and adaptation scenarios are documented in the associated ACCREU deliverables.

## Contact

Francesco Colelli, CMCC Foundation, [francesco.colelli@cmcc.it](mailto:francesco.colelli@cmcc.it)

## Funding Acknowledgement

This work was supported by the **Assessing Climate Change Risk in Europe (ACCREU)** project, funded by the European Commission under the **Horizon Europe** programme (grant agreement No. 101081358).

**Project website:** [ACCREU Website](https://www.accreu.eu/)
