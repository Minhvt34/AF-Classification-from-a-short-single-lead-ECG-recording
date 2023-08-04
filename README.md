# AF-Classification-from-a-short-single-lead-ECG-recording
This repos is to analysis Cardiologist-level arrhythmia based on paper source "Cardiologist-level arrhythmia detection and classification in ambulatory electrocardiograms using a deep neural network"


# The Physionet 2017 Challenge 

These instructions go through the training and evaluation of a model on the
[Physionet 2017 challenge](https://www.physionet.org/challenge/2017/) dataset.

Limitation: Due to restrictions apply to the availability of the training dataset, which was used under license from iRhythm Technologies, Inc.

## Data

To access to all files data from the challenge:

Access the files:

[Physionet 2017 base source](https://www.physionet.org/content/challenge-2017/1.0.0/#files-panel) dataset

Access the files using the Google Cloud Storage Browser here. Login with a Google account is required.
Access the data using the Google Cloud command line tools (please refer to the gsutil documentation for guidance): gsutil -m -u YOUR_PROJECT_ID cp -r gs://challenge-2017-1.0.0.physionet.org DESTINATION
Download the files using your terminal: wget -r -N -c -np https://physionet.org/files/challenge-2017/1.0.0/

To build the datasets run:

```
python ecg/examples/cinc17/buid_datasets.py -r "data_path"
```

## Training

Change directory to the repo root directory (`ecg`) and run

```
python ecg/train.py examples/cinc17/config.json -e cinc17
```

## Evaluation

Model performance will be evaluated using confusion matrix, AUC metric, ROC and PR curves.

