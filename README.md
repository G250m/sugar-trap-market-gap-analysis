The "Sugar Trap" Market Gap Analysis

Client: Helix CPG Partners
Project Type: Market Gap & Product Strategy Analysis
Tools Used: Python (Pandas), Google Colab, Tableau Public

A. Executive Summary

This analysis examined 44,140 food products from the Open Food Facts dataset to identify underserved opportunities in the “Healthy Snacking” market. A Nutrient Matrix comparing sugar and protein content revealed a clear white-space opportunity in the Snacks category. Although Snacks account for over 5,000 products, only 6.8% meet high-protein (>10g) and low-sugar (<5g) criteria. Products in this quadrant cluster around 16–20g of protein and under 4g of sugar per 100g, indicating a strong formulation benchmark for new product development.

Based on the data, the biggest market opportunity is in Snacks, specifically targeting products with 16–20g of protein and less than 4g of sugar per 100g.

B. Project Links

Notebook (Google Colab):
🔗 [Insert Colab Share Link Here — set to “Anyone with link can view”]

Interactive Dashboard (Tableau Public):
🔗 [Insert Tableau Public Link Here — must be publicly accessible]

Presentation Deck (PDF/PPT):
🔗 [Insert Google Drive / OneDrive Link Here — set to “Anyone with link can view”]


C. Technical Explanation
1. Data Ingestion & Cleaning (Story 1)

The Open Food Facts dataset exceeds 3GB in raw size. To ensure efficiency and reproducibility, a manageable subset was processed using chunked loading in Google Colab.

Cleaning Steps

Selected only required columns:

product_name

categories_tags

sugars_100g

proteins_100g

ingredients_text

Converted nutritional columns to numeric using:

pd.to_numeric(errors="coerce")

Removed rows missing:

product_name

sugars_100g

proteins_100g

Filtered biologically impossible values:

Nutritional values constrained between 0–100g per 100g

These steps ensured that erroneous entries and invalid nutritional data did not skew the analysis.

Deliverable: Cleaned Pandas DataFrame exported for visualization.

2. Category Engineering (Story 2)

The categories_tags column contains thousands of comma-separated product tags. To make the analysis business-readable:

Parsed the first category tag per product.

Applied keyword-based mapping rules.

Assigned each product to a simplified Primary Category.

High-level buckets created include:

Snacks

Beverages

Dairy

Meat & Seafood

Condiments & Sauces

Desserts

Frozen Foods

Cereals & Breakfast

Plant-Based Foods

Prepared Meals

Other

This reduced categorical noise and enabled strategic category-level comparison.

3. Nutrient Matrix Visualization (Story 3)

A scatter plot was developed in Tableau Public with:

X-axis: Sugar (g per 100g)

Y-axis: Protein (g per 100g)

Color: Primary Category

Interactive filter: Primary Category

Reference lines were added at:

Protein = 10g

Sugar = 5g

This clearly identified the High Protein + Low Sugar quadrant, representing the strategic “Blue Ocean.”

4. Recommendation (Story 4)

Based on the data, the biggest market opportunity is in Snacks, specifically targeting products with 16–20g of protein and less than 4g of sugar per 100g.

Although Snacks account for over 5,000 products, only 6.8% meet high-protein and low-sugar criteria, indicating significant whitespace opportunity in this segment.

5. Bonus Story – Hidden Gem (Ingredient Analysis)

Products within the High Protein + Low Sugar cluster were filtered and analyzed using the ingredients_text column.

Keyword frequency analysis revealed the top protein sources among successful products:

Soy (21 occurrences)

Whey (15 occurrences)

Oat (5 occurrences)

This insight provides actionable guidance for R&D teams when formulating competitive high-protein snack products.

6. Candidate’s Choice – Opportunity Density Metric

An additional metric called Opportunity Density (%) was introduced.

This metric calculates the percentage of products within each category that meet High Protein + Low Sugar criteria.

Why this adds value:

Quantifies whitespace numerically

Allows category comparison beyond visual inspection

Supports strategic prioritization

Strengthens the business case for category selection

This enhances the dashboard by providing measurable market saturation insight.

Submission Checklist Confirmation
Repository & Code

✔ Public GitHub repository
✔ .ipynb notebook uploaded
✔ HTML or PDF export uploaded
✔ Raw dataset (3GB file) NOT uploaded
✔ Code uses relative paths

Deliverables

✔ Public Tableau dashboard link
✔ Public presentation deck link
✔ README updated with executive summary and technical explanation

Completeness

✔ Stories 1–4 completed
✔ Candidate’s Choice implemented and explained
✔ Hidden Gem analysis completed

Conclusion

This project demonstrates the ability to:

Process large-scale real-world datasets efficiently

Clean and structure messy nutritional data

Engineer business-level product categories

Identify market whitespace using quantitative analysis

Translate data findings into actionable product strategy

The analysis provides a data-backed roadmap for launching a high-protein, low-sugar snack product in an underserved segment of the market.
