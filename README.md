# simple-webapp
Basic Web App with Flask & MySQL

This repository contains a straightforward Python Flask application connected to a MySQL database. It serves as an example for provisioning environments with Ansible Playbooks.

Below you’ll find step-by-step instructions to set this up on a typical Linux system.

Overview of setup steps

Install necessary packages & libraries

Set up the MySQL database

Launch the database service

Install and configure the Flask application

Start the Flask web server

Access the app via a web browser

Install required packages
Make sure Python, pip, and other dependencies are installed:

apt-get update
apt-get install -y python3 python3-pip python3-dev build-essential libmysqlclient-dev
pip3 install mysqlclient flask flask-mysql

Install & configure MySQL
Install the MySQL server and client tools:
apt-get install -y mysql-server mysql-client

Start MySQL and prepare the database
Start the MySQL service:

service mysql start

Log in and set up your database and user:

mysql -u root -p

CREATE DATABASE employee_db;
CREATE USER 'db_user'@'%' IDENTIFIED BY 'Passw0rd';
GRANT ALL PRIVILEGES ON employee_db.* TO 'db_user'@'%';
USE employee_db;
CREATE TABLE employees (name VARCHAR(20));
INSERT INTO employees VALUES ('JOHN');

Set up the Flask appDownload or create your app.py file. Make sure to update it with your database connection parameters (host, user, password, db).
Install Flask dependencies if you haven’t already:

pip3 install flask flask-mysql

Run the web server
Use Flask to launch the app on all interfaces:
export FLASK_APP=app.py
flask run --host=0.0.0.0

Try it out
Open your browser and test the endpoints:
http://<your-server-ip>:5000 → should show: Welcome

http://<your-server-ip>:5000/how%20are%20you → should respond: I am good, how about you?

http://<your-server-ip>:5000/read%20from%20database → should display: JOHN

