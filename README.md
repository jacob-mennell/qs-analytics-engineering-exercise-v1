# Analytics-engineering Project

### Client
The client is the owner of a high-end chain of bars. Recently they've experienced complaints about the time it's taken staff to deliver their drinks after they've been ordered.

An initial analysis by the team has shown that this issue is primarily driven by the lack of available glasses for the drinks being ordered. The owners want to take a data driven approach to business decisions in future but they currently have no historical data. They have asked staff to start recording data and we have been provided with an inventory across all three bars as well as the last week of transaction data.

They use the online cocktails database (`https://www.thecocktaildb.com/api.php`) for their menu and all bars serve a subset of these drinks according to the instructions in the database.

The bars are 24hour and for simplicity you can assume they are equally busy around the clock.

### Task
Create a database for the bar owners so that they can begin their data jouney, structuring the tables in a sensible way so that queries can easily be written and potential new data sources added. 

The database will be populated with data in a way which minimises the overhead as new data is generated by the bars. A  proof of concept table is provided (poc_analysis) to enable the staff in each bar to make decisions on glass purchases.

## Module requirements
- Listed in the bar_envs.yml file 

## Dates 
 - For batch database upload the last_update.txt file can be populated with the date 2000/01/01 for Budapest, New York and London. This will add all available data to the database.
 - After running the script once the last_update.txt date will reflect the latest input for Budapest, New York and London. It will then only add records after this date.

## Outputs
- SQL file with CREATE TABLE statements for setting up database.
- SQL file with queries to create a PoC table to enable bar staff to manage glass stock.
- *single* python script (build_database.py) which:
    - Reads in the datafiles
    - Imports the relevant data from the cocktails database API
    - Generates the data for the database
    - Creates the database and tables using the data_tables SQL script
    - Imports the data to the database
    - Runs the poc_tables SQL script
- .sqlite database (bar_db)
- Repository to enable future data analysis on bar performance.