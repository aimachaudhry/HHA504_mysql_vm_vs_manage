# MySQL on VM vs Managed Service

## Overview
On Google Cloud Platform (GCP), I created and interacted with two databases. The first was a MySQL instance on a virtual machine and the other was a managed Cloud SQL. I connected to both the databases using SQLAlchemy in Python, created a table, and read it back. The region that I chose was us-central1-a.

## Learning Objectives

From this assignment, I was able to learn the differences between self-managed MySQL on a VM and managed MySQL in the cloud. I learned how to configure network and create users, as well as testing and connecting the databases. 

### MySQL on a VM Steps:
1. Create a VM instance in GCP
2. Create a Firewall Rule to allow traffic to come into port 3306 and port 22
3. Install & configure MySQL in the SSH terminal by installing server packages and ensuring that all privileges are granted to the user
4. Create the database in the terminal and change the bind-address to allow all ingress
5. Test locally on VS Code by creating a .env file with credentials and running a python script using pandas
   

### MySQL on a Managed Service Steps:
1. Create an instance in Cloud SQL
2. Connect database by using Cloud Shell
3. Grant privileges
4. Run script to test on VS Code
