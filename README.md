# The bigger your circle, the more you post?

---

## Abstract
Replication is an important condition for scientific findings. While the Liang and al. article examines the attention and productivity proposition using a dataset with tweets up to 2015, we propose to analyze and compare using a new dataset collected in 2020 as the behavior of users evolves. The hypothesis states that Twitter users who experience attention from more people will post more often than those who experience less attention. To validate this hypothesis, we plan to obtain ego profiles and their timelines from Twitter’s API by generating $3\times30,000$ random numbers in a range from $0$ to $3,000,000,000$. Then, we intend to identify egos’ friends using user mentions, illustrate the dependence of average number of tweets and total number of tweets from number of followees, followers and friends and fit a logistic regression model to obtain statistics. The Pearson correlation between these features will also be computed to be compared.
  
## Research Questions

1. Is there a correlation between average number of tweets and number of followers/followees/friends?
2. Is there a correlation between total number of tweets and number of followers/followees/friends?
3. Is there a saturation point for the number of total posts as a function of the number of followers/followees/friends?
 
## Proposed dataset

Self-collected (with the Twitter API) egos’ profiles from the [**GET /2/users** endpoint](https://developer.twitter.com/en/docs/twitter-api/users/lookup/api-reference/get-users) and egos’ timelines from the [**GET /1.1/statuses/user_timeline.json** endpoint](https://developer.twitter.com/en/docs/twitter-api/v1/tweets/timelines/api-reference/get-statuses-user_timeline).

## Methods
We will approach the problem of hypothesis validation conceptually. It means that we are not merely going to reproduce previous findings but replicate former conceptual claims using independent data. In this way, all analyses in the extension will be based on the random sample of ego users.     

### Data collection

We will sign up for Twitter’s API to collect data. We will generate $3\times30,000$ random numbers in a range from $0$ to $3,000,000,000$ as in the paper and use the [**GET /2/users** endpoint](https://developer.twitter.com/en/docs/twitter-api/users/lookup/api-reference/get-users) to collect active and public user information. We will then pull user mentions from the egos’ tweets using the [**GET /1.1/statuses/user_timeline.json** endpoint](https://developer.twitter.com/en/docs/twitter-api/v1/tweets/timelines/api-reference/get-statuses-user_timeline).

### Data processing
We will clean egos’ profiles data to extract public metrics (including follower count, followee count and tweet count). We will retain valid public egos’ profiles with at least one alter (follower or followee) for the first two graphs and valid public egos’ timelines of users with at least one alter and one tweet for the last graph.

### Data analysis 
We will explore data and dependence, run basic statistic tests and plot user distribution.

### Data visualization
We will replicate Fig 3. Content productivity and attention received. The average number of tweets as a function of (A) the number of followers, (B) the number of followees, and (C) the number of friends. Friend here is defined as a user who has been mentioned at least twice in an ego’s timeline.
 
### Observational studies
We will fit local  regressions and perform a number of statistical tests

### Results interpretation

We will interpret the significance of findings and compare the graphs, correlation and statistics with other scientific papers, particularly with Liang and al., Huberman and al. and Kwak and al.

## Proposed timeline

### Week 1

Downloading the dataset with the Twitter API. 

### Week 2

Processing, analysing data and making the visualization in the Notebook.

### Week 3

Cleaning the Notebook and GitHub, writing the report and making the video.

## Organization within the team

In week 1 **Jérémy** will produce the random IDs and **Jules** will download the data with the help of **Jérémy** because **Kate** didn’t get the access to the Twitter API.
In week 2 **Kate** and **Jérémy**  will produce the visualization and **Kate** will fit the linear regression and compare with findings of other articles.
In week 3 **Jules** will clean the github and all three will collaborate on the report and make the pitch video.

## Actual contributions

As in *Organization within the team*, except that we were expecting to extend the exposure hypothesis so Jules spent the first week trying to pull ego profiles, timelines and follower and followee IDs. Having realized this would not be possible in the imparted time frame, we switched to the currently described project.