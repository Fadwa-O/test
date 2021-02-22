# Full Stack Developer course - Final Project

## Casting Agency Project

The Casting Agency models a company that is responsible for creating movies and managing and assigning actors to those movies.
Depending on my studies in this course, my role comes in applying what I have learned in creating a website for this agency, starting from scratch.


## Runing the application locally
### Installing Dependencies

##### Python 3.7

Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)

##### Key Dependencies

- [Flask](http://flask.pocoo.org/)  is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) is the Python SQL toolkit and ORM we'll use handle the lightweight sqlite database. You'll primarily work in app.py and can reference models.py.

- [Flask-CORS](https://flask-cors.readthedocs.io/en/latest/#) is the extension we'll use to handle cross origin requests from our frontend server.

##### PIP Dependencies
Once you have your virtual environment setup and running, install pip dependencies by navigating to the `/starter` directory and running:

```bash
pip3 install -r requirements.txt
```
This will install all of the required packages.

### Database Setup
With Postgres running, restore a database using the capstoneFSND.psql file provided. From the starter folder in terminal run:

```bash
psql capstoneFSND < capstoneFSND.psql
```


### Running the server

From within the `/starter` directory first ensure you are working using your created virtual environment.

To run the server, execute:

```bash
# On Linux : export

 export FLASK_APP=app.py
 export FLASK_ENV=development # enables debug mode
 python3 app.py

# On Windows : set

set FLASK_APP=app.py;
set FLASK_ENV=development
flask run
```


## Testing
In order to running tests locally navigate to the `/starter` folder and run the following commands:
```
dropdb capstoneFSND_test
createdb capstoneFSND_test
psql capstoneFSND_test < capstoneFSND.psql
python3 test_app.py
```
The first time you run the tests, omit the dropdb command.



## API Reference

### Getting Started
* Base URL: This application can be run locally at http://0.0.0.0:8080/, and is hosted on Heroku at https://capstone-fsnd-fadwa.herokuapp.com
* Authentication: This application requires authentication to perform various actions. All the endpoints require various permissions, except the  `\health` endpoint, that are passed via the Bearer token.

* The application has three different types of roles:
     - Casting Assistant:
       * Can view actors and movies
     - Casting Director:
       * All permissions a Casting Assistant has and…
       * Add or delete an actor from the database
       * Modify actors or movies
     - Executive Producer
       * All permissions a Casting Director has and…
       * Add or delete a movie from the database

### Error Handling
Error Handling

Errors are returned as JSON objects in the following format:

```
{
    "success": False,
    "error": 400,
    "message": "bad request"
}
```

The API will return following errors based on how the request fails:

* 400: Bad Request
* 401: Unauthorized
* 403: Forbidden
* 404: Resource Not Found
* 405: Method Not Allowed
* 422: Not Processable

### Endpoints

#### GET /actors
* General: Returns a list of actors and success value.

```
{
    "actors": [
        {
            "age": 17,
            "gender": "Male",
            "id": 1,
            "name": "A"
        },
        {
            "age": 18,
            "gender": "Male",
            "id": 2,
            "name": "B"
        },
        {
            "age": 19,
            "gender": "Male",
            "id": 3,
            "name": "C"
        },
        {
            "age": 20,
            "gender": "Male",
            "id": 4,
            "name": "D"
        }
    ],
    "success": true
}
```
#### GET /movies
* General: Returns a list of movies and success value.

```
{
    "movies": [
        {
            "id": 1,
            "movie_title": "Movie 1",
            "release_date": "Wed, 06 May 2020 11:51:55 GMT"
        },
        {
            "id": 2,
            "movie_title": "Movie 2",
            "release_date": "Thu, 06 May 2021 11:51:55 GMT"
        },
        {
            "id": 3,
            "movie_title": "Movie 3",
            "release_date": "Fri, 06 May 2022 11:51:55 GMT"
        },
        {
            "id": 4,
            "movie_title": "Movie 4",
            "release_date": "Sat, 06 May 2023 11:51:55 GMT"
        }
    ],
    "success": true
}
```



#### POST /actors

* General:
  - Creates a new actor.
  - Returns the new actor info and success value.


```
{
    "created_actor": [
        {
            "age": 23,
            "gender": "Female",
            "id": 5,
            "name": "fadwa"
        }
    ],
    "success": true
}
```

#### POST /movies

* General:
  - Creates a new movie.
  - Returns the new movie info and success value.


```
{
    "created_movie": [
        {
            "id": 5,
            "movie_title": "Taken 3",
            "release_date": "Tue, 06 May 2014 11:51:55 GMT"
        }
    ],
    "success": true
}
```


#### PATCH /actors/{actor_id}

* General:
  - Update the information of a previously registered actor.
  - Returns the actor updated info and success value.


```
{
    "success": true,
    "updated_actor": [
        {
            "age": 17,
            "gender": "Female",
            "id": 1,
            "name": "fadwa up"
        }
    ]
}
```


#### PATCH /movies/{movie_id}

* General:
  - Update the information of a previously registered movie.
  - Returns the movie updated info and success value.

```
{
    "success": true,
    "updated_movie": [
        {
            "id": 2,
            "movie_title": "Taken3 Patch",
            "release_date": "Thu, 06 May 2021 11:51:55 GMT"
        }
    ]
}
```


#### DELETE /actors/{actor_id}
* General:
  - Deletes the actor of the given ID if it exists.
  - Returns id of deleted actor upon success and success value.


```
{
    "deleted_actor_id": 1,
    "success": true
}

```


#### DELETE /movies/{movie_id}
* General:
  - Deletes the movie of the given ID if it exists.
  - Returns id of deleted movie upon success and success value.


```
{
    "deleted_movie_id": 2,
    "success": true
}
```




## Authors
Fadwa Alorini created this application.
