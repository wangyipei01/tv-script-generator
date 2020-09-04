This project includes my solution for TV script generation project in Udacity deep learning course. Instructions for set up can be found in its [original repo](https://github.com/udacity/deep-learning-v2-pytorch/tree/master/project-tv-script-generation)

# Project Overview

This project builds a RNN model training on 9 seasons of [Seinfeld dataset](https://www.kaggle.com/thec03u5/seinfeld-chronicles#scripts.csv) to generate "fake" TV script.

# Model Details
## Data Preprocessing
There are a few steps we take to prepare the training data from the raw TV script:
* tokenize punctuation (convert punctuation as an individual word)
* collect vocabulary of words from the data set and convert each word into a int index in the vocabulary
* Given a sequence length, the input features are the number of sequence length words, and the prediction target is the word after.

## Architecture
The model is implemented through pytorch, constructed by an embedding layer, a LSTM layer with 2 hidden layers, and a fully connected linear layer to generate the final output.

## Loss Function 
Cross Entropy.

# Example Generated Script
We use "jerry" as start word and use our model to generate a script with length of 400 words to give people more idea about how well the model is performing currently:

```
jerry: 13.

hoyt: so?

jerry: oh, come on.

jerry: hey!

hoyt: so what are you doing?

kramer: well, it's a very dangerous wind.

hoyt: and basically the defendants- less frosting.

chiles: objection overruled?

george: i was carjacked.

kramer: hey, what do you know?

kramer: yeah yeah, well...

hoyt: so, essentially, you know what?

george: yeah, yeah.

hoyt: and you don't want to be the only thing i've ever had, but i was on the plane.

george: i think i know how to make it out.

chiles: so what?

george: i don't know what it means.

jerry: you know, this is elizabeth 4th.

george: i know.

hoyt: so, you know, i don't want to talk to jill about this testimony.

jerry: what?

hoyt: this flavor is killing me.

hoyt: what do you think?

elaine: no, it's not.

jerry: what?

jerry: i don't want to talk to you.

george: what?

hoyt: and the judge is a saab-- nguh war- absorption- absorption?!

george: no.

hoyt: no, no, no. no, no, no. no. donald, you know, the bubble boy is the nature- tub.

[new witness: police detective].

hoyt: so, what do ya mean?

jerry: no. i can't believe that.

[new witness: police detective], 000 crespi?

hoyt: no further questions?

chiles: i think it's a saab. i was wondering if you can be a kid.

george: i can't.

chiles: you know what?

chiles: objection stu.

george: what?

jerry: oh, yeah, yeah. i was carjacked, and i was in
```

As shown above, most of the sentences are complete and makes sense. It does look like tv script structurally, though many of the conversation turns look weird and far from a real conversations on TV.



