Q1:-
Import the function create_engine from the module sqlalchemy.
Create an engine to connect to the SQLite database 'Chinook.sqlite' and assign it to engine.

Solution:-
# Import necessary module
from sqlalchemy import create_engine

# Create engine: engine
engine = create_engine('sqlite:///Chinook.sqlite')

Q2:-
Import the function create_engine from the module sqlalchemy.
Create an engine to connect to the SQLite database 'Chinook.sqlite' and assign it to engine.
Using the method table_names() on the engine engine, assign the table names of 'Chinook.sqlite' to the variable table_names.
Print the object table_names to the shell.

Solution:-
# Import necessary module
from sqlalchemy import create_engine

# Create engine: engine
engine = create_engine('sqlite:///Chinook.sqlite') 

# Save the table names to a list: table_names
table_names = engine.table_names()

# Print the table names to the shell
print(table_names)

Q3:-
Open the engine connection as con using the method connect() on the engine.
Execute the query that selects ALL columns from the Album table. Store the results in rs.
Store all of your query results in the DataFrame df by applying the fetchall() method to the results rs.
Close the connection!

Solution:-
# Import packages
from sqlalchemy import create_engine
import pandas as pd

# Create engine: engine
engine = create_engine('sqlite:///Chinook.sqlite')

# Open engine connection: con
con = engine.connect()

# Perform query: rs
rs = con.execute("select * from Album")

# Save results of the query to DataFrame: df
df = pd.DataFrame(rs.fetchall())

# Close connection
con.close()

# Print head of DataFrame df
print(df.head())

Q4:-
Execute the SQL query that selects the columns LastName and Title from the Employee table. Store the results in the variable rs.
Apply the method fetchmany() to rs in order to retrieve 3 of the records. Store them in the DataFrame df.
Using the rs object, set the DataFrame's column names to the corresponding names of the table columns.

Solution:-
# Open engine in context manager
# Perform query and save results to DataFrame: df
with engine.connect() as con:
    rs = con.execute("select LastName,Title from Employee")
    df = pd.DataFrame(rs.fetchmany(size=3))
    df.columns = rs.keys()

# Print the length of the DataFrame df
print(len(df))

# Print the head of the DataFrame df
print(df.head())

Q5:-
Complete the argument of create_engine() so that the engine for the SQLite database 'Chinook.sqlite' is created.
Execute the query that selects all records from the Employee table where 'EmployeeId' is greater than or equal to 6. Use the >= operator and assign the results to rs.
Apply the method fetchall() to rs in order to fetch all records in rs. Store them in the DataFrame df.
Using the rs object, set the DataFrame's column names to the corresponding names of the table columns.

Solution:-
# Create engine: engine
engine = create_engine('sqlite:///Chinook.sqlite')

# Open engine in context manager
# Perform query and save results to DataFrame: df
with engine.connect() as con:
    rs = con.execute("select * from employee where EmployeeId>=6")
    df = pd.DataFrame(rs.fetchall())
    df.columns = rs.keys()

# Print the head of the DataFrame df
print(df.head())

Q6:-
Using the function create_engine(), create an engine for the SQLite database Chinook.sqlite and assign it to the variable engine.
In the context manager, execute the query that selects all records from the Employee table and orders them in increasing order by the column BirthDate. Assign the result to rs.
In a call to pd.DataFrame(), apply the method fetchall() to rs in order to fetch all records in rs. Store them in the DataFrame df.
Set the DataFrame's column names to the corresponding names of the table columns.

Solution:-
# Create engine: engine
engine = create_engine('sqlite:///Chinook.sqlite')

# Open engine in context manager
with engine.connect() as con:
    rs = con.execute("select * from employee order by BirthDate")
    df = pd.DataFrame(rs.fetchall())

    # Set the DataFrame's column names
    df.columns = rs.keys()

# Print head of DataFrame
print(df.head())


Q7:-
Import the pandas package using the alias pd.
Using the function create_engine(), create an engine for the SQLite database Chinook.sqlite and assign it to the variable engine.
Use the pandas function read_sql_query() to assign to the variable df the DataFrame of results from the following query: select all records from the table Album.
Run the rest of the code to confirm that the DataFrame created by this method is equal to that created by the previous method that you learned.

Solution:-
# Import packages
from sqlalchemy import create_engine
import pandas as pd

# Create engine: engine
engine = create_engine('sqlite:///Chinook.sqlite')

# Execute query and store records in DataFrame: df
df = pd.read_sql_query("select * from album", engine)

# Print head of DataFrame
print(df.head())

# Open engine in context manager
# Perform query and save results to DataFrame: df1
with engine.connect() as con:
    rs = con.execute("SELECT * FROM Album")
    df1 = pd.DataFrame(rs.fetchall())
    df1.columns = rs.keys()

# Confirm that both methods yield the same result: does df = df1 ?
print(df.equals(df1))

Q8:-
Using the function create_engine(), create an engine for the SQLite database Chinook.sqlite and assign it to the variable engine.
Use the pandas function read_sql_query() to assign to the variable df the DataFrame of results from the following query: 
select all records from the Employee table where the EmployeeId is greater than or 
equal to 6 and ordered by BirthDate (make sure to use WHERE and ORDER BY in this precise order).

Solution:-
from sqlalchemy import create_engine
import pandas as pd

# Create engine: engine
engine = create_engine('sqlite:///Chinook.sqlite')

# Execute query and store records in DataFrame: df
df = pd.read_sql_query("select * from employee where EmployeeId >= 6 order by BirthDate",engine) 

# Print head of DataFrame
print(df.head())

Q9:-
Assign to rs the results from the following query: select all the records, extracting the Title of the record and Name of the artist of each record from the Album table and the Artist table, respectively. To do so, INNER JOIN these two tables on the ArtistID column of both.
In a call to pd.DataFrame(), apply the method fetchall() to rs in order to fetch all records in rs. Store them in the DataFrame df.
Set the DataFrame's column names to the corresponding names of the table columns.

Solution:-
# Open engine in context manager
# Perform query and save results to DataFrame: df
with engine.connect() as con:
    rs = con.execute("select Title,Name from album inner join artist on album.ArtistID = artist.ArtistID")
    df = pd.DataFrame(rs.fetchall())
    df.columns = rs.keys()

# Print head of DataFrame df
print(df.head())

Q10:-
Use the pandas function read_sql_query() to assign to the variable df the DataFrame of results from the following query: 
select all records from PlaylistTrack INNER JOIN Track on PlaylistTrack.TrackId = Track.
TrackId that satisfy the condition Milliseconds < 250000.

Solution:-
# Execute query and store records in DataFrame: df
df = pd.DataFrame(pd.read_sql_query("select * from PlaylistTrack INNER JOIN Track on PlaylistTrack.TrackId = Track.TrackId where Milliseconds < 250000",engine))

# Print head of DataFrame
print(df.head())
