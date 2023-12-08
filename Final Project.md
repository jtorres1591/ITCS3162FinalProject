**Introduction**

For this project we would be trying to divide a list of Pokemon into tiers based on how high their base stats are. Across the Generations, there have usually been cases of more Pokemon being introduced with higher base stat totals, we wanted to see if this was true, or if it was true for any other category. We will be using clustering, seperating them by base stats. They will then be grouped up by generations. The main question for this project is “Which Generation has the highest average base stat total?”  

**About the Data**

The dataset was obtained from Kaggle and is titled “Pokemon Stats” by Ulrik Thyge Pedersen. This dataset is 60KB, has 13 columns and 1072 entries. The usability of the data is at 10. This dataset accounts for all Pokemon up to Pokemon Sword and Shield’s Expansion Pass (The other entries are for all alternate forms, such as regional variants, Megas, Gigantamax, gender, and other alternate forms). The 13 features include the Pokedex number, Name, two Types, six Base Stats, Base Stat total, Generation, and whether the Pokemon is a Legendary. 

**Methods**

- Pre-processing; To ensure the quality of the data, we took some steps of preprocessing. The first pre-processing step we did was get 
  the info of the data we found. This was important to gain insights into the nature of the variables and identify any potential 
  discrepancies.
  The next step was to check for any missing values, as addressing these gaps in the data is crucial for effective clustering analysis. 
  Missing values can introduce bias and distort the similarity metrics essential for clustering algorithms, potentially leading to 
  inaccurate groupings and undermining the reliability of the entire clustering process. To handle these missing values, we replaced 
  them by assigning the string 'None' to the respective column.
  The last step we did is to check for any duplicate rows. We found none. With that, we cleaned the data and are ready to visualize the 
  data to further understand it.

- Visualizations (If necessary)
  
  **Modeling 1 ( K-means)**
  
    In the modeling section, the goal was to categorize a list of Pokémon into tiers based on their total base stats, using two 
    clustering algorithms, k-means and hierarchical clustering.  
    The process began by extracting the 'total' column from the dataset, which represents the cumulative base stats of each Pokémon. 
     To determine the optimal number of clusters (k), the elbow method was employed. The sum of squared distances between data points 
     and 
     their assigned cluster centers (inertia) was calculated for various values of k, and the results were visualized through an elbow 
      method graph. 
     Based on the analysis, a suitable value of k was chosen—in this case, three clusters (tiers). The k-means algorithm was then 
     applied to the 'total' column, and the resulting clusters were visualized using a scatter plot with color-coded tiers. 
    Additionally, the cluster centers were marked on the plot. To further refine the tier assignment, percentile thresholds were 
     calculated, and Pokémon were categorized into three tiers (Tier 1, Tier 2, and Tier 3) based on their total base stats. 
    A countplot was generated to illustrate the distribution of Pokémon across these tiers, providing a comprehensive overview of the 
     clustering results. 
    Finally, the count of Pokémon in each tier was displayed to summarize the tier distribution within the dataset.

**Modeling 2 (Hierarchy Clustering)**

    In search of improving the Silhouette Score (we’ll be covered more in evaluation), we employed an alternative clustering model, 
    specifically the hierarchical clustering algorithm.Similar to the k-means approach, the hierarchical clustering method involved 
    utilizing the same tier assignment methodology based on percentiles of the 'total' base stats.


**Evaluation**

- Evaluation 1
  
The evaluation of the k-means clustering model was performed using the Silhouette Score. The Silhouette Score measures the compactness and separation of clusters, with values ranging from -1 to 1. A higher Silhouette Score indicates better-defined clusters, where data points within a cluster are more similar to each other than to those in other clusters. In this case, the score of 0.616 suggests that the clusters formed by the k-means algorithm are distinct and well-separated, validating the effectiveness of the clustering process. However, we wanted to see if we can improve this even more so we used Hierarchy clustering to see how the model functions.

- Evaluation 2
  
After assessing the hierarchical clustering model, we found that it performed better than the k-means approach, as indicated by a higher Silhouette Score of 0.898. This score suggests that the hierarchical clustering method created more distinct and internally cohesive groups for Pokémon based on their total base stats. Which means, that Pokémon within the same tier are more similar to each other and different from those in other tiers


**Storytelling and Conclusion**
  Pokemon is a very popular game and its name is recognized by almost everyone. Pokemon Stats are of great interest to many fans of this game. The strength of the species is known as base stats and these base stats are important  in determining the power and potential the species has in a battle. A species’s base stats ranges from 1 to 255. A lot of people claim that a common pattern in Pokemon is species which have a higher evolutionary stage will have higher base stats. We know that there are exceptions like Scizor and Klevor but we want to see if the pattern of species belonging to a higher evolutionary stage have higher base stats. We are using clustering models to analyze the base stats because we feel this information can be useful to players of Pokemon, especially new players of Pokemon. In order to play the game well, a player needs to know how the base stats values of each species are assigned.
One thing that we noted while looking at the base stats of Pokemon is that species from different branches with a split evolutionary line often times have similar base stats. Another interesting thing that we noted is that Pokemon with very high base stats are often times  banned from battle facilities. Our modeling and evaluation shows that species which have a higher evoluntionary stage indeed do have higher base stats. Both of the models- K-means model and hierarchical clustering model show that the higher base stats are strongly correlated with the Pokemon species being placed higher on the evolution stages. Generation 8 has the highest base stats.

**Impact Section**

  A positive impact from this project is that it can be used to understand the different pokemon from each generations. Maybe it can help beginners or even veteran players see that each generation pokemons were not made equally as the total base stats are different from each other. A negative impact from this is that pokemon is just a game and you can really just make your team the way you want. It doesn't really matter if one generation is stronger then the next or vice versa. Another positive impact is that people can use this information from our project to improve their gaming skills when their playing Pokemon the next time. People who play Pokemon on a regular basis can look at our project and now have more knowledge and insights about how the species work in Pokemon and how their base stats are assigned. This project might help them learn new things about the game they didn't notice or pay attention to before. 
