# Concepts Covered in the Lab

## Authentication
The process of verifying the identity of a user or system.

## User
Represents an individual who interacts with the Django application.  
It typically includes information such as **username**, **password**, and **email**.

## Registration
The process of creating a new user account in the application.

## Login
The process by which a user provides credentials (such as username and password)  
to access a protected area of the application.

## Logout
The process of ending a user’s session and removing their authentication status.

# 🛠️ Import OnlineCourse App Template and Database

## Step 1: Open the Terminal
If the terminal is not already open:
- Navigate to the top menu bar.
- Click on `Terminal > New Terminal`.
- Ensure your current working directory is `/home/project`.

## Step 2: Download and Extract the Code Template
Run the following commands in the terminal to import the OnlineCourse app template and database:

```bash
wget "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0251EN-SkillsNetwork/labs/m5_django_advanced/lab2_template.zip"
unzip lab2_template.zip
rm lab2_template.zip

#🚀 Setup Guide: Import and Run the OnlineCourse App

## 📁 Step 1: Navigate to the Project Folder

Open your terminal and ensure you're in the correct directory:

```bash
cd lab2_template
```

# 📦 Step 2: Install Required Packages
Run the following commands to set up your Python environment and install dependencies:
pip install --upgrade distro-info
pip3 install --upgrade pip==23.2.1
pip install virtualenv
virtualenv djangoenv
source djangoenv/bin/activate
pip install -U -r requirements.txt

hese steps will:
• 	Upgrade system info tools and pip
• 	Create and activate a virtual environment named 
• 	Install all required packages from 

# 👤 Display User Information with Django Authentication

Django's authentication system is a built-in app used for managing user authentication and authorization.

---

## 🔐 Step 1: Create a Superuser

Stop the development server if it's running, then execute the following command:

```bash
python3 manage.py createsuperuser
```
Enter the required details:
• 	Username
• 	Email
• 	Password
Once completed, you should see:
Superuser created successfully.

# Step 2: Restart the Server
Start the development server again:
`python3 manage.py runserver`

```python
python3 manage.py runserver
```

# 🌐 Step 3: Access the Admin Interface
- Click Launch Application and enter port 8000.
- In the browser tab that opens, go to:

`https://userid-8000.theiadocker-1.proxy.cognitiveclass.ai/admin`

- Log in using the superuser credentials you just created.

# 🧾 Step 4: Update Superuser Profile
- Click Users under the AUTHENTICATION AND AUTHORIZATION section.
- Select the superuser you created.
- Add profile details such as:
- First name
- Last name
- Scroll down and click Save to store the changes.

# 🖥️ Step 5: Display User Info on the Main Page
Open the template file:
onlinecourse/templates/onlinecourse/course_list.html


Locate the comment <!--Authentication section--> and insert the following code snippet below it:
{% if user.is_authenticated %}
  <p>Username: {{ user.username }}, First name: {{ user.first_name }}, Last name: {{ user.last_name }}</p>
{% endif %}



🧠 How It Works
- Django automatically provides the user object to templates and views based on the session ID after login.
- The {% if user.is_authenticated %} tag checks if the user is logged in.
- If authenticated, it displays profile information such as username, first name, and last name.

# 🧪 Step 6: Test the Setup
Ensure the development server is running, then visit:
`https://userid-8000.theiadocker-1.proxy.cognitiveclass.ai/onlinecourse`


You should now see the logged-in user's information displayed at the top of the page.

✅ You're now successfully using Django's authentication system to display user profile data!











