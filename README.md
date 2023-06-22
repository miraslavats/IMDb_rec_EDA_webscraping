# IMDb_rec_EDA_webscraping
I web scraped my own IMDb top-1000 dataset, did EDA on it and created a simple recommendation system based on the gathered information. The project is accessible via "website scraping.ipynb" file attached, along with detailed explanations of what I did and the interpretation of the results in the document. 
The project has the following structure:
1. Web Scraping:
   - creating a function that parses through every movie on a single webpage and gathers the needed information (stars, directors, rating, etc);
   - creating a function that goes through every page on the website and gathers information from every movie on every page using the function described above;
   - review scraper, gathers every review written on the movie, parses through each movie on a signle web page, however, I did not end up using this function;
   - the resulting dataset:
     <img width="1013" alt="Screenshot 2023-06-22 at 3 57 18 PM" src="https://github.com/miraslavats/IMDb_rec_EDA_webscraping/assets/112869592/6fa9937c-4623-4979-bdfb-c8e7ddc0089c">

2. Data cleaning & EDA:
   - cleaning every dtaframe column (getting rid of unnecessary symbols, punctuation, making sure data types are consistent for further analysis, etc):
    <img width="989" alt="Screenshot 2023-06-22 at 3 58 02 PM" src="https://github.com/miraslavats/IMDb_rec_EDA_webscraping/assets/112869592/8c36657d-0474-4d8b-93e9-8374953ca85a">
   - EDA:
       - Histograms of movie release year, rating, and duration:<img width="989" alt="Screenshot 2023-06-22 at 3 59 16 PM" src="https://github.com/miraslavats/IMDb_rec_EDA_webscraping/assets/112869592/19471064-97f8-4b9f-a484-bac373730eb5">
       - Box plots showcasing outliers:<img width="989" alt="Screenshot 2023-06-22 at 4 00 05 PM" src="https://github.com/miraslavats/IMDb_rec_EDA_webscraping/assets/112869592/b7d05f6a-7810-4c19-bcad-c02f809affc9">
       - Scatterplots showcasing possible correlation:<img width="989" alt="Screenshot 2023-06-22 at 4 01 12 PM" src="https://github.com/miraslavats/IMDb_rec_EDA_webscraping/assets/112869592/bf74bfa4-47a8-4541-9d76-1538cc406b8d">
       - Interpretation of the plots;
       - p-value calculation
       - "Occurrence of certain genres within the top-1000 movies" bar plot:<img width="609" alt="Screenshot 2023-06-22 at 4 02 58 PM" src="https://github.com/miraslavats/IMDb_rec_EDA_webscraping/assets/112869592/452fada8-2ef8-42c2-b0a3-bab16efb8ea7">
3. Simple recommendation system:
   The recommendation system uses the information I have gathered (description, stars, directors, and genres) to calculate cosine similarity between all the movies in the top. The similarity values are then used to make suggestions. More specifically, a text combining description, stars, directors, and genres is generated for each movie. Then, this text is represented numerically using CountVectorizer. The resulting vectors are then used to calculate the cos. similarity between all movie pairs. So, when a user inputs their favorite movie they get n number of most similar movies within the gathered datset. Fro example:<img width="609" alt="Screenshot 2023-06-22 at 4 09 09 PM" src="https://github.com/miraslavats/IMDb_rec_EDA_webscraping/assets/112869592/ae9885f3-84ab-4d5f-90cb-970e1f73f2a2">
   The system has a number of limitation which I talk about in the attached document. The most prominent ones are: lack of personalization, limited number of movies, inaccuracy relative to other more powerful methods (item-item, user-user and matrix based systems)




