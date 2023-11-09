# database
# database
**1.Create a Database called movies.**
```
test> use Movies
switched to db Movies
Movies> 
```
**2. Create a collection called moviedetails.**
```
Movies> db.createCollection("MovieDetails")
{ ok: 1 }
```
**3.Create above 5 movie documents into a moviedetails collection.**
```
Movies> db.MovieDetails.insertMany([
...     {"Movie-Title": "Jurassic Park", "Genre": "Adventure", "Director": "Steven Spielberg", "Release Year": "1993"},
...     {"Movie-Title": "Forrest Gump", "Genre": "Drama", "Director": "Robert Zemeckis", "Release Year": "1994"},
...     {"Movie-Title": "Titanic", "Genre": "Romance", "Director": "James Cameron", "Release Year": "1997"},
...     {"Movie-Title": "The Dark Knight", "Genre": "Action", "Director": "Christopher Nolan", "Release Year": "2008"},
...     {"Movie-Title": "Avatar", "Genre": "Science Fiction", "Director": "James Cameron", "Release Year": "2009"}
... ])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("654c85248d02aa3894f3247b"),
    '1': ObjectId("654c85248d02aa3894f3247c"),
    '2': ObjectId("654c85248d02aa3894f3247d"),
    '3': ObjectId("654c85248d02aa3894f3247e"),
    '4': ObjectId("654c85248d02aa3894f3247f")
  }
}
```
**4.List all documents created.**
```
Movies> db.MovieDetails.find()
[
  {
    _id: ObjectId("654c85248d02aa3894f3247b"),
    'Movie-Title': 'Jurassic Park',
    Genre: 'Adventure',
    Director: 'Steven Spielberg',
    'Release Year': '1993'
  },
  {
    _id: ObjectId("654c85248d02aa3894f3247c"),
    'Movie-Title': 'Forrest Gump',
    Genre: 'Drama',
    Director: 'Robert Zemeckis',
    'Release Year': '1994'
  },
  {
    _id: ObjectId("654c85248d02aa3894f3247d"),
    'Movie-Title': 'Titanic',
    Genre: 'Romance',
    Director: 'James Cameron',
    'Release Year': '1997'
  },
  {
    _id: ObjectId("654c85248d02aa3894f3247e"),
    'Movie-Title': 'The Dark Knight',
    Genre: 'Action',
    Director: 'Christopher Nolan',
    'Release Year': '2008'
  },
  {
    _id: ObjectId("654c85248d02aa3894f3247f"),
    'Movie-Title': 'Avatar',
    Genre: 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': '2009'
  }
]
```
**5.List James Cameron’s movies.**
```
Movies> db.MovieDetails.find({ "Director": "James Cameron" })
[
  {
    _id: ObjectId("654c85248d02aa3894f3247d"),
    'Movie-Title': 'Titanic',
    Genre: 'Romance',
    Director: 'James Cameron',
    'Release Year': '1997'
  },
  {
    _id: ObjectId("654c85248d02aa3894f3247f"),
    'Movie-Title': 'Avatar',
    Genre: 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': '2009'
  }
]

**6.List  James Cameron’s movies released in 2009.**
Movies> db.MovieDetails.find({ "Release Year": "2009" })
[
  {
    _id: ObjectId("654c85248d02aa3894f3247f"),
    'Movie-Title': 'Avatar',
    Genre: 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': '2009'
  }
]
```
**7.Delete the movie which you don’t like.**
```
Movies> db.MovieDetails.remove({ "Movie-Title": "Titanic" })
DeprecationWarning: Collection.remove() is deprecated. Use deleteOne, deleteMany, findOneAndDelete, or bulkWrite.
{ acknowledged: true, deletedCount: 1 }
**
**8.Add the movie which is your favourite**
Movies> db.MoieDetails.insertOne({"Movie-Title": "Avengers", "Genre": "Action", "Director": "Joss Whedon", "Release Year": "2012"})
{
  acknowledged: true,
  insertedId: ObjectId("654c8c4c8d02aa3894f32480")
}
```
**9.List movie Directed  by Christopher Nolan in 1994.**
```
Movies> db.MovieDetails.find({"Director": "James Cameron", "Release Year": "1994" })

Movies> 
```
**10.List out the Director’s Name in your document.**
```
Movies> db.MovieDetails.distinct("Director")
[
  'Christopher Nolan',
  'James Cameron',
  'Robert Zemeckis',
  'Steven Spielberg'
]
```

