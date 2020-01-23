# ironhack_project_data_thieves
this is a repo for our project at the ironhack data-analysis bootcamp








## 1. Data used



### 1.1 iMBd data dumps

* source data
	* source: https://datasets.imdbws.com/
	* **We used iMBD dumps the following data**
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


    

    

    

    

   


