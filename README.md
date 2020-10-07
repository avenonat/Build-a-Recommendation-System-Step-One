# Build-a-Recommendation-System-Step-One

In this exercise, you will use the provided classes Movie.java, Rating.java, and Rater.java and read in and store information about movies and ratings of movies by different movie raters to answer simple questions about both movies and ratings.

For this assignment you will be given three starter files.

The class Movie is a Plain Old Java Object (POJO) class for storing the data about one movie. It includes the following items:

Eight private variables to represent information about a movie including:

id - a String variable representing the IMDB ID of the movie
title - a String variable for the movie’s title
year - an integer representing the year
genres - one String of one or more genres separated by commas
director - one String of one or more directors of the movie separated by commas
country - one String of one or more countries the film was made in, separated by commas
minutes - an integer for the length of the movie
poster - a String that is a link to an image of the movie poster if one exists, or “N/A” if no poster exists
A constructor with eight parameters to initialize the private variables

Eight getter methods to return the private information such as the method getGenres that returns a String of all the genres for this movie.

A toString method for representing movie information as a String so it can easily be printed.

The class Rating is also a POJO class for storing the data about one rating of an item. It includes

Two private variables to represent information about a rating:

item - a String description of the item being rated (for this assignment you should use the IMDB ID of the movie being rated)
value - a double of the actual rating
A constructor with two parameters to initialize the private variables.

Two getter methods getItem and getValue.

A toString method to represent rating information as a String.

A compareTo method to compare this rating with another rating.

The class Rater keeps track of one rater and all their ratings. This class includes:

Two private variables:

myID - a unique String ID for this rater
myRatings - an ArrayList of Ratings
A constructor with one parameter of the ID for the rater.

A method addRating that has two parameters, a String named item and a double named rating. A new Rating is created and added to myRatings.

A method getID with no parameters to get the ID of the rater.

A method getRating that has one parameter item. This method returns the double rating of this item if it is in myRatings. Otherwise this method returns -1.

A method numRatings that returns the number of ratings this rater has.

A method getItemsRated that has no parameters. This method returns an ArrayList of Strings representing a list of all the items that have been rated.

Data files
You’ll use several data files for this project. There are multiple versions of each type of file or different sizes. In creating recommendations you'll need two data files: one of movies, and one of ratings of these movies by different raters.

First there is a CSV file with movie data, the smallest of which is called ratedmovies_short.csv. The other similar files are larger, so we have created this small file with just a few entries in it that you can use for testing. Each file of this type has a header row as the first line, first followed by one line for each movie. Shown below is this shorter file that has six lines, the header line first followed by six movies. The lines are so long that they are wrapping in this document, each movie line is displayed here in two to three lines. For example the first movie has the IMDB number 0006414, the name of the movie is “Behind the Screen,” and the movie was made in 1916 in the USA. The genres for this movie are Short, Comedy, and Romance. The director is Charles Chaplin, and the length of the film is 30 minutes. The last item is a link to a .jpg image of a poster for the movie if one exists, or “N/A” if there is not one.

Next there is a CSV file with rating/rater data, the smallest of which is called ratings_short.csv. Again, the other similar files are quite large so we have created this small file with just a few entries in it that you can use for testing. Each file of this type has a header first followed by one line for each rating. Shown below is this shorter file that has eleven lines. The first line is the header. The second line shows the rater_id is 1, the IMDB movie ID is 0068646, the movie was rated a 10, and the time was 1381620027.


First Assignment:
In this assignment you will create a new class named FirstRatings to process the movie and ratings data and to answer questions about them. You may find it helpful to use CSVParser and CSVRecord.

Specifically for this assignment you will write the following methods in a new class named FirstRatings:

Write a method named loadMovies that has one parameter, a String named filename. This method should process every record from the CSV file whose name is filename, a file of movie information, and return an ArrayList of type Movie with all of the movie data from the file.

Write a void method named testLoadMovies that should do several things.

Call the method loadMovies on the file ratedmovies_short.csv and store the result in an ArrayList local variable . Print the number of movies, and print each movie. You should see there are five movies in this file, which are all shown above. After this works you should comment out the printing of the movies. If you run your program on the file ratedmoviesfull.csv, you should see there are 3143 movies in the file.
Add code to determine how many movies include the Comedy genre. In the file ratedmovies_short.csv, there is only one.
Add code to determine how many movies are greater than 150 minutes in length. In the file ratedmovies_short.csv, there are two.
Add code to determine the maximum number of movies by any director, and who the directors are that directed that many movies. Remember that some movies may have more than one director. In the file ratedmovies_short.csv the maximum number of movies by any director is one, and there are five directors that directed one such movie.
In the FirstRatings class, write a method named loadRaters that has one parameter named filename. This method should process every record from the CSV file whose name is filename, a file of raters and their ratings, and return an ArrayList of type Rater with all the rater data from the file.

Write a void method named testLoadRaters that should do several things.

Call the method loadRaters on the file ratings_short.csv and store the result in a local ArrayList variable. Print the total number of raters. Then for each rater, print the rater’s ID and the number of ratings they did on one line, followed by each rating (both the movie ID and the rating given) on a separate line. If you run your program on the file ratings_short.csv you will see there are five raters. After it looks like it works, you may want to comment out the printing of each rater and their ratings. If you run your program on the file ratings.csv, you should get 1048 raters.
Add code to find the number of ratings for a particular rater you specify in your code. For example, if you run this code on the rater whose rater_id is 2 for the file ratings_short.csv, you will see they have three ratings.
Add code to find the maximum number of ratings by any rater. Determine how many raters have this maximum number of ratings and who those raters are. If you run this code on the file ratings_short.csv, you will see rater 2 has three ratings, the maximum number of ratings of all the raters, and that there is only one rater with three ratings.
Add code to find the number of ratings a particular movie has. If you run this code on the file ratings_short.csv for the movie “1798709”, you will see it was rated by four raters.
Add code to determine how many different movies have been rated by all these raters. If you run this code on the file ratings_short.csv, you will see there were four movies rated.

Second Assignment:
In this assignment you will modify a new class named SecondRatings, which has been started for you, to do many of the calculations focusing on computing averages on movie ratings. You will also create a second new class named MovieRunnerAverage, which you will use to test the methods you created in SecondRatings by creating a SecondRatings object in MovieRunnerAverage and calling its methods.

Specifically for this assignment you will write the following classes and methods:

Note that the SecondRatings class has been started for you. This class includes two private variables, one named myMovies of type ArrayList of type Movie, and a second one named myRaters of type ArrayList of type Rater. A default constructor has also been created for you. Until you create the second constructor (see below), the class will not compile.
Write an additional SecondRatings constructor that has two String parameters named moviefile and ratingsfile. The constructor should create a FirstRatings object and then call the loadMovies and loadRaters methods in FirstRatings to read in all the movie and ratings data and store them in the two private ArrayList variables of the SecondRatings class, myMovies and myRaters.
In the SecondRatings class, write a public method named getMovieSize, which returns the number of movies that were read in and stored in the ArrayList of type Movie.
In the SecondRatings class, write a public method named getRaterSize, which returns the number of raters that were read in and stored in the ArrayList of type Rater.
Create a new class named MovieRunnerAverage. In this class, create a void method named printAverageRatings that has no parameters. This method should:
- Create a SecondRatings object and use the CSV filenames of movie information and ratings information from the first assignment when calling the constructor.

- Print the number of movies and number of raters from the two files by calling the appropriate methods in the SecondRatings class. Test your program to make sure it is reading in all the data from the two files. For example, if you run your program on the files ratings_short.csv and ratedmovies_short.csv, you should see 5 raters and 5 movies.

- We will add more code to this method in a bit.

In the SecondRatings class, write a private helper method named getAverageByID that has two parameters: a String named id representing a movie ID and an integer named minimalRaters. This method returns a double representing the average movie rating for this ID if there are at least minimalRaters ratings. If there are not minimalRaters ratings, then it returns 0.0.
In the SecondRatings class, write a public method named getAverageRatings, which has one int parameter named minimalRaters. This method should find the average rating for every movie that has been rated by at least minimalRaters raters. Store each such rating in a Rating object in which the movie ID and the average rating are used in creating the Rating object. The method getAverageRatings should return an ArrayList of all the Rating objects for movies that have at least the minimal number of raters supplying a rating. For example, if minimalRaters has the value 10, then this method returns rating information (the movie ID and its average rating) for each movie that has at least 10 ratings. You should consider calling the private getAverageByID method.
In the SecondRatings class, write a method named getTitle that has one String parameter named id, representing the ID of a movie. This method returns the title of the movie with that ID. If the movie ID does not exist, then this method should return a String indicating the ID was not found.
In the MovieRunnerAverage class in the printAverageRatings method, add code to print a list of movies and their average ratings, for all those movies that have at least a specified number of ratings, sorted by averages. Specifically, this method should print the list of movies, one movie per line (print its rating first, followed by its title) in sorted order by ratings, lowest rating to highest rating. For example, if printAverageRatings is called on the files ratings_short.csv and ratedmovies_short.csv with the argument 3.
In the SecondRatings class, write a method getID that has one String parameter named title representing the title of a movie. This method returns the movie ID of this movie. If the title is not found, return an appropriate message such as “NO SUCH TITLE.” Note that the movie title must be spelled exactly as it appears in the movie data files.
In the MovieRunnerAverage class, write the void method getAverageRatingOneMovie, which has no parameters. This method should first create a SecondRatings object, reading in data from the movie and ratings data files. Then this method should print out the average ratings for a specific movie title, such as the movie “The Godfather”. If the moviefile is set to the file named ratedmovies_short.csv, and the ratingsfile is set to the file ratings_short.csv, then the average for the movie “The Godfather” would be 9.0.
