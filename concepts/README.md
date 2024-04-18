# ![Intro to Flask - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to articulate Flask's characteristics in the web framework ecosystem.

# What is Flask?

[**Flask**](https://flask.palletsprojects.com/en/2.1.x/) is a do it yourself micro web framework written in Python used to build applications and API's. It is a non-intrusive web framework similar to Express that allows you to make design decisions based on your applications needs. It is very bare bones upon initial install, but can easily be elevated with Flask extensions.

[Welcome to Flask - Flask Documentation (2.1.x)](https://flask.palletsprojects.com/en/2.1.x/)

Flask was created by [**Armin Ronacher**](https://en.wikipedia.org/wiki/Armin_Ronacher) with the intent of building a framework that would allow developers to get started very quickly.

[Armin Ronacher - Wikipedia](https://en.wikipedia.org/wiki/Armin_Ronacher)

Flask is more explicit than Django and is also easier to learn because it requires less base code to implement a simple web-app.

<aside>
⚠️ Although **Flask has a built-in web server**, it's not suitable for production and needs to be put behind a real web server able to communicate with Flask through a WSGI protocol. A common choice for that is Gunicorn (a Python WSGI HTTP server).

</aside>

<aside>
🗣 WSGI is pronounced *whiskey.*

</aside>

# **Quick Notes**

- Flask is a Python micro web framework.
- It can create and write the entire back-end in Python!
- It can do small tasks (e.g., create a microblog or stand up a simple API).
- It can do complex tasks (e.g., Pinterest's API or create a Twitter clone).

# **App’s that use Flask**

- Pinterest
- Netflix
- Reddit
- LinkedIn

# Web Frameworks

A web framework is a component designed to support the development of web applications. Essentially, it is a tool representing a collection of libraries and modules that provide a web app developer with the necessary resources to easily develop web applications.

Web Application Frameworks have **three capabilities** fundamental to writing a back-end web application:

1. The ability to define routes
2. The ability to process HTTP requests using middleware
3. The ability to use a view engine to render dynamic templates