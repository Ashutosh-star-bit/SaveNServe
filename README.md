🍽️ Save N Serve: Redirecting Surplus Food
Save N Serve is a full-stack web application designed to connect food donors (Mess Staff, Event Organizers) with organizations (NGOs, shelters, and animal care facilities) to prevent food waste and combat hunger. The platform facilitates the seamless reporting, requesting, and management of surplus food donations.

✨ Key Features
The system supports a dual-role user structure to manage the donation lifecycle:
Feature,Role,Description
User Authentication,All,Secure sign-up and login with distinct roles: Mess Staff (Donor) and NGO / Shelter (Requester).
Surplus Reporting,Mess Staff,"Quick form to report available leftovers, including quantity and pickup location."
Event Donations,Donor,"Dedicated form for scheduling large-scale donations (e.g., weddings, conferences)."
Food Requests,NGO / Shelter,Ability for NGOs to submit requests for food pickups.
Animal Feed Redirect,All,Separate form for directing food unsuitable for human consumption to animal shelters.
Dashboard Management,Staff/NGO,Role-specific dashboard for accepting or declining pending donations (for NGOs) and pending requests (for Staff).
Statistics & History,All,Track total meals saved and view a history of all accepted/declined activities.
Map Tracker,All,Interactive map preview to visualize nearby NGOs and shelters (requires Google Maps API key).

💻 Tech Stack
Component,Technology,Description
Backend Framework,Python (Flask),Provides the RESTful API endpoints for application logic and data processing.
Database,MySQL,"Persistence layer for storing user accounts, donations, requests, and activity data."
Database Connector,mysql.connector,Python library for interacting with the MySQL database.
Frontend,"HTML5, CSS3, Vanilla JavaScript",Responsive and clean user interface with a modern aesthetic defined in styles.css.
API Handling,Fetch API,Centralized script (scripts/app.js) handles all form submissions and API communication.

🛠️ Setup and Installation Guide
Prerequisites
Ensure you have the following installed on your system:

Python 3.x

MySQL Database Server

1. Clone the Repository
git clone https://github.com/Ashutosh-star-bit/SaveNServe.git
cd save-n-serve

2. Install Python Dependencies
Install the required Python libraries using pip:
pip install Flask mysql-connector-python

3. Database Configuration
The application is configured to connect to a MySQL server.

Database Connection: The default credentials used for connection are user='root' and password='tiger'.

Update Credentials: You must open SaveNServe/app.py and change the MYSQL_CONFIG dictionary to match your local MySQL credentials if they are different:
# SaveNServe/app.py
MYSQL_CONFIG = {
    'user': 'root',
    'password': 'your_mysql_password_here', # <-- UPDATE THIS
    'host': 'localhost',
    'database': 'savenserve_db'
}
Automatic Setup: The backend handles the creation of the savenserve_db database and all necessary tables (users, donations, food_requests, etc.) upon the first successful run and interaction with API routes.

4. Google Maps Setup (Optional)
To enable the map functionality in map.html and index.html:

Get a Google Maps JavaScript API Key.
Open SaveNServe/scripts/config.js and replace the placeholder value:
// SaveNServe/scripts/config.js
const GOOGLE_MAPS_API_KEY = "REPLACE_WITH_YOUR_REAL_KEY";

5. Run the Application
Start the Flask development server:
python SaveNServe/app.py
The server will typically start at http://127.0.0.1:5000.

📌 Usage
Access the application in your web browser at: http://127.0.0.1:5000/

Demo Credentials
You can use the following accounts to test the different user roles:
Role,Username,Password
Mess Staff (Donor),staff,1234
NGO / Shelter (Requester),ngo,1234
General,student,1234
,(Or sign up for a new account),
