+++
title = "What can the labor flow of 500 million people on LinkedIn tell us about the structure of the global economy?"
date = 2019-08-02T20:53:37-04:00
draft = true

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Jaehyuk Park"]

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ['linkedin', 'labor market', 'global economy', 'network science', 
        'future of work', 'labor flow network']
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = "linkedin_featured_image.png"
caption = ""
preview = true

+++
This post is what I wrote on *LinkedIn* as [a blog post](https://www.linkedin.com/pulse/what-can-labor-flow-500-million-people-linkedin-tell-us-jaehyuk-park/).
You can find the original article here: [Global labor flow network reveals the hierarchical organization and dynamics of geo-industrial clusters](https://www.nature.com/articles/s41467-019-11380-w)

Recent advancement of information technology, such as artificial intelligence and robotics, makes business owners, city planners, and policy makers challenging to prepare for the future of the labor market. Between all the news articles and company reports depicting either utopian or dystopian future of labor they feel lost, but at the same time, feel pressured to be the next Silicon Valley, as the competition for the Amazon's second headquarters showed. How can we prepare for our journey to the future of labor market more strategically? Similar to the wars in human history, it should be begun with having a good map to visualize the landscape of the whole economy. 

Unfortunately, visualizing the landscape of the global economy is much harder than drawing a map of geographical landscape. The global economy is a complex system of heterogeneous level of agents - worker, firm, and country - and keeps evolving, so it is difficult to capture a snapshot of the whole structure. Also, the economic structure is influenced by both geographical and industrial constraints, we cannot assume the similar structure would be appealed for the same industry in different regions, and vice versa. 

One of the most popular concepts for policy makers and business economists to understand the structure of the global economy is "cluster", the geographical agglomeration of interconnected firms such as Silicon Valley, Wall Street, and Hollywood. By studying those well-known clusters, we become to understand the advantage of participating in a geo-industrial cluster for firms and how it is related to the economic growth of a region. 

However, the existing definition of geo-industrial cluster is not systematic enough to reveal the whole picture of the global economy. Often, after defining as a group of firms in a certain area, the geo-industrial clusters are considered as independent to each other. As we should consider the interaction between accounting team and marketing team to understand the organizational structure of a firm, the relationships among those geo-industrial clusters are the essential part of the whole picture.

Also, since geo-industrial clusters are related to each other, they can't be defined just in one level. Rather, they should be defined in multiple levels in the hierarchical ladder of the global economy. Again, in the example of a firm, a core data science team can be a part of an analytics team, separated from accounting team, but also consists of other sub-teams based on its sub-projects. Thus, we need to understand the geo-industrial clusters in the view of hierarchical structure, which allows us to map them in different scales based on our interests.

In this new study, my colleagues and I at Indiana University -- with support from LinkedIn -- have finally overcome these limitations by defining geo-industrial clusters through labor flow and constructing a global labor flow network from LinkedIn’s individual-level job history dataset. Our access to this data was made possible by our selection as one of 11 teams selected to participate in the [LinkedIn Economic Graph Challenge](http://archive.news.indiana.edu/releases/iu/2015/06/iu-linkedin-project.shtml).

The transitioning of workers between jobs and firms -- also known as labor flow -- is considered central in driving firms towards geo-industrial clusters due to knowledge spillover and labor market pooling. In response, we mapped the cluster structure of the world economy based on labor mobility between firms during the last 25 years, constructing a “labor flow network.” 

To do this, we leverage LinkedIn’s data on professional demographics and employment histories from more than 500 million people between 1990 and 2015. The network, which captures approximately 130 million job transitions between more than 4 million firms, is the first-ever flow network of global labor.

The resulting “map” allows us to:

    - identify geo-industrial clusters systematically and organically using network community detection
    - verify the importance of region and industry in labor mobility
    compare the relative importance between the two constraints in different hierarchical levels, and
    - reveal the practical advantage of the geo-industrial cluster as a unit of future economic analyses.
    - show a better picture of what industry in what region leads the economic growth of the industry or the region, at the same time
    - find out emerging and declining skills based on the representativeness of them in growing and declining geo-industrial clusters

As the first attempt, in our best knowledge, to map the hierarchical structure of the global economy our approach suggests a lot of possible directions for future studies including the relationship between different skills, the job mobility pattern of workers based on their skill similarities, the role of skill influx on the growth of a geo-industrial cluster and etc.

Furthermore, we expect this study will provide a powerful foundation for further systematic analysis of geo-industrial clusters in the context of business strategy, urban economics, regional economics, and international development fields - as well as providing useful insights for policymakers and business leaders.

{{< figure library="true" src="linkedin_blog_figure.png" title="A caption" lightbox="true" >}}

**Figure 1**. **A**, A labor flow network is comprised of organizations (nodes) and the flows of people between them (directed, weighted edges) as defined by historical records of job changes. **B and C**, Two illustrative examples of geo-industrial clusters defined as hierarchically-organized geo-industrial clusters in the labor flow network with high intra-cluster talent mobility. **D and E**, A transition matrix of labor flows between LinkedIn users’ self- reported industries (normalized with the expected transition volume) highlights labor flows within and between macroeconomic sectors. The effect of geographic proximity on labor mobility is also evident in the matrix of labor flows between US states. **F**, The large-scale organization of geo-industrial clusters in the labor flow network. Each circle represents a geo-industrial cluster, with size proportional to its number of employees. The colors represent the highest-level community membership. **G–J**, Two examples of hierarchical sub-structures in the labor flow network are illustrated. Each circle represents a firm and the bar charts show the reduction in industry and region entropy within the cluster as a proportion of the parent cluster’s entropy. **K–N**, The influx of educated labor force is linked to the growth of geo-industrial clusters. The horizontal axis represents the five-year trend in college-degree labor flux from 2010 to 2014. Similarly, the vertical axis represents the five-year trend in log-scaled market capitalization within the cluster over time. **K**, The trends for individual firms, **L**, The trends for geographical regions, **M**, The trends for industries, and **N**, The trends for geo-industrial clusters, which displays the strongest relationship.
