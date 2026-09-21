# Facilitator Guide — Build the Future ML Bootcamp
 
> **Run this yourself.** This guide is for anyone who wants to deliver this curriculum at their own organisation. Everything here is under a CC BY 4.0 licence — you can adapt, translate, and redistribute it as long as you credit the original authors (see CITATION.cff).
 
---
 
## Overview
 
**Build the Future** is a five-day machine learning bootcamp for teenagers aged 13–17 with no prior coding experience. Participants go from zero to a deployed machine learning product in five days, guided through the full CRISP-DM workflow. The 2026 cohort built **TrendCaster**, a live XGBoost classifier that predicts the trajectory of a short video before it is posted.
 
| Detail | Value |
|---|---|
| Duration | 5 days (approx. 4–5 hours per day) |
| Audience | Teenagers aged 13–17, no coding experience required |
| Platform | Google Colab (free, browser-based, no installation) |
| Language | Python |
| Cohort size | 10–30 participants recommended |
| Delivery style | Instructor-led with group project work |
 
---
 
## What Participants Learn
 
- **Day 1 — Introduction to AI and Data:** What AI is, how machines learn, data literacy basics, first Colab notebook
- **Day 2 — Supervised and Unsupervised Learning:** Classification with Decision Trees, clustering with K-Means, the elbow method, evaluating models (accuracy, precision, recall, F1)
- **Day 3 — CRISP-DM and Feature Engineering:** The data science workflow end to end, cleaning messy data, feature selection, avoiding data leakage
- **Day 4 — Model Selection and Deployment:** Comparing Logistic Regression, Random Forest, and XGBoost; choosing the best model; deploying a Gradio app to Hugging Face Spaces
- **Day 5 — Pitch Your MVP:** Groups present their own data projects to a panel; celebration and certificates
---
 
## Kit and Room Requirements
 
### Per participant
- A device with a browser (laptop or tablet; Chromebooks work fine)
- A Google account (or access to a parent/guardian's Google account for Colab)
- Stable internet connection
### For the room
- A projector or large display the group can see
- Whiteboard or flip chart for live sketching
- Printed or digital copies of each day's slides (provided in `/slides/`)
- Sticky notes for the icebreaker and ideation activities (optional but helpful)
### Facilitator machine
- Laptop connected to the projector
- Google account logged in to Colab
- All notebooks pre-run at least once before the session so outputs are cached
---
 
## Software and Accounts to Set Up (Before Day 1)
 
1. **Google Colab** — no installation; just a Google account. Ask participants to sign in on Day 1.
2. **Hugging Face** — free account at huggingface.co. Needed on Day 4 for deployment. Create accounts as a group activity at the start of Day 4.
3. **GitHub** — the curriculum website and notebooks are hosted at github.com/creedaberdeen/creed-ml-bootcamp. No GitHub account is needed by participants.
4. **Gradio** — installed inside the Colab notebook with `pip install gradio`. No separate setup.
---
 
## Day-by-Day Facilitator Notes
 
### Day 1 — Introduction
- Open with an icebreaker: *"Name one thing you think AI can't do — and one thing you think it already does."* Write answers on the board and revisit at the end of the week.
- Keep the theory short. The goal is to get everyone into a running notebook within the first 45 minutes.
- Common issue: participants who share a Google account with a parent may have Drive storage limits. Have them use "Connect to a new runtime" if they see quota errors.
- Close the day by showing a live AI tool (image generator, chatbot, recommendation system) — it sets the tone for what they are building toward.
### Day 2 — Supervised and Unsupervised Learning
- Walk through the supervised section cell by cell before splitting into groups.
- When you reach the elbow plot: ask the group *"What do you notice about the curve?"* before revealing k=4. The discovery moment matters more than the answer.
- The unsupervised section takes longer than it looks. If you are running short on time, skip the scaling explanation and come back to it on Day 3.
- Speaker note approach used in the 2026 cohort: facilitators spoke relationally from the class experience rather than reading scripted notes. Slides contain the structure; the narrative came from the room.
### Day 3 — CRISP-DM and Feature Engineering
- Start with the CRISP-DM diagram and ask participants to label which stage they were at on Day 2.
- The leakage discussion is the most important conceptual moment of the week. Spend time on it. *"Why can't we use likes and shares to predict whether a video will trend?"* is the question that unlocks it.
- Good check: ask participants to look at the correlation table and tell you which features they would exclude, and why, before you reveal the answer.
- If a group finishes early, point them to the bonus dataset cards in the notebook.
### Day 4 — Model Selection and Deployment
- Model comparison table should be filled in live with the group before you show the pre-built one. Let them vote on which model to deploy.
- Deployment section is 10–15 minutes. It is a guided DIY: show the Hugging Face Spaces UI, walk through the file structure (`app.py`, `requirements.txt`, the saved model), and let them click "Deploy". The product moment — a live URL the group can share with their parents — is the payoff for the week.
- If a participant's Space fails to build, the most common cause is a `gradio` / `huggingface_hub` version mismatch. Pin versions in `requirements.txt`:
```
  gradio==3.50.2
  huggingface-hub==0.19.4
  scikit-learn==1.3.2
  xgboost==2.0.2
  pandas==2.1.3
```
 
### Day 5 — Pitch Your MVP
- Groups need their dataset, a short slide deck (3–5 slides), and a one-minute demo.
- Judging criteria used in 2026: Clarity of problem statement, quality of data exploration, honesty about model limitations, creativity of presentation.
- Certificates can be printed or sent digitally. The 2026 cohort received a group photo and a LinkedIn-shareable graphic.
- Close with the icebreaker revisit from Day 1: *"Has your answer changed about what AI can't do?"*
---
 
## Adapting This Curriculum
 
You are free to adapt this curriculum under CC BY 4.0. A few things worth knowing:
 
- **Shorter format:** Days 1–3 work well as a standalone three-day introduction. Day 4 (deployment) can be run as a standalone half-day workshop for a group that has already done the basics.
- **Older audience:** For university students or adult learners, replace the TikTok/YouTube dataset with a domain-relevant dataset for your audience (health, finance, retail). The CRISP-DM structure stays the same.
- **No installation required:** All notebooks can be downloaded and run easily with google collab. The Gradio deployment section would need to be replaced with a local demo.
- **Translated versions:** If you translate the slides or materials, please share your version back to the repository so others can benefit.
When you publish or present work based on this curriculum, please cite it using the metadata in `CITATION.cff`.
 
---
 
## Repository Structure
 
```
creed-ml-bootcamp/
├── index.html              # Curriculum website (GitHub Pages)
├── CITATION.cff            # Citation metadata
├── LICENSE                 # CC BY 4.0
├── README_FACILITATOR.md   # This file
├── assignments/
│   └── licklider_1960.pdf  # Day 2 reading assignment
├── data/
│   ├── trendcaster_dataset.csv       # Main dataset used in Day 3 and Day 4
│   └── trendcaster_data_dictionary.csv  # Field definitions for the dataset
└── slides/
    ├── day1.pptx
    ├── day2.pptx
    ├── day3.pptx
    └── day4.pptx
 ---
 
## Citing This Work
 
If this curriculum has been useful to you, please cite it:
 
> Olabode, O. F., Oroboade, A. J., & Akindele, Q. (2026). *Build the Future: A Five-Day Machine Learning Bootcamp for Teenagers* (v1.0.0). CREED Aberdeen / RCCG Fountain of Love Aberdeen. [https://doi.org/10.5281/zenodo.22883648].
 
A machine-readable citation is available in `CITATION.cff`.
 
---
 
## Contact
 
Questions about the curriculum or delivery: **creed.aberdeen@gmail.com**
 
The full project notebook (EDA, leakage analysis, model comparison, feature importance) is available on request from Ayodeji Oroboade.
 
---
 
*CREED Aberdeen | RCCG Fountain of Love Aberdeen (Charity No: SC031429) | Aberdeen, Scotland*
