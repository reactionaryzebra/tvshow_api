# TV Show API

This API can be used to create, read, and edit TV shows in a database.  It is built using Firebase and Firestore.

## /shows

### Request
GET https://tvshow-api-8483b.firebaseapp.com/api/v1/shows

### Parameters

limit - limits the number of results from the query (defaults to 100)

sort_by - sorts the query results by a given field (defaults to title)

start_at - starts the query results at a given point based on how the results are sorted (ex: if the results are sorted by originalAirDate you could start_at 01/01/2010 to view all shows started after that date)

### Sample Response 

``` 
{
  status: 200,
  data: [
    {
      id: "g09IgYRsXujz2LvamNvn",
      data: {
        description: "America's favorite gameshow",
        originalAirDate: "1/1/2000",
        rating: "9.5/10",
        keywords: [
        "sports",
        "commentary"
        ],
        duration: 60,
        title: "Jeopardy"
      }
    },
    {
      id: "CJsuB8QURVxXrimC1U0K",
      data: {
        rating: "9.5/10",
        keywords: [
        "sports",
        "commentary"
        ],
        duration: 60,
        title: "Life in Pieces",
        description: "The story of a quirky family",
        originalAirDate: "1/1/2000"
      }
     },
     {
      id: "zqwxPns5Do23PjeM8CYF",
      data: {
        duration: 60,
        title: "Life in Pieces",
        description: "The story of a quirky family",
        originalAirDate: "1/1/2000",
        rating: "9.5/10",
        keywords: [
        "sports",
        "commentary"
        ]
      }
     }
   ],
   lastItem: "Life in Pieces"
}
```
### Request
POST https://tvshow-api-8483b.firebaseapp.com/api/v1/shows

### Object Format
Shows should be posted with the following properties in the following formats:
* title - String
* description - String
* duration - Number(minutes)
* originalAirDate - String (MM/DD/YYYY format)
* rating - String (N.N/10 format)
* keywords - Array of Strings


## /shows/:id

### Request
PUT https://tvshow-api-8483b.firebaseapp.com/api/v1/shows/:id

Shows can be updated with any or all of the above properties
