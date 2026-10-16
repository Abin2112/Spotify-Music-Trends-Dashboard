# Spotify Music Trends Dashboard — 100 Years of Sound

An interactive **Tableau** dashboard exploring how music in Spotify's catalogue changed from 1922 to 2021. Built as an **Storytelling with Data** project using a cleaned dataset of **586,600 tracks**.

> **Project team:** Abin Pillai and Rashmi Ashok  
> **Guidance:** Shweta Ma'am  
> **Programme:** M.Sc. Data Science, NMIMS Mumbai  
> **Tool:** Tableau Public / Tableau Desktop

## Project Overview

Music data becomes difficult to understand when it is stored as hundreds of thousands of rows. This project turns the Spotify catalogue into a visual story that helps viewers explore five questions:

1. How has the number of tracks released per year changed?
2. How has the sound of music changed across decades?
3. Has the share of tracks marked explicit increased?
4. Which artists have the highest average popularity in the dataset?
5. Are more danceable tracks associated with higher average popularity?

The dashboard brings together **5 KPI cards, 5 visualizations and 3 interactive filters** on one page.

## Key Findings

- **Catalogue growth:** Track releases in the dataset rise from 276 in 1922 to 13,937 in 2020.
- **Changing sound:** Average acousticness falls from 0.89 in the 1920s to 0.27 in the 2020s, while energy rises from 0.28 to 0.63.
- **Explicit content:** The explicit-track share reaches 23.1% in the 2020s, compared with 11.8% in the 2010s.
- **Artist popularity:** Harry Styles has the highest average popularity in the all-data Top 10 shown in the project (77.8), among artists with at least 10 tracks.
- **Danceability and popularity:** Average popularity is 22.5 for low-, 27.3 for medium-, and 32.3 for high-danceability tracks.

These are patterns in this dataset, not universal claims about all music or all listeners.

## Dashboard Preview

### Full dashboard
![Spotify Music Trends Dashboard](images/01_dashboard_overview.png)

### Dashboard filtered to the 2020s
![Spotify dashboard filtered to the 2020s](images/02_dashboard_2020s_filter.png)

## Visualizations

| Chart | What it explains |
|---|---|
| Tracks released per year — line chart | Long-term growth in track releases |
| Audio features by decade — multi-line chart | Changes in acousticness, energy, danceability and valence |
| Explicit percentage by decade — bar chart | How the explicit share varies by decade |
| Top 10 artists by average popularity — horizontal bar chart | Artists with the highest average popularity, requiring at least 10 tracks |
| Popularity by danceability band — bar chart | Average popularity for low, medium and high danceability |

## KPI Summary

| KPI | Value across all data | Meaning |
|---|---:|---|
| Total Tracks | 586,600 | Size of the cleaned track catalogue |
| Total Artists | 98,504 | Distinct artist IDs in the track-artist table |
| Average Popularity | 27.6 / 100 | Overall popularity benchmark |
| Explicit % | 4.4% | Share of tracks marked explicit |
| Average Duration | 3.83 minutes | Average track duration |

## Interactive Filters

- **Decade:** Select an era from the 1920s to the 2020s.
- **Explicit:** Compare tracks marked Yes or No.
- **Content Type:** Choose Music or Spoken Word.

The filters apply across the dashboard so the KPI cards and charts update together. For example, selecting the 2020s changes the total track count to 20,218, the explicit share to 23.1%, and average popularity to 41.7.

## Data Source

**Dataset:** [Spotify Dataset 1921–2020, 600k+ Tracks — Kaggle](https://www.kaggle.com/datasets/yamaerenay/spotify-dataset-19212020-600k-tracks)

The dataset was collected through the Spotify Web API. The source data includes track names, artists, popularity, duration, release dates, explicit flags and audio features.

## Data Preparation

The data was prepared for analysis before building the dashboard:

- Removed 71 tracks with missing names and one 1900 date outlier.
- Created clean Year and Decade fields from mixed date formats.
- Converted duration from milliseconds to minutes.
- Changed explicit values from 0/1 to Yes/No.
- Created a Content Type field using the project's speechiness threshold.
- Grouped danceability into Low (0–0.4), Medium (0.4–0.7) and High (0.7–1.0).
- Created a track-artist table to support tracks with multiple artists.
- Standardized artist and genre text and removed unused columns.

## Tools and Techniques

- **Tableau Public / Tableau Desktop** — dashboard design, calculated fields, charts and interactive filters.
- **Data cleaning and preparation** — consistent dates, duration, content labels and artist relationships.
- **Calculated fields / aggregations** — distinct track and artist counts, average popularity and duration, and explicit percentage.
- **Data storytelling** — arranging charts in a sequence from catalogue growth to sound, content, artists and popularity.

## Limitations

- Spotify popularity is recency-weighted, so recent artists and songs may be favoured.
- The 2021 data is partial; the dataset ends on 16 April 2021.
- Re-releases and remasters are counted as separate track releases.
- The relationship between danceability and popularity is an association; it does **not** prove that danceability causes popularity.
- Some year-to-year dips may reflect dataset sampling gaps.
- Averages do not show the full spread of individual tracks.
- Genre analysis is limited because many artist genre values are unknown.

## Future Improvements

- Improve genre coverage and add a genre-based dashboard view.
- Add a scatter plot of energy against danceability, coloured by popularity.
- Compare danceability and popularity within each decade to reduce the effect of differences between eras.
- Validate unusual yearly dips against an independent data source.

## Project Documentation

The full project documentation PDF should be added to this repository as:

`docs/Spotify_Music_Trends_Dashboard_Documentation.pdf`

Once uploaded, link it here:

**[View the complete project documentation](docs/Spotify_Music_Trends_Dashboard_Documentation.pdf)**

## Team and Acknowledgement

Created by **Abin Pillai** and **Rashmi Ashok**, M.Sc. Data Science, NMIMS Mumbai, as a Storytelling with Data project, under the guidance of **Shweta Ma'am**.

## Important Note

The dashboard describes the dataset used for this academic project. The results should be interpreted with the limitations above and should not be treated as proof of cause-and-effect relationships.
