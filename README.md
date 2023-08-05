# PyChorus Song Chorus Detection

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

This repository contains code that uses the PyChorus library to detect the main chorus part of a song. The input is a full song in audio format, and the output is the timestamp where the main chorus section starts.

## Introduction

In this project, we've utilized the PyChorus library to automatically detect the main chorus part of a song. The code processes the audio input and identifies the timestamp at which the chorus starts. This can be useful for various applications such as music analysis, automatic song tagging, and more.

## Installation

1. Clone this repository:

    ```bash
    git clone https://github.com/Amankd777/Chorus-Detection-using-Pychorus.git
    cd Chorus-Detection-using-Pychorus
    ```

2. Install the required dependencies:

    ```bash
    pip install pychorus
    ```

## Usage

1. Provide the input song in audio format (e.g., MP3) and update the file paths in the code.

2. Run the script:

    ```bash
    python chorus_detection.py
    ```

    The output will provide the timestamp (in seconds) where the main chorus section of the song starts.

## Chorus Detection

The chorus detection is performed using the `find_and_output_chorus` function from the PyChorus library. This function takes an audio file as input and returns the start time of the main chorus section.

## Similarity Analysis

The code also demonstrates how to create a chroma representation of the input audio and perform similarity analysis using time-time and time-lag similarity matrices.

```python
from pychorus import create_chroma
from pychorus.similarity_matrix import TimeTimeSimilarityMatrix, TimeLagSimilarityMatrix

chroma, _, sr, _ = create_chroma("input_song.mp3")
time_time_similarity = TimeTimeSimilarityMatrix(chroma, sr)
time_lag_similarity = TimeLagSimilarityMatrix(chroma, sr)
