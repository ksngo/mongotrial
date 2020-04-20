show databases

### create or use a new db
use mydatabase

db.mydatabase.insert({
    'name':'julian'
})

db.mydatabase.find()

db.listingsAndReviews.find({

}, {name:1, bedrooms:1 ,bathrooms:1}
).limit(5).pretty()

db.listingsAndReviews.find({
    bedrooms: 2,
    room_type:'Private room'
}, {name:1, bedrooms:1 , room_type:1}).limit(5).pretty()

db.listingsAndReviews.find({
    'host.host_total_listings_count': {$gt:2}
}, {name:1, 'host.host_total_listings_count':1}).limit(10).pretty()

<!-- Qn2a -->
<!-- a -->
db.movies.count()

<!-- b -->
db.movies.count({
    year: {$lt:2000}
})

<!-- c -->

db.movies.find({
    countries:'USA'
}, {title:1 , countries:1}).limit(10).pretty()

<!-- d -->
 
 db.movies.find({
    countries: { $nin: ['USA'] }
 }, {title:1 , countries:1}).limit(10).pretty()

<!-- e -->

db.movies.find({
    'awards.wins' : { $gte:3 } 
}, {title:1, 'awards.wins':1})

<!-- f -->

db.movies.find({
    'awards.nominations' : { $gte:3 }
}, {title:1, 'awards.nominations':1})

db.movies.find({
    'awards.nominations' : { $gte:3 },
    'awards.wins' : { $gte:3 } 
}, {title:1, 'awards.nominations':1, 'awards.wins':1}).limit(5).pretty()