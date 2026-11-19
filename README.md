# Factors Associated with Police Officer Injury: Exploratory Data Analysis in R

Do police division, month and officer gender relate to how often officers are injured during use-of-force incidents? This is a descriptive analysis of 2,383 use-of-force records from 2016, each with officer, subject, location and force-type details (47 fields).

University of Essex, M.Sc. Data Science coursework 1 (exploratory data analysis and visualisation). Individual work.

**Data.** The records were downloaded from Kaggle (the report names the folder `Dept37-0049`). Every record has `LOCATION_CITY = Dallas` and `LOCATION_STATE = TX`, and the seven divisions (Central, North Central, Northeast, Northwest, South Central, Southeast, Southwest) are Dallas Police Department divisions. The report text refers to the UK; the data are from Dallas, Texas.

## What the analysis shows

Running the report code on `dataset.csv` gives these results, which match the figures quoted in the report:

| Officer gender | Not injured | Injured |
|---|---:|---:|
| Female | 209 | 31 |
| Male | 1,940 | 203 |

As shares of all records, injured male officers make up 8.5% and injured female officers 1.3%. That gap mostly reflects the size of the workforce. Within each group, the injury rates are similar: 12.9% for female officers and 9.5% for male officers.

| Division | Records | Injured | Injury rate |
|---|---:|---:|---:|
| Central | 563 | 56 | 9.9% |
| Southeast | 362 | 29 | 8.0% |
| Northeast | 341 | 38 | 11.1% |
| North Central | 319 | 16 | 5.0% |
| South Central | 310 | 22 | 7.1% |
| Southwest | 297 | 45 | 15.2% |
| Northwest | 191 | 28 | 14.7% |

Central has the most injuries in absolute terms. Southwest and Northwest have the highest injury rates per incident. The report also plots injuries by month.

## Repository contents

| File | Description |
|---|---|
| `Course_work_1.Rmd` | Original R Markdown report (reads the data from `C:/Users/HP/Desktop/dataset.csv`) |
| `Course_work_1_reproducible.Rmd` | Identical except that it reads `dataset.csv` from this folder |
| `Course_work_1.docx` | Rendered report |
| `dataset.xltx` | Original dataset, saved as an Excel template |
| `dataset.csv` | Same data exported to CSV, as the report code expects (both header rows kept, since the code drops the second) |

## Reproducing

```r
install.packages(c("rmarkdown", "ggplot2", "breakDown"))
rmarkdown::render("Course_work_1_reproducible.Rmd")
```

Only base R graphics and tables are used in the active code. `ggplot2` and `breakDown` are loaded, but the lines that would use them are commented out.
