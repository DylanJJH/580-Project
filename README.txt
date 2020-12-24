README: Project 2
Class: ANLY 580-02
Team: Hot Dog
Name: Dongru Jia, Jianhao Ji, Miao Wang, Yuxuan Yao
NetID : dj465, jj913, mw1219, yy560
========================================================

* 580_project2_report.ipynb: 
Everything required to operate and understand this project.


* REQUIRED PACKAGES:
csv, re, string, pandas, numpy, sklearn(cosine_similarity), nltk, gensim(Doc2Vec, TaggedDocument), matplotlib.pyplot


* REQUIRED FILES:
- tmdb_5000_credits.csv: contains basic information of movies, such as movie name, character list, crew team and so on.

- tmdb_5000_movies.csv: contains features information of movies, such as their names, genres, overview, popularity and so on.


* UNDERSTANDING THE DATA:(Column name: description)
- tmdb_5000_credits.csv: 
1.Title: Movie name - System return label; 
2.Cast:Cast and character list - Potential model feature; 
3.crew: Firm crew team - Potential model feature

- tmdb_5000_movies.csv:
1.Genres: Movie type - Feature or label in two recommendation models;
2.Keywords: Views summarized movie keywords - Model feature;
3.Overview: Brief movie summary - Model feature;
4.Popularity:Movie popularity - Ranking conference for return labels;
5.Production_companies: Movie production companies - Model feature;
6.Title: Movie name - System return label;
7.vote_average: Viewer overall vote score - Final return table display


* PROGRAM ANALYSIS STRATEGY:
Three main functions in this program, Data Cleaning, Model 1 and Model 2. Model 1 and Model 2 are both recommendation systems.
- Data Cleaning mainly extracts the columns we use in the program and cleans the punctuations and stopwords.
- Model 1 is based on cosine similarity. User enters movie names and the system would calculate the cosine similarity, then return the recommended movies sorted by popularity.
- Model 2 is based on Doc2Vec model from Gensim. User enters keywords or stories and the system would find the genres of input, then compare with the cosine similarity of overviews of movies. Finally, return the recommended movies.


* CONCLUSION:
As expected, both methods can generate reasonably similar movies. Cosine Similarity based model performs really well when two input movies are close in terms of cosine or similar. For the second method which applies Doc2Vec, it sometimes can provide surprisingly precise result, but the performance is not consistent. 

- Model 1:
Input:'Spider-Man', 'the avengers'.
Results: movie similarity:  0.374
movie similarity:  0.374
recommendation by commonplace
     index  similarity                                title  popularity  \
26      26       0.481           captain america: civil war  198.372395   
7        7       0.553              avengers: age of ultron  134.279229   
68      68       0.470                             iron man  120.725053   
182    182       0.663                              ant-man  120.093610   
126    126       0.535                 thor: the dark world   99.499595

     vote_average  
26            7.1  
7             7.3  
68            7.4  
182           7.0  
126           6.8  


- Model 2:
Input: 'A young man and a young woman fell in love'
Results: romance fantasy movie tv thriller
 index  similarity                                 title  popularity  \
100     100       0.600   the curious case of benjamin button   60.269279   
2108   2108       0.516                   edward scissorhands   47.513630   
1132   1132       0.516                       red riding hood   45.151657   
2017   2017       0.600                                 ghost   41.967005   
295     295       0.516                           the tourist   41.426678   

vote_average  
100            7.3  
2108           7.5  
1132           5.6  
2017           6.9  
295            6.0  


* CONTACT
We have comments on every functions for understanding when you view and run our program. If you have any questions or concerns about this program, we can be contacted at (dj465, jj913,mw1219,yy560)@georgetown.edu.
