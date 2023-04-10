# *Crypto Arbitrage Trading* 
**As a financial analyst, the goal of our project is to extract and analyze three months of historial financial data betweem two crypto exchanges, Bitstamp and Coinbase, and pinpoint the price dislocations to determine the opitmum arbitrage opporutnities and profits.**

---
## Technologies
This project leverages Pandas with the following libraries:
* Pandas
* Pathlib - For setting a path for a .csv file.
* %Matplotlib

---
## Installation 
[Jupyter Lab and Jupyter Notebook](https://jupyter.org/install)

[JupyterLab - Getting Started](https://jupyterlab.readthedocs.io/en/stable/getting_started/starting.html)

[Jupyter Notebook - Getting Started](https://docs.jupyter.org/en/latest/running.html)

[Visual Studio Code](https://code.visualstudio.com/download)


---
## Usage

After my team and I have done extensive research and collaborated on how to handle and present data, we all decided to align our approach with the best practices for collection, preparation/cleaning, analayzing, plotting and arbitrage calculations.  

**1.)Collecting the Data**
* Using the Pandas read_csv function and the Path module, import the data from the Bitstamp and Coinbase CSV files, amd create dataframes called bitstamp and coinbase.  Set the Datetimeindex as the Timestamp column, and parse and format the dates.  

![Screenshot 2023-04-07 at 1 01 49 AM](https://user-images.githubusercontent.com/111409358/230568569-fcaa01db-fb76-4a2a-bf33-717640c787da.png)
![Screenshot 2023-04-07 at 1 02 20 AM](https://user-images.githubusercontent.com/111409358/230568659-b07dae2b-f59e-4c94-b6cb-1d4189b6f38d.png)


* Use the head and/or tail functions to inspect and verify that Pandas properly imported the data.  
![Screenshot 2023-04-07 at 1 04 39 AM](https://user-images.githubusercontent.com/111409358/230569142-94e08449-7e82-4225-a9e7-dbb2fa194b95.png)
![Screenshot 2023-04-07 at 1 05 59 AM](https://user-images.githubusercontent.com/111409358/230569241-2939bd0d-c8d5-44b2-8528-c7a7c6fef6dd.png)



**2.)Preparing the Data**
* Replace or drop all Nan values, or missing values in the dataframe.<br>
![Screenshot 2023-04-08 at 7 12 45 AM](https://user-images.githubusercontent.com/111409358/230725821-369ef0dd-de92-406c-a571-9a4b2b0d2edd.png)

* Use the str.replace function to remove the dollar signs ($) from the values in the Close column.<br>
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
* i.)Choosing the columns of data on which to focus the analysis. Using iloc to slice the entire Close column.<br>
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

* Plotting the one month datasets of January 2018, February 2018 and March 2018 - Using the Loc function to create an overlay plot that visualizes the price action of both dataframes for a one month period early in the dataset.<br>

Exchange Comparison - January 2018<br> 
![Screenshot 2023-04-08 at 9 34 42 AM](https://user-images.githubusercontent.com/111409358/230732554-0eee3fd0-ad18-4608-be0e-91573a6ec13b.png)<br>

Exchange Comparison - February 2018<br>
![Screenshot 2023-04-09 at 10 37 31 PM](https://user-images.githubusercontent.com/111409358/230833966-cf241294-aaf7-4b00-95ed-353e5d760012.png)

Exchange Comparison - March 2018<br> 
![Screenshot 2023-04-08 at 10 21 50 AM](https://user-images.githubusercontent.com/111409358/230734611-dd842a42-0d02-4d02-8825-d657cc3d8048.png)


* iv.)Focusing the Analysis on Three Specific Dates for Arbitrage Opportunities<br>
Exchange Comparison - Bitstamp vs Coinbase - January 16, 2018.
![Screenshot 2023-04-08 at 10 27 29 AM](https://user-images.githubusercontent.com/111409358/230734851-726656e4-18be-4270-9f06-cbd950c810b3.png)
Calculate the arbitrage spread and generating the summary statistics.
![Screenshot 2023-04-08 at 10 33 55 AM](https://user-images.githubusercontent.com/111409358/230735138-9192513b-6b59-41cd-b412-e69e15f9659b.png)
Plot the arbitrage spread on a box plot. 
![Screenshot 2023-04-08 at 10 35 03 AM](https://user-images.githubusercontent.com/111409358/230735180-95be07e5-5215-4cec-908b-82ce1c9f963b.png)

Exchange Comparison - Bitstamp vs Coinbase - February 24, 2018
![Screenshot 2023-04-08 at 10 41 18 AM](https://user-images.githubusercontent.com/111409358/230735460-7157c2b9-3a29-4228-ad15-0c39d591201a.png)
Calculate the arbitrage spread and generating the summary statistics.
![Screenshot 2023-04-08 at 10 43 38 AM](https://user-images.githubusercontent.com/111409358/230735570-f7f48fe8-2de5-4aa0-8fba-cbc3a2d2a455.png)
Plot the arbitrage spread on a box plot. 
![Screenshot 2023-04-08 at 10 44 56 AM](https://user-images.githubusercontent.com/111409358/230735616-7fdc6365-c5d9-4d7c-b6c6-97751f86c6d8.png)

Exchange Comparison - Bitstamp vs Coinbase - March 24, 2018
![Screenshot 2023-04-08 at 10 46 22 AM](https://user-images.githubusercontent.com/111409358/230735682-f21fe6e4-7479-4eb4-8085-4cc40a6d1869.png)
Calculate the arbitrage spread and generating the summary statistics.
![Screenshot 2023-04-08 at 10 47 50 AM](https://user-images.githubusercontent.com/111409358/230735740-9dfc29e3-614b-4b1c-bea8-fa1ceb736831.png)
Plot the arbitrage spread on a box plot.
![Screenshot 2023-04-08 at 10 48 42 AM](https://user-images.githubusercontent.com/111409358/230735795-566a6f83-9dcb-4a38-93b0-a972d5414e75.png)


**4.)Calculating the Arbitage Profits**

i.)Measure the arbitrage spread between the two exchanges by subtracting the lower-priced exchange from the higher-priced one Use a conditional statement to generate the summary statistics for each arbitrage_spread DataFrame.<br>

January 16, 2018<br>
![Screenshot 2023-04-08 at 10 57 40 AM](https://user-images.githubusercontent.com/111409358/230736559-97bd6c06-34f2-443d-8eb6-5a9e6e9cdd7c.png)

February 24, 2018<br>
![Screenshot 2023-04-09 at 8 14 29 PM](https://user-images.githubusercontent.com/111409358/230818384-5da97e0f-fb56-42c0-bbe9-67d5807c014e.png)

March 26, 2018<br>
![Screenshot 2023-04-09 at 8 15 11 PM](https://user-images.githubusercontent.com/111409358/230818398-c892daac-c742-498b-b417-05942d9797ad.png)


ii.)Calculate the spread returns by dividing the instances when the arbitrage spread is positive (> 0) by the price of Bitcoin from the exchange you are buying on (the lower-priced exchange).<br>

January 16, 2018<br>
![Screenshot 2023-04-08 at 10 58 31 AM](https://user-images.githubusercontent.com/111409358/230736569-c64bb3f1-79f0-414c-a967-86ad540b0beb.png)

February 24, 2018<br>
![Screenshot 2023-04-09 at 8 22 09 PM](https://user-images.githubusercontent.com/111409358/230819162-e1bcdf72-3c0a-491f-bcd8-9cfcaf4b3f9e.png)

March 26, 2018<br>
![Screenshot 2023-04-09 at 8 21 51 PM](https://user-images.githubusercontent.com/111409358/230819232-6cf1eb8e-7de4-4287-9cc5-6ecada0236c7.png)


iii.)Determine the number of times your trades with positive returns exceed the 1% minimum threshold (.01) that you need to cover your costs. Review the first five profitable trades.<br>

January 16, 2018<br>
![Screenshot 2023-04-09 at 11 06 31 PM](https://user-images.githubusercontent.com/111409358/230838340-71768413-c6df-4c54-905b-b6a3b5b30591.png)

February 24, 2018<br>
![Screenshot 2023-04-09 at 11 08 08 PM](https://user-images.githubusercontent.com/111409358/230838377-83871ba0-57b3-472c-bc14-3e17d6ec1947.png)

March 26, 2018<br>
![Screenshot 2023-04-09 at 11 09 19 PM](https://user-images.githubusercontent.com/111409358/230838401-f7e5138b-f491-4f2e-8946-ac82efb4013b.png)

iv.)Generate the summary statistics for the profitable trades or you trades where the spread returns are are greater than 1%.<br>

January 16, 2018<br>
![Screenshot 2023-04-08 at 10 59 32 AM](https://user-images.githubusercontent.com/111409358/230736583-e47fe4d5-688f-459e-90c4-23f2d54cbb2f.png)

February 24, 2018<br>
![Screenshot 2023-04-09 at 8 29 36 PM](https://user-images.githubusercontent.com/111409358/230819953-3401f109-5ed5-4a1b-93e1-70f84d56f530.png)

March, 26, 2018<br>
![Screenshot 2023-04-09 at 8 29 52 PM](https://user-images.githubusercontent.com/111409358/230819974-25110611-a59e-41bb-aa2f-a26d359177a3.png)


v.)Calculate the potential profit per trade in dollars. Multiply the profitable trades by the cost of the Bitcoin that was purchased. Drop any missing values from the profit DataFrame. View the early profit DataFrame.<br>

January 16, 2018<br>
![Screenshot 2023-04-08 at 11 02 53 AM](https://user-images.githubusercontent.com/111409358/230736585-cc1d837d-eff2-4ccf-9af4-456a15ff1a5b.png)

Februrary 24, 2018<br>
![Screenshot 2023-04-09 at 8 35 06 PM](https://user-images.githubusercontent.com/111409358/230820643-9c3ff3ed-8084-441b-baf2-26e9ef470517.png)

March 26, 2018<br>
![Screenshot 2023-04-09 at 8 35 21 PM](https://user-images.githubusercontent.com/111409358/230820731-cd07c21a-28a2-4e0b-b8fe-d42d6fe20a72.png)


vi.)Generate the summary statistics and plit the three results.<br>

Janurary 16, 2018<br>
![Screenshot 2023-04-08 at 11 03 28 AM](https://user-images.githubusercontent.com/111409358/230736589-194c2cea-9c62-44fe-801d-e47532a9c36c.png)
![Screenshot 2023-04-08 at 11 04 05 AM](https://user-images.githubusercontent.com/111409358/230736592-cbee0d99-8cc4-4a83-94bf-451680aecf33.png)

February 24, 2018<br>
![Screenshot 2023-04-09 at 8 42 08 PM](https://user-images.githubusercontent.com/111409358/230821357-dd76570c-552a-49fd-96b9-d8117afd885c.png)<br>
![Screenshot 2023-04-09 at 8 42 41 PM](https://user-images.githubusercontent.com/111409358/230821503-144d7462-ccb0-47c0-84a4-bb2ac9b2616c.png)

March 26, 2018<br>
![Screenshot 2023-04-09 at 8 42 23 PM](https://user-images.githubusercontent.com/111409358/230821386-a9eceeda-5cf2-470e-953b-2d0664e7a754.png)<br>
![Screenshot 2023-04-09 at 8 43 01 PM](https://user-images.githubusercontent.com/111409358/230821530-9f70063e-344d-4691-a661-5182e92dc816.png)


vii.)Calculate the potential arbitrage profits on each one day using the Sum() function<br>

January 16, 2018<br>
![Screenshot 2023-04-09 at 9 01 17 PM](https://user-images.githubusercontent.com/111409358/230823291-71aa09da-2be9-4e9c-969e-68ab0215ac2f.png)<br>

February 24, 2018<br>
![Screenshot 2023-04-09 at 9 01 27 PM](https://user-images.githubusercontent.com/111409358/230823349-b70d430f-a8b5-400c-b7da-5a75e6bcafd6.png)<br>

March 26, 2018<br>
![Screenshot 2023-04-09 at 9 01 40 PM](https://user-images.githubusercontent.com/111409358/230823362-c2da3189-63d1-4f20-a007-0819370c7b1d.png)


viii.)Calculate the cumuluative profits using the cumsum() function.<br>

January 16, 2018<br>
![Screenshot 2023-04-08 at 11 05 33 AM](https://user-images.githubusercontent.com/111409358/230736606-b310a159-2583-42ce-904c-5246b7f80931.png)<br>
![Screenshot 2023-04-08 at 11 06 55 AM](https://user-images.githubusercontent.com/111409358/230736612-0bab6b13-4aa3-49be-96df-8c5762f8c521.png)

February 24, 2018<br>
![Screenshot 2023-04-09 at 9 05 23 PM](https://user-images.githubusercontent.com/111409358/230823660-973dbd43-0263-4b37-9df6-4e3570a883a0.png)<br>
![Screenshot 2023-04-09 at 9 09 57 PM](https://user-images.githubusercontent.com/111409358/230824151-207ca855-4873-4a4c-b800-e727036dff7b.png)

March 26. 2018<br>
![Screenshot 2023-04-09 at 9 07 56 PM](https://user-images.githubusercontent.com/111409358/230823944-ee7a5d88-e359-4d0a-a7c2-10f154986514.png)<br>
![Screenshot 2023-04-09 at 9 11 11 PM](https://user-images.githubusercontent.com/111409358/230824269-22abe101-b0c9-43fd-8ca2-601f7295d2c7.png)


---
## Contributors
Alexander Valenzuela<br>
[LinkedIn Profile](<https://www.linkedin.com/in/alex-valenzuela-97826842/>)

---
## License
The Unlicense

