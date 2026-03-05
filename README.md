# Graph-Based Movie Recommender System: A Bipartite Network Analysis

##  Overview
This project leverages graph theory to build robust movie recommendation engines using user interaction data scraped from Letterboxd. By modeling users and movies as a bipartite network, the project compares traditional item-item collaborative filtering (Unipartite) against multi-hop network traversals (Bipartite) to generate highly personalized recommendations.

## Dataset
* Data was sourced from Letterboxd, focusing on a dense sub-network of "power users" and highly reviewed films.
* **Nodes:** 1,483 Users | 503 Movies
* **Edges:** 13,719 total interactions (network density optimized for efficient analysis).

##  Methodology & Architecture
1. **Network Construction (Task B):** Built a sparse, highly connected bipartite graph mapping users to the movies they have reviewed. 
2. **Recommender Systems (Task C):**
   * **Unipartite Model:** Projected the graph into an Item-Item network to recommend movies based on shared audience weight (capturing broad popularity and genre trends).
   * **Bipartite Model:** Implemented a multi-hop diffusion algorithm (User $\rightarrow$ Movie $\rightarrow$ Similar User $\rightarrow$ New Movie) with degree normalization to surface niche, serendipitous recommendations and penalize generic blockbusters.
3. **Community Detection (Task D):**
   Extracted distinct viewing communities (e.g., "Gritty Thrillers", "Marvel Cinematic Universe") to segment audiences and enhance recommendation context.

## Key Insights
* The **Unipartite model** excels at identifying massive pop-culture overlaps (e.g., linking *Star Wars* to *Marvel*).
* The **Bipartite model** successfully combats popularity bias, identifying tighter user-taste clusters to recommend "hidden gems" (e.g., matching niche psychological thrillers).


##  Tech Stack
* **Python:** pandas, standard libraries (`random`, `pickle`)
* **Network Analysis:** NetworkX, `networkx.algorithms.bipartite`
* **Visualization:** Matplotlib
