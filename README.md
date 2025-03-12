# nosql-challenge


## Code Snippets Explained

* **`pprint(db.establishments.find_one())`**: Displays the first restaurant document.
* **`establishments.insert_one(new_restaurant)`**: Adds a new restaurant.
* **`pprint(establishments.find_one({"BusinessName":"Penang Flavours"}))`**: Shows details for "Penang Flavours".
* **`pprint(establishments.find_one({"BusinessType":"Restaurant/Cafe/Canteen"}, {"BusinessTypeID":1, "BusinessType":1}))`**: Shows BusinessType and ID.
* **`establishments.update_one({"BusinessName":"Penang Flavours"}, {"$set":{"BusinessTypeID":"1"}})`**: Sets "Penang Flavours" BusinessTypeID to 1.
* **`establishments.delete_many({"LocalAuthorityName":"Dover"})`**: Removes Dover restaurants.
* **`update = establishments.update_many({}, [{"$set": {"geocode.latitude": {"$toDouble": "$geocode.latitude"}}}, {"$set": {"geocode.longitude": {"$toDouble": "$geocode.longitude"}}}]) pprint(update.modified_count)`**: Converts geocodes to numbers.
* **`establishments.update_many({"RatingValue": {"$in": non_ratings}}, [ {'$set':{ "RatingValue" : None}} ])`**: Sets non-numeric ratings to null.
* **`query = {"scores.Hygiene": 20}`**: Finds hygiene score 20.
* **`count = establishments.count_documents(query)`**: Counts matching documents.
* **`pprint(establishments.find_one(query))`**: Shows first match.
* **`df = pd.DataFrame(list(establishments.find(query)))`**: Creates Pandas DataFrame.
* **`print(df.shape[0])`**: Displays DataFrame row count.
* **`df.head(10)`**: Shows first 10 DataFrame rows.
* **`query = {"LocalAuthorityName": {"$regex": "London", "$options": "i"}, "RatingValue": {"$gte": 4}}`**: Finds London restaurants, rating >= 4.
* **`print(establishments.count_documents(query))`**: Counts London/rating matches.
* **`pprint(establishments.find_one(query))`**: Shows first London/rating match.
* **Geospatial Search**: Finds restaurants near a location, rating 5, sorted by hygiene.