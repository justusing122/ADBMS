# ADBMS
from pymongo import MongoClient

# Connect to the MongoDB database
client = MongoClient("mongodb://localhost:27017/")  # Replace with your MongoDB URI
db = client["grocery_shop_db"]
collection = db["products"]

# Define and create indexes
collection.create_index([("name", 1)])  # Create an index on "name" field in ascending order
collection.create_index([("price", -1)])  # Create an index on "price" field in descending order

# Verify the indexes
indexes = collection.list_indexes()
for index in indexes:
    print(index)

# Test your indexed queries
# For example, querying products by name with the "find" method
result = collection.find({"name": "Milk"})
for product in result:
    print(product)

# Drop an index
collection.drop_index("price_-1")  # Drop the index on "price" field in descending order

# Verify the indexes again to see that the "price" index is dropped
indexes = collection.list_indexes()
for index in indexes:
    print(index)
