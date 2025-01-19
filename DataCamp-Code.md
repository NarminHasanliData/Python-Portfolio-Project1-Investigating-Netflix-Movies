**Netflix**! What started in 1997 as a DVD rental service has since exploded into one of the largest entertainment and media companies.

Given the large number of movies and series available on the platform, it is a perfect opportunity to flex your exploratory data analysis skills and dive into the entertainment industry.

You work for a production company that specializes in nostalgic styles. You want to do some research on movies released in the 1990's. You'll delve into Netflix data and perform exploratory data analysis to better understand this awesome movie decade!

You have been supplied with the dataset `netflix_data.csv`, along with the following table detailing the column names and descriptions. Feel free to experiment further after submitting!

## The data
### **netflix_data.csv**
| Column | Description |
|--------|-------------|
| `show_id` | The ID of the show |
| `type` | Type of show |
| `title` | Title of the show |
| `director` | Director of the show |
| `cast` | Cast of the show |
| `country` | Country of origin |
| `date_added` | Date added to Netflix |
| `release_year` | Year of Netflix release |
| `duration` | Duration of the show in minutes |
| `description` | Description of the show |
| `genre` | Show genre |
What was the most frequent **movie** duration in the 1990s? Save an approximate answer as an integer called `duration` (use 1990 as the decade's start year).

A movie is considered short if it is less than 90 minutes. Count the number of **short action movies** released in the 1990s and save this integer as `short_movie_count`.

```python
# Importing pandas and matplotlib
import pandas as pd
import matplotlib.pyplot as plt

# Read in the Netflix CSV as a DataFrame
netflix_df = pd.read_csv("netflix_data.csv")

# Filter the data for movies released in the 1990s
movies_1990s = netflix_df[(netflix_df['release_year'] >= 1990) & (netflix_df['release_year'] <= 1999) & (netflix_df['type'] == 'Movie')]

print(movies_1990s)

# Find the most frequent movie duration
plt.hist(movies_1990s['duration'])
plt.xlabel('duration')
plt.ylabel('amount')
plt.title('Duration Frequency')
plt.show()
duration = 100
print('Most frequent movie duration in minutes is' , duration, 'minutes')

# Count the number of short action movies from the 1990s
short_action_movies = movies_1990s[(movies_1990s['genre'] == 'Action') &(movies_1990s['duration'] < 90)]
print(short_action_movies)
short_movie_count = short_action_movies.shape[0]
print('The number of short action movies in 1990s is', short_movie_count)

```
