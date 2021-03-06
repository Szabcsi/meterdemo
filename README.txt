- Application name:meterdemo

- Main class of the application:MeterdemoApplication.
  Path to package:hu.itsolutions.meterdemo.

- Building and running the application from 
  the application root folder:
   mvnw clean package -Dmaven.test.skip=true
   mvn spring-boot:run

- Port settings:8080(default)

- Root context:localhost:8080/meterdemo

- Database:
  H2 Memory database.
  name:testdb
  console:/h2
  The application.properties file in the root folder 
  contains the details.

- REST queries:
  GET:
 - localhost:8080/meterdemo/meterings
   Lists all the metering/consumption data.

 - localhost:8080/meterdemo/meterings/0001
   Lists all metering data by meterId like 0001

 - localhost:8080/meterings/id/1
   Lists all metering data with Id like 1.
   It is database generated id.

 - localhost:8080/meterings/years/2017
   Lists all metering data according year like 2017 

 - localhost:8080/meterings/yeartotal/2017
   Lists total consumption for the year like 2017

 - localhost:8080/meterings/year/2017
   Lists metering/consumption data with monthly detail in year 2017
   Somehow it is not working however the native SQL query works.
   It is not completed.

 - localhost:8080/meterings/years/2017/months/jan
   Lists consumption data in year 2017 and month January
   Please use the three letter acronym for months like jan,feb,mar,apr,may,jun,... etc.
   The letter case is indifferent.

  POST:
 - localhost:8080/meterings/0001/2017/30
   Only one update method is implemented just for modifying the meterPosition data.
   Updates the meterPosition (consumption) data on the meterId like 0001 and on the year 
   like 2017 to 30.

  DELETE:
 - localhost:8080/meterings/id/1
   Removes the meter data with id 1.
   It is an id generated by the database.
