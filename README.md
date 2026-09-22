# Index Integrity — Deflation, Substitution Bias & Goodhart

## Objective

This project develops and validates an index-integrity workflow for converting nominal data into constant dollars, quantifying substitution bias across consumer price indexes, and detecting metric gaming through changes in KPI relationships.

## Methodology

* Diagnosed and corrected four errors in a deflation pipeline, including misaligned dates, missing-value handling, an incorrect CPI base, and output expressed in 1982–84 dollars but labelled as 2020 dollars.
* Converted nominal wages into constant 2020 dollars using the average CPI for the base year.
* Normalized CPI-U and Chained CPI-U to a common December 1999 base and calculated their compound annual inflation rates.
* Distinguished the cumulative index-point gap from the annual percentage-point difference in inflation rates.
* Measured the correlation between DAU/MAU and time per session separately during organic-growth and gaming phases.
* Packaged the validated `deflate_series()` function in a reusable and tested `deflation_utils.py` module.
* Built an interactive index-integrity monitor with CPI controls, a rolling-correlation window, visualizations, and a Goodhart’s Law alert.

## Key Findings

CPI-U increased at an annualized rate of 2.61%, compared with 2.35% for C-CPI-U, producing an estimated upper-level substitution bias of 0.27 percentage points per year. The corresponding gap of 0.50 index points per year is different because index points measure changes in the normalized index level, whereas percentage points compare compound annual inflation rates. The relationship between DAU/MAU and time per session also changed sharply: their correlation moved from approximately +0.93 during organic growth to −0.96 during the gaming phase. This reversal indicates that the primary engagement metric improved while the counter-metric deteriorated, providing evidence consistent with Goodhart’s Law.

