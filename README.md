# Module 5: Capstone
By Alex Billinger

## Purpose of Project:
Using audio files of spoken English, develop an algorithm that can predict what word is spoken in a particular audio clip

## Process:
* Business Understanding: speech recognition can be used to supply subtitles on videos, or voice-to-text applications
* Data Understanding: link to dataset: https://www.kaggle.com/mozillaorg/common-voice has phrases in audio, and text translations of each phrase
* Data Preparation:
	* Load audio data into jupyter notebook using pydub
	* Normalize audio volume
	* Cut silence out
	* Get syllable count from labeled phrase, split audio to create individual words
	* Convert quality to reduce samples and make all arrays the same size
	* Convert to numpy array
	* Normalize values with standard scaling
	* Find 1000 most common words, treat all others (approx 7000) as [UNRECOGNIZED] category
	* Binarize labels
* Modeling: neural network with supervised learning, using keras library

For an in depth description of my process, read my blog post here: https://anbillinger.github.io/training_speech_recognition

## Results:
No model has a high degree of accuracy. Given the type of data and number of data points, my computer simply did not have the processing power necessary to run all of the data at once, and definitely not enough to test for best parameters. There are over 1000 classes in the labels, which greatly added to complexity of model.
To create a useful model, it would require much greater processing power, probably would require parallel and distributed computing.
Best accuracy 16%, best validation accuracy 2% (training got as high as 49%, but that had extreme overfitting). Given that there are 1000 labels to try to predict, random guessing would be .1%, so the model is at least a large improvement from that baseline.

## Contents of Repo:
### Note: no "Data" folder present, as data is too large for github
### Jupyter Notebooks:
* EDA: Exploring data, testing splitting process, listening to sound to find minimum quality
* Preprocessing: add syllables column to original spreadsheet. Using this data and audio files, it processes data as described in "Data Preparation" through conversion to numpy array. It saves this data as new spreadsheets. Only able to process 5000 lines at a time, because of computing power.
* Model Testing: using 5000 lines of data (approx 47000 words, or about 2.5% of total data set), test a variety of parameters for keras based neural network model
* Modeling with more data: uses 15000 lines of data ( approx 141000 words, or about 7.5% of total data set) to improve model determined in Model Testing
### slides.pdf: 
images and findings in context of presentation