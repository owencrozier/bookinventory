# Description
ER diagram.
![diagram](diagram.png?raw=true)

### Tables
|tablename|description|
|----------|----------|
|books|books' data like ISBN, title, author, publisher, etc.|
|authors|authors' data, can be a porson or a company|
|publishers|publishers' data, just name|
|genres|list of them|
|books_genres|points which genre or genres is a book|
|customers|list of them, contains a lot of personal info|
|discounts|name and % value|
|books_discounts|points discounts of specific book|
|customers_discounts|points discounts of a costumer|
|shippers|list of couriers and their phone numbers|
|orders|list of them, points shipper, discount and customer|
|orders_details|points orders and tells amount of specific book|
|reviews|0 - 10 ratings and comments|
### Views
|view name|descpription|
|-|-|
|book_adder|adding book here cares about existence of authors and publishers|
|books_rank|shows ranking of books with average rate and amount of sold copies|

### Additional information
There are triggers validating e.g. ISBNs correctness (database can handle both ISBN-10 and ISBN-13) and 9-digit phone numbers.
Customer has to have a book bought in order to rate it. Multiple rating of same book by same user updates resulting one.
Removing customer from database makes all his data deleted (orders, ratings and related).
If adding a book with book_adder fails it's publisher and author won't be added to database.
