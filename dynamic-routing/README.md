# ![Intro to Flask - Dynamic Routing](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to set up routes with parameters in Flask.

## Dynamic Routing

We can define parameters for our routes with different routes being triggered based on where the data is passed.

We define route parameters using this syntax: `<variable>` - where `variable` is the name of the parameter that will be defined in the function where we want to access it.

Let's add a third route to our app to demonstrate, only this route will be flexible based on the provided route parameter:

```python
@app.route('/profile/<name>')
def profile(name):
    return 'This is the profile information for {}'.format(name.upper())

if __name__ == '__main__':
    app.run()
```

Now, when you make requests to `localhost:5000/profile/whatever`, you should see the last section of the url included in the response message.

You can do anything you need to with that `name` variable. You can even pass dictionaries as parameters!

> 🚀 Check out the Flask docs for a deeper dive on [routing](https://flask.palletsprojects.com/en/1.1.x/api/?highlight=route#flask.Flask.route).

## 🎓 You Do: Create a personnel route for an employee directory

In this exercise, we'll want to provide users access to a simple data structure through a Flask route.

Users will make requests to `/personnel/<name>` and our Flask app will provide the information stored in a personnel dictionary about that person.

If there is no person with the requested name, return a 404 response. As always, consult the [documentation](https://flask.palletsprojects.com/en/3.0.x/errorhandling/#error-handlers) for guidance on how to implement this.

```python
personnel = {
    "rachel": "Executive Vice President of Managerial Functions",
    "wallace": "Senior Vice President of Managerial Functions",
    "rosie": "Staff Vice President of Managerial Functions",
    "james": "Vice Vice President of Managerial Functions",
    "henri": "Junior Vice President of Managerial Functions"
}
```

So, a request to `localhost:5000/personnel/henri` should provide a response of `"Junior Vice President of Managerial Functions"`.

## Query Parameters

Another effective way to pass additional information in a URL to a server is though query parameters. Query parameters are added to the end of a URL after a `?` and are formatted as `key=value` pairs. In Express, these parameters are conveniently accessible through the `req.query` object.

For example, consider the following URL `localhost:5000/employee-search?name=Christy&age=32.`

This URL contains two query parameters:

- `name` with a value of "Christy"
- `age` with a value of "32".

These parameters follow the `?` symbol in the URL and are separated by `&`.

When a request is made to this URL, the server can retrieve these values from the `request` object.

We'll need to add an import to the top of our `app.py` in order to access this object:

```python
from flask import request
```

The request will then be able to access query parameters using a `request.args.get()` method, like so:

```python
@app.route('/employee-search')
def employee_search():
    name = request.args.get('name')
    age = request.args.get('age')
    return f"I searched for employees named {name} who are {age} years old"
```

The `name` and `age` keys in the `request` object correspond to the query parameters in the URL. The server can then use this data, commonly for filtering results from a database.