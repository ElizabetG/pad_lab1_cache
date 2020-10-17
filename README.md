# pad_lab1_cache

Run the following commands

python3 main_cache.py


Create a connection with "127.0.0.1" host and 5000 port.

The caching service will be listening and analyze the received messages to match one of these 2 categories:


1. JSON containing "expects":
  e.g.
  { "expects": "users", "id": 1 }
  
  OR
  
  { "expects": "insurances", "id": 2 }
  
Once the service gets a JSON with a value "expects", it will return you:
    1. {"message": "no data"} --> in case if no user/insurance of the provided id exists in db
    2. [{ ... }] --> json with all the data of the particular user/insurance



2. other JSON:
  e.g.
  {"id": "4", "firstName": "Eliza", "lastName": "G", "email": "liza@gmail.com", "birthDate": "2020-10-10"}
  
Once received, the service will save it to the db (in the @/db file), to the according table which the JSON belongs.
