<div align="center">
  
[1]: https://github.com/Pradnya1208
[2]: https://www.linkedin.com/in/pradnya-patil-b049161ba/
[3]: https://public.tableau.com/app/profile/pradnya.patil3254#!/
[4]: https://twitter.com/Pradnya1208


[![github](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/c292abd3f9cc647a7edc0061193f1523e9c05e1f/icons/git.svg)][1]
[![linkedin](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/9f5c4a255972275ced549ea6e34ef35019166944/icons/iconmonstr-linkedin-5.svg)][2]
[![tableau](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/e257c5d6cf02f13072429935b0828525c601414f/icons/icons8-tableau-software%20(1).svg)][3]
[![twitter](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/c9f9c5dc4e24eff0143b3056708d24650cbccdde/icons/iconmonstr-twitter-5.svg)][4]

</div>

# <div align="center">Visualizing data using the embedding projector in Tensorboard</div>
<div align="center"><img src = "https://github.com/Pradnya1208/Visualizing-data-using-the-embedding-projector-in-Tensorboard/blob/main/outputgif.gif" width="80%"></div>


## Overview:
Using the TensorBoard Embedding Projector, you can graphically represent high dimensional embeddings. This can be helpful in visualizing, examining, and understanding your embedding layers.

## Dataset:
[IMDB reviews](https://www.tensorflow.org/datasets/catalog/imdb_reviews)<br>

We will be using a dataset of 25,000 IMDB movie reviews, each of which has a sentiment label (positive/negative). Each review is preprocessed and encoded as a sequence of word indices (integers). For simplicity, words are indexed by overall frequency in the dataset, for instance the integer "3" encodes the 3rd most frequent word appearing in all reviews. This allows for quick filtering operations such as: "only consider the top 10,000 most common words, but eliminate the top 20 most common words".

As a convention, "0" does not stand for any specific word, but instead is used to encode any unknown word. Later in the tutorial, we will remove the row for "0" in the visualization.

## Implementation:

**Libraries:**  `NumPy`  `pandas` `sklearn`  `Matplotlib` `tensorflow` `keras`


### Keras embedding layer:
A Keras Embedding Layer can be used to train an embedding for each word in your vocabulary. Each word (or sub-word in this case) will be associated with a 16-dimensional vector (or embedding) that will be trained by the model.
```
# Create an embedding layer.
embedding_dim = 16
embedding = tf.keras.layers.Embedding(encoder.vocab_size, embedding_dim)
# Configure the embedding layer as part of a keras model.
model = tf.keras.Sequential(
    [
        embedding, # The embedding layer should be the first layer in a model.
        tf.keras.layers.GlobalAveragePooling1D(),
        tf.keras.layers.Dense(16, activation="relu"),
        tf.keras.layers.Dense(1),
    ]
)
```
### Saving the data for tensorboard:
TensorBoard reads tensors and metadata from the logs of your tensorflow projects. The path to the log directory is specified with log_dir below. For this tutorial, we will be using /logs/imdb-example/.

In order to load the data into Tensorboard, we need to save a training checkpoint to that directory, along with metadata that allows for visualization of a specific layer of interest in the model.
<br>

Checkout the [Notebook](https://github.com/Pradnya1208/Visualizing-data-using-the-embedding-projector-in-Tensorboard/blob/main/docs/tensorboard_projector_plugin.ipynb) for implementation details.

### Run tensorboard against on log data we just saved:
```
%tensorboard --logdir /logs/imdb-example/
```


The TensorBoard Projector is a great tool for interpreting and visualzing embedding. The dashboard allows users to search for specific terms, and highlights words that are adjacent to each other in the embedding (low-dimensional) space.



### Learnings:
`Word embeddings` `embedding layers` `tensorboard` 






## References:
[Word embeddings](https://www.tensorflow.org/text/guide/word_embeddings?hl=en)

### Feedback

If you have any feedback, please reach out at pradnyapatil671@gmail.com


### 🚀 About Me
#### Hi, I'm Pradnya! 👋
I am an AI Enthusiast and  Data science & ML practitioner


[1]: https://github.com/Pradnya1208
[2]: https://www.linkedin.com/in/pradnya-patil-b049161ba/
[3]: https://public.tableau.com/app/profile/pradnya.patil3254#!/
[4]: https://twitter.com/Pradnya1208


[![github](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/c292abd3f9cc647a7edc0061193f1523e9c05e1f/icons/git.svg)][1]
[![linkedin](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/9f5c4a255972275ced549ea6e34ef35019166944/icons/iconmonstr-linkedin-5.svg)][2]
[![tableau](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/e257c5d6cf02f13072429935b0828525c601414f/icons/icons8-tableau-software%20(1).svg)][3]
[![twitter](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/c9f9c5dc4e24eff0143b3056708d24650cbccdde/icons/iconmonstr-twitter-5.svg)][4]



