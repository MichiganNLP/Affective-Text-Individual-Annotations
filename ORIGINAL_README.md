# AFFECTIVE TEXT 
_This file contains the original README from Semeval 2007 Task 14_

Semeval 2007 task  
Carlo Strapparava, Rada Mihalcea


The "Affective Text" task focuses on the classification of emotions
in news headlines, and is meant as an exploration of the connection
between emotions and lexical semantics. Headlines typically consist 
of a few words and are often written by creative people with the 
intention to "provoke" emotions, and consequently attract the readers' 
attention. These characteristics make this kind of data particularly 
suitable for use in an automatic emotion recognition setting, as the 
affective/emotional features (if present) are guaranteed to appear 
in these short sentences. 


TASK ORGANIZATION

The structure of the task is as follows:

    * Corpus: News headlines, extracted from news web sites (such as 
      Google news, CNN) and/or newspapers.

    * Objective: Provided a set of predefined emotion labels (e.g. 
      joy, fear, surprise), classify the titles with the appropriate 
      emotion score and/or with a valence (positive/negative) score. 

The emotion annotation and the valence labeling are regarded as two 
separate subtasks, and therefore a team can choose to participate in 
only one or both annotation tasks.

The task is carried out in an unsupervised setting, and consequently no 
training data is provided. We want to emphasize the study of emotion 
lexical semantics, and avoid biasing the participants toward simple "text 
categorization" approaches. Nonetheless supervised systems will be 
not precluded from the participation, and in such cases the participating 
teams will be allowed to create their own supervised training sets.


TIMELINE

The timeline of the task will follow the general Semeval-2007 timeframe:

    * [three weeks before the deadline]: a development/trial data set 
      of approximately 250 headlines annotated for emotions is provided
    * [one week before the deadline]: the data set of approx. 1,000 news 
      headlines is provided
    * [deadline]: the participants submit the headlines annotated with 
      emotion labels and/or a valence indication (positive/negative). 

As done in previous Senseval evaluation, the participating teams are 
free to choose their own submission deadline, as long as it falls 
within the window of time imposed by Semeval-2007. 


DATA FORMAT

The headlines are provided in an SGML formatted file, with one headline
per line that also includes the id of the headline.

The emotions and the valence indicators are provided in separate files.

Each line in the emotion annotations file follows the format:
   
          id  anger disgust fear joy sadness surprise 

where:

- the id is the headline identifier from the SGML formatted file

- each of the six emotions are indicated using a score of [0, 100]
(0 = the emotion is not present in the headline; 100 = the maximum 
amount of emotion is found in the headline)
  

Each line in the valence annotations file follows the format:
   
          id valence

where:

- the id is the headline identifier from the SGML formatted file

- the valence is indicated using a score in the interval [-100, 100]
where -100 means strongly negative, +10O means strongly positive, and
O means neutral.


SUBMISSION FORMAT

Each team can choose the task in which they want to participate: 
the annotations of emotions, the annotation of valence, or both.

A system participating in the emotion annotation task should 
submit a file similar to the emotion gold standard file, with 
each line including the id of the headline and a score in the 
[0, 100] range for each of the six emotions. 

A system participating in the valence annotation task should 
submit a file similar to the valence gold standard file, with
each line including the id of the headline and a score in the
[-100, 100] range indicating the valence.

Note that systems that choose to provide only a coarse-grained 
scoring are free to do so, by using a binary labeling for the
emotions (0 = absence; 100 = presence), and three labels for 
the valence (-100 = negative; 0 = neutral; 100 = positive)

EVALUATION

The evaluation will be conducted using a measure of correlation
between the system scores and the gold standard scores, averaged
over all the headlines in the data set (and averaged over the 
six emotions for the emotion annotation subtask). 

We also plan to run a coarse-grained evaluation, where each 
emotion score will be mapped to a 0/1 value by dividing the 
[0,100] interval in two, and each valence will be mapped to 
a -1/0/1 value, with [-100,-50] assigned to -1, (-50,50) 
assigned to 0, [50,100] assigned to 1. 


COMMENTS AND SUGGESTIONS

Since this is a new task with a new evaluation scheme, we 
encourage comments and suggestions from the task participants.
Please email us at rada at cs.unt.edu and strappa at itc.it.

