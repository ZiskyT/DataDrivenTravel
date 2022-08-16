# Data Driven Travel
Create a Travel-app class and automate testing with data driven from SQL database<br>

[data types](https://www.w3schools.com/sql/sql_datatypes.asp),
[hsqldb](http://hsqldb.org/),
[java api](https://docs.oracle.com/javase/7/docs/api/),
[sql](https://www.w3schools.com/sql/)

## Steps
* Ensure the Eclipse IDE has Maven by looking for M2E from Help About ([details](https://www.vogella.com/tutorials/EclipseMaven/article.html))
* Install `DBViewer Plugin 1.2.2.v20101009` by ZIGEN from the Eclipse IDE marketplace
* Import into Eclipse as Git with smart import (accepting all defaults in wizard)
* Let the IDE finish building dependencies before proceeding (see bottom right of Eclipse)
* Run as JUnit test the file `TravelAppTest.java` for sanity testing the local database

## Database Schema


**Animal table** 
- ID CHAR(36)
- Name Varchar(100)
- howHungry INT
- OwnerID char(36)
- Species Char(1)

Owner table
- ID char(36)
- Town Varchar(100)
- Name Varchar(100)


'create table Owner (Id char(36), Town Varchar(100), Name Varchar(100), PRIMARY KEY(Id));'

'create table Animal(Id CHAR(36), Name Varchar(100),Hunger INT, OwnerId char(36),Species Char(1), PRIMARY KEY(Id), FOREIGN KEY (OwnerId) referances Owner(Id) );'

'INSERT INTO Owner(Id, Name,Town) VALUES('240ae40b-d3d1-4196-97a7-600837b1806e', 'Floz', 'Bridgenorth');'

'INSERT INTO Animal(id, Name, Hunger, OwnerId, Species) VALUES ('ecedbbfa-6cb9-4369-bf79-cf173c4f1682', 'Jess', 0, '240ae40b-d3d1-4196-97a7-600837b1806e', 'C' );'
'INSERT INTO Animal(id, Name, Hunger, OwnerId, Species) VALUES ('db20c901-5cdf-486f-9779-8a5f453df853', 'Crystal', 0, '240ae40b-d3d1-4196-97a7-600837b1806e', 'D' );'

'SELECT Hunger,Id, Species FROM Animal WHERE Name = 'Jess'; '

'SELECT animal.Name, animal.Species FROM Animal animal, Owner owner WHERE owner.Name = 'Floz';'

