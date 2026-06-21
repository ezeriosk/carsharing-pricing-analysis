# Upfront Pricing Precision in Carsharing

An end-to-end product analytics case study investigating why the price shown to a rider before a trip can differ from the final metered price.

The project combines data preparation, exploratory analysis, segmentation and stakeholder communication. It analyzes **2,875 orders** and translates the findings into concrete product and modeling recommendations.

## Business question

Upfront prices depend on predicted distance and duration. When those estimates are inaccurate, customers may see a different final price, affecting trust and potentially increasing support contacts.

This analysis asks:

- How large and frequent are upfront-pricing deviations?
- Which operational, geographic and technical factors are associated with larger gaps?
- What changes could improve pricing precision?

## Executive summary

- The average gap between predicted and metered prices was **24%**.
- **38%** of orders ended with a higher metered price than initially predicted.
- **44%** of orders experienced a price change, while **3%** had an overpricing-related complaint.
- Poor GPS confidence was present in roughly **8%** of orders and was associated with a **55%** average price variation, compared with **21%** for orders with good GPS confidence.
- Non-European orders showed an average price variation approximately **three times higher** than European orders.
- Older and newly released app versions showed specific patterns worth further investigation.

These findings suggest that pricing precision is primarily a prediction and data-quality problem rather than a demand-timing problem.

## Recommendations

1. Add GPS-confidence signals to the pricing model and monitor them as a quality feature.
2. Improve duration and distance estimation for low-confidence trips.
3. Separate or recalibrate models for European and non-European markets.
4. Investigate regressions across Android and iOS app versions.
5. Track pricing precision, price changes and complaints in a centralized monitoring dashboard.

## Deliverables

- [Full analysis notebook](./Upfront%20pricing%20precision.ipynb)
- [Executive presentation](./Analysis%20Presentation.pdf)

The notebook contains the complete workflow and saved outputs. The presentation summarizes the business problem, main findings and proposed action plan.

## Analytical workflow

1. Assessed data quality, missing values, duplicates and field distributions.
2. Consolidated multiple attempts and support tickets at order level.
3. Built price, distance and duration deviation metrics.
4. Analyzed patterns across time, GPS confidence, geography, app version and device.
5. Evaluated limitations and translated findings into product recommendations.

## Technology

Python, pandas, NumPy, Matplotlib, Seaborn and Jupyter Notebook.

## Repository structure

```text
.
├── Analysis Presentation.pdf
├── Data/
│   └── README.md
├── Upfront pricing precision.ipynb
├── requirements.txt
└── README.md
```

## Running the notebook

```bash
git clone https://github.com/ezeriosk/carsharing-pricing-analysis.git
cd carsharing-pricing-analysis
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook "Upfront pricing precision.ipynb"
```

The original dataset is not included. Place an authorized compatible file at `Data/Test.csv` to rerun the notebook. Saved notebook outputs remain available for reviewing the analysis without the source data.

## Limitations

- The dataset represents a limited observation window and does not establish causality.
- Some segments have small samples and are explicitly treated as directional.
- Reproduction requires an equivalent authorized dataset with the documented schema.

## About

Created by [Ezequiel Rios Kaliman](https://www.linkedin.com/in/ezequiel-rioskaliman/) as a product and business analytics portfolio project.
