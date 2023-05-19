# Sales-Insights

A Data Analysis Project

![Sales Insights](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/4279bd48-37ca-4b0f-b240-8819590f0efa)

PART I — Problem Statement

AtliQ hardware is a company in India which supplies computer hardware and peripheral devices across India only. The have many stores across India such as surge stores, Nomad stores etc. The head office of the company is situated in Delhi.

Scenario —

The sales manager of the company is facing many challenges. He is facing issues in tracking sales in dynamically growing market. He is having issues with the insights of his business.

In order to this he has some of the regional managers in North, south and central India working for the company. So, he calls them and ask about the insights he wants to know. They tell him about the sales in last quarter and the growth in that quarter.

So, the problem is that the conversations that are happening are verbal. Hence, the regional managers are sugar coating the facts and the manager of the company does not get the clear picture of the facts. Even after knowing that the sales are declining, he cannot do anything because he does not have the clear picture of the sales. Asking for the records the regional manager provides him with excel files. But by this he cannot figure out small things.

All what the manager wants is a view of the weakest area the company need to focus to increase the sales and improvise the declination. He is interested in simple, understandable and digestive insight. So, he is more interested in a dashboard which he can go and look at the real data because data speaks the truth. All he wants is a simple data visualization tool which he can access on daily basis.

Hence, by using such tools and technology one can make data driven decisions which helps to increase the sales of the company.

So, in this project we will help a company make its own sales related dashboard using PowerBI.

PART II — Data Discovery

Project planning using AIMS grid –

AIMS grid: It is a project management tool which consists of four components to it.

1) Purpose (what to do exactly)

2) Stack holders (who will be involved)

3) End result (what do you want to achieve)

4) Success criteria (cost optimization and time save)

In our case the end result will be the dashboard created and success criteria will be bumping up the sales using cost optimization and save the time of the manager of the company.

![Data Analysis 2](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/24563d3e-dbbc-4288-83cb-8cae6d4139d4)

Flowchart of the project execution –

![Data Analysis 3](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/1d9e8b35-6b22-4519-bd6a-4713a3788df9)

How will the company work —

There is a team of software engineers (falcons) which owns sales management system. The records of this system are stored in MySQL database.

The team of Data Analyst (Data masters) reaches out to the software engineers to get an access to data base which they can use to create the dashboard in PowerBI.

In this same manner our project is going to be executed. We are going to fetch the data from the database from company’s website and then we are going to transform and load the data in the PowerBI to build the dashboard.
How will the company work —

There is a team of software engineers (falcons) which owns sales management system. The records of this system are stored in MySQL database.

The team of Data Analyst (Data masters) reaches out to the software engineers to get an access to data base which they can use to create the dashboard in PowerBI.

In this same manner our project is going to be executed. We are going to fetch the data from the database from company’s website and then we are going to transform and load the data in the PowerBI to build the dashboard.

PART III — Data Analysis using SQL

Step 1: Importing Data to MySQL workbench


![Data Analysis 4](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/9d6a8163-3b8b-4b7c-9733-758d644b38fc)


![Data Analysis 4](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/6699ad0a-d8f9-47e7-9be1-2ccbc3cb8c63)


The import of data is done from an already existing MySQL file. This file has to be loaded into MySQL workbench for further data analysis.

The following images show that the import is a success.

Step 2: Simple analysis of data by looking into different tables and reflecting garbage values

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/234985eb-96f0-45e1-b251-512f44d889c6)

Here, we can see that the table market contains certain values which are incorrect. AtliQ hardware company works only in India but there are some records of different non-existing cities in India.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/e4464122-7eee-4dd3-aa2e-66e492403062)


Here, we can see that table transactions contain certain negative value in amount which is not possible.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/e50e2adf-aff4-4b6b-b22e-516045fcd158)


Here, you can see that certain transactions are in USD. Hence, filtration of that is also needed by converting into INR.

Step 3: Primary analysis of data base by running different SQL statements

1. To find out how many total records are there in transaction table.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/7a48c666-9841-49c0-9b58-0d8011b5ef54)

2. To find number of records in customer table.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/518a1164-2870-4ddd-901f-57a01fe45539)

3. To find out the records from transaction table with a specific market code.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/d2350f3a-d860-4426-9aed-3dc4dbb4a837)

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/1ba4a51f-5ac9-474b-b075-39acf74614d6)

4. To find out transaction of a particular year which is joint by the date table.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/2798f06d-9e1f-43be-a49d-c48aa78138f8)


![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/c255b294-7841-47cd-8447-0fdf2c308553)


Here, we are performing inner join by joining the date and year together which shows record only of the year 2020.

5. To find out the total revenue of a particular year.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/293b5888-6e71-4e5b-a935-fea22b74ec52)

6. To find out the business you did in a particular city (eg. Chennai).

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/28d09007-4544-41d8-abf9-9c4fa73cceb3)

Here the market code of Chennai is used to get all the records. Similarly, if we want different of any other particular city the market code of that city is used.

PART IV — Data Cleaning and ETL (extract transform load)

Step 1: We are going to connect MySQL with the PowerBI dektop

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/47d6b35c-6831-430b-91fb-2fed777bc21e)

Here, we are using MySQL database to connect with the desktop.

Step 2: Loading the data into the PowerBI desktop


![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/8abd08c4-46b4-4ab1-9bb0-85c4dcdc1e52)


Here, we are going to load all the tables we have created in the data base. This load option will connect with the SQL and pull all the records into power BI environment.


![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/8cfe04fb-d9e4-492d-bf1b-352551d69c95)

Step 3: Transforming data with the help of Power Query

1) Performing filtration in market’s table —

When we click on the transform data option, we are directed to Power query editor. Power query editor is where we perform out ETL. Here we can perform data transformation i.e. Data Cleaning/ Data Wrangling/ Data Munging.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/1ac2aaca-d4be-46ff-9108-76f583b91a8b)


Here, we need to filter the rows where the values are null and are inappropriate.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/7499f418-8c3a-430e-9977-45393bc22e0a)

So, we are filtering the data and deselecting the blank option.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/fe65c8e6-bfab-4778-a119-873aff6c190e)


2) Converting the currency from USD to INR in the transaction’s table —

Here the company only works in India so the USD values are not possible. So, we need to convert those USD values into INR by using some formulas. Here we are going to form a separate column and display the converted currency value into it.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/f4f84656-8f4d-4865-9274-72e0ed758b83)


Finding out the total values having USD as currency.


![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/7b0acd7e-0125-4d23-ac52-b24174c17ab6)

By using the correct formula of the conversion, we have converted the USD currency into INR.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/e32bfe19-eb0d-42a9-865b-071d7327ccc1)

Now when we checked the filtration, we found something. Due to some reason the USD is appearing twice. So now we will filter those values also.


![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/0d5ca015-a634-4e40-b2d3-1babb33fa54f)


Hence, all the USD values are converted into INR now.

PART V — Building a Dashboard or a Report

Dashboards/reports are created according to the requirement. What actually the company wants to look for and what is more important for the company is taken into consideration and then after the dashboard is created. There can be n number of variations to create a dashboard. Generally, the dashboard should look understandable and an ease to access.

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/8bdbeb00-2031-49d0-be86-f37c3ff2386f)

This is how the dashboard looks after formatting it completely.

PART VI — Publishing the Report

Step 1: Publishing the report to the web version of PowerBI

![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/d846f13a-40e0-4c2e-b743-7a6332988b85)


![image](https://github.com/PayalGarg1201/Sales-Insights/assets/133757186/a4e8299e-891c-46c2-bf7e-6c1ddaab8aa4)



