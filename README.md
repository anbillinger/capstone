# Module 5: Capstone
By Alex Billinger


## Process:
* Business Understanding: create a mode for speech prediction/recognition. Can be used to supply subtitles on videos, or voice-to-text applications
* Data Understanding: link to dataset: https://www.kaggle.com/mozillaorg/common-voice has phrases in audio, and text translations of each phrase
* Data Preparation: load audio data into python with pydub, break audio phrases into individual words by syllables, convert to numpy array. Normalize values, change target to ohe
* Modeling: will use neural network