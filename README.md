# Internetless Translator
The aim of this project is to build an efficient translator to put on a rasberry pi which will be in a small case with a few buttons. It should be all local since the goal is to not use internet.
Also an app on the phone will be designed so we can communicate with the case. The use of the device will be through the case that will give us an answer via its speaker and the app will be useful for us to change parameters of the device such as the origin language and the target one. The app will also be useful for checking the log of the output (the answer will be stored on the SDcard as a text).
Another solution would be to use the case only as an accessory to run the model for translating. This would imply transferring the audio file from the phone to the case and the audio and txt file with the translation from the case to the phone. This might result in quite a time eater process but it is worth trying at first.

To do so we use 3 differents type of model in a pipeline as follow:

  - Audio-to-Text model to transform the audio as an input for the next model
  - Text-to-Text model to translate our text from the previous model to text in the target language
  - Text-to-Speech model to finally get an answer from our translator as an audio

## Introduction:

First of all we need to put some bases on the project. The goal is to build a translator but several questions remains:
- What languages do we translate?
- Do we try using one model by part of the pipeline or do we chose the model to use according to the language? This also means that it will be necessary to use a bunch of models for each part of the process.
- How is the case designed? 

[Paragraph to modify as the project grows]

The language translated will be: english, french, german, russian, spanish, italian, japanese, korean, chinese

Here we want to use at first the model from Whisper to get the audio and to translate it. It should help us do both the first and second part of the pipeline with only using this model. This part might be handled with data as a stream that would not be stored until the end of the 2 first parts of the pipeline. This would allow us to optimize the time used for translation by giving the possibility to make 1st and 2nd part at the same time. For the last part ElevenLabs will be used at first for testing and another model will be taken on according to what's found on GitHub or HuggingFace.

There's two possibilities:
- If the whole interface is on the app,  the communication will be through the phone and not the case. It means that the case will be much minimalist with no speaker and no mic.
- If the app is only for modifying the languages and checking the log, we want to design a case with a speaker and a mic. Such device will be a little more energy consuming so we might also take it into account when using the battery. This configuration will also need a button for beginning the translation.
  
In the end what's needed whatever the possibility will be: a power button, the battery, a place in the case to setup the charging, the rasberry pi and an SDcard

