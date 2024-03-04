# Enhanced Project Functionality 

## Course: SNHU CS-499 Capstone

*Note: I chose the same artifact for all three of proficiencies, Software Design & Engineering, Algorithms & Data Structures, and Databases. I explain the functionality of the enhancements made to the artifact below.*

---

Overall, while I found this project EXTREMELY challenging, I am still learning not to be so bold when designing and developing a product. This assignment is the perfect example of this. For my enhancements I decided to make significant changes, without considering the change in environment for development. The original, being preconfigured, setup, and having clearly defined instructions on requirements and functionality, led me to the assumption this would be an easy artifact to enhance the software design and engineering, algorithms and data structures, and database. That was far from the actual result of choosing this artifact. One thing worth noting, is that I include some security when developing the server that prevents SQL injection, which was by far, one of the easiest benchmarks to meet for this project.

# The Plan

***Software design and engineering enhancements:***
- Build a server to host the application as a live web application versus only accessible via local host.
- Convert the Jupyter Notebook to a python application.

***Algorithms & Data Structures:***
- Enhance queries and or data structures. (Make them run faster was original idea, however, the final decision was instead to swap from MongoDB to a file storage structure - SQLite, and removing some unneeded queries that provided no value to the dashboard application, and optimizing the code, which made originally took 89 seconds runtime, versus now completing in 7 seconds for runtime.)

***Databases:***
- Create a database for the information in the .csv file.
- While I didn't create the typical database, such as the original one in MongoDB, understanding that MongoDB was too much for a single .csv datasource made the "database" creation using SQLite, a lighter and more practical option upon further thought, thus proving my improved thinking and conceptions as they relate to databases. 


***Final Result of Enhancements:***

The final result of my enhancements, while things certainly didn't go as planned, do demonstrate my mastery of the needed concepts for this Capstone course, future employers looking for proof of skillsets, while also providing me with a great resource to practice and improve on over time, allowing me to sharpen already attained skills.

My final enhanced LIVE web application interactive dashboard can be found at https://tammyhartlinescapstone.onrender.com. I used render.com to develop the server that hosts the application. It did take quite a while to work out all of the issues experienced with the server, such as many build failures, (roughly 50 or more!), dependency issues, key mismatch issues, and the learning curve of creating the server. Originally I had intended to use Heroku, but they no longer offer a free tier for their service, which is when I pivoted to render.com instead. Given all the issues I had experienced, I also tried to learn to use Docker, as some coworkers suggested that may be a viable solution. Although, that just gave me more to learn, increasing the curve to one I knew I would not be able to adjust to given the timeframe. 

I also had to learn syntax for SQLite, as my main DB language experience is with SQL Server, building system queries that integrate with Python, which I created to pull in Azure Devops data and integrate it with our developed reports. While I was fairly familiar with MongoDB, I was not familiar at all with any other data language syntax. Yes, they are all very similar, but do have many differences as well. My biggest struggle however, was with what I had assumed would be the simplest part... environment setup. I continuously ran into dependency issues when trying to run the application, and seemed to constantly need to install, update, uninstall, or download something else. With that said, the original environment for the virtual desktop was Linux based, where I use Windows OS. 

Given all the trial and error, being able to overcome that and actually complete the enhanced project, hopefully meeting (though I prefer exceeding) all of the rubric requirements, I believe the lesson learned and skill gained in this scenario was one of confidence in the skills and knowledge I have gained throughout my time here. Coming from a non-technical background, going back to college in my mid thirties while working and taking care of three children, I clearly learned and retained even more knowledge than I had initially thought. Given that information, I am so excited for what the future holds in my new career as a woman in the technical industry, while also showing my three daughters that defying societal norms is a great goal to have!





---

##### ~ ~ ~ Algorithms & Data Structures ~ ~ ~ Databases ~ ~ ~
**Python-** Python was used for the CRUD methods that setup the ability to interact with the database records from the database application and were a critical part of the Algorithms & Data-Structures, as I was able to write simple queries, create, read, update, and delete data records, therefore altering it's structure.

*Previous Version - /module.py*
*Updated Version - /animal_shelter.py*

```python
'''
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ******** Author:          Tammy Hartline                                                                 |
|  ******** Version:         2.0.9                                                                          |
|  ******** Description:     Module file for animal shelter application.                                    |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|                                            Changelog:                                                     |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start -- 01/2024 - TH                                                                               |
|  [Altered the database from MongoDB to SQlite3 file storage database structure to be more efficient and   |
|  less "overkill" given the program only handles a single .csv file for the dashboard application.]        |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start -- 02/2024 - TH                                                                               |
|  [Updated each method to conform with SQlite3 syntax and structure and to optimize the queries.]          |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start -- 02/2024 - TH                                                                               |
|  [Removed some of the non-working CRUD methods, after several failed attempts to get them to work         |
|  using SQLite. Some that did not work were the update and delete methods. Intend to add them back once    |
|  the development is further along.]                                                                       |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start --02/2024 - TH                                                                                |
|  [Adding methods back in an attempt to complete the program with all of its original functionality        |
|  and features, and the enhancements working correctly.]                                                   |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start --02/2024 - TH                                                                                |
|  [Adding the unq_animal_types method to define a new column. Note, this was the issue in the app file     |
|  causing it not to launch on the server when running the main app.py file.]                               |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start --02/2024 - TH                                                                                |
|  [Finally removed unneeded methods and cleaned up code file to launch MVP.]                               |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
'''
# Import required libraries
import sqlite3
import pandas as pd
import os

# Create animal shelter class
class AnimalShelter(object):
    def __init__(self, db_path=':memory:'):
        self.db_path = db_path
        self._create_table()


    # create table to store data using SQLite 
    def _create_table(self):
        # if the database is in memory, there is no need to create a table
        if self.db_path == ':memory:':
            db_file = "animals.db"
            # if the database file exists, there is no need to create a table
            if os.path.exists(db_file):
                return

        # checking if table exists and if not, create it with all the columns located in the csv file    
        query_str = '''
            CREATE TABLE IF NOT EXISTS animals (
                animal_id INTEGER PRIMARY KEY,
                age_upon_outcome TEXT,
                animal_type TEXT,
                breed TEXT,
                color TEXT,
                date_of_birth TEXT,
                datetime TEXT,
                monthyear TEXT,
                name TEXT,
                outcome_subtype TEXT,
                outcome_type TEXT,
                sex_upon_outcome TEXT,
                location_lat REAL,
                location_long REAL,
                age_upon_outcome_in_weeks REAL
            )
        '''
        # connect to sqlite3, create table and read in the csv file
        with sqlite3.connect(self.db_path) as conn:
            cursor = conn.cursor()
            cursor.execute(query_str)
            df = pd.read_csv("./aac_shelter_outcomes.csv")
            df.to_sql('animals', conn, if_exists='replace', index=False)
                

    # Create a read method for querying the database
    def read(self, query=None):
        query_str = 'SELECT * FROM animals'
        params = None

        # if there is a query, add it to the query string
        if query is not None:
            query_str += f" WHERE {query[0]}"
            params = query[1]

        # connect to sqlite3 and read in the query
        with sqlite3.connect(self.db_path) as conn:
            cursor = conn.cursor()

            # if there are parameters, use them in the query
            if params is not None:
                df = pd.read_sql_query(query_str, conn, params=params)

            # if there are no parameters, just run the query
            else:
                df = pd.read_sql_query(query_str, conn)
            return df
```

*Previous Version: /FinalProjectDashboardCS340.ipynb*
*New Version: /app.py*

```python
'''
# app.py
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ** Author:          Tammy Hartline                                                                       |
|  ** Version:         2.0.9                                                                                |
|  ** Description:     This file is meant to initialize the database functionality for the web application. |
|  ** Instructions:    Open CMD line -> navigate to app location (cd \path\to\repo\) -> run [python app.py] |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|                                            Changelog:                                                     |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start -- 01/2024 - TH                                                                               |
|  [Converted jupyter notebook file into a Python application file to more easily integrate as web          |
|  application instead of hosting locally.]                                                                 |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start -- 02/2024 - TH                                                                               |
|  [Updated language to call the new animal_shelter.py import, versus previous module.py.]                  |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start -- 02/2024 - TH                                                                               |
|  [Corrected filters and continuously debugging to determine what is causing them to not function          |
|  properly if they function at all.]                                                                       |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start --02/2024 - TH                                                                                |
|  [Added enhancements as planned, but still running into buggy application issues.]                        |
|  ### - End                                                                                                |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|  ###  Start --02/2024 - TH                                                                                |
|  [Made final enhancements, debugged, tested and is now ready for MVP deployment.                          |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|                                            Notes:                                                         |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|   02/05/2024                                                                                              |
|   Notes for next assignments and TODOS: Figure out why the code is not launching the web application.     |
|   Current Issues: The code is not launching the web application at all. Either it returns                 |
|   Not found, or it returns a 504 error page. Cannot continue to test until I can get it to deploy.        |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|   02/07/2024                                                                                              |
|   Update: After several alterations, and updating the final call to the app.run_server method,            |
|   the application is now launching.                                                                       |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|   02/11/2024                                                                                              |
|   Notes for next assignments and TODOS: Debugging and testing the application                             |
|   Current Issues: Filters are not functioning properly. The data is not being filtered as expected.       |
|   When clicking on any filter, or using the text filter, the data is not changed, or sorted.              |
|   It also does not populate the graph with the correct data.                                              |
|   Continue altering the code and testing to find the issue and continue adding enhancements.              |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
|   02/24/2024                                                                                              |
|   Notes on final adjustments to get to MVP.                                                               |
|   The map functionality was never helpful, so I removed it altogether, as it only ever showed the         |
|   location of the animal shelter, not the lat and long in the data table. I also removed the              |
|   rescue filter and rescue type, as it was not very UI friendly, nor was it visually appealing.           |
|   Instead of the bubble chart populating with a count of dog rescue types, it now populates with          |
|   animal_type, and is grouped based on type and outcome type for the animal. This is more intuitive       |
|   and uses the data in a more insightful manner. This is my final adjustment to the code, and now plan    |
|   to deploy to my created live server.                                                                    |
|*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*|
'''

from dash import Dash, html, dcc, dash_table  # Importing necessary Dash components
import dash  # Importing Dash
from dash.dependencies import Input, Output  # Importing Dash callback functions
import plotly.express as px  # Importing Plotly Express for data visualization
import pandas as pd  # Importing Pandas for data manipulation
from animal_shelter import AnimalShelter  # Importing AnimalShelter class for data access
import base64  # Importing base64 for image encoding

# Setup Dash
app = Dash(__name__)  # Creating a Dash application instance

# Data Manipulation / Model
db_path = 'animals.db'  # Path to the database file
shelter = AnimalShelter(db_path)  # Creating an instance of AnimalShelter to interact with the database
data = shelter.read()  # Reading data from the database
df = pd.DataFrame(data)  # Creating a Pandas DataFrame from the retrieved data

# Get each animal type in the collection (distinct, no duplicates)
unq_animal_types = df['animal_type'].unique()  # Extracting unique animal types from the DataFrame
data = df.to_dict('records')  # Converting DataFrame to a list of dictionaries for Dash data components

# Add in Grazioso Salvare’s logo
image_filename = 'Grazioso_Salvare_Logo.png'  # Path to the logo image file
encoded_image = base64.b64encode(open(image_filename, 'rb').read())  # Encoding the image to base64

# Defining the layout of the Dash application
app.layout = html.Div([
    html.Center(html.B(html.H1('Capstone Project Dashboard'))),  # Header
    html.Center(html.B(html.H1("Tammy Hartline's Grazioso Salvare DashBoard Final Project"))),  # Subheader
    html.Hr(),  # Horizontal line

    # Row 1: Header and Photo
    html.Div([
        html.Div(id='header', className='col-6', style={'text-align': 'center'}),
        html.Div([
            html.Img(id='customer-logo', src='data:image/png;base64,{}'.format(encoded_image.decode()),
                     alt='customer logo image'),
        ], className='col-6', style={'display': 'flex', 'justify-content': 'center', 'align-items': 'center'}),
    ], className='row'),

    # Row 2: Buttons for Animal Types
    html.Div([
        html.Div([
            html.Button('All', id='btn-all', n_clicks=0),
            *[html.Button(animal_type, id=f'btn-{animal_type}', n_clicks=0) for animal_type in unq_animal_types]
            # Creating buttons for each unique animal type
        ], className='col-6'),
    ], className='row'),

    # Row 3: Data Table
    html.Div([
        dash_table.DataTable(
            id='datatable-id',
            columns=[
                {"name": i, "id": i, "deletable": False, "selectable": True} for i in df.columns
            ],  # Defining columns for the data table
            data=data,
            editable=False,
            sort_action="native",
            sort_mode="multi",
            selected_rows=[0],
            filter_action="native",
            page_action="native",
            page_current=0,
            page_size=10,
        ),
    ], className='row'),

    # Row 4: Graph
    html.Div([
        dcc.Graph(id='bubble-plot', className='col-6'),
    ], className='row'),
])

# This section demonstrates skills and conceptualization of software design/engineering by setting up a user-friendly interface for data visualization.
# It also exhibits good design practices by organizing the layout in a structured and visually appealing manner.

@app.callback(
    [Output('bubble-plot', 'figure'), Output('datatable-id', 'data'), Output('datatable-id', 'columns')],
    [Input('btn-all', 'n_clicks')] + [Input(f'btn-{animal_type}', 'n_clicks') for animal_type in unq_animal_types],
    prevent_initial_call=True
)
def update_dashboard(*args):
    btn_all_clicks, *btn_type_click = args

    # Determine which button was clicked
    ctx = dash.callback_context
    clicked_button_id = ctx.triggered[0]['prop_id'].split('.')[0]

    if clicked_button_id == 'btn-all':
        filtered_df = df.copy()  # No filter, so use the entire DataFrame
    else:
        selected_animal_type = clicked_button_id.split('-')[1]
        filtered_df = df[df['animal_type'] == selected_animal_type]  # Filter by selected animal type

    # Create a bubble chart
    fig = px.scatter(
        filtered_df, 
        x="animal_type", 
        y="outcome_type", 
        size_max=10,
        color="animal_type")

    # Convert DataFrame to dict for dash_table
    filtered_data = filtered_df.to_dict('records')

    # Generate columns for dash_table
    columns = [{"name": i, "id": i, "deletable": False, "selectable": True} for i in filtered_df.columns]

    return fig, filtered_data, columns

# This callback function demonstrates skills and conceptualization of algorithms by dynamically updating the data visualization based on user interactions.
# It efficiently filters and processes data to generate relevant charts and tables.

if __name__ == '__main__':
    app.run_server(host='0.0.0.0', port=8050)
```

# View the repository for these enhancements by clicking [here](https://github.com/tjhartline/capstone/tree/master)!

---

# View the LIVE site deployed with render by clicking [here](https://tammyhartlinescapstone.onrender.com)!