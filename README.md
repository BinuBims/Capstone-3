# CAN YOU PREDICT THE ARTISTS BASED ON THEIR PAINTING STYLE?

<p align="center">
<img src="data/readme/header.jpg" />
</p>

## Introduction
Painting is all about the expression of ideas and emotions, with the creation of certain aesthetic qualities. The elements of this language—its shapes, lines, colours, tones, and textures—are used in various ways to produce sensations of volume, space, movement, and light on a flat surface. These elements are combined into expressive patterns in order to represent real or supernatural phenomena, to interpret a narrative theme, or to create wholly abstract visual relationships. Three of the most recognizable images in Western art history are paintings: Leonardo da Vinci’s Mona Lisa, Edvard Munch’s The Scream and Vincent van Gogh’s The Starry Night. These three art works are examples of how painting can go beyond a simple mimetic function, that is, to only imitate what is seen. The power in great painting is that it transcends perceptions to reflect emotional, psychological, even spiritual levels of the human condition. BUT WAIT A SECOND? How accurate you can predict the artist based on a given painting. At least for me, not that accurate unless I have seen all the paintings and memorize which of them belong to which artist. So, I decided to build a machine learning model to predict the artist based on their painting style.

## Data
The data set, I have fed into my convolutional neural network(CNN) came from kaggle (https://www.kaggle.com/ikarus777/best-artworks-of-all-time). I just want to take a moment and thanks the person for doing all the hard work, collecting those paintings and making this dataset widely available on kaggle. This data set is about paintings from 50 different artists, and data is not evenly spread out between each artists. So, I decided to filter out only 11 different artists who had more than 200 paintings. Why 200? It is about right amount of data to do transfer learning.

## Workflow
### Let's start with my first model

I have used 4 convolutional layers and two dense layers in my first model and ran it for 100 epochs. Validation loss and training loss get diverged as the model continue to learn predicting training data. This is a sign of overfitting. After a certain point, model start getting good at predicting training data but not the validation data. Final test accuracy was at 72 after 100 epochs and quite promising. In the next model, I focus on regularizing my model to prevent overfitting. 

### Second model
<p align="center">
  <img src="data/Images/2nd model.png" width="400">
  <img src="data/Images/2ndgraph.png" height="400">
</p>

I have reduced the learning rate from .001 to .0001, and included 0.001 of L2 normalization to the second from the last dense layer. I also add 2 more dense layers to make the model more flexible. After 30 epochs, I kind of end up getting the same result as validation accuracy wonders around 70's. Final test accuracy endup being 73. I have seen just a little progress in the second model, but I was not really happy with results I am getting.

### conclusion:
It seems like my model start overfitting after a certain number of epochs. I have regularized my model to be more flexible, but have not seen any progress. I was looking at what I can do next. First things, that came to mind was that I do not have enough data to deal with in the training dataset(100 images per species). Unfortunately, there was nothing I could do about that. Then, I went back to see my actual data, and found out that the data is not always about a picture of one monkey. Some pictures are about bunch of monkeys. Then, I start isolating pictures of one monkey.



 BatchNormalization layer will run in inference mode, and will not update its mean and variance statistics.
