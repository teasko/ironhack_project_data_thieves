# ironhack_project_data_thieves
This is a repo for our project at the ironhack data-analysis bootcamp. We look at data on movies available from different sources. We take data form

* IMDB
* TMDB
* Box Office Mojo

The aim of the project is to collect data with different methods, to merge and to analyze them. We want to see which movies and movie categories are rated highest and make the most revenue. We consider movies from 2000 to 2019.



## 1. Data used

### 1.1 IMDB data dumps

* source data
	* source: https://datasets.imdbws.com/
	* **We used IMDB dumps the following data**
	* title.basics.tsv
		* table on titles and basic info
	*  title.ratings.tsv
		* table with titles, average ratings and number of votes
* data cleaning
	* from the original data sets we droped all titles that are not movies
	* we dropped some columns not interesting for our analysis 
	* we added the ratings and votes from *title.ratings* to *title.basics*
	* we dropped all movies that started before year 2000
	* **result**: DataFrame with
		* 9 columns
			* tconst: movie id
			* primaryTitle 
			*originalTitle 
			* isAdult: 0/1 for is adult
			* startYear 
			* runtimeMinutes
			* genres 
			* avrg_rating
			* num_votes
	* 226,576 row, i.e. movies
	* 125328 of the movies (55%) have a rating
	
### 1.2. Box Office Mojo Scraping

* source data:
	* source: https://www.boxofficemojo.com
	* provide data on movies and the revenue they made
	* we scraped data for the years 2000-2019
* **result**: DataFrame with
	* 3 columns
		* title
		* revenue worldwide (in dollar as int)
		* revenue domestic (us) (in dollar as int)
	* 12499 rows aka movies


### 1.3 TMDB API
* source data:
	* https://developers.themoviedb.org/3/find/find-by-id
	* data on movies with imdb id and own rating
	* we scraped all those movies that are in the merge of the imdb and box office data (ca. 8000 movies)
* **result**: df with 
	* ca 8000 movies
	* 90 imdb id's could not be found
	* 4 columns
		* imdb id
		* tmdb rating
		* tmdb votes
		* tmdb popularity
    
## 2. Merged Data
The final data was merged from the three above datasets. It contains a total of **7968** movies and 13 columns:
	* imdb_id
	* title 
	* isAdult
	* year
	* minutes (movie run time)
	* genres
	* imdb_rating
	* imdb_votes
	* tmdb_rating
	* tmdb_votes
	* popularity
	* worldwide (revenue)
	* domestic (revenue)
	
	

	    

   


