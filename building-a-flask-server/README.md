# ![Intro to Flask - Building a Flask Server](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create a simple app entry point with Flask.

## Flask server boilerplate

Let's get started with the absolute minimal code required for a Flask app, which is surprisingly little!

Create an `app.py` file in your project directory and fill it with the following: 

```python
# app.py
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello Flask!'

if __name__ == '__main__':
    app.run()
```

If this seemed like a bit of magic, don't worry: we got it from the Flask docs, same as you would.

To run the app, execute `python app.py` in the command line and watch it go! You should be able to send a request (through browser, postman, whatever) to localhost:5000 and see the response.

## Defining routes

In Python, `decorators` are wrapper functions used to modify and extend the behavior of a normal function.

In Flask, we can use `route()` decorators like @app.route("/") to assign functions to specific URL paths. When a user accesses a specific route, Flask is able to determine which function needs to run. 

To add a second route to our Flask app, simply define another function beneath a new `@app.route()` decorator, like so:

```python
# app.py
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello Flask!'

@app.route('/information')
def info():
    return 'Flask is the micro-framework of choice for building Machine Learning API endpoints'

if __name__ == '__main__':
    app.run()
```