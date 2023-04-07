# *Crypto Arbitrage Trading* 
**.**

---
## Technologies
This project leverages Pandas with the following libraries:
* Pandas
* pathlib - For setting a path for a .csv file.
* %Matplotlib

---
## Installation 
 

---
## Usage

Collecting the Data
* Using the Pandas read_csv function adn the Path module, import the data from the Bitstamp and Coinbase CSV files, amd create dataframes called bitstamp and coinbase.  Set the Datetimeindex as the Timestamp column, and parse and format the dates.  

![Screenshot 2023-04-07 at 1 01 49 AM](https://user-images.githubusercontent.com/111409358/230568569-fcaa01db-fb76-4a2a-bf33-717640c787da.png)
![Screenshot 2023-04-07 at 1 02 20 AM](https://user-images.githubusercontent.com/111409358/230568659-b07dae2b-f59e-4c94-b6cb-1d4189b6f38d.png)


* Use the head and/or tail function to confirm that Pandas properly imported the data.
![Screenshot 2023-04-07 at 1 04 39 AM](https://user-images.githubusercontent.com/111409358/230569142-94e08449-7e82-4225-a9e7-dbb2fa194b95.png)
![Screenshot 2023-04-07 at 1 05 59 AM](https://user-images.githubusercontent.com/111409358/230569241-2939bd0d-c8d5-44b2-8528-c7a7c6fef6dd.png)



Preparing the Data
* Replace or drop all Nan, or missing value in the dataframe.
* Use the str.replace function to remove the dollar signs ($) from the values in the Close column
* Convert the data type of the Close column to float.
* Review the data for duplicate value, and drop them if necessary.

Analyzing the Data
* Choose the columns of data on which to focus your analysis.
* Get the summary statistics and plot the data.
* Focus your analysis on specific dates.
* Calculate the arbitage profits.

---
## Contributors
Alexander Valenzuela<br>
[LinkedIn Profile](<https://www.linkedin.com/in/alex-valenzuela-97826842/>)

---
## License
The Unlicense

