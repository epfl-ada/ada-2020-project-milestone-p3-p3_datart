# How topics influence retweets

---

## Abstract

While the paper examines the exposure hypothesis for all topics, we propose to analyze and compare political and food related tweets. To do so, we plan to obtain egos, alters and their timelines from Twitter’s API by generating $3\times30,000$ random numbers in a range from $0$ to $3,000,000,000$. Then, we intend to identify egos’ retweets using official RT, classify tweets by topics based on hashtags (and keywords if the dataset is lacking content) and create a follower/followee graph. To calculate the probability of retweeting alters’ tweets by egos we will use a more solid approach then what is described in the paper “Differences in the Mechanics of Information Diffusion Across Topics” where the probability is equal to the number of users that were k times exposed to a hashtag and retweeted before the ($k+1$)-th exposure, divided by the number of users that were k-times exposed to the hashtag. Finally, we plan to visualize results as well as analyze the probability by breaking down users based on betweenness, clustering coefficient and number of followees.

## Research Questions

1. Is there a significant difference between the probability of retweeting when the tweet is about food and when it is about politics ?
2. Is there a significant difference in the number of times a tweet is retweeted depending on whether it is about food or politics ?
3. Is there a relation between user betweenness, size of cluster or number of friends with the retweet probabilities ?

## Proposed dataset

Self-collected (with the Twitter API) ego and alter timelines with all tweet fields from the [**GET /2/users** endpoint](https://developer.twitter.com/en/docs/twitter-api/users/lookup/api-reference/get-users) and all user fields except for `profile_image_url`.

## Methods

### Data collection

We will sign up for Twitter’s API to collect data. We will generate $3\times30,000$ random numbers in a range from $0$ to $3,000,000,000$ as in the paper and use the [**GET /2/users** endpoint](https://developer.twitter.com/en/docs/twitter-api/users/lookup/api-reference/get-users) to collect active and public user information with all tweet fields and all user fields except for profile_image_url.

### Building the network

We will use networkx to build a directed network of followers  in which nodes are users (egos and alters) and edges are the following relationships (without the following relationships among alters). Next, we will build another network where relationships among alters of active egos are included.

### Calculating retweet probability

For each ego, we will count the number of followees who have retweeted a post (exposures) on a certain topic at a certain date. We will get the information like this: an ego $i$ was exposed to $200$ posts about this topic only once, among which $i$ retweeted $50$ (probability is $50/200 = 25\%$); at the same time, $i$ was exposed to $100$ posts about this topic twice, among which $i$ retweeted $50$ ($probability = 50\%$); … Finally, we will calculate a sequence of probability for each ego. (Same procedure as in the paper.) If there is sufficient data, we will apply a t-test to identify whether the distribution of retweets for each exposure count is significantly different from one topic to the other. We will also try to compare the distribution of retweet probabilities between topics.

### Community detection

We will use the second ego networks to compute clustering coefficients and betweenness of the active egos.

### Data analysis

We will compare the retweet probabilities based on betweenness, number of followers and clustering for each topic, much like in *Figure 6* in the paper.

## Proposed timeline

### Week 1

Downloading the dataset with the Twitter API. Building the network.

### Week 2

Calculating retweet probability and community detection.

### Week 3

Making the visualization in the Notebook, writing the report, making the video.

## Organization within the team

**Jérémy** will produce the random IDs and **Jules** will download the data with the help of **Jérémy** (if his request for an account is accepted) in week 1 while **Kate** sets up the code for building the network.

**Jules** and **Jérémy** will compute retweet probability while **Kate** does the community detection in week 2.

**Kate** will produce the visualization while **Jérémy** makes the pitch video and all three will collaborate on the report.

## Questions for TAs (optional)

- In the event where we do not have enough data to perform a t-test on the distributions for each exposure count, how can we test whether the distributions of exposures are significantly different from one topic to the next ?
- Kate's application to access the Twitter API was rejected twice without an explanation. Could you help us get access for her ?