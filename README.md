
# Safehouse Algorithm
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
