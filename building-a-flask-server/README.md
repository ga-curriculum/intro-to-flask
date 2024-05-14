# ![Intro to Flask - Building a Flask Server](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create a simple app entry point with Flask.

## Flask server boilerplate

Let's get started with the absolute minimal code required for a Flask app, which is surprisingly little!

Create an `app.py` file in your project directory:

```bash
touch app.py
```

Next, add the following to `app.py`: 

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

To run the app, execute the following command in your terminal:

```bash
python3 app.py
```

You should see something like the following in your terminal:

```plaintext
* Serving Flask app 'app'
* Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
* Running on http://127.0.0.1:5000
Press CTRL+C to quit
```

In your browser, navigate to `http://127.0.0.1:5000`. You should see the 'Hello Flask!' response.

## Defining routes

In Python, `decorators` are wrapper functions used to modify and extend the behavior of a normal function.

In Flask, we can use `route()` decorators like @app.route("/") to assign functions to specific URL paths. When a user accesses a specific route, Flask is able to determine which function needs to run. 

To add a second route to our Flask app, simply define another function beneath a new `@app.route()` decorator, like so:

```python
# app.py
@app.route('/information')
def info():
    return 'Flask is the micro-framework of choice for building Machine Learning API endpoints'
```

To access the new route, restart your server and navigate to `http://127.0.0.1:5000/information`.