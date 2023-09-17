![image](https://github.com/ThanhVuong138/Second_hand_car_analytics/assets/106426014/699f5e29-afd4-4f90-9b9f-7dbb4470eb49)

1, Business objective: The purpose of the business is to develop the car company's app in the future, which will integrate additional features such as buying and selling used cars, analyzing the second-hand car market in Vietnam in terms of preference level and resale value, thereby identifying and capturing potential customers. It will serve as a data foundation for customer conversion and cross-selling tasks.

2, Requirements: Combine customer data from car purchases and services at the company's database stored on AWS with customer data from web scraping of used car transactions on websites like xetot.com, chotot.com, etc to provide analysis and supplement additional data for the sales team to enhance marketing efforts.

3, Description of the data retrieval and processing workflow:

Step 1: Retrieve data from S3, convert the unstructured data (.json) into structured data, and process fields with null values, duplicates, missing information, using Lambda.

Step 2: Synchronize the processed data from Lambda to Redshift.

Step 3: Perform web scraping on used car transactions on an on-premise server.

Step 4: Push the web scraped data onto AWS Redshift through by S3.

Step 5: Mapping the two data sources and map key join such as name, age, phone number, car model, and year of purchase.

Step 6: Export the processed data from RDS to an Excel file on the on-premise server through by S3, that make it easily accessible for the sales or user team.

Note: Processes are automated and monitored through Airflow. EC2 instances are used for computing, CloudWatch logs historical data, and CloudTrail tracks user activities within the pipeline, S3 and Redshift for storing data.