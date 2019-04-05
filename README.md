# Global Search

## DATA GATHERING

## Site Information
- [Algolia vs Elastic](https://blog.algolia.com/algolia-v-elasticsearch-latency/)
- [Inside Algolia Search Engine](https://blog.algolia.com/inside-the-algolia-engine-part-1-indexing-vs-search/)

## Algolia Build Videos
- [Algolia YouTube Channel](https://www.youtube.com/channel/UCTNkiq-SO8hay1PRx-it9Cw)
- [Algolia build 101 for php developers](https://www.youtube.com/watch?v=d_funo7sm0M)

## Algolias Ranking Formula
Notes: 
- most other search engines(Solr, Elastic) inherit their ranking from an Engine called Lucene developed in 1999
	- For. agiven Query a Lucene based engine will use its algorithm to compute a single score per results and order all results according to those values.
	- Pure-textual relevance and other paramaters are mixed into this hard-to-debug numeric value
- ALgolia uses a tie-breaking algorithm
- "n" Rules applied in succession
- The tie-breaking algotithm is called "The Ranking Formula"

#### The Ranking Formula
8 Rules applied in succession
- initially all matching records are sorted by the first criterion e.g. Rule1(Color)
- If any records are tied those are then sorted by the second criterion e.g Rule2(Edge)
- If there are still records tied then those are then sorted according to the third Criterion and so.

**Here is Algolias 8 ranking/sorting rules**

 - Rule 1 - TYPO
 - Rule 2 - GEO
 - Rule 3 - WORDS
 - Rule 4 - FILTERS
 - Rule 5 - PROXIMITY
 - Rule 6 - ATTRIBUTE
 - Rule 7 - EXACT
 - Rule 8 - CUSTOM
 	- This one is key for injecting our own business data

 #### Tie Breaking Algorithm Strengths
 - Ranking is clear and easy to understand **No More black box**
 - Modify rules order and add custom rules

 #### Exploring the engine
 Here are three examples which should highlight how powerful and **Debt** free Algolia really is
 - Ecommerce 
 - Media
 - Mobile

 Ecommerce.   
 As a User looking to buy a new iPhone I want to see the latest version at the top as opposed to the old one or some accessories

