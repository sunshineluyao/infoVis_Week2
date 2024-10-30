# Analysis of Data Abstraction Techniques in "Deciphering Bitcoin Blockchain Data by Cohort Analysis"

As a professor specializing in data visualization and computer vision, I will analyze the data abstraction techniques in the paper, **"Deciphering Bitcoin Blockchain Data by Cohort Analysis"**, by Liu, Zhang, and Zhao. The focus is on how effectively the authors identified, categorized, and transformed raw data elements for visualization purposes.

## Data Abstraction Overview
The authors use data abstraction to distill raw blockchain data into cohort-based datasets, enabling efficient querying and visualization. They apply cohort analysis, traditionally used in population studies, to Bitcoin's UTXO (Unspent Transaction Output) and STXO (Spent Transaction Output) data. This abstraction allows for interpreting blockchain data in terms of "birth" and "death" events of UTXOs, creating meaningful cohorts for longitudinal analysis.

### Data Types and Structures
In this study, the authors consider several critical data types:
- **Items:** UTXOs and STXOs, representing transactions in Bitcoin.
- **Attributes:** Attributes like age, lifespan, and value of UTXOs and STXOs.
- **Links:** Links between nodes (transactions) are implicit, based on the flow of UTXOs between transaction inputs and outputs.
  
The authors organize this data within **tables**—a format suitable for time series analysis and efficient partitioning in Google BigQuery. This choice enhances computational feasibility given the size of Bitcoin’s transaction history, which spans billions of records.

### Data and Dataset Types
The authors employ specific data representations:
- **Tables:** Structured with columns representing key attributes (e.g., timestamp, UTXO value).
- **Clusters and Sets:** Daily cohorts of UTXOs and STXOs form clusters categorized by creation and spend dates, allowing for grouped analysis of transaction outputs.
  
This abstraction supports their cohort-based approach, where the birth (creation) and death (spending) of UTXOs represent distinct cohorts. The paper demonstrates the utility of cohort analysis by generating visualizations like the lifespan distribution of STXOs and age distribution of UTXOs, reflecting the data’s temporal dynamics.

### Dataset Availability and Dynamics
The authors distinguish between static and dynamic data types:
- **Static Data:** Historical UTXO and STXO data that remains unchanged.
- **Dynamic Data:** The dataset’s time series structure, updated as new Bitcoin transactions occur, requiring a scalable and modular abstraction approach.
  
They use partitioned tables, which segment data by timestamps, enabling efficient access to daily cohorts. This technique aligns well with BigQuery’s infrastructure, reducing query cost and time. Additionally, this dynamic structure enables regular updates to cohort data, facilitating ongoing time series visualization.

## Effectiveness of Data Abstraction
The abstraction methods applied in this study are effective, as they:
1. **Optimize Data Volume Management:** Partitioning and cohorting allow the handling of large datasets in a computationally feasible way.
2. **Facilitate Meaningful Insights:** By creating visualizations of age and lifespan distributions, the authors effectively demonstrate Bitcoin’s functionality as a store of value and medium of exchange.
3. **Enable Reproducibility and Extension:** The methods are adaptable to other UTXO-based blockchains, broadening the study’s relevance.

### Suggested Alternative Approaches
While effective, the study could further enhance its abstraction by:
1. **Applying Network Analysis:** Explicitly mapping UTXO and STXO flows could enrich the understanding of transactional relationships.
2. **Incorporating Spatial Geometry:** If UTXOs were spatially linked to specific wallets or regions, spatial analysis could add a valuable dimension to the data.

In summary, the authors’ data abstraction techniques successfully support the visualization and analysis of Bitcoin transaction data. Their approach makes blockchain data accessible for economic insights while enabling modular updates and broader applicability to similar blockchain structures.

