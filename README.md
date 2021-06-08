# Handwritten Text Recognition from an Image with Android Application
To store information from handwritten documents for future use is became a necessity nowadays. An easy way to store information is to capture images of handwritten documents and save them in image format.
This project uses android application for the text extraction from an image.
## Getting Started
Clone this project using below github url: https://github.com/hanumantmule/Handwritten-Text-Recognition_Android-APP

### Prerequisites

Python packages you need to install. The list of libraries and its version is added in requirement.txt file. 

* [NumPy](https://pypi.org/project/numpy/) - NumPy is an open-source numerical Python library.
* [pandas](https://pandas.pydata.org/) - Python Data Analysis Library.
* [matplotlib](https://matplotlib.org/) - Library for creating static, animated, and interactive visualizations.
* [seaborn](https://seaborn.pydata.org/) - Python data visualization library based on matplotlib.
* [nltk](https://www.nltk.org/) - Natural Language Toolkit 
* [sklearn](https://scikit-learn.org/) - Simple and efficient tools for predictive data analysis.
* [imblearn](https://pypi.org/project/imblearn/) - Imbalanced-learn is a python package offering a number of re-sampling techniques.
* [allennlp]() - NLP library for developing state-of-the-art deep learning models on a wide variety of linguistic tasks.
* [allennlp-models]() - Provides an easy way to download and use pre-trained models.
* [python_speech_features]() - This library provides common speech features for ASR including MFCCs and filterbank energies.
* [torch]() - PyTorch is a Python package that provides Tensor computation and Deep neural networks built.
* [wave]() -Read and write WAV files.
* [librosa]() - A python package for music and audio analysis.
* [tensorflow]() - Open source software library for high performance numerical computation.
* [re]() - A compendium of commonly-used regular expressions.
* [pyAudioAnalysis]() - Python library covering a wide range of audio analysis tasks.
* [eyed3]() - Python tool for working with audio files.
* [scipy]() - Scientific Library for Python

## Installing
Here we are using ```PIP``` which is a package manager for Python packages.

Note: If you have Python version 3.4 or later, PIP is included by default.
To install the all the dependencies for the project. Type below command in python console. 
```
pip install -r requirements.txt
```
This will install all the libraries mentioned in the requirements.txt file.

We have divided this project into **two** activities: 
1. **Model evaluation** and saving the model into the disk.

2. **Android Application** uses saved model --> A folder named as 'FreeOCR Android Application Code', contains the zip file of the application code. 

**Note:** User need to save the model using the step 1 and then android application will use the saved model.
## Steps involved in model evaluation
1. Download the IAM Database : [https://fki.tic.heia-fr.ch/databases/iam-handwriting-database](https://fki.tic.heia-fr.ch/databases/iam-handwriting-database)
2. 
3.
4.
5.

## Steps involved in android application setup
1. Open the 'model_save.py' file from the application folder.
2. Change the saved model file name and output tflite file name in the file.
2. Save the tflite model file.
3. Head over to the [Firebase Console](https://console.firebase.google.com/u/0/) and create a project. After that, you need to register your application with that project.

![Firebase console](https://github.com/hanumantmule/Handwritten-Text-Recognition_Android-APP/blob/main/Screenshots/App/1.png?raw=true)

4. Download the Google JSON file and place it in the app folder of your application. This file contains configurations that are specific to the project and app you just registered.

![Firebase console](https://github.com/hanumantmule/Handwritten-Text-Recognition_Android-APP/blob/main/Screenshots/App/2.png?raw=true)

5. The next step is to add the Firebase SDK to the application.
```
apply plugin: 'com.android.application'
apply plugin: 'com.google.gms.google-services'

dependencies {
  // ...

  implementation 'com.google.firebase:firebase-ml-model-interpreter:22.0.3'
}
```
6. Add the Google Services plugin to the App-level build.gradle file.
```
apply plugin: 'com.google.gms.google-services'
```
7. In the  App-level build.gradle file define the dependencies needed for this application.
```
dependencies {
    implementation platform('com.google.firebase:firebase-bom:26.2.0')
    implementation 'com.google.firebase:firebase-analytics'
    implementation 'com.google.firebase:firebase-ml-model-interpreter'

    implementation 'org.tensorflow:tensorflow-lite:2.3.0'
    implementation 'org.tensorflow:tensorflow-lite-support:0.0.0-nightly'
    
    ........
    
    }
```
8. Next, you need to upload your model to Firebase.

![deploy model](https://github.com/hanumantmule/Handwritten-Text-Recognition_Android-APP/blob/main/Screenshots/App/3.png?raw=true)

9. After this, you will be prompted to name and upload your model. Note that this is the name that you will use to download the model.

![deploy model](https://github.com/hanumantmule/Handwritten-Text-Recognition_Android-APP/blob/main/Screenshots/App/4.png?raw=true)

10. Now import the code to ```Android Studio``` and build the APK.

## How to use ?
1. Download the android application from the play store.
 [Link here](https://play.google.com/store/apps/details?id=com.bitshift.free.ocr)
2. Install the application.
3. Browse the images from the gallery or capture from the camera.
4. Save the extracted text into the text file.


![Home Page](https://github.com/hanumantmule/Handwritten-Text-Recognition_Android-APP/blob/main/Screenshots/App/app_home.png?raw=true)

## Results


## References
[1] https://pip.pypa.io/en/stable/reference/pip_install/  
[2] https://fki.tic.heia-fr.ch/databases/iam-handwriting-database  
[3] https://heartbeat.fritz.ai/custom-tensorflow-lite-model-on-android-using-firebase-ml-7cc78cd057ec      
[4] https://developer.android.com/

## Contributing

Please read [CONTRIBUTING.md](https://github.com/hanumantmule/Email_Classification/blob/main/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Authors

* **Hanumant Mule** 
* **Namrata Kadam** 

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details


