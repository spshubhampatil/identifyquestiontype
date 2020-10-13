# Identify-Question-Type
Given a question, the aim is to identify the category it belongs to. The four categories to handle for this assignment are : Who, What, When, Affirmation(yes/no). Label any sentence that does not fall in any of the above four as "Unknown" type.

### Requirements for running `train.py` and `run.py` :
Python packages :
> python >= 3.5 \
> keras = 2.0.8 \
> tensorflow = 1.1.0\
> numpy = 1.13.1\
> pandas = 0.20.2\
> sklearn = 0.18.1\
> argparse\
> re\
> json\
> random\
> pickle

Others:
> This program uses GLoVe pretrained model for word embedding so you need to download `glove.42B.300d.txt` from [here](http://nlp.stanford.edu/data/glove.42B.300d.zip) then save it and update `GLOVE_EMBEDDING_PATH` path in `config.json` accordingly.

`config.json` file is configuration file which contains information regarding model configuration with some other program related configuration.
```
{
  "input_file":"label.txt",
  "model_json_file": "model.json",
  "weights":"model_checkpoints.h5",
  "GLOVE_EMBEDDING_PATH": "E:/Projects/Word2Vec/glove.42B.300d.txt",
  "VECTORIZER_PATH": "vectorizer.pk",
  "LABEL_ENCODER_PATH":"label_encoder.pk",
  "MAX_NB_WORDS":20000,
  "MAX_SEQUENCE_LENGTH":30,
  "EPOCHS":20,
  "BATCH_SIZE":128,
  "LSTM_OUT":196,
  "VALIDATION_SPLIT": 0.20,
  "seed": 2017
}

```
All the json parameters above are self explanatory

## For Training
> python train.py

## For Testing
> python run.py  -q="What time does the train leave ?"

You need to pass your question with `-q` argument from terminal/command prompt . And output is printed at terminal/cmd like this `Question Type : when`

## Analysis
`analysis.ipynb` contains the initial classification analysis script, where I code different classifiers and compare them with each other, then select best model for training and testing. \
For running `analysis.ipynb` you need all requirements mentioned above and `nltk = 3.2.1` with all english language add-on downloads.
To dowload `nltk` related add-on downloads type 
```
import nltk
nltk.download()
```
at python console. \
For more info regarding `nltk` please visit [here](http://www.nltk.org/index.html).
