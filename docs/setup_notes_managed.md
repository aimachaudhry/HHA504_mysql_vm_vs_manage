# MYSQL on Managed Service: Google Cloud Provider

## In Cloud SQL create an instance:
- Choose Sandbox version and MySQL 8.0
- Create a username and password
- Select **Public IP**
- Create instance
<img width="1044" height="121" alt="Screenshot 2025-11-19 at 8 37 14 PM" src="https://github.com/user-attachments/assets/4ed7c0f7-ba3d-4e59-a873-f14a547684a0" />
<img width="541" height="301" alt="Screenshot 2025-11-19 at 8 38 28 PM" src="https://github.com/user-attachments/assets/0241d391-e579-4ed6-a3a0-7d389f72c34f" />

## Grant user rights
In the Google Cloud Shell enter:

````
gcloud sql connect aimadb --user=root --quiet
````
Enter in your password

- When I tried to grant privileges, I continued to run into errors
- To resolve this I had to create a user:
````
CREATE USER 'aima'@'%' IDENTIFIED BY 'PASSWORD'
GRANT ALL PRIVILEGES ON aimadb.* to 'aima'@'%'
FLUSH PRIVILEGES
````
Note: An example passowrd was used to maintain confidentiality 
<img width="1142" height="467" alt="Screenshot 2025-11-19 at 8 54 45 PM" src="https://github.com/user-attachments/assets/52990217-ec8c-4c9b-942b-93456f559ee1" />

## Connecting & Testing:

On VS Code, create .env file and fill in credentials:
```
MAN_DB_HOST=your-managed-endpoint
MAN_DB_PORT=3306
MAN_DB_USER=class_user
MAN_DB_PASS=change_me
MAN_DB_NAME=class_db_netid
```

- Once I tried to run the code to create the dataframe, I was having connectivity issues. I was getting a message that the server could not be connected and was timed out. As an attempt to resolve this, I edited the database in GCP to **allow unencrypted network traffic.** However, I continued to get the same message.
-  <img width="778" height="40" alt="Screenshot 2025-11-19 at 9 24 30 PM" src="https://github.com/user-attachments/assets/9fe6244d-61fe-4491-bcf2-871abe450122" />


