# Negative Recommendation Engine

> "Don't show me what I like—hide what I hate."

A machine learning system that predicts user **aversion** (disgust) rather than preferences.

## The Concept

**Traditional Recommenders:** Optimize for clicks/views, create filter bubbles
**Negative Recommender:** Detects recoil behavior (pause-then-flee patterns) and blocks anxiety-inducing content

## Key Innovation: The Recoil Signal

| Behavior | Scroll Speed | Pause Duration | Pattern |
|----------|--------------|----------------|---------|
| Disinterest | Fast | None | Didnt look |
| Disgust | Very Fast | Brief (300-800ms) | Saw it, hated it, fled |
| Interest | Slow | Long | Actually reading |

## Dataset

- 6,000 interactions from 300 simulated users
- 7 content categories: politics, cute_animals, horror, cooking, tech, gossip, ads
- Target: behavior_type (disgust/disinterest/interest)

## Model Performance

- Algorithm: Random Forest Classifier
- Accuracy: ~85% distinguishing disgust from disinterest
- Most Important Feature: recoil_signal (pause-then-flee detection)

## How to Use

```python
from anti_recommender import NegativeRecommender
anti_rec = NegativeRecommender(model)
safe_content, blocked = anti_rec.filter_content(user_data, new_content)
```

## Files

- negative_recommendation_engine.ipynb - Full Colab notebook
- aversion_model.pkl - Trained model
- scroll_data.csv - Synthetic dataset

Created with Google Colab

