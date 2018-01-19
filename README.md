# tfidf_example
Simple way to get the top features from text using TFIDF

What is TF-IDF?
TF-IDF stands for "Term Frequency, Inverse Document Frequency." It's a way to score the importance of words (or "terms") <br>
in a document based on how frequently they appear across multiple documents.

TF-IDF (Term Frequency-Inverse Document Frequency) is a text mining technique used to categorize documents.<br> 
Have you ever looked at blog posts on a web site, and wondered if it is possible to generate the tags automatically? <br>
Well, that's exactly the kind of problem TF-IDF is suited for.

Intuitively…
If a word appears frequently in a document, it's important. Give the word a high score.<br>
But if a word appears in many documents, it's not a unique identifier. Give the word a low score.<br>
Therefore, common words like "the" and "for," which appear in many documents, will be scaled down. <br>
Words that appear frequently in a single document will be scaled up.<br>

Scikit-learn provides two methods to get to our end result (a tf-idf weight matrix). One is a two-part <br>
process of using the CountVectorizer class to count how many times each term shows up in each document, <br>
followed by the TfidfTransformer class generating the weight matrix. The other does both steps in a single TfidfVectorizer class<br>

Let’s take a moment to describe these parameters as they are the primary levers for adjusting what feature <br>
set we end up with. First is “min_df” or mimimum document frequency. This sets the minimum number of documents <br>
that any term is contained in. This can either be an integer which sets the number specifically, or a decimal <br>
between 0 and 1 which is interpreted as a percentage of all documents. Next is “max_df” which similarly controls<br>
the maximum number of documents any term can be found in. If 90% of documents contain the word “spork” then it’s<br>
so common that it’s not very useful. Finally, we have “ngram_range” which is a tuple containing the range of ngram <br>
sizes to use. (1, 3) means use 1-grams, 2-grams, and 3-grams. We’re just using 1- and 2-grams.<br>


After setting up our CountVectorizer, we follow the general fit/transform convention of scikit-learn, starting with fitting:<br>

