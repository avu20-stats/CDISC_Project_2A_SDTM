# CDISC SDTM Creation & Validation - Project 2-A

Transforms raw CRF data from study **CMP135** into 5 SDTM domains (DM, EX, MH, DS, VS) using R, and validates the output against gold-standard reference XPT files.

## Project Structure

```
crfdata/                        # Raw CRF source datasets (SAS .sas7bdat / .xpt)
SDTM Data for Validation/       # Reference SDTM XPT files for validation
Project 2-A.R                   # Main R script (all steps + validation)
Project 2-A.Rmd                 # R Markdown version (knits to HTML)
Project-2-A.html                # Compiled report
```

## SDTM Domains

| Domain | Description |
|---|---|
| **DM** | Demographics - subject-level data, arm assignment, investigator info |
| **EX** | Exposure - dosing records with ISO 8601 datetime and study day |
| **MH** | Medical History - MedDRA-coded terms (LLT → SOC) |
| **DS** | Disposition - informed consent, completion, discontinuation |
| **VS** | Vital Signs - TEMP, RESP, HR, WEIGHT, HEIGHT, SYSBP, DIABP |

## Usage

Open and run `Project 2-A.R` in RStudio, or knit `Project 2-A.Rmd` to regenerate the report. Derived domains are compared against the validation XPT files using `identical()`, `all.equal()`, and `anti_join()`.

## Requirements

R packages: **dplyr**, **lubridate**, **stringr**, **haven**
