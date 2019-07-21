# Star Wars Fan Reviews

In this project, sentiment analysis was performed using Survey Results conducted by FiveThirtyEight, with Star Wars movie watchers as the respondent. A total of 835 responses were recorded, which can be downloaded from FiveThirthyEight's [GitHub repository](https://github.com/fivethirtyeight/data/tree/master/star-wars-survey).

## Data Cleaning

- First, rows in which the `RespondentID` column was NaN were removed, since `RespondentID` is how survey-takers are distinguished.
- Certain columns that contained "Yes" and "No" values stored as strings were converted to Boolean values instead. 
- Due to some column names being very long (e.g.`Which of the following Star Wars films have you seen? Please select all that apply.` being an entire column), column-renaming was also done.
- Columns in which responders ranked films from 1-6 were converted to numeric type.

## Visualizing fan sentiments

The mean ratings of each movie were visualized:

### Fan Ratings

![Mean ratings](https://i.gyazo.com/808b9b90122530741372c4ba3df49d34.png)

The x-axis values, e.g. `ranking_1`, `ranking_2`, etc, correspond to the Star Wars episode. Keep in mind that a lower mean score translates to a higher average rating, since a rank 1 movie would have a rating of 1.

In general, it certainly seems like the original movies were more favorably rated (remember that Star Wars episodes 4-6 were made before episodes 1-3). **"The Empire Strikes Back" was the most highly rated with a mean score of 2.5, which means on average, most respondents rated it either their 1st or 2nd most favorite Star Wars movie.**

### Moview Viewership

![Movie viewership](https://i.gyazo.com/fbcd26382d468dd67ea63ad48275746c.png)

Viewership of each movie among survey respondents was also visualized. In general, there was an undeniable correlation between viewership and a movie's rank. The original movies were the most viewed ones, and the fifth movie, "The Empire Strikes Back" was the most viewed, just as it was the most highly rated. **However, this does also call attention to a flaw in the methodology we've been using: Respondents have been rating movies that they simply haven't seen**. It might have produced us a more accurate result if we only looked at respondent's rankings who've seen all 6 movies.

### Fan Ratings only among respondents who saw all 6 movies.

![Fan ratings who saw all](https://i.gyazo.com/e16d14098a5b21d50f86ac614dee8bbe.png)

When we narrowed down the respondents and considered only the opinions of those who had seen all 6 movies, we observed much of the same results that we did before narrowing down the dataframe. Movie 5, "The Empire Strikes Back" is rated the most highly. Once again, the original movies were rated a lot better. The sequel movies were rated even more poorly than they were earlier when we included in all respondents, which makes sense. This confirms our views that among both ardent fans and everyday viewers, the original movies are seen more favorably, with "The Empire Strikes Back" standing out as the most highly rated one.

### Viewership by Gender

![Viewership by Gender](https://i.gyazo.com/3547ccbcb5226e0465e2c835d37ae1a6.png)

There were noticeably more male than female viewers overall.

### Viewership based on whether respondent identifies as a fan

![fan or not](https://i.gyazo.com/0fc98f2e43200b0b237463cc4684a7e6.png)

For viewership numbers between self-described fans and non-fans, the results are very predictable. **While fans tend to have watched the original movies more, they're also more likely to have seen all 6 movies**. For instance, the difference between the most viewed and least viewed movies by fans is only around 15-20%. In contrast, among non-fans while on average the original movies were seen more, non-fans are a lot more likely not to have seen one or more of the 6 movies. For instance, the difference between the most viewed and least viewed movies by non-fans is nearly 60%. This is likely in part because non-fans are less likely to see a movie out of interest in a franchise, and instead base their decision to see it around other factors like the movie's ratings.

### Fan ratings based on whether respondent identifies as a fan

![fan or not ratings](https://i.gyazo.com/f4d5a693a2f5b1769ed9b229f461bfc8.png)

Again, somewhat predictably, fans were more zealous in their love of the original movies, whereas non-fans were more likely to give favorable reviews to the sequel movies. **Among non-fans, movie 1 and movie 5 are rated almost equally high, which is an interesting observation. Among fans on the other hand, all 3 originals were rated the highest by a margin**.


