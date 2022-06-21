## Intro

Task description: Given survey results in the past 5 days in a specific state in the U.S., then predict the percentage of new tested positive cases on the 5th day.

The kaggle link: <https://www.kaggle.com/competitions/ml2022spring-hw1/overview>

## Data

- States (37, encoded to one-hot vectors)
- COVID-like illness(4)
  - *cli, ili, ...*
- Behavior Indicators(8)
  - *wearing_mask, travel_outside_state, ...*
- Mental Health Indicators(3)
  - *anxious, depressed, ...*
- Tested Positive Cases(1)
  - **tested_positive (this is what we want to predict)**

## Grading

- [ ] boss line: 0.86161
- [x] strong baseline: 1.05728
- [x] medium baseline: 1.49430
- [x] simple baseline: 2.28371

## 🧐 What I did

Finally, I achieved the strong baseline with Private(1.05047) && Public(1.01159). I used the following methods:

- I use `f_regression` in the `scikit-learn` package to choose the *important* features.
- I use `AdamW` instead of the default `SGD`.
- `nn.BatchNorm1d` to speed up learning.
- `nn.Dropout` to do regularization.

In my opinion, by trying different `random seed`, I may achieve better results.
