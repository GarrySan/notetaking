# Description
This is a simple notetaking app built using the Django framework for python. One can add new notes and view the previous ones.

# Running the app
Make sure you have the latest Django installed on your system.
In order to run the app, open the terminal, move to the notetaking app folder and write `python manage.py runserver` in the terminal.
This will start the server and you can access the app in your browser at [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

# Creating a superuser
In order to access the admin priveleges of the app you must create a superuser.
To create a superuser run the command `python3 manage.py runserver`

# URL enpoints
The app has just two endpoints:
- `/` : This leads to the homepage of the application.
-  `/admin` : This takes you to the admin page where you can login with your superuser credentials.

# Database models
The app has only one database model:
- Note
    - text: contains a string value of the note taken.
    - created: contains a datetime value autopopulated at the time of creation of the note.

# Styling
All styling related css files can be found at `/static/css/` inside the notes app folder.
The current app has only one main.css file.

# HTML templates
All the html templates for the app can be found at `/templates/` inside the notes app folder
The current app has only one note.html file.

# Views
Views are the funtions that process the request from the frontend, link our data to our templates and link the forms with our Form model inside `forms.py`. This app contains only one view:
- Home: 
    - Adds the NoteObjects data to the template inorder to display all the notes.
    - Links with the NoteForm if the request is a Post request.
    - Renders the template.



# Forms
Forms are a schema for the body of the post api calls from the client to the server. 
This is for when the user is creating a new note. Can be found in the `forms.py` file inside the notes folder.
The app currently has one form:
- NoteForm: Linked to the Note model inside the database.

# Deployment
The app is deployed on a heroku server. Deployment steps followed:
- Install the heroku CLI in your terminal:
    - `brew install heroku/brew/heroku` for mac
    - `sudo snap install heroku --classic` for ubuntu
- Type `heroku login` to login to the heroku CLI
- Go to the git repository of the project through the terminal. Type in terminal: `heroku git:remote -a notetakingdj`
- When you want to deploy the app you can push it using `git push heroku master`
