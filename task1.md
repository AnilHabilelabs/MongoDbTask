## MATCH

> db.getCollection("listingsAndReviews").aggregate([{$match:{"bedrooms":15}}])

```
{
    "_id" : "27383511",
    "listing_url" : "https://www.airbnb.com/rooms/27383511",
    "name" : "LEGNOCASA",
    "summary" : "Sultan Ahmet Cami Ayasofya Kapalı çarşı 5 (beş) dakika yürüme mesafesi",
    "space" : "",
    "description" : "Sultan Ahmet Cami Ayasofya Kapalı çarşı 5 (beş) dakika yürüme mesafesi",
    "neighborhood_overview" : "",
    "notes" : "",
    "transit" : "",
    "access" : "",
    "interaction" : "",
    "house_rules" : "",
    "property_type" : "Hotel",
    "room_type" : "Private room",
    "bed_type" : "Real Bed",
    "minimum_nights" : "1",
    "maximum_nights" : "30",
    "cancellation_policy" : "strict_14_with_grace_period",
    "last_scraped" : ISODate("2019-02-18T05:00:00.000+0000"),
    "calendar_last_scraped" : ISODate("2019-02-18T05:00:00.000+0000"),
    "first_review" : ISODate("2018-08-12T04:00:00.000+0000"),
    "last_review" : ISODate("2018-08-13T04:00:00.000+0000"),
    "accommodates" : NumberInt(16),
    "bedrooms" : NumberInt(15),
    "beds" : NumberInt(2),
    "number_of_reviews" : NumberInt(2),
    "bathrooms" : NumberDecimal("1.0"),
    "amenities" : [
        "TV",
        "Wifi",
        "Air conditioning",
        "Heating",
        "Essentials",
        "Shampoo",
        "Hangers"
    ],
    "price" : NumberDecimal("127.00"),
    "extra_people" : NumberDecimal("0.00"),
    "guests_included" : NumberDecimal("1"),
    "images" : {
        "thumbnail_url" : "",
        "medium_url" : "",
        "picture_url" : "https://a0.muscache.com/im/pictures/025028e3-2589-4ceb-b0a6-9da891e46006.jpg?aki_policy=large",
        "xl_picture_url" : ""
    },
    "host" : {
        "host_id" : "206364535",
        "host_url" : "https://www.airbnb.com/users/show/206364535",
        "host_name" : "Abdulmutalip",
        "host_location" : "Istanbul, Istanbul, Turkey",
        "host_about" : "caressing,reliable, sympathetic\r\n",
        "host_thumbnail_url" : "https://a0.muscache.com/im/pictures/user/d61a59fc-db04-440c-b656-f5015a098bef.jpg?aki_policy=profile_small",
        "host_picture_url" : "https://a0.muscache.com/im/pictures/user/d61a59fc-db04-440c-b656-f5015a098bef.jpg?aki_policy=profile_x_medium",
        "host_neighbourhood" : "",
        "host_is_superhost" : false,
        "host_has_profile_pic" : true,
        "host_identity_verified" : false,
        "host_listings_count" : NumberInt(1),
        "host_total_listings_count" : NumberInt(1),
        "host_verifications" : [
            "email",
            "phone"
        ]
    },
    "address" : {
        "street" : "Fatih, İstanbul, Turkey",
        "suburb" : "Fatih",
        "government_area" : "Fatih",
        "market" : "Istanbul",
        "country" : "Turkey",
        "country_code" : "TR",
        "location" : {
            "type" : "Point",
            "coordinates" : [
                28.96373,
                41.00331
            ],
            "is_location_exact" : false
        }
    },
    "availability" : {
        "availability_30" : NumberInt(30),
        "availability_60" : NumberInt(60),
        "availability_90" : NumberInt(90),
        "availability_365" : NumberInt(90)
    },
    "review_scores" : {
        "review_scores_accuracy" : NumberInt(6),
        "review_scores_cleanliness" : NumberInt(4),
        "review_scores_checkin" : NumberInt(6),
        "review_scores_communication" : NumberInt(6),
        "review_scores_location" : NumberInt(6),
        "review_scores_value" : NumberInt(6),
        "review_scores_rating" : NumberInt(60)
    },
    "reviews" : [
        {
            "_id" : "306209092",
            "date" : ISODate("2018-08-12T04:00:00.000+0000"),
            "listing_id" : "27383511",
            "reviewer_id" : "171559276",
            "reviewer_name" : "Mohammad",
            "comments" : "انصح المسافرين بعدم الحجز في هذا الفندق لعدم مصداقيتهم بالاضافة الى ان الصور ليست مطابقة للواقع حيث أني حجزت حسب الصور وشاهدت شيئاً آخر"
        },
        {
            "_id" : "306792533",
            "date" : ISODate("2018-08-13T04:00:00.000+0000"),
            "listing_id" : "27383511",
            "reviewer_id" : "68424965",
            "reviewer_name" : "Katharina",
            "comments" : "Extraordinarily helpful!! Even on short notice!"
        }
    ]
}

```

## Project

> db.getCollection("customers").aggregate([{$project:{name:"Elizabeth Ray",birthdate:"1977-03-02T02:20:31.000+0000"}}])

```
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a68"),
    "name" : "Elizabeth Ray",
    "birthdate" : "1977-03-02T02:20:31.000+0000"
}
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a69"),
    "name" : "Elizabeth Ray",
    "birthdate" : "1977-03-02T02:20:31.000+0000"
}
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a6a"),
    "name" : "Elizabeth Ray",
    "birthdate" : "1977-03-02T02:20:31.000+0000"
}
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a6b"),
    "name" : "Elizabeth Ray",
    "birthdate" : "1977-03-02T02:20:31.000+0000"
}
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a6c"),
    "name" : "Elizabeth Ray",
    "birthdate" : "1977-03-02T02:20:31.000+0000"
}



```

## FIND

> db.getCollection("customers").find({})
>
> > there are so many records but i am listing here only five for readability

```
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a68"),
    "username" : "fmiller",
    "name" : "Elizabeth Ray",
    "address" : "9286 Bethany Glens\nVasqueztown, CO 22939",
    "birthdate" : ISODate("1977-03-02T02:20:31.000+0000"),
    "email" : "arroyocolton@gmail.com",
    "active" : true,
    "accounts" : [
        NumberInt(371138),
        NumberInt(324287),
        NumberInt(276528),
        NumberInt(332179),
        NumberInt(422649),
        NumberInt(387979)
    ],
    "tier_and_details" : {
        "0df078f33aa74a2e9696e0520c1a828a" : {
            "tier" : "Bronze",
            "id" : "0df078f33aa74a2e9696e0520c1a828a",
            "active" : true,
            "benefits" : [
                "sports tickets"
            ]
        },
        "699456451cc24f028d2aa99d7534c219" : {
            "tier" : "Bronze",
            "benefits" : [
                "24 hour dedicated line",
                "concierge services"
            ],
            "active" : true,
            "id" : "699456451cc24f028d2aa99d7534c219"
        }
    }
}
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a69"),
    "username" : "valenciajennifer",
    "name" : "Lindsay Cowan",
    "address" : "Unit 1047 Box 4089\nDPO AA 57348",
    "birthdate" : ISODate("1994-02-19T23:46:27.000+0000"),
    "email" : "cooperalexis@hotmail.com",
    "accounts" : [
        NumberInt(116508)
    ],
    "tier_and_details" : {
        "c06d340a4bad42c59e3b6665571d2907" : {
            "tier" : "Platinum",
            "benefits" : [
                "dedicated account representative"
            ],
            "active" : true,
            "id" : "c06d340a4bad42c59e3b6665571d2907"
        },
        "5d6a79083c26402bbef823a55d2f4208" : {
            "tier" : "Bronze",
            "benefits" : [
                "car rental insurance",
                "concierge services"
            ],
            "active" : true,
            "id" : "5d6a79083c26402bbef823a55d2f4208"
        },
        "b754ec2d455143bcb0f0d7bd46de6e06" : {
            "tier" : "Gold",
            "benefits" : [
                "airline lounge access"
            ],
            "active" : true,
            "id" : "b754ec2d455143bcb0f0d7bd46de6e06"
        }
    }
}
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a6a"),
    "username" : "hillrachel",
    "name" : "Katherine David",
    "address" : "55711 Janet Plaza Apt. 865\nChristinachester, CT 62716",
    "birthdate" : ISODate("1988-06-20T22:15:34.000+0000"),
    "email" : "timothy78@hotmail.com",
    "accounts" : [
        NumberInt(462501),
        NumberInt(228290),
        NumberInt(968786),
        NumberInt(515844),
        NumberInt(377292)
    ],
    "tier_and_details" : {

    }
}
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a6b"),
    "username" : "serranobrian",
    "name" : "Leslie Martinez",
    "address" : "Unit 2676 Box 9352\nDPO AA 38560",
    "birthdate" : ISODate("1974-11-26T14:30:20.000+0000"),
    "email" : "tcrawford@gmail.com",
    "accounts" : [
        NumberInt(170945),
        NumberInt(951849)
    ],
    "tier_and_details" : {
        "a15baf69a759423297f11ce6c7b0bc9a" : {
            "tier" : "Platinum",
            "benefits" : [
                "airline lounge access"
            ],
            "active" : true,
            "id" : "a15baf69a759423297f11ce6c7b0bc9a"
        }
    }
}
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a6c"),
    "username" : "charleshudson",
    "name" : "Brad Cardenas",
    "address" : "2765 Powers Meadow\nHeatherfurt, CT 53165",
    "birthdate" : ISODate("1977-05-06T21:57:35.000+0000"),
    "email" : "dustin37@yahoo.com",
    "accounts" : [
        NumberInt(721914),
        NumberInt(817222),
        NumberInt(973067),
        NumberInt(260799),
        NumberInt(87389)
    ],
    "tier_and_details" : {

    }
}
```

## LIMIT

> db.getCollection("customers").find({}).limit(1)

```
{
    "_id" : ObjectId("5ca4bbcea2dd94ee58162a68"),
    "username" : "fmiller",
    "name" : "Elizabeth Ray",
    "address" : "9286 Bethany Glens\nVasqueztown, CO 22939",
    "birthdate" : ISODate("1977-03-02T02:20:31.000+0000"),
    "email" : "arroyocolton@gmail.com",
    "active" : true,
    "accounts" : [
        NumberInt(371138),
        NumberInt(324287),
        NumberInt(276528),
        NumberInt(332179),
        NumberInt(422649),
        NumberInt(387979)
    ],
    "tier_and_details" : {
        "0df078f33aa74a2e9696e0520c1a828a" : {
            "tier" : "Bronze",
            "id" : "0df078f33aa74a2e9696e0520c1a828a",
            "active" : true,
            "benefits" : [
                "sports tickets"
            ]
        },
        "699456451cc24f028d2aa99d7534c219" : {
            "tier" : "Bronze",
            "benefits" : [
                "24 hour dedicated line",
                "concierge services"
            ],
            "active" : true,
            "id" : "699456451cc24f028d2aa99d7534c219"
        }
    }
}
```

## UNWIND

> db.getCollection("listingsAndReviews").aggregate([{ $unwind: "$host" }, { $unwind: "$amenities" },{$unwind:"$reviews"},{$limit:1}])

```
{
    "_id" : "10006546",
    "listing_url" : "https://www.airbnb.com/rooms/10006546",
    "name" : "Ribeira Charming Duplex",
    "summary" : "Fantastic duplex apartment with three bedrooms, located in the historic area of Porto, Ribeira (Cube) - UNESCO World Heritage Site. Centenary building fully rehabilitated, without losing their original character.",
    "space" : "Privileged views of the Douro River and Ribeira square, our apartment offers the perfect conditions to discover the history and the charm of Porto. Apartment comfortable, charming, romantic and cozy in the heart of Ribeira. Within walking distance of all the most emblematic places of the city of Porto. The apartment is fully equipped to host 8 people, with cooker, oven, washing machine, dishwasher, microwave, coffee machine (Nespresso) and kettle. The apartment is located in a very typical area of the city that allows to cross with the most picturesque population of the city, welcoming, genuine and happy people that fills the streets with his outspoken speech and contagious with your sincere generosity, wrapped in a only parochial spirit.",
    "description" : "Fantastic duplex apartment with three bedrooms, located in the historic area of Porto, Ribeira (Cube) - UNESCO World Heritage Site. Centenary building fully rehabilitated, without losing their original character. Privileged views of the Douro River and Ribeira square, our apartment offers the perfect conditions to discover the history and the charm of Porto. Apartment comfortable, charming, romantic and cozy in the heart of Ribeira. Within walking distance of all the most emblematic places of the city of Porto. The apartment is fully equipped to host 8 people, with cooker, oven, washing machine, dishwasher, microwave, coffee machine (Nespresso) and kettle. The apartment is located in a very typical area of the city that allows to cross with the most picturesque population of the city, welcoming, genuine and happy people that fills the streets with his outspoken speech and contagious with your sincere generosity, wrapped in a only parochial spirit. We are always available to help guests",
    "neighborhood_overview" : "In the neighborhood of the river, you can find several restaurants as varied flavors, but without forgetting the so traditional northern food. You can also find several bars and pubs to unwind after a day's visit to the magnificent Port. To enjoy the Douro River can board the boats that daily make the ride of six bridges. You can also embark towards Régua, Barca d'Alva, Pinhão, etc and enjoy the Douro Wine Region, World Heritage of Humanity. The Infante's house is a few meters and no doubt it deserves a visit. They abound grocery stores, bakeries, etc. to make your meals. Souvenir shop, wine cellars, etc. to bring some souvenirs.",
    "notes" : "Lose yourself in the narrow streets and staircases zone, have lunch in pubs and typical restaurants, and find the renovated cafes and shops in town. If you like exercise, rent a bicycle in the area and ride along the river to the sea, where it will enter beautiful beaches and terraces for everyone. The area is safe, find the bus stops 1min and metro line 5min. The bustling nightlife is a 10 min walk, where the streets are filled with people and entertainment for all. But Porto is much more than the historical center, here is modern museums, concert halls, clean and cared for beaches and surf all year round. Walk through the Ponte D. Luis and visit the different Caves of Port wine, where you will enjoy the famous port wine. Porto is a spoken city everywhere in the world as the best to be visited and savored by all ... natural beauty, culture, tradition, river, sea, beach, single people, typical food, and we are among those who best receive tourists, confirm! Come visit us and feel at ho",
    "transit" : "Transport: • Metro station and S. Bento railway 5min; • Bus stop a 50 meters; • Lift Guindais (Funicular) 50 meters; • Tuc Tuc-to get around the city; • Buses tourist; • Cycling through the marginal drive; • Cable car in Gaia, overlooking the Port (just cross the bridge).",
    "access" : "We are always available to help guests. The house is fully available to guests. We are always ready to assist guests. when possible we pick the guests at the airport.  This service transfer have a cost per person. We will also have service \"meal at home\" with a diverse menu and the taste of each. Enjoy the moment!",
    "interaction" : "Cot - 10 € / night Dog - € 7,5 / night",
    "house_rules" : "Make the house your home...",
    "property_type" : "House",
    "room_type" : "Entire home/apt",
    "bed_type" : "Real Bed",
    "minimum_nights" : "2",
    "maximum_nights" : "30",
    "cancellation_policy" : "moderate",
    "last_scraped" : ISODate("2019-02-16T05:00:00.000+0000"),
    "calendar_last_scraped" : ISODate("2019-02-16T05:00:00.000+0000"),
    "first_review" : ISODate("2016-01-03T05:00:00.000+0000"),
    "last_review" : ISODate("2019-01-20T05:00:00.000+0000"),
    "accommodates" : NumberInt(8),
    "bedrooms" : NumberInt(3),
    "beds" : NumberInt(5),
    "number_of_reviews" : NumberInt(51),
    "bathrooms" : NumberDecimal("1.0"),
    "amenities" : "TV",
    "price" : NumberDecimal("80.00"),
    "security_deposit" : NumberDecimal("200.00"),
    "cleaning_fee" : NumberDecimal("35.00"),
    "extra_people" : NumberDecimal("15.00"),
    "guests_included" : NumberDecimal("6"),
    "images" : {
        "thumbnail_url" : "",
        "medium_url" : "",
        "picture_url" : "https://a0.muscache.com/im/pictures/e83e702f-ef49-40fb-8fa0-6512d7e26e9b.jpg?aki_policy=large",
        "xl_picture_url" : ""
    },
    "host" : {
        "host_id" : "51399391",
        "host_url" : "https://www.airbnb.com/users/show/51399391",
        "host_name" : "Ana&Gonçalo",
        "host_location" : "Porto, Porto District, Portugal",
        "host_about" : "Gostamos de passear, de viajar, de conhecer pessoas e locais novos, gostamos de desporto e animais! Vivemos na cidade mais linda do mundo!!!",
        "host_response_time" : "within an hour",
        "host_thumbnail_url" : "https://a0.muscache.com/im/pictures/fab79f25-2e10-4f0f-9711-663cb69dc7d8.jpg?aki_policy=profile_small",
        "host_picture_url" : "https://a0.muscache.com/im/pictures/fab79f25-2e10-4f0f-9711-663cb69dc7d8.jpg?aki_policy=profile_x_medium",
        "host_neighbourhood" : "",
        "host_response_rate" : NumberInt(100),
        "host_is_superhost" : false,
        "host_has_profile_pic" : true,
        "host_identity_verified" : true,
        "host_listings_count" : NumberInt(3),
        "host_total_listings_count" : NumberInt(3),
        "host_verifications" : [
            "email",
            "phone",
            "reviews",
            "jumio",
            "offline_government_id",
            "government_id"
        ]
    },
    "address" : {
        "street" : "Porto, Porto, Portugal",
        "suburb" : "",
        "government_area" : "Cedofeita, Ildefonso, Sé, Miragaia, Nicolau, Vitória",
        "market" : "Porto",
        "country" : "Portugal",
        "country_code" : "PT",
        "location" : {
            "type" : "Point",
            "coordinates" : [
                -8.61308,
                41.1413
            ],
            "is_location_exact" : false
        }
    },
    "availability" : {
        "availability_30" : NumberInt(28),
        "availability_60" : NumberInt(47),
        "availability_90" : NumberInt(74),
        "availability_365" : NumberInt(239)
    },
    "review_scores" : {
        "review_scores_accuracy" : NumberInt(9),
        "review_scores_cleanliness" : NumberInt(9),
        "review_scores_checkin" : NumberInt(10),
        "review_scores_communication" : NumberInt(10),
        "review_scores_location" : NumberInt(10),
        "review_scores_value" : NumberInt(9),
        "review_scores_rating" : NumberInt(89)
    },
    "reviews" : {
        "_id" : "58663741",
        "date" : ISODate("2016-01-03T05:00:00.000+0000"),
        "listing_id" : "10006546",
        "reviewer_id" : "51483096",
        "reviewer_name" : "Cátia",
        "comments" : "A casa da Ana e do Gonçalo foram o local escolhido para a passagem de ano com um grupo de amigos. Fomos super bem recebidos com uma grande simpatia e predisposição a ajudar com qualquer coisa que fosse necessário.\r\nA casa era ainda melhor do que parecia nas fotos, totalmente equipada, com mantas, aquecedor e tudo o que pudessemos precisar.\r\nA localização não podia ser melhor! Não há melhor do que acordar de manhã e ao virar da esquina estar a ribeira do Porto."
    }
}

```

## GROUP

> db.listingsAndReviews.aggregate([{ $group: { _id: "$bed_type" } }])

```
{
    "_id" : "Airbed"
}
{
    "_id" : "Couch"
}
{
    "_id" : "Pull-out Sofa"
}
{
    "_id" : "Futon"
}
{
    "_id" : "Real Bed"
}
```

## LOOKUP
```
db.comments.aggregate([{

    $lookup: {
        from: "movies",
        localField: "movie_id",
        foreignField: "_id",
        as: "movie_details",
    },

},
{
$limit: 1
}
])
```

```
{
    "_id" : ObjectId("5a9427648b0beebeb69579e7"),
    "name" : "Mercedes Tyler",
    "email" : "mercedes_tyler@fakegmail.com",
    "movie_id" : ObjectId("573a1390f29313caabcd4323"),
    "text" : "Eius veritatis vero facilis quaerat fuga temporibus. Praesentium expedita sequi repellat id. Corporis minima enim ex. Provident fugit nisi dignissimos nulla nam ipsum aliquam.",
    "date" : ISODate("2002-08-18T04:56:07.000+0000"),
    "movie_details" : [
        {
            "_id" : ObjectId("573a1390f29313caabcd4323"),
            "plot" : "A young boy, opressed by his mother, goes on an outing in the country with a social welfare group where he dares to dream of a land where the cares of his ordinary life fade.",
            "genres" : [
                "Short",
                "Drama",
                "Fantasy"
            ],
            "runtime" : NumberInt(14),
            "rated" : "UNRATED",
            "cast" : [
                "Martin Fuller",
                "Mrs. William Bechtel",
                "Walter Edwin",
                "Ethel Jewett"
            ],
            "num_mflix_comments" : NumberInt(1),
            "poster" : "https://m.media-amazon.com/images/M/MV5BMTMzMDcxMjgyNl5BMl5BanBnXkFtZTcwOTgxNjg4Mg@@._V1_SY1000_SX677_AL_.jpg",
            "title" : "The Land Beyond the Sunset",
            "fullplot" : "Thanks to the Fresh Air Fund, a slum child escapes his drunken mother for a day's outing in the country. Upon arriving, he and the other children are told a story about a mythical land of no pain. Rather then return to the slum at day's end, the lad seeks to journey to that beautiful land beyond the sunset.",
            "languages" : [
                "English"
            ],
            "released" : ISODate("1912-10-28T00:00:00.000+0000"),
            "directors" : [
                "Harold M. Shaw"
            ],
            "writers" : [
                "Dorothy G. Shore"
            ],
            "awards" : {
                "wins" : NumberInt(1),
                "nominations" : NumberInt(0),
                "text" : "1 win."
            },
            "lastupdated" : "2015-08-29 00:27:45.437000000",
            "year" : NumberInt(1912),
            "imdb" : {
                "rating" : 7.1,
                "votes" : NumberInt(448),
                "id" : NumberInt(488)
            },
            "countries" : [
                "USA"
            ],
            "type" : "movie",
            "tomatoes" : {
                "viewer" : {
                    "rating" : 3.7,
                    "numReviews" : NumberInt(53),
                    "meter" : NumberInt(67)
                },
                "lastUpdated" : ISODate("2015-04-27T19:06:35.000+0000")
            }
        }
    ]
}
```
