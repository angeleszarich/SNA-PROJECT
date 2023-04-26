# Hollywood Elitism: the social network of the film industry
Sna2 Final Project - Mia K. Bellemare, Angie Zarich, Tara rafaty and Kanami Konishi

## Introduction

The Hollywood film industry is known for its glamorous world of movies and celebrities, where actors often work together in multiple films, forming a web of connections and close personal relationships. But how many of the opportunities and film collaborations come from use of personal connections rather than talent?

Our team has decided to focus on the role of elitism and potential nepotism in Hollywood by analysing the network of connections among the actors of the top-rated movies in the decade spanning from 2010 to 2019. In this analysis, we aim to explore the role of personal connections within opportunities in the film industry from the viewpoint of social network analysis, taking into account Granovetter’s theory of the strength of weak ties (1973), and Milgram’s small world problem (1967). We begin by taking our data from the most popular public online film rating database, IMDb, by scraping the data of the top 50 films from the decade spanning from 2010-2019. From there we created a social network of the actors involved in said films, utilising the shared films as their connections within the network. By doing so, and obtaining other social network analyses metrics, we could understand where actors lied within this network of the most prestigious films of the decade, and whether there were certain patterns observed. By examining these connections, we seek to answer the question: how well connected are the top-rated films' actors? Overall, we hope that our analysis will provide a deeper understanding of the Hollywood elitism, the relationships among Hollywood's top actors and how they contribute to the success of top-rated films.


## Literature Review 

According to Granovetter's (1973) theory of the strength of weak ties, while strong ties, such as family members or close friends, share similar information and resources, it is weak ties, such as friends of friends or colleagues of family members, who provide access to novel information and opportunities by acting as bridges across network clusters: the only connections between two nodes within a network (Granovetter, 1973). These connections are crucial in social networks because they promote diversity of thought among populations by enabling the dissemination of information from otherwise homogeneous networks.

Additionally, Milgram concludes in his experimental study about the small world problem (1967) that the average diameter of a social network – diameter being the longest shortest path between two nodes in a network – is never higher than 6, labelling the well-known phenomenon as the ‘six degrees of separation’. His theory applies to a widespread population over the US, and therefore, applying to our network analysis, it would be probable that our diameter would be much smaller than this due to the probable personal connections and shared professions of all members of the population.


## Hypotheses

From reviewing the literature and our initial contextual knowledge of the industry, we developed hypotheses before analysing the data: 

   🔍 Actors featured higher rated films will be more connected and important in the network than those in lower-rated films

   🔍 Actors in high-rated films are more likely to be featured in other top-rated films due to their connections within the industry.

   🔍 The social network will have a diameter <6

Generally, we believe that we will find that the ranking the film that an actor is in will be proportional to their importance in the social network, meaning that their role within facilitating ties between actors will be high. We also believe to find that the actors within the highest rated films will be more likely to be present in other high rated films. The elitism and preference for actors who have already performed in high-rated pictures due to their established personal connections is our reason for this assumption. Finally we believe the social network will have a diameter less than 6 as presumed by Milgram (1967), and also due to the fact that the individuals we aim to analyse share a career path and therefore have a high probability of being connected.


## Methodology

In order to discover the social network of actors within top rated films, we utilised data from ‘IMDb’ (Internet Movie Database). This choice was made as it is the most popular form of online film ranking and therefore would have the most accurate data for us to analyse. We utilised the 50 top ranked films, by number of audience votes, from the decade of 2010-2019. Rather than looking at the 50 top rated movies of all time, we focused our analysis simply on one 10 year time span in order to increase the probability of the actors having ties; the likelihood that the actors from a top rated film from 1980 are connected to the actors from a film made in 2020 is quite unlikely due to generational differences and the changing landscape of the film industry and it therefore could mess with our analysis.

 > The list can be seen [here](https://www.imdb.com/search/title/?release_date=2010,2019&title_type=feature&sort=num_votes,desc). 


Our simple four step methodology was as follows:

1. Scrape the data of movie titles and 5 main actors of each film
2. Set the actors as nodes and movies as edges within our social network
3. Create social network visualisation with data
4. Find social network analysis statistics and create other graphed visualisations


The data was scraped in python using the BeautifulSoup package in conjunction with headers and user agents in order to bypass the IMDb bot anti-scraping measures put in place. Once the data was extracted, we created an interactive social network visualisation graph utilising networkx and Sigma. We set each actor as a node within the network and each movie as an edge in order to see how the movies connected the actors.

After creating our initial visualisation, we again used networkx in order to get the betweenness centrality, degree centrality and, and clustering coefficient for each actor, as well as the diameter of the network. Each is defined as the following:


**Betweenness centrality** : The number of shortest paths between pairs of nodes within the network that pass through the node. Measure of the importance of the node in facilitating communication.

**Degree centrality**: The number of edges connected to a node divided by the total number of edges in the network. A measure of how well connected a node is in a network.

**Clustering coefficient**: Measure of how tightly clustered a node’s neighbours are in a network.

**Diameter**: The maximum distance between any two nodes in a network.

By obtaining the above statistics we could meaningfully analyse our network and gain a deeper understanding in the most well-connected actors and the characteristics of the network as a whole.


 > Our code can be seen [here](https://colab.research.google.com/drive/1YjDicn5V7WQIe2QNg8_8qkkFQl55XCPD?usp=sharing)


## Results

Once the coding process was complete, we obtained our visualisations and statistics. Sigma created our network and we obtained an interactive graph which was initially hard to read (see figure 1), but once refined with the software we created a much more visually meaningful visualisation (figure 2). 

We also obtained the mentioned social network analysis statistics and created tables in order to compare them by actor. The figures obtained for betweenness centrality, degree centrality, and clustering coefficient can be seen in tables 1, 2, and 3, respectfully.

It is important to note that when attempting to calculate the diameter of our social network, we obtained an error code. As stated, the diameter of a network is the maximum distance between any two nodes in the network however as we can see in figure 2, there are many nodes that have no connection whatsoever, meaning that the diameter of the network does not exist, or can be assumed to be infinite.


## Analysis

First of all from the visualization of the social network, we were able to analyze the overall structure of the industry. As seen in figure 2, there is one prominent cluster, which consists of most of the actors in the network. From this we can understand that in general, actors from top rated movies are connected with one another through a large network, although the diameter of the clustered network identifies that those ties may not be strong. This contradicts with the Migram’s “six degrees of separation” theory (1967) as well one of our initial hypotheses. One reason that could lead to this result is the fact that the interaction between actors is not very fluid; it takes an average of 4 to 5 years to produce 1 film. Thus considering how the data we scraped was only from a span of 10 years, we can predict that actors did not have enough time to appear in many films, which would explain why many of them are not strongly tied with one another. It is also important to note that, whilst not connected in our social network, this does not signify that these actors are not connected at all. Therefore, we cannot assume from our analysis that Milgram’s theory is incorrect, as we have not considered the whole lifetime of each actor and other ways in which they may have personal connections. We can only assert that, within the 10-year span and these top rated films, Milgram’s theory is not upheld.

On the other hand, the other actors that do not belong to that cluster are mostly only connected to actors that they filmed the same movie with. However it is not necessarily the case that those actors are from the films rated very low in the list. For example, although the actors are isolated from the others, films such as “Deadpool” (2016) and "Intouchables” (2011) are respectively ranked 12th and 20th, which is not a low rank out of 50. This could be because the social network of actors is not a homogeneous group, and there may be subgroups or clusters within the network that are more tightly connected than others. In the case of "Intouchables,” it is a French produced film, making it less likely for its actors to be connected with other mainstream Hollywood actors. Yet it is true that actors that starred in any movie above rank 11, belong in the large clustered network, indicating the possibility of actors in high rated films to be more likely to be featured in other top rated films due to their personal connections within the industry. 

Looking more specifically into particular statistics and actors within the network we find interesting assertions.

### Betweenness centrality:

Leonardo DiCaprio is the most important actor in the network according to his high betweenness centrality score of 0.153. This is because he has been in many high-profile films and has worked with many other actors on the list. Actors such as Joseph Gordon-Levitt, Elliot Page, Ken Watanabe, and others have a betweenness centrality score of 0, indicating that they are not important in facilitating communication between other nodes in the network. Matthew McConaughey has a relatively low betweenness centrality score compared to DiCaprio but still plays an important role in connecting other nodes in the network. Actors like Anne Hathaway, Jessica Chastain, Margot Robbie, and others have betweenness centrality scores greater than 0 but less than McConaughey's, meaning that they are less central to the network but still play an important role in connecting other nodes.

### Degree centrality:

In this analysis, the degree centrality values of actors in a network are provided, where each actor is assigned a value that represents the proportion of connections they have with other actors. It is observed that Leonardo DiCaprio has the highest degree centrality value, indicating that he is the most connected actor in the network, correlating with his high betweenness centrality. Other highly connected actors include Chris Evans and Robert Downey Jr. However, some actors such as Joseph Gordon-Levitt, Elliot Page, Ken Watanabe, and Mackenzie Foy have lower degree centrality values, suggesting that they are less connected in the network and may be less important. Nonetheless, other factors such as the strength and nature of the connections and their roles in the network can also impact their importance.

### Clustering coefficient:

We can observe that certain actors have very high clustering coefficients of 1.0, which means that all of their neighbors are connected to each other meaning they are not important within the network in facilitating ties – they do not act as bridges (sole connections between two nodes). These actors include Joseph Gordon-Levitt, Elliot Page, Ken Watanabe, Gary Oldman, Jamie Foxx, Christoph Waltz, Kerry Washington, Martin Scorsese, Jonah Hill, Emily Mortimer, Ben Kingsley, Joaquin Phoenix, Zazie Beetz, Frances Conroy, Chris Pratt, Vin Diesel and many others. Interestingly, these actors also have a betweenness centrality score of 0, again indicating that they are not important in facilitating communication between other nodes in the network.

Conversely, some actors have lower clustering coefficients, which means that their neighbors are not as closely connected to each other. For instance, Leonardo DiCaprio has a clustering coefficient of 0.137, while Matthew McConaughey's clustering coefficient is 0.429. Scarlett Johansson's clustering coefficient is 0.619, while Robert Downey Jr.'s is 0.327.

In general, the clustering coefficients reveal that certain actors are more central in the network than others. High clustering coefficients within our network tend to go hand in hand with low betweenness centralities and low degree centralities, due to the many homogenous clusters we see within our network.

Figures 3, 4, 5, and 6 show isolated networks and statistics of some individuals within the network that seem to have high importance. As stated, Leonardo DiCaprio is the most important node in connecting and facilitating ties between actors. He acts as a bridge for many connections, and has starred in 5 of the top 50 films, 3 of which lie within the top 10, and exist across genres.

From the statistics, we can understand that Matthew McConaughey is the second most important node within the network, having the second highest degree and betweenness centrality, however he only stars in 3 of the top 50 films. Two of these lie within the top 10, which aligns with our hypothesis about high rated actors being the most connected however goes against our other hypothesis about high rated actors starring in more highly rated films than others. Chris Evans and Robert Downey Jr. star in the most films within the top 50 (8 and 7, respectfully) which would make us believe, according to our hypothesis that they would be more central to the network than Matthew McConaughey. However, the majority of these films are within the Marvel franchise, meaning their connections are not as widespread across genre as Matthew McConaughey, despite them having lower clustering coefficients than him. We can potentially understand Matthew McConaughey’s importance within the network as the films he stars in are all of different genres and contain all different actors; although having less total ties he is a bridge for much more nodes than Chris Evans or Robert Downey Jr.
 

## Conclusions 

Our research findings suggested that actors from top-rated movies are connected to one another through a large network, but the ties may not be strong. There is one prominent cluster consisting of most actors in the network, which can be seen as potentially the most ‘elitist’ cluster within the network, only containing actors in Hollywood films. This asserts that the problem of elitism and nepotism within the film industry is a Hollywood issue; actors from foreign films had no connections to the large cluster. Actors with long careers within Hollywood tend to have been the most important within the network, such as Leonardo DiCaprio, who had the highest betweenness centrality score, indicating that he plays a crucial role in connecting other nodes in the network. The research found that actors in high rated films are more likely to be featured in other top rated films due to their personal connections within the industry. The study suggests that the Hollywood industry's social network is not homogeneous and may have subgroups or clusters with varying degrees of connection. 

Whilst our hypothesis about the diameter of the network was unfortunately beyond the scope of what we analysed, our other hypotheses with regards to higher rated actors being more connected were upheld, with the interesting exception of Matthew McConaughhey, who was one of the most well-connected actors within the network but only starred in 3 of the top 50 films.

An interesting detail we discovered whilst undertaking this analysis is that the top 3 films of the list are all directed by Christopher Nolan. Thus, directors and production staff may also play an important role in facilitating ties within Hollywood as they act as the hiring staff within the industry and therefore may follow a similar theory as asserted by Granovetter (1973) – they provide novel connections and information by connecting other actors through their productions. Further social network study including directors would provide more interesting and meaningful data, as well as possibly studying the network as a dynamic social network to understand how ties develop over time within the industry, as done by Kossinets and colleagues, in their ‘empirical analysis of an evolving social network’ (Kossinets et. al, 2006). 

Overall, our research provides insight into Hollywood elitism and its impact on the film industry.


## Appendix 


<img width="312" alt="figure 1" src="https://user-images.githubusercontent.com/130977477/234343171-eef7fd1e-8257-4aec-84da-839cfad3f530.png">

<img width="311" alt="Figure 2" src="https://user-images.githubusercontent.com/130977477/234343205-e4239de3-16a6-4ec4-92a8-cc434c48ba23.png">

<img width="595" alt="Figure 3" src="https://user-images.githubusercontent.com/130977477/234343242-fbe86440-d652-4513-b351-f938656f7756.png">

<img width="475" alt="Figure 4 " src="https://user-images.githubusercontent.com/130977477/234343274-98d38b65-f17f-4b09-83e4-61dfc68933a0.png">

<img width="561" alt="Figure 5 " src="https://user-images.githubusercontent.com/130977477/234343297-fcd7c0b8-8d13-4dac-8897-252382a1c105.png">

<img width="569" alt="Figure 6" src="https://user-images.githubusercontent.com/130977477/234343324-bff65a29-d4db-4baf-8e3e-1b7c99c622d4.png">

<img width="130" alt="Table 1" src="https://user-images.githubusercontent.com/130977477/234343355-2d2092e6-ce73-4051-8535-e029e35e17bc.png"> <img width="205" alt="Table 2" src="https://user-images.githubusercontent.com/130977477/234343421-10f15b55-4163-4a73-8ebb-d38a51e71aa3.png"> <img width="121" alt="Table 3 " src="https://user-images.githubusercontent.com/130977477/234343443-43f0724c-abaf-4384-b9ed-51422346af09.png">




## Bibliography

- Granovetter, M., 1973. The Strength of Weak Ties. American Journal of Sociology, 78(6), pp. 1360- 1380. 

- Kossinets, G. and Watts, D.J., 2006. Empirical analysis of an evolving social network. science, 311(5757), pp.88-90.

- Milgram, S. (1967). The small world problem. Psychology Today, 2(1), pp. 60-67.


