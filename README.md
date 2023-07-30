# Netflix Recommender System
Rapid data growth brings a new era of information. Recommendation Systems filter data, enhance search results &amp; suggest relevant items based on user history efficiency &amp; relevance at its best. They predict a user's rating or preference for an item. Almost every major tech company has applied them in some form: Amazon uses it to suggest products to customers, YouTube uses it to decide which video to play next on auto-play, and Facebook uses it to recommend pages to like and people to follow. Moreover, companies like Netflix and Spotify depend highly on the effectiveness of their recommendation engines for their business and success.

## Motivation
In this project, we’ll build a baseline Movie Recommendation System using TMDB 5000 Movie Dataset. For novices like me, this kernel will serve as a foundation in recommendation systems and provide you with something to start with.

### There are three types of recommender systems:-
**(1) Demographic Recommender System:** Demographic recommender systems recommend items to users based on demographic information such as age, gender, location, occupation, and other personal characteristics. These systems assume that users with similar demographic profiles tend to have similar preferences and interests.

Demographic recommender systems are relatively straightforward and can provide personalized recommendations, especially in scenarios without historical user-item interaction data. For example, a demographic recommender system might recommend specific products or services to users based on their age group or geographical location.

**(2) Content-Based Recommender System:** Content-based recommender systems recommend items to users based on the similarity between items' attributes and the user's preferences. The system analyzes the content or features of things and creates user profiles based on their past interactions or explicit preferences. It then suggests items with characteristics similar to those the user has shown interest in. For example, if a user has liked action movies in the past, the system might recommend similar action movies based on genre, actors, directors, or other relevant attributes.

**(3) Collaborative Filtering Recommender System:** Collaborative filtering is a popular recommendation technique suggesting items to users based on similar preferences. This method relies not on explicit item attributes but user-item interactions or historical data. There are two main types of collaborative filtering:

**(a) User-based collaborative filtering:** This approach identifies users with similar preferences and interests to the target user and recommends items similar users have liked. For instance, if User A and User B have both enjoyed similar movies in the past and User A has yet to see a particular film that User B has rated highly, the system may recommend that movie to User A.

**(b) Item-based collaborative filtering:** Instead of comparing users, this method focuses on finding similarities between items based on how users have interacted with them. If a user has positively rated or interacted with one thing, the system will recommend similar items others have liked.

**Data source -**: All required data for this project is available in a data folder.

**To start this project, we have to create a virtual environment of Python from scratch in Anaconda Command Prompt and install all necessary libraries in that environment, including the Surprise library. So we have to follow some steps to create a virtual environment -**

**(1)** Go to Anaconda Command Prompt.
**(2)** Initially, you are in the base environment, the default environment in the Anaconda Command Prompt. Now create an environment using this command in Command Prompt:
```Python
conda create --name myenv
```
In place of myenv, you can write your name, whichever you want to keep.

**(3)** Now you can check whether your environment is made or not just by using this command:
```Python
conda info --envs
```
This will give you the list of environments present in Anaconda. 

**(4)** Now activate your created environment in the command prompt using the command:
```Python
conda activate myenv
```
PS: Always remember that myenv is an abbreviation, not a universal name to create an environment. You can keep any name rather than myenv. 

**(5)** Now install pip in your **myenv** environment if you haven't installed it yet using this command:
```Python
conda install pip
```
**(6)** Now install the following libraries one-by-one likewise in the **myenv** environment using the commands:
```Python
conda install numpy
conda install pandas
conda install cython
pip install scikit-surprise
pip install --upgrade setuptools wheel
conda install -c conda-forge scikit-surprise
```
**(7)** Now your **Surprise** library has been installed with the proper requirements of other libraries.

PS: If you are still facing any issues in the installation of the **Surprise** library, follow the following steps:
```Python
git clone https://github.com/NicolasHug/Surprise.git
cd Surprise
pip install .
```
**(8)** Now install and open the **Jupyter Notebook** in the **myenv** environment, using the commands:
```Python
conda install jupyter
jupyter notebook
```

Now you are ready with the whole environment setup of the **Surprise** library.

## Some other Python libraries we have to import are following:
```Python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.metrics.pairwise import linear_kernel
from ast import literal_eval
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.metrics.pairwise import cosine_similarity
from surprise import SVD, Reader
from surprise import Dataset
from surprise.model_selection import cross_validate
from surprise import Dataset, Reader, KNNBasic
from surprise.model_selection import train_test_split
from surprise import accuracy
import matplotlib.pyplot as plt
```

## Metrics and Results

* Demographic filtering, we use the **IMDB** formula to calculate the rating or preferences of users.

* In Content-based filtering **(Plot description based Recommender)**, we first create a matrix representation to calculate the similarity scores between movies based on their plot descriptions. In this matrix, each column corresponds to a word from the vocabulary, which includes all the words appearing in at least one movie's plot overview. Each row represents a movie, as before.

* This matrix is constructed using the **Term Frequency-Inverse Document Frequency (TF-IDF)** technique. **TF-IDF** reduces the importance of words frequently occurring in plot overviews because such words might contribute little to a movie's overall meaning and theme. After creating the matrix with plot descriptions, we can compute a similarity score to measure how similar two films are in their plots.

* In the Credits, Genres, and Keywords Based, Recommender system, we'll follow a process similar to what we did with our plot description-based recommender. However, there's a crucial difference: instead of using TF-IDF, we'll opt for the CountVectorizer(). This change is to avoid diminishing an actor's or director's importance based on their involvement in multiple movies. Assessing their significance relative to the number of films they've worked on could make more sense. With CountVectorizer(), every occurrence of an actor or director is treated as equally important. This approach enables us to capture their presence in the metadata without considering how frequently they appear in the dataset.

* In dealing with scalability and sparsity issues in **Collaborative Filtering (CF)**, we can employ a **latent factor model** that captures the inherent resemblances between users and items. The objective is to convert the recommendation problem into an optimization challenge.

* Using the Collaborating technique (Content Based), our final average RMSE value is 0.89 approx in Item-Based Corss-Validation Filtering.
* The RMSE value for User-Based CF is greater than the RMSE value for Item-Based. 







