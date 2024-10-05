# Lambda_RDS_Datatream
ETL pipeline to use Amazon EventBridge schedule Lambda task, pulling API data and loading to MySQL RDS.
![Lambda_RDS_Datatream](https://github.com/user-attachments/assets/f46da575-5f26-4777-8223-64b84f080c34)

## MySQL RDS
1. Open Amazon RDS and in the Databases section select "Create database".
2. Choose "Easy Create" and "MySQL" in configuration.
3. Free tier for DB instance Size.
4. Under "DB instance identifier" provide the database the name of your choice.
5. Create username and password and kleep a note of them.
6. In the Inbound and Outbound traffic, allow all traffic for your computer IP address.
7. Take the RDS info from the database and enter it in your local MySQL Workbench to setup the connection.
8. Once connected, create a new databse and provide the database the name of your choice..

## Lambda
1. Open Lambda and create a new function.
2. For Runtime, choose "Python 3.12" or any other latest version.
3. Everything else can be left as default.
4. In the code section add the script from "API2RDS.txt" file
5. For the code to work we are importing 3 libraries:-
   - requests
   - pandas
   - mysqlConnector
6. pip install these libraries in a python environment and upload it in the Layers section of Lambda.
   FIles in the Layers folder can also be used for upload.
   This link is helpful to understand it:-
   https://www.youtube.com/watch?v=grRW1Z_C9vw&ab_channel=TechwithHitch
7. Got to the Configuration tab in the fuction and look for RDS databases.
8. Select "Connect to RDS database" and select the database we just creted.
9. In the code change the bucket name adn database connection info as per your choice.
10. To test the connection and data output, create a Test eventy an run this.

## Amazon EventBridge
1. To schedule this task open Amazon EventBridge.
2. Create schedule using "Eventbridge Schedule".
3. Give it some name and description.
4. Select "Recurring schedule" under Schedule pattern.
5. And then based on your prefernce you can schedule the task.
