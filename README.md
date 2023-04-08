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

**1.)Collecting the Data**
* Using the Pandas read_csv function adn the Path module, import the data from the Bitstamp and Coinbase CSV files, amd create dataframes called bitstamp and coinbase.  Set the Datetimeindex as the Timestamp column, and parse and format the dates.  

![Screenshot 2023-04-07 at 1 01 49 AM](https://user-images.githubusercontent.com/111409358/230568569-fcaa01db-fb76-4a2a-bf33-717640c787da.png)
![Screenshot 2023-04-07 at 1 02 20 AM](https://user-images.githubusercontent.com/111409358/230568659-b07dae2b-f59e-4c94-b6cb-1d4189b6f38d.png)


* Use the head and/or tail function to confirm that Pandas properly imported the data.
![Screenshot 2023-04-07 at 1 04 39 AM](https://user-images.githubusercontent.com/111409358/230569142-94e08449-7e82-4225-a9e7-dbb2fa194b95.png)
![Screenshot 2023-04-07 at 1 05 59 AM](https://user-images.githubusercontent.com/111409358/230569241-2939bd0d-c8d5-44b2-8528-c7a7c6fef6dd.png)



**2.)Preparing the Data**
* Replace or drop all Nan, or missing value in the dataframe.<br>
![Screenshot 2023-04-08 at 7 12 45 AM](https://user-images.githubusercontent.com/111409358/230725821-369ef0dd-de92-406c-a571-9a4b2b0d2edd.png)

* Use the str.replace function to remove the dollar signs ($) from the values in the Close column
![Screenshot 2023-04-08 at 7 15 52 AM](https://user-images.githubusercontent.com/111409358/230725990-a8ebcbb7-fe79-471c-adaa-6c0ef4c5262b.png)<br>
![Screenshot 2023-04-08 at 7 25 55 AM](https://user-images.githubusercontent.com/111409358/230726563-01903672-28fa-44a2-9414-8ca2d1066a4b.png)
![Screenshot 2023-04-08 at 7 31 17 AM](https://user-images.githubusercontent.com/111409358/230726836-f1ec4d73-3181-4815-ae0b-976ba5b4a7c8.png)


* Convert the data type of the Close column to float.<br>
![Screenshot 2023-04-08 at 7 18 39 AM](https://user-images.githubusercontent.com/111409358/230726110-7d5f4973-174d-4b9c-aa4d-1edc3c42ffb9.png)<br>
![Screenshot 2023-04-08 at 7 21 12 AM](https://user-images.githubusercontent.com/111409358/230726264-132e092f-7172-47a0-b7ec-0b16cd7652c0.png)
![Screenshot 2023-04-08 at 7 21 12 AM](https://user-images.githubusercontent.com/111409358/230728330-e7b88083-46cc-4c7b-b72f-a1afccc1cbb1.png)


* Review the data for duplicate values, and drop them if necessary.<br>
![Screenshot 2023-04-08 at 7 35 30 AM](https://user-images.githubusercontent.com/111409358/230727239-71d0eb83-9cbd-412b-a7b8-aa567af9852a.png)
![Screenshot 2023-04-08 at 7 38 38 AM](https://user-images.githubusercontent.com/111409358/230727141-4196e061-2cbe-45ed-9b53-56e942b52a6d.png)



**3.)Analyzing the Data**<br>
* i.)Choosing the columns of data on which to focus the analysis.<br>
![Screenshot 2023-04-08 at 7 46 40 AM](https://user-images.githubusercontent.com/111409358/230727571-4eacc732-0ddf-47a3-907f-43e3caa8dedf.png)
![Screenshot 2023-04-08 at 7 50 48 AM](https://user-images.githubusercontent.com/111409358/230727784-b8b8b5ba-30c0-4990-8e6e-22c09a5e4aba.png)


* ii.)Getting the summary statistics of the data by using the describe function.<br>
![Screenshot 2023-04-08 at 7 58 02 AM](https://user-images.githubusercontent.com/111409358/230728145-86bb1773-4a68-4892-81ae-b943c4fb2a64.png)

* iii.)Plotting the full datasets<br>
Bitstamp Prices - Line plot of the dataframe for the full length of time in the dataset.<br>
![Screenshot 2023-04-08 at 8 05 03 AM](https://user-images.githubusercontent.com/111409358/230728493-805d45e4-f368-4e7e-8496-9149cab82cfb.png)<br>
Coinbase Prices - Line plot of the dataframe for the full length of time in the dataset.<br>
![Screenshot 2023-04-08 at 8 05 50 AM](https://user-images.githubusercontent.com/111409358/230728534-67445717-cb7b-4da7-94aa-e734676814b8.png)<br>
Exchange Comparison - Line plot overlay of the Bitstamp and Coinbase dataframes<br>
![Screenshot 2023-04-08 at 9 00 46 AM](https://user-images.githubusercontent.com/111409358/230731147-66a0fcca-c280-4ccc-89b1-9c9b8ed9c99f.png)

* Plotting the one month dataset of January 2018 and March 2018<br>
Exchange Comparison (January 2018) - Using the Loc function to create an overlay plot that visualizes the price action of both dataframes for a one month period early in the dataset.<br>
![Screenshot 2023-04-08 at 9 34 42 AM](https://user-images.githubusercontent.com/111409358/230732554-0eee3fd0-ad18-4608-be0e-91573a6ec13b.png)
Exchange Comparison (March 2018) - Using the Loc function to create an overlay plot that visualizes the price action of both dataframes for a one month period early in the dataset.<br>
![Screenshot 2023-04-08 at 10 21 50 AM](https://user-images.githubusercontent.com/111409358/230734611-dd842a42-0d02-4d02-8825-d657cc3d8048.png)


* iv.)Focusing the Analysis on Three Specific Dates for Arbitrage Opportunities<br>
Exchange Comparison - Bitstamp vs Coinbase - January 16, 2018.
![Screenshot 2023-04-08 at 10 27 29 AM](https://user-images.githubusercontent.com/111409358/230734851-726656e4-18be-4270-9f06-cbd950c810b3.png)
Calculating the arbitrage spread and generating the summary statistics.
![Screenshot 2023-04-08 at 10 33 55 AM](https://user-images.githubusercontent.com/111409358/230735138-9192513b-6b59-41cd-b412-e69e15f9659b.png)
Obtaining the arbitrage spread on a box plot. 
![Screenshot 2023-04-08 at 10 35 03 AM](https://user-images.githubusercontent.com/111409358/230735180-95be07e5-5215-4cec-908b-82ce1c9f963b.png)

Exchange Comparison - Bitstamp vs Coinbase - February 24, 2018
![Screenshot 2023-04-08 at 10 41 18 AM](https://user-images.githubusercontent.com/111409358/230735460-7157c2b9-3a29-4228-ad15-0c39d591201a.png)
Calculating the arbitrage spread and generating the summary statistics.
![Screenshot 2023-04-08 at 10 43 38 AM](https://user-images.githubusercontent.com/111409358/230735570-f7f48fe8-2de5-4aa0-8fba-cbc3a2d2a455.png)
Obtaining the arbitrage spread on a box plot. 
![Screenshot 2023-04-08 at 10 44 56 AM](https://user-images.githubusercontent.com/111409358/230735616-7fdc6365-c5d9-4d7c-b6c6-97751f86c6d8.png)

Exchange Comparison - Bitstamp vs Coinbase - February 24, 2018
![Screenshot 2023-04-08 at 10 46 22 AM](https://user-images.githubusercontent.com/111409358/230735682-f21fe6e4-7479-4eb4-8085-4cc40a6d1869.png)
Calculating the arbitrage spread and generating the summary statistics.
![Screenshot 2023-04-08 at 10 47 50 AM](https://user-images.githubusercontent.com/111409358/230735740-9dfc29e3-614b-4b1c-bea8-fa1ceb736831.png)
Obtaining the arbitrage spread on a box plot.
![Screenshot 2023-04-08 at 10 48 42 AM](https://user-images.githubusercontent.com/111409358/230735795-566a6f83-9dcb-4a38-93b0-a972d5414e75.png)


**4.)Calculating the Arbitage Profits for January 16, 2018**

i.)Measure the arbitrage spread between the two exchanges by subtracting the lower-priced exchange from the higher-priced one Use a conditional statement to generate the summary statistics for each arbitrage_spread DataFrame.<br>
![Screenshot 2023-04-08 at 10 57 40 AM](https://user-images.githubusercontent.com/111409358/230736559-97bd6c06-34f2-443d-8eb6-5a9e6e9cdd7c.png)

ii.)Calculate the spread returns by dividing the instances when the arbitrage spread is positive (> 0) by the price of Bitcoin from the exchange you are buying on (the lower-priced exchange).<br>
![Screenshot 2023-04-08 at 10 58 31 AM](https://user-images.githubusercontent.com/111409358/230736569-c64bb3f1-79f0-414c-a967-86ad540b0beb.png)

iii.)Determine the number of times your trades with positive returns exceed the 1% minimum threshold (.01) that you need to cover your costs. Review the first five profitable trades.<br>
![Screenshot 2023-04-08 at 10 59 08 AM](https://user-images.githubusercontent.com/111409358/230736571-878bd663-5355-4871-9593-e2ef214f2272.png)

iv.)Generate the summary statistics for the profitable trades or you trades where the spread returns are are greater than 1%.<br>
![Screenshot 2023-04-08 at 10 59 32 AM](https://user-images.githubusercontent.com/111409358/230736583-e47fe4d5-688f-459e-90c4-23f2d54cbb2f.png)

v.)Calculate the potential profit per trade in dollars. Multiply the profitable trades by the cost of the Bitcoin that was purchased. Drop any missing values from the profit DataFrame. View the early profit DataFrame.<br>
![Screenshot 2023-04-08 at 11 02 53 AM](https://user-images.githubusercontent.com/111409358/230736585-cc1d837d-eff2-4ccf-9af4-456a15ff1a5b.png)

vi.)Generate the summary statistics for the early profit per trade DataFrame<br>
![Screenshot 2023-04-08 at 11 03 28 AM](https://user-images.githubusercontent.com/111409358/230736589-194c2cea-9c62-44fe-801d-e47532a9c36c.png)

vii.)Plot the results for the early profit per trade DataFrame<br>
![Screenshot 2023-04-08 at 11 04 05 AM](https://user-images.githubusercontent.com/111409358/230736592-cbee0d99-8cc4-4a83-94bf-451680aecf33.png)

viii.)Calculate the sum of the potential profits for the early profit per trade DataFrame.<br>
![Screenshot 2023-04-08 at 11 05 16 AM](https://user-images.githubusercontent.com/111409358/230736599-6327e97c-1a19-4283-b8ab-67bcbf8d5c76.png)

ix.)Use the cumsum function to calculate the cumulative profits over time for the early profit per trade DataFrame.<br>
![Screenshot 2023-04-08 at 11 05 33 AM](https://user-images.githubusercontent.com/111409358/230736606-b310a159-2583-42ce-904c-5246b7f80931.png)

x.)Plot the cumulative sum of profits for the early profit per trade DataFrame.<br>
![Screenshot 2023-04-08 at 11 06 55 AM](https://user-images.githubusercontent.com/111409358/230736612-0bab6b13-4aa3-49be-96df-8c5762f8c521.png)



---
## Contributors
Alexander Valenzuela<br>
[LinkedIn Profile](<https://www.linkedin.com/in/alex-valenzuela-97826842/>)

---
## License
The Unlicense

