# simple-webapp
**Basic Web App with Flask & MySQL**

This repository contains a very simple Python Flask web application.  
It’s meant as a minimal example for learning Flask.

Below you’ll find step-by-step instructions to set this up on a typical Linux system.

**Overview of setup steps**

This app provides two routes:
- `/` → returns **"Welcome!"**
- `/how are you` → returns **"I am good, how about you?"**


1. Install necessary packages & libraries

2. Install and configure the Flask application

3. Start the Flask web server

4. Access the app via a web browser

**Install required packages**
Make sure Python, pip, and other dependencies are installed:

apt-get update
apt-get install -y python3 python3-pip python3-dev build-essential libmysqlclient-dev

pip3 install flask flask-mysql

**Run the web server**
Use Flask to launch the app on all interfaces:
export FLASK_APP=app.py
flask run --host=0.0.0.0

**Try it out**
Open your browser and test the endpoints:
http://<your-server-ip>:5000 → should show: Welcome

http://<your-server-ip>:5000/how%20are%20you → should respond: I am good, how about you?



