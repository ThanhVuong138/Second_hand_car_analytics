![p2 architech](https://github.com/ThanhVuong138/Second_hand_car_analytics/assets/106426014/965c7d90-f232-4ff6-8d04-c3cb3c927f95)

1, Business objective: The purpose of the business is to develop the car company's app in the future, which will integrate additional features such as buying and selling used cars, analyzing the second-hand car market in Vietnam in terms of preference level and resale value, thereby identifying and capturing potential customers. It will serve as a data foundation for customer conversion and cross-selling tasks.

2, Requirements: Combine customer data from car purchases and services at the company's database stored on AWS with customer data from web scraping of used car transactions on websites like xetot.com, chotot.com, etc to provide analysis and supplement additional data for the sales team to enhance marketing efforts.

3, Description of the data retrieval and processing workflow:

Step 1: Retrieve data from S3, convert the semi-structured data (.json) into structured data, and process fields with null values, duplicates, and missing information, using Lambda.

Step 2: Transform the processed data from Lambda to S3 for storing purposes.

Step 3: Synchronize the processed data from S3 to AWS Redshift for analytic purposes

Step 4: Perform web scraping on used car transactions on an on-premise server.

Step 5: Push the web scraped data onto AWS Redshift through the S3 public environment. Mapping the two data sources and map key joins such as name, age, phone number, car model, and year of purchase and storing data on Redshift

***In case the user team needs data for their activities to serve for sale or service, customer marketing, continue doing step 6 --> step 7. 

Step 6: After mapping data, push the web scraped data onto AWS Redshift through an S3 public environment

Step 7: Export the processed data from RDS to an Excel file on the on-premise server through S3, which makes it easily accessible for the sales or user team.

Note: Processes are automated and monitored through Airflow. EC2 instances are used for computing, CloudWatch logs historical data, CloudTrail tracks user activities within the pipeline, S3, and Redshift for storing data.
