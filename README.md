Firstly, the code reads the listings dataset in a dataframe.
Then according to the data I have designed the classes.
The Host class:
It represents the host that provides rooms. It has id and name
The Neighbor hood Group class:
It represents all the regions in which neighborhoods occur, containing id and name, northern Region, central Region etc. 
The Neighborhood class:
It represents a neighborhood with its id and name, along with the regions id.
And finally the room class:
It contains all the remaining columns, after normalizing, hence it doesnt have host_name, but only the id. It also contains the price, reviews, name, neighborhood id columns.

Now we define the wrapper classes for reading and writing the dataset and encapsulating the operations.
ReaderService:
It contains the methods like get_unique_neighborhoods() to get specific columns from the dataframe.

DatabaseService:
It gets the database file name from the constructor and stores the connection in an instance variable (self.conn). It provides all the methods required to add/fetch data from the database encapsulated, like query_all_hosts() etc.

Later in the code, it uses the service instances to populate and retrive the data for testing




PANDAS, SQLITE3



## Installation




Use the package manager [pip](https://pip.pypa.io/en/stable/) to install pandas and sqlite3.

```bash
pip install pandas
pip install pysqlite
```

if you have error in Sqlite built in python you can use Conda to solve this conflict
```bash
conda install sqlite
```
## Usage

```python
import pandas as pd
# we use panad
df = pd.read_csv('listings.csv/listings.csv') # load data form CSV into df
```
```python
import sqlite3
from sqlite3 import Error
class DatabaseService:
    create_queries = """
        CREATE TABLE IF NOT EXISTS hosts (
            host_id integer PRIMARY KEY,
            host_name text NOT NULL
        );
        <next>
        CREATE TABLE IF NOT EXISTS neighborhood_groups (
            id integer PRIMARY KEY,
            name text NOT NULL
        );
        <next>
        CREATE TABLE IF NOT EXISTS neighborhoods (
            id integer PRIMARY KEY,
            name text NOT NULL,
            group_id integer
        );
        <next>
        CREATE TABLE IF NOT EXISTS rooms (
            id integer PRIMARY KEY,
            name text,
            host_id integer,
            neighborhood_id integer,
            lat text,
            lng text,
            room_type text,
            price integer,
            min_nights integer,
            num_reviews integer
        );
    """
```
## Contributing
Pull requests are welcome. For major changes.

Please make sure to update tests as appropriate.

