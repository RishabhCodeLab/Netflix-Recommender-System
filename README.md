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









