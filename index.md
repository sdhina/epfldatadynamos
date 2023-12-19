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


## Plot Example

{: .text-justify} 
{% include articles_distribution.html %}
{% include degree_centrality_plot.html %}

This is our first plot.
{: .text-justify}

## Next section

Test
