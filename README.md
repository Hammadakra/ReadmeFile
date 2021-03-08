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

