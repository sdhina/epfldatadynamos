---
layout: page
title: Wiki-Wandering A tale of luck or skill?
subtitle: Player based optimization of wikipedia for Wikispeedia!
cover-img: /assets/img/wallpaper.png
---

If you’ve ever dived into a wikipedia article, only to emerge 5 articles later with 10 facts unrelated to your search, you know that the digital labyrinth is full of gems and dead-ends. Your initial quest to understand the history of pizza might take you three articles down to the Spanish Wars of Succession as you learn about the House of Savoy and Princess Margarita, the eponym to the three ingredient classic. 

At times navigating wikipedia is a skillful hunt for the right fact, at others it’s a random stroll, gathering and picking the most insightful information. You might be of those who strategically dives through hyperlinks to a specific target seeking for a unique embedded fact, or you might aimlessly skim until a striking concept or unknown word changes your trajectory.
{: .text-justify}

<p align="center">
<img src="assets/img/meme.png" alt="No"/>
</p>

Whether you search wikipedia the way you wander through a park, or are an experienced researcher with targeted goals, it remains that your answers are often scattered on multiple pages, with infinite paths tying them all together. So, if like us, you’re prone to clicking frenzies and falling down deep rabbit holes, you might be wondering if Wikipedia is responsible for any of your chaotic searches, and if it was really built for humans to intuitively navigate it…

While explaining why you ended up on this or that page is out of the scope of a naive datascientist’s capabilities, looking at West and Leskovec’s Wikispeedia game might shed some light on your odd behaviours. Wikispeedia, a game which tracks user paths from a source to a target article through a reduced Wikipedia dataset, can allow us to delve into strategies users can follow to go from one article to target information and whether they are effective, all the while studying how wikipedia’s architectural choices match user behaviour. More precisely, West and Leskovec note that humans tend to use "hub" nodes and leverage content cues to guide their navigation. Using this same game, we follow the digital breadcrumbs left by players on the Wikispeedia game and (1) rank their performance in order to assess (2) how their success is tied to the content of articles as well as (3) how the interconnections between articles determine the outcome of their attempts relative to category connections proposed by wikipedia.

## A digital treasure hunt on a miniature Wikipedia

In Wikispeedia players start from a source article, and have to reach a target article as fast as they can on a subset of wikipedia. The goal is to race as fast as possible from one article to the next to be the fastest at finding articles on Wikipedia! The paths players take are reported alongside whether or not they reached their target and the time they’ve taken to finish it. As you can see there are more finished paths than not, and trials where the paths were finished were less time-consuming on average.

{: .text-justify}

{: .text-center}
  
| Finished        | Count           | Average Time played  |
| ------------- |:-------------:| -----:|
| Unfinished      | 24874 | 835.25940 |
| Finished     | 51323      |   158.276199 |

      



The Wikispeedia game is composed of 4604 articles and their metadata from the original Wikipedia, including article categories, content and linking relations. The articles range from Alexander the Great to the United States and are layered inside of categories ranging from countries to famous people:
{% include articles_distribution.html %}

As players navigate from one article to another they visit articles organized under different categories arbitrarily created by wikipedia to group information and facilitate search. Interestingly, players do not systematically converge to articles on dominant categories! 
{: .text-justify} 

## Part 2: Network Preferences

Similarly, if article contents might affect how a player reaches his target, the network of articles itself will determine the path the player chooses to his target; to do so, the player can choose articles that have certain network characteristics.

Notably, we look at:

* Degree Centrality: a measure of the importance of a node in a network based on the number of connections (edges) it has.
* Betweenness Centrality: a measure of the extent to which a node lies on the shortest paths between other nodes in the network. Nodes with high betweenness centrality act as bridges or intermediaries in the network.
* Closeness Centrality: calculates how close a node is to all other nodes in the network on average. Nodes with higher closeness centrality are more central because they can reach other nodes more quickly.
* Eigenvector Centrality: assigns importance to a node based on its connections to other important nodes. Nodes connected to other nodes with high eigenvector centrality will also have high centrality scores.
* Clustering Coefficient: quantifies the likelihood that neighbors of a node are also connected to each other. High clustering coefficients indicate the presence of tightly knit communities or cliques in the network.

{: .text-justify} 

{% include centralities.html %}

Centrality measurements seem to be skewed towards the lower end of their respective distributions showing that fewer nodes have high centrality measurements. However, we should note that the closeness centrality histogram appears to be more uniformly distributed showing a peak in the mid-range centrality values, thereon suggesting that nodes are on average equally distant from one another in the network. Similarly, clustering coefficients follow a slightly less skewed distribution, suggesting some level of tight-knit communities within the network. 

Do you think you would intuitively optimize for any of these measurements to reach your target? 

While evaluating whether a player optimized for any of these measurements out of his free will is beyond the scope of our narrow data oriented minds, we can look at whether or not players tended to choose paths that favored some of the network characteristics over another. 






