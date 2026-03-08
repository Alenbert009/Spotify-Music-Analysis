🎧 Spotify Music Analysis Dashboard (Power BI)

📊 Project Overview

This project is an interactive Power BI dashboard built to analyze Spotify music streaming data. The dashboard provides insights into track popularity, streaming trends, artist performance, and music characteristics.

Using Power BI, DAX, and a custom Calendar table, the dashboard enables time-based analysis of Spotify tracks and helps identify trends in music streaming behavior.

🚀 Key Features

📈 Total Streams Analysis

🎵 Track Count and Average Streams

📅 Streams by Release Date

📊 Monthly Track and Stream Distribution

📆 Daily Streaming Trends

⭐ Top 5 Most Streamed Tracks

🎤 Most Streamed Artist Track

🎚 Music Feature Analysis

Energy %

Danceability %

Speechiness %

Liveness %

Instrumentalness %

🖥 Dashboard Preview

📂 Dataset Information

The dataset contains Spotify track information including:

Column	                            Description

Track Name	                        Name of the song

Artist(s)_name	                    Artist(s) performing the track

Streams	                            Total number of streams

Release Date	                    Song release date

BPM	                                Beats per minute

Danceability_%	                    Measure of danceability

Energy_%	                        Intensity and activity level

Speechiness_%	                    Presence of spoken words

Acousticness_%	                    Acoustic quality

Liveness_%	                        Presence of live audience

Instrumentalness_%	                Likelihood of instrumental track

Cover_URL	                        Album cover image

🧠 Data Model

The project uses a Star Schema Model:

Tables Used

1️⃣ Spotify Dataset (Fact Table)
2️⃣ Calendar Table (Date Dimension)
3️⃣ Data Dictionary (Reference Table)

Relationship:

Calendar[Date] 1 ---- * Spotify Dataset[Date]

This allows time intelligence analysis like monthly, yearly, and daily trends.

📅 Calendar Table (DAX)

A custom Calendar table was created using DAX to support time-based filtering and analysis.

CALENDAR =
ADDCOLUMNS(
    CALENDAR(
        MIN('Spotify Dataset'[Date]),
        MAX('Spotify Dataset'[Date])
    ),
    "Year", YEAR([Date]),
    "Quarter", QUARTER([Date]),
    "Quarter (Q)", FORMAT([Date], "QQ"),
    "Month", MONTH([Date]),
    "MonthName", FORMAT([Date], "mmm"),
    "Day Of Week", WEEKDAY([Date]),
    "DayName", FORMAT([Date], "dddd")
)

This table enables filtering by:

Year

Quarter

Month

Day of Week

📊 Dashboard Insights

The dashboard answers several analytical questions:

Which tracks have the highest streams?

Which months release the most popular songs?

Which day of the week has the most streams?

Which artist track is the most streamed?

What music characteristics are common in popular songs?

🛠 Tools & Technologies

Tool	Purpose

Power BI	Data visualization

DAX	Data modeling & calculations

Power Query	Data transformation

GitHub	Version control

Spotify Dataset	Data source
