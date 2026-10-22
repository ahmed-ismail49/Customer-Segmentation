# Customer Segmentation using Machine Learning

## Project Overview
This project applies unsupervised machine learning techniques to segment customers of an online retail business based on their purchasing behavior. The goal is to identify meaningful customer groups that can support data-driven business and marketing decisions.

## Dataset
The project uses the Online Retail dataset, which contains transaction records such as invoice numbers, product information, quantities, invoice dates, unit prices, customer IDs, and countries.

## Tools and Technologies
- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Workflow
1. **Data Exploration:** Inspected the dataset, missing values, duplicates, cancelled invoices, and invalid transactions.
2. **Data Cleaning:** Removed cancelled invoices, records without CustomerID, non-positive quantities, and non-positive unit prices.
3. **Feature Engineering:** Calculated customer-level RFM metrics:
   - Recency: Days since the customer's last purchase.
   - Frequency: Number of distinct invoices per customer.
   - Monetary: Total purchase value.
4. **Data Preparation:** Applied log transformation and feature scaling to prepare the RFM features for clustering.
5. **K-Means Clustering:** Tested cluster counts from 2 to 8 and evaluated the results using inertia and silhouette scores.
6. **DBSCAN Clustering:** Explored density-based clustering and identified noise points.
7. **Cluster Evaluation:** Compared clustering results and examined customer segment profiles.
8. **Export:** Prepared a customer segmentation CSV file with CustomerID and recommended segment labels.

## Results
### K-Means
- Selected number of clusters: 3
- Best tested silhouette score: approximately 0.4156
- Segment sizes: 2,036; 1,323; and 979 customers

### DBSCAN
- Parameters: eps = 0.5, min_samples = 5
- Number of clusters: 2 (excluding noise)
- Noise proportion: approximately 1.1%
- Silhouette score: approximately 0.3269

K-Means achieved the higher silhouette score among these tested configurations. DBSCAN provided a density-based comparison and identified a small proportion of noise points.

## Customer Segments
The three K-Means segments were profiled using their median RFM values to understand differences in purchase recency, frequency, and monetary value. Business actions can then be proposed based on observed purchasing behavior rather than unsupported assumptions about customers.

## Output
- `customer_segments.csv` — customer IDs and their assigned segment labels.
- Jupyter Notebook — data cleaning, feature engineering, clustering, and evaluation.

## How to Run
1. Clone or download this repository.
2. Install the required libraries:
   `pip install pandas numpy matplotlib seaborn scikit-learn jupyter`
3. Open the Jupyter Notebook.
4. Make sure the Online Retail dataset is available at the file path specified in the notebook.
5. Run the notebook cells in order.

## Key Learning Outcomes
- Data cleaning and exploratory data analysis.
- RFM feature engineering.
- Feature transformation and scaling.
- K-Means and DBSCAN clustering.
- Model evaluation using silhouette scores.
- Customer segmentation and data-driven business recommendations.

## Disclaimer
This is an analytical machine learning project. The customer segments and recommendations are based on historical transaction data; their actual business impact has not been experimentally measured.

## Author
Ahmed Ismail
