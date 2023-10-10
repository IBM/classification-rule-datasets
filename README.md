# About Binary Classification Rule Datasets Collection (BCRD)

The Binary Classification Rule Datasets Collection (BCRD) serves as a benchmark designed to facilitate the learning of expressive rules in binary classification tasks.

## About Data collection methodology

Datasets are created by applying ground truths on randomly generated features.

For the balanced datasets, they are generated randomly with the same ground truth as unbalanced datasets.
Then, they are upsampled until the minority class represents half of the goal dataset size and appropriate number of majority class are randomly removed.

### Description of the data

Datasets are divided into 3 main categories :
- flat data (non-sequential)
- sequential data
- datasets that combined flat data and sequential data.

Dataset names consist of the dataset name group and the number of the dataset.

|     Type     |  Dataset Group Name  | Description                                                                                                                                                                                                |
|:------------:|:--------------------:|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     flat     |          sl          | Simple Logical Rules. 10k instances composed of 10 binary features $F_0,\dot,F_9$.                                                                                                                         |
|  sequential  |          st          | Short-term dependency Rules on Sequences. 10k sequences of length 7 composed of 10 binary features $F_{0}, \dots, F_{9}$                                                                                   |
|  sequential  |          lg          | Rules with Local and Global patterns on Sequences. 1000 sequences of length from 4 to 14 composed of letters (A to F)                                                                                      |
|  sequential  |          sa          | Rules with Aggregates. 6000 sequences of length from 4 to 14 composed of 10 numerical features.                                                                                                            |
|  seq & flat  |          sf          | Rules on both sequential and flat data. 6000 elements composed of 11 features. 8 features $F_i$ are sequences of length from 4 to 14. 3 features $FF_j$ are non sequential (flat) (2 numerical, 1 binary). |


In each dataset folder there is a data.csv file and a rule.txt file.

```
datasets/
  -flat/
    -dataset_name/
      - data.csv
      - rule.txt
    -...
  -sequential/
  -sequential_and_flat/
-README.md
```              

### Usage

```python
import pandas as pd
path = './datasets/flat/sl_1/data.csv'
df = pd.read_csv(path)
```

## License
CC-BY-4.0, detailed LICENSE is available [here](https://github.com/IBM/synth-sequential-datasets/blob/main/LICENSE.txt).