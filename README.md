Lateshow API
Project Title:
Lateshow API - A Flask API that manages episodes, guests, and appearances in a late-night show environment.

Project Description:
The Lateshow API is designed to manage and expose data related to episodes, guests, and their appearances on a late-night television show. This project implements an API to handle CRUD operations for episodes, guests, and the appearances made by guests in episodes.

Key Features:
Episodes Management: CRUD operations for managing episodes.

Guest Management: Allows the addition and retrieval of guest information.

Appearance Management: Tracks which guests appeared on which episodes with ratings.

API Endpoints:

Get all episodes

Get episode by ID along with guest appearances

Get all guests

Add a new guest appearance

The backend of this API is built using Flask with SQLAlchemy for database management. The API also integrates Flask-Migrate for database migrations and Flask-CORS to allow cross-origin resource sharing.

The application uses a SQLite database, with models defining relationships between Episodes, Guests, and Appearances.

Technologies Used:
Flask: A micro web framework used for building the API.

SQLAlchemy: ORM for handling the database models and relationships.

Flask-RESTful: To build REST APIs using Flask.

Flask-Migrate: For database migration support.

Flask-CORS: To handle Cross-Origin Resource Sharing.

SQLite: A lightweight SQL database.

Challenges Faced:
Ensuring the correct relationships and data integrity between episodes, guests, and appearances.

Handling circular imports between the models and app configurations.

Setting up database migrations to allow the API schema to evolve over time without losing data.

Table of Contents:
How to Install and Run the Project

How to Use the Project

API Endpoints

Contributing

How to Install and Run the Project:
To get this project up and running locally on your machine, follow the steps below:

Prerequisites:
Python: Version 3.6 or higher.

pip: Python package manager.

Virtual Environment (optional but recommended).

Steps:
Clone the repository:


git clone https://github.com/yourusername/Lateshow-API.git
cd Lateshow-API
Create a virtual environment (optional):


python -m venv venv
source venv/bin/activate  # For macOS/Linux
venv\Scripts\activate     # For Windows
Install dependencies:


pip install -r requirements.txt
Set up the database:

Initialize the database with migrations:


flask db init
flask db migrate
flask db upgrade
Run the Flask application:


flask run
Your application should now be running on http://127.0.0.1:5000.

How to Use the Project:
Once the API is running, you can use the following API endpoints:

1. Get All Episodes:
Endpoint: /episodes

Method: GET

Description: Fetches all episodes.

2. Get Episode by ID:
Endpoint: /episodes/<int:id>

Method: GET

Description: Fetches a specific episode by its ID, along with all guest appearances.

3. Get All Guests:
Endpoint: /guests

Method: GET

Description: Fetches all guests.

4. Add Appearance:
Endpoint: /appearances

Method: POST

Description: Adds a guest appearance to an episode. Requires a JSON payload with the following fields:

rating (integer): The rating of the guest appearance.

episode_id (integer): The ID of the episode.

guest_id (integer): The ID of the guest.