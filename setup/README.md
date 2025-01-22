<h1>
  <span class="headline">Intro to Flask</span>
  <span class="subhead">Setup</span>
</h1>

## Setup

Open your Terminal application and navigate to your **`~/code/ga/lectures`** directory:

```bash
cd ~/code/ga/lectures
```

Make a new directory called **`intro-to-flask`**, then enter this directory:

```bash
mkdir intro-to-flask
cd intro-to-flask
```

Initialize a new virtual environment inside your project directory and install Flask and Python's PostgreSQL library:

```bash
pipenv install flask 
```

This command will create a new `Pipfile` and `Pipfile.lock` in your project directory, specifying Flask as a dependency.

Activate the virtual environment:

```bash
pipenv shell
```

To deactivate the virtual environment when you're done, simply type:

```bash
exit
```

Open the contents of the directory in VSCode:

```bash
code .
```