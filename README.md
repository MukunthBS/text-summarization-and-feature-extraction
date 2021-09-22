# text-summarization-and-feature-extraction
## Goals
<i><b>Natural language processing</b></i> includes many different techniques for interpreting human language,
ranging from statistical and machine learning methods to rules-based and algorithmic approaches.
NLP is important because it helps resolve ambiguity in language and adds useful numeric structure
to the data for many downstream applications, such as speech recognition or text analytics.

By understanding how NLP has been of significant importance in solving real-world problems, we
are aiming to use it in the <i><b>healthcare industry</b></i> and to build a model that can extract features and
automatically summarize several drug reviews by several patients more accurately.

As this is a sensitive dataset to deal with, relevancy is a key factor that we are concerned about.
And to get that we are building and <i><b>comparing with several techniques</b></i> and finding the most
appropriate one.

## Implementation
Firstly, based on a research paper we used <i><b>unsupervised k-means</b></i> to summarize reviews in an
extractive way. In this method, we preprocessed the reviews by grouping all reviews drug-wise
and remove symbols, stop-words, and other unnecessary noises in the data and then apply standard
k-means clustering algorithm and print the top n selected reviews according to the minimum
Euclidean distance given by the algorithm. This seems to give promising results but still, we want
to hyper-tune this algorithm to improve its results for more relevancy.

After clustering using the k-means algorithm, we use <i><b>Agglomerative clustering</b></i> to find important
sentences from the review. Agglomerative clustering is the most common type of hierarchical
clustering used to group objects in clusters based on their similarity. In each step of the algorithm,
the initial clusters are combined with their nearest neighbor until the required number of clusters
is reached. We do this to find the important sentences which were not detected by the k-means
algorithm.

For feature extraction, we use modules like <i><b>RAKE</b></i> and <i><b>BERT</b></i> models to extract features. Rapid
Automatic Keyword Extraction (RAKE) is a well-known keyword extraction method that uses a
list of stop words and phrase delimiters to detect the most relevant words or phrases in a piece of
text. BERT is an Encoder stack of transformer architecture. A transformer architecture is an
encoder-decoder network that uses self-attention on the encoder side and attention on the decoder
side. We then combine the keywords generated out of these modules and use <i><b>conventional methods
like TF-IDF</b></i> to order the extracted keywords. TF-IDF which stands for Term Frequency – Inverse
Document Frequency. It is one of the most important techniques used for information retrieval to
represent how important a specific word or phrase is to a given document. We then perform <i><b>POS
Tagging</b></i> on the resultant keywords and filter them based on the requirements
(adjectives/nouns/gerunds etc.).
