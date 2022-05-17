# Affective Text Individual Annotations
This repository includes the individual annotations for the SemEval-2017 Task 14: Affective Text.

The original aggregated data is available [here](http://web.eecs.umich.edu/~mihalcea/affectivetext/). The task is described in ["SemEval-2007 Task 14: Affective Text"](https://aclanthology.org/S07-1013.pdf) by Carlo Strapparava and Rada Mihalcea. The [original README](ORIGINAL_README.md) for that data is included in this repository.

This README describes the included disaggregated annotations from the Affective Text test set.

## Headlines
The news headlines that are annotated for six emotions and valence are included in [affectivetext_test.xml](affectivetext_test.xml). The xml file includes the headline text and an ID.

## Annotations
The annotations of the six annotators are included in the [Annotations directory](Annotations/). Each file corresponds to a single annotator. The annotation files follow the following format:

```
id  anger disgust fear joy sadness surprise valence
```
where
* id is the headline identifier from the xml file
* each of the six emotions are indicated using a score of [0, 100] (0 = the emotion is not present in the headline; 100 = the maximum amount of emotion is found in the headline)
* the valence is indicated using a score in the interval [-100, 100] where -100 means strongly negative, +100 means strongly positive, and 0 means neutral

### Reading annotation files
The text file format is simple and can be easily read in your programming language of choice. One simple way to read the data is with pandas:

```python
import pandas as pd
DATA_COLS = ["id", "anger", "disgust", "fear", "joy", "sadness", "surprise", "valence"]
FILENAME = "Annotations/F1.txt"
annotation_df = pd.read_csv(FILENAME, names=DATA_COLS, sep="\s", engine="python")
```

### Annotator Gender
This disaggregated data is being released along with a paper studying effects of annotator gender on annotation. Therefore, each annotator filename starts with M (male) or F (female) to indicate the gender of the annotator.
