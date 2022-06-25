## Intro

1. Data Preprocessing: Extract MFCC features from raw waveform (already done by TAs!)
2. Classification: Perform framewise phoneme classification using pre-extracted MFCC features

The kaggle link: <https://www.kaggle.com/competitions/ml2022spring-hw2/overview>

## Data

[LibriSpeech](https://www.openslr.org/12/)

- Each frame only contains `25` ms of speech. Usually, a phoneme will span several frames.

- Training: `4268` preprocessed audio features with labels (total `2644158`
  frames)

- Testing: `1078` preprocessed audio features (total `646268` frames)

- Label: `41` classes, each class represents a phoneme

> The dataset is too big to upload to the github.

## Grading

- [ ] boss line: 0.82324(sequence-labeling(using RNN))
- [x] strong baseline: 0.75028(concat n, batchnorm, dropout, add layers)
- [x] medium baseline: 0.69747(concat n frames, add layers)
- [x] simple baseline: 0.45797(sample code)

## 🧐 What I did

Finally, I achieved the strong baseline with **Private(0.75510) && Public(0.75773)**. I used the following methods:

- `nn.BatchNorm1d` to speed up learning.
- `nn.Dropout` to do regularizations.
- Add more hidden layers. Trust deep network : )
- Hyperparameters tuning. I found that the `concat_nframes` will have a greater impact on the training results. 

The training loss and validation loss are still decreasing. I may get better results if I increase the `epochs`. But I am satisfied with passing the strong baseline though.
