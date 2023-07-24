# Internetless Translator
The aim of this project is to build an efficient translator to put on a rasberry pi which will be in a small case with a few buttons. It should be all local since the goal is to not use internet.

To do so we use 3 differents type of model in a pipeline as follow:

  - Audio-to-Text model to transform the audio as an input for the next model
  - Text-to-Text model to translate our text from the previous model to text in the target language
  - Text-to-Speech model to finally get an answer from our translator as an audio

## Introduction:

First of all we need to put some bases on the project. The goal is to build a translator but several questions remains:
- What languages do we translate?
- Do we try using one model by part of the pipeline or do we chose the model to use according to the language? This also means that it will be necessary to use a bunch of models for each part of the process.
- How are the pipeline designed?

[Paragraph to modify as the project grows]

The language translated will be: english, french, german, russian, spanish, italian, japanese, korean, chinese

## 1st model:

