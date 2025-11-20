# MySQL on a VM: Google Cloud Provider

## Create a VM instance in GCP:
1. Select default region (us-central1-a)
2. Choose E2-small as the machine type to have 2GB of Memory
3.  Select Ubuntu as the operating system
<img width="1057" height="315" alt="Screenshot 2025-11-19 at 3 20 55 PM" src="https://github.com/user-attachments/assets/a83acacb-6a99-48e3-8af3-82a8272bb667" />

4. Create a Firewall Rule to allow traffic to come into port 3306 and port 22
5.  For the Source IPv4 Range, enter the range 0.0.0.0/0
  <img width="780" height="202" alt="Screenshot 2025-11-19 at 2 32 32 PM" src="https://github.com/user-attachments/assets/917c84fc-2766-43f8-a650-7976f3f82a51" />

 ## Install & Configure MySQL:

### In SSH Window:
**Install server packages:**
````
sudo apt-get update
sudo apt install mysql-server mysql-client -y
```````
<img width="896" height="340" alt="Screenshot 2025-11-19 at 2 48 13 PM" src="https://github.com/user-attachments/assets/67838d58-fe62-4c43-a22c-d08880058e75" />

### **Create user and grant all privileges:**

````
sudo mysql
CREATE USER ‘user’@’%’ IDENTIFIED BY ‘password’;
GRANT ALL PRIVILEGES on *.* to ‘user’@’%’WITH GRANT OPTION;
SELECT * from mysql.user \G
````
**Note: the username and password are protected and example names were used**
<img width="490" height="504" alt="Screenshot 2025-11-19 at 3 25 00 PM" src="https://github.com/user-attachments/assets/fd614196-e14f-4e53-a7e5-939a08452bbf" />



### **Create Database:**
````
Show databases;
Create database tempdata;
Show databases;
Use tempdata;
````
<img width="194" height="197" alt="Screenshot 2025-11-19 at 3 20 16 PM" src="https://github.com/user-attachments/assets/4ee22902-e9ee-49f2-b172-abfb0eecf65b" />


### **Open a new terminal to configure Nano and bind-address:**
````
Sudo apt install nano
sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
````
- To allow all ingress change both bind-address and mysqlx-bind-address to 0.0.0.0
- Press CTRL + O to save
- Press Enter to confirm
- Then exit

## Testing Locally on VS Code:

### - Create .env file and fill in actual credentials:
````
VM_DB_HOST=10.0.1.10
VM_DB_PORT=3306
VM_DB_USER=class_user
VM_DB_PASS=change_me
VM_DB_NAME=class_db_netid
````

### - Run `scripts/managed_demo.py` to create dataframe

<img width="649" height="144" alt="Screenshot 2025-11-19 at 5 53 28 PM" src="https://github.com/user-attachments/assets/135be1d8-5a53-4972-8b90-8e998391e7cb" />

### - Confirm database was created by showing tables in SSH:
````
sudo mysql
show databases;
use tempdata;
show tables;
select * from visits;
````
<img width="527" height="403" alt="Screenshot 2025-11-19 at 5 58 05 PM" src="https://github.com/user-attachments/assets/91a9c548-b9ef-465a-99ea-5e499ef413eb" />

### - Be sure to delete VM instance at the end




