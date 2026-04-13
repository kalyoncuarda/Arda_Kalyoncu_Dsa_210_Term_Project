# DSA 210 - Clickbait Headlines and Reddit Engagement

## Project Overview
This project investigates whether clickbait headlines in Reddit news posts receive more upvotes and comments than non-clickbait headlines, and whether the credibility of the news source affects this relationship.

## Research Question
Do clickbait headlines on Reddit receive more upvotes and comments than non-clickbait headlines? And does the credibility of the news source affect this relationship?

## Datasets
| Dataset | Description | Size | Download |
|---|---|---|---|
| posts.csv | ~110,000 posts from r/worldnews (Kaggle - Umar Haddi) | 36 MB | [Google Drive](https://drive.google.com/file/d/1yAV3VxUYPxhQ4cahfFNjIVLNJsJ01Usk/view?usp=sharing) |
| clickbait_data.csv | ~32,000 labeled headlines (Kaggle - amananandrai) | 1.8 MB | Included in repo |
| reddit_final.csv | Final processed dataset with clickbait and reliability labels | 22 MB | Included in repo |

## Project Structure
```
├── Dsa_210_Project.ipynb   # Main notebook
├── clickbait_data.csv      # Clickbait labeled dataset
├── reddit_final.csv        # Final processed dataset
├── posts.csv               # Reddit dataset (too large for GitHub, download from Google Drive)
├── graphs/                 # EDA visualizations
│   ├── score_distribution.png
│   ├── source_reliability_distribution.png
│   ├── avg_upvote_by_reliability.png
│   ├── clickbait_distribution.png
│   ├── avg_upvote_by_clickbait.png
│   ├── clickbait_words.png
│   └── non_clickbait_words.png
├── requirements.txt        # Python dependencies
└── README.md
```

## How to Run
1. Clone the repository
2. Install dependencies:
```
pip install -r requirements.txt
```
3. Open `Dsa_210_Project.ipynb` in Google Colab
4. Download `posts.csv` from [Google Drive](https://drive.google.com/file/d/1yAV3VxUYPxhQ4cahfFNjIVLNJsJ01Usk/view?usp=sharing) and upload to your environment
5. Upload `clickbait_data.csv` to your environment
6. Run all cells top to bottom

## Methodology
1. **Data Cleaning** — Removed posts without URLs and internal Reddit links
2. **Domain Extraction** — Extracted news source domains from URLs
3. **Source Credibility** — Top 200 domains manually verified on Media Bias/Fact Check
4. **Clickbait Classifier** — Logistic Regression trained on 32,000 labeled headlines (96% accuracy)
5. **EDA** — Analyzed upvote/comment distributions and word patterns
6. **Hypothesis Testing** — Mann-Whitney U and Chi-square tests

## Findings
| Hypothesis | Result |
|---|---|
| Clickbait headlines receive more upvotes | ✅ Significant (p < 0.05) |
| Unreliable sources use more clickbait | ❌ Not significant (p = 0.5352) |
| Clickbait headlines receive more comments | ✅ Significant, but non-clickbait gets more comments |

## Author
Arda Kalyoncu
