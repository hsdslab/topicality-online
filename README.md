# Topicality Boosts Popularity Online
Supplementary data for the paper the Topicality Boosts Popularity: A Comparative Analysis of NYT Articles and Reddit Memes - Barnes et al. (2024)

## How to cite

@article{barnes2024topicality, <br>
&nbsp;&nbsp;  title={Topicality boosts popularity: a comparative analysis of NYT articles and Reddit memes}, <br>
&nbsp;&nbsp;  author={Barnes, Kate and Juh{\'a}sz, P{\'e}ter and Nagy, Marcell and Molontay, Roland}, <br>
&nbsp;&nbsp;  journal={Social Network Analysis and Mining}, <br>
&nbsp;&nbsp;  volume={14}, <br>
&nbsp;&nbsp;  number={1}, <br>
&nbsp;&nbsp;  pages={119}, <br>
&nbsp;&nbsp;  year={2024}, <br>
&nbsp;&nbsp;  publisher={Springer} <br>
}

## Source

The Reddit data was collected using the [Pushshift API](https://pypi.org/project/psaw/), and it consists of all posts starting from January 1st, 2018 to November 14th, 2022 from the r/memes subreddits.

The New York Times data was collected using the [NYT Archive API](https://developer.nytimes.com/docs/archive-product/1/overview), and it consists of all articles published in the same time frame.

Open access to both data sets in the [data](./data) folder.

## Summary of data

A total of 255,783 NYT articles were distilled into 2 sets of 120 topics using the [BERTopic](https://maartengr.github.io/BERTopic/index.html) and [LDA](https://jmlr.csail.mit.edu/papers/v3/blei03a.html) algorithms. 

After cleaning steps, the Reddit data set included 899,766 meme posts. We used several meta data features and engineered novel features from the meme images: 

| Feature | Type | Description |
|----------------------|-------------------------------|--------------------------------------------------------|
| score | int | upvotes - downvotes |
| comments | int | number of comments |
| viral | binary | indicates if meme score is in top 5% |
| date | string | date on which meme was posted |
| day-of-week | category | day on which meme was posted |
| all-text | string | title, BLIP image caption, OCR text |
| title length | int | number of characters in title |
| thumbnail size | float | size of image thumbnail |
| over18 | binary | Reddit content warning |
| emoji | binary | identifies emojis in text |
| sentiment | float | text valence score |
| HSV/RGB | floats | mean image values |
| 10 colors | floats | normalized pixels of color in image |
| face | binary | indicates face in image |
| topic | int | highest probability topic assigned to meme |
| probability | float | topic's probability |
| entropy | float | entropy of topic distribution assigned to meme |
| monthly | float | monthly average topicality |
| daily | float | daily average topicality |
| slope | float | slope of topicality distribution |

## Code files

Python code files with exploratory analysis of the data sets, feature extraction, topic analysis and popularity prediction are available in the [code](./code) folder.

## Supplementary figures

The 5-year daily distributions of all topics explored in this project can be found in the [figures](./figures) folder or at [this](https://k-barnes.github.io/memes_topicality.html) link. Daily and monthly distributions for 23 of these topics are displayed and discussed in more detail in the article.
