

# General

## Safehouse Algorithm
The safehouse algorithm was used to identify if the adversary was conducting attack behavior to the safehouse. The data sources used from elasticsearch was:

1. "ifttt"
2. "persondetect"
3. webcam-pcap"
4. "safehouse-ap-devices"
5. "gammarf".

The data was to converted to a sequence of events and modeled to find a baseline behavior. If the future sequence of events deviated from baseline behavior, the algorithm would determine this behavior as an attack.

The models chosen is the apriori algorithm. This model was chosen for its robustness to outlier events and the capability to model a sequence of events. The algorithm was first introduced to assist in the feature reduction process. The next stage in this project is to validate multiple machine learning models.

### Note:
This code and algorithm were used for Proof of Concept. Please do not deploy this code into a production environment. This model can be used as a baseline for the model selection and validation process.

# Code to Run

### Steps:


Instructions

```
git clone https://github.com/sofwerx/safehouse-data-transformations.git

```

```
cd Docker
```

```
docker build -t safehouse .
```

```
docker run -ti --rm -e TZ=America/New_York -v /home/david/Documents/safehouse-algorithm:/home/david/Documents/safehouse-algorithm safehouse bash

```


```
cd /home/david/Documents/safehouse-algorithm/prod
```

```
cd /home/david/Documents/safehouse-algorithm/prod
```

```
python3 codetorun.py
```


# Access Data from Github

If you would like to train a new model please clone this repo https://github.com/sofwerx/safehouse-data.git .

The data in this repo is in JSON format. Each hit in the JSON files is an observation. I trained this model by treating each observation as an action and modeled a sequence of action.

Data to retrain the model provided in the Safehouse Algorithm Repo:

1. Select data sources listed in General
2. Standardize format for the time across JSON files
3. Concatenate all features for each observation keep time as a separate feature.
4. Append data sources and sort data by the standardized while keeping time feature.
