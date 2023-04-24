# HOLLYWOOD ELITISM
Sna2 Final Project - Mia K. Bellemare, Angie Zarich, Tara rafaty and Kanami Konishi

## Introduction


## Hypotheses
🔍 Actors in high rated films are more likely to be featured in other top rated films, due to their personal connections in the industry
🔍 Strength of weak ties, small world problem


## Methodology



Our code can be seen [here](https://colab.research.google.com/drive/1YjDicn5V7WQIe2QNg8_8qkkFQl55XCPD?usp=sharing)

## Results
<img width="517" alt="python graph" src="https://user-images.githubusercontent.com/130977477/233947068-0ed112a9-66a2-485d-a487-97da305fc199.png">
Organizing the clusters.


<img width="477" alt="graph 3 " src="https://user-images.githubusercontent.com/130977477/233955116-1489ee2e-a14d-48ac-a2e9-e6e3937511ae.png">
Relationship between Node degree and Betweennes Centrality


## Analysis
The aim of our research was to explore whether top rated actors are the most well connected in the film industry. To do this we looked at the top 50 rated films on IMDb, based on the number of votes, released between 2010/01/01 and 2019/12/31. Each film consists of a list of 4 or 5 “stars”, who serve as the lead actors, and thus from the data we extracted their names to construct the nodes of our network. Each node is connected through a movie title, serving as the edge of the network. 

### General results 
<img width="223" alt="graph 2 " src="https://user-images.githubusercontent.com/130977477/233947603-4c526193-3192-4d58-af71-bdd19e2789bc.png">
First of all from the visualization of the social network, we were able to analyze the overall structure of the industry. As the graph shows, there is one prominent cluster, which consists of most of the actors in the network. From this we can understand that in general, actors from top rated movies are connected with one another through a large network, although the diameter of the clustered network identifies that those ties may not be strong. This contradicts with the “six degrees of separation"[^1]. theory which suggests that any two individuals in the world can be connected through a network of no more than six intermediaries. One reason that could lead to this result is the fact that the interaction between actors is not very fluid; it takes an average of 4 to 5 years to produce 1 film. Thus considering how the data we scraped was only from a span of 10 years, we can predict that actors did not have enough time to appear in many films, which would explain why many of them are not strongly tied with one another. 

 On the other hand, the other actors that do not belong to that cluster are mostly only connected to actors that they filmed the same movie with. However it is not necessarily the case that those actors are from the films rated very low in the list. For example, although the actors are isolated from the others, films such as “Deadpool” (2016) and "Intouchables” (2011) are respectively ranked 12th and 20th, which is not a low rank out of 50. This could be because the social network of actors is not a homogeneous group, and there may be subgroups or clusters within the network that are more tightly connected than others. In the case of "Intouchables,” it is a French produced film, making it less likely for its actors to be connected with other mainstream Hollywood actors. Yet it is true that actors that starred in any movie above rank 11, belong in the large clustered network, indicating the possibility of actors in high rated films to be more likely to be featured in other top rated films due to their personal connections within the industry. 
 
 [^1]:Watts, D. J., & Strogatz, S. H. (1998). Collective dynamics of "small-world" networks. Nature, 393(6684), 440-442. [Link](https://drive.google.com/file/d/16S35ZnSkVf6FwNbc-yzeQ9QHNerguISo/view?usp=sharing) .
 
 
 
 ### Some Specific Actors and betweennes centrality
👤_Leonardo DiCaprio:_ 
- Degree Centrality: 0.116 HIGHEST 
- Betweenness Centrality: 0.15300935623516262
- Clustering Coefficient: 0.137
- Films starred in: 1. Inception 5. Wolf of Wall Street 7. Shutter Island 32. The Revenan 39. Once Upon a Time...in Hollywood

👤 _Chris Evans:_
- Degree Centrality: 0.090
- Betweenness Centrality: 0.05281385281385282
- Clustering Coefficient: 0.26373626373626374
- Films starred in:6. Avengers Assemble 10. Avengers Endgame 11. Avengers Infinity War  19. Avengers: Age of Ultron 24. Captain America: The Winter Soldier 25. Captain Amercia: The First Avenger 33. Captain America: Civil War 46. Knives Out

👤 _Robert Downey Jr.:_
- Degree Centrality: 0.07096774193548387
- Betweenness Centrality: 0.04203323558162264
- Clustering Coefficient: 0.327
- Films starred in: 6. Avengers Assemble 10. Avengers Endgame  11. Avengers: Infinity War  19. Avengers: Age of Ultron
  22. Iron Man 3 31. Iron Man 2 33. Captain Amercia: Civil War

👤 _Matthew McConaughey:_
- Degree Centrality: 0.04516129032258064
- Betweenness Centrality: 0.02787320206675043
- Clustering Coefficient: 0.42857142857142855
- Films starred in: 2. Interstellar 5. The Wolf of Wall Street  35. The Imitation Game

Leonardo DiCaprio has the highest betweenness centrality, which means he is the most important node in the network. This makes sense given that he has been in a number of high-profile films and has worked with many of the other actors on the list.

 ### Some Specific Actors and clustering coefficient
 
Looking at the clustering coefficients provided, we can see that some actors have very high clustering coefficients of 1.0, indicating that all of their neighbours are connected to each other as well. For example, Gary Oldman, Daniel Radcliffe, Emma Watson, Joseph Gordon-Levitt, etc.

On the other hand, some actors have lower clustering coefficients, indicating that their neighbors are not as tightly connected to each other. For example, Leonardo DiCaprio has a clustering coefficient of 0.137, while Matthew McConaughey has a clustering coefficient of 0.429. Scarlett Johansson has a clustering coefficient of 0.619, while Robert Downey Jr. has a clustering coefficient of 0.327.

 ### Some Specific Actors and degree centrality
 
Looking at the degree centrality values provided, we can see that Leonardo DiCaprio has the highest degree centrality value of 0.116, indicating that he is the most connected actor in the network. Other highly connected actors include Chris Evans with a value of 0.090 and Robert Downey Jr. with a value of 0.071. These actors are likely to be important in the network due to their high number of connections.


## Conclusions 

