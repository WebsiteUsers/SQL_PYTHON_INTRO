# Python Porfolio

Welcome to my portfolio, this will look at the python
projects that i have created this year:

## Intro To SQL with python
```python
def insertFirstSQL():
    c.execute("""INSERT INTO tblEmployees(ID,FN,SN) VALUES ("2", "Barry", "Scott");""")
    conn.commit()

def viewDatabase():
    print("you are viewing the database:")
    # This will get all data from the database:
    c.execute("""SELECT * FROM tblEmployees""")


    for row in c.fetchall():
        print(row)

    return
 
# Introduction to SQL within Python
 
# SQL = Structured Query Langauge
 
# Start out by importing SQL:
import sqlite3 as sq
 
# To make our database, we create a connection:
conn = sq.connect('firstDB.db')
 
# We create a "cursor" to interact with our database. DO NOT ASK ME WHY THIS IS A THING:
c = conn.cursor()
 
'''
We are going to create a table of employees:
ID | FN  | SN
1  | Ben | Jones
2  | Fred| Rick
3  | Jon | Bon
'''
 
# To create a database table, in SQL we use a "CREATE" statement, this looks like the following:
'''
SQL CREATE TABLE Syntax:
 
CREATE TABLE IF NOT EXISTS tblName (
    col1 dataType validation,
    col2 dataType validation ...
);
'''
 
# Our create code:
c.execute("""CREATE TABLE IF NOT EXISTS tblEmployees(
          ID integer PRIMARY KEY,
          FN text NOT NULL,
          SN text NOT NULL);""")
 
 
# To display data within our table, we can run the following:
c.execute("""PRAGMA table_info(tblEmployees)""")
tableInfo = c.fetchall()
print(tableInfo)
 
 # CREATE MENU SYSTEM - THAT ALLOWS FOR THE USER TO CHOOSE BETWEEN THE FOLLOWING OPTIONS
 # ENTER 1 TO INSERT IN THE FIRST ROW(this goes to the insertFirstSQL procedure)
 # ENTER 2 TO THE DISPLAY THE DATA THAT IS WITHIN THE TABLE/VIEW THE DATABASE
 # ENTER 3 TO END THE PROGRAM

print("### Select items from the below menu ### ")
print("1 - Enter in the first row")
print("2 - Display data from the data set")
print("3 - End the program")

choice = int(input("Enter in your item here: "))
if choice == 1:
    insertFirstSQL()
elif choice == 2: 
    viewDatabase()
elif choice == 3:
    exit()

c.close()
```

### Output Of Intro To SQL
![alt tag for screen readers](images/IntroToSQLwhenran.PNG)