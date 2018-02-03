# Overview of project
An application that allows the user to enter a text and finds the intent behind the text and display it to the user using the wit.ai api.
The Study planner app supports both week and day rotation schedules as well as timetables that repeat every week and enables the user to know about his/her upcoming tests,assignments and homeworks by simply asking the bot for it.
Goals and tasks
### Front end:
(SKELETAL INTEGRATION OF API)
 1.  Take text  input from the user or allow the user to pick from a set of texts.
 2.  Display the intent of the text entered by the user if the intent has been found by the wit api.
 3.  Display some kind of an  error message if intent of text is not found.
(APP)
 1.  Make a login page
 2.  Allow the user to add , change and delete assignments, tests and homeworks.
 3.  Make a chat component that allows the user to ask the bot questions like, 
     - Which classes do I have tomorrow?
     - Do I have any tests tomorrow or within the next two days?
     - Do I have any pending assignments?
     - What are the assignments and homeworks I need to submit tomorrow?
 4. Display the answers of the above questions to the user
 5. Allow the user to upload notes and Timetable.
### Back end:
-Design the complete application with specifications and documenting everything with complete details.
-Create or find a spreadsheet which contains almost all forms of questions and phrases for targeted intents.
-Train the wit app for handling all these(through code snippet).
-Create a database where the information about authentication, users, tests, assignments,etc is stored.
-Add security features to the client to server connection for transferring the data without interference.
-Develop the code for all the basic operations stated in the app. This includes -
-Fetching the data from the client.
-Storing and sending the data to the wit app and extracting information from the received response.
-Updating/adding/deleting/searching the data in the database depending upon the type of response.
-Properly formatting the answer or the acknowledgement(in case of updation or deletion) and sending it back to the client.
-Adding the feature-centric code.
-Testing the application code rigorously without and with the extra features.

## Specifications

### Frameworks used:
   ### Front end
1.ReactJS
2. Material-UI
   ### Back-end
1. Python-Flask

## Documents referred
1. Material-UI  -  https://material.io/guidelines/material-design/introduction.html#
2. Wit.ai  -  https://wit.ai/docs
3. ReactJS - https://reactjs.org/tutorial/tutorial.html
5. Wit.ai and Python - https://github.com/wit-ai/pywit
6. Using Wit.ai - https://github.com/wit-ai/wit-api-only-tutorial/blob/master/README.md


# React

React is a JavaScript library for building user interfaces.

### Declarative:
React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes. Declarative views make your code more predictable, simpler to understand, and easier to debug.
### Component-Based:
Build encapsulated components that manage their own state, then compose them to make complex UIs. Since component logic is written in JavaScript instead of templates, you can easily pass rich data through your app and keep state out of the DOM.

[Learn how to use React in your own project.](https://reactjs.org/docs/hello-world.html)

# Examples of a ReactJS project


```class HelloMessage extends React.Component {
  render() {
    return <div>Hello {this.props.name}</div>;
  }
}

ReactDOM.render(
  <HelloMessage name="John" />,
  document.getElementById('container')
);
```

This example will render "Hello John" into a container on the page.

More examples [on the website](https://reactjs.org/)

You'll notice that we used an HTML-like syntax; we call it JSX. JSX is not required to use React, but it makes code more readable, and writing it feels like writing HTML. We recommend using Babel with a React preset to convert JSX into native JavaScript for browsers to digest.

# Installation
React is available as the react package on [npm](https://www.npmjs.com/). It is also available on a [CDN](https://reactjs.org/docs/cdn-links.html).

React is flexible and can be used in a variety of projects. You can create new apps with it, but you can also gradually introduce it into an existing codebase without doing a rewrite.

The recommended way to install React depends on your project. Here you can find short guides for the most common scenarios:

- [Trying Out React](https://reactjs.org/docs/try-react.html)
- [Creating a New Application](https://reactjs.org/docs/add-react-to-a-new-app.html)
- [Adding React to an Existing Application](https://reactjs.org/docs/add-react-to-an-existing-app.html)

### To make changes to the project

1. Clone the project
2. you can edit the project files which are found in the src folder.
3. Open command prompt in the app folder and type `npm start` to see the output in your web browser.



# hello-python-flask

Boilerplate Hasura project with [Flask](http://flask.pocoo.org/) microservice.


## Getting started

### Prerequisites

- [Hasura CLI](https://docs.hasura.io/0.15/manual/install-hasura-cli.html)
- [Git](https://git-scm.com)
- [Python 3](https://www.python.org/downloads/) and [pip](https://pip.pypa.io/en/stable/installing/) (required only for local development)

### Quickstart

```bash
# Quickstart from this boilerplate 
$ hasura quickstart hello-python-flask
```

The `quickstart` command does the following:

1. Creates a new directory `hello-python-flask` in the current working directory
2. Creates a free Hasura cluster and sets it as the default for this project
3. Sets up `hello-python-flask` as a git repository and adds `hasura` remote to push code
4. Adds your SSH public key to the cluster so that you can push to it

### Deploy

```bash
# Navigate to the project directory
$ cd hello-python-flask

# git add, commit and push to deploy
$ git add . && git commit -m "First commit"
$ git push hasura master
```

Once the git push goes through, Flask microservice (called `app`) will be available at a URL.

```bash
# Open the flask app url in browser
$ hasura microservice open app
```

If the browser shows a "Hasura Hello World" page, everything is working as expected.
If it doesn't, go through the previous steps and see if you missed anything.


## Edit and deploy code

### Directory structure

The flask microservice is located in `microservices/app` directory in your Hasura project with the following structure:

```bash
.
├── Dockerfile                   # instructions to build the image
├── k8s.yaml                     # defines how the app is deployed
├── conf
│   └── gunicorn_config.py       # configuration for the web server
└── src
    ├── config.py                # some utilities to configure URLs etc
    ├── hasura.py                # hasura API examples
    ├── __init__.py              # main Flask app is defined here
    ├── requirements.txt         # python dependency requirements
    └── server.py                # main Flask server code
```

### Edit

`server.py` is where the main app is present. You can edit this file and deploy the changes.
For example, un-comment lines `2`, `11-13` to add new URL `/json`:

```python
from flask import jsonify

@app.route("/json")
def json_message():
    return jsonify(message="Hello World")
```

These lines will add `/json` which returns `{"message": "Hello World"}`.

### Deploy

Save the file, git add, commit and push to deploy the changes:

```bash
# git add, commit and push to deploy
$ git add src/server.py
$ git commit -m "add new url /json"
$ git push hasura master
```

### Verify

To checkout the new URL, open the microservice URL in a browser and navigate to `/json`:

```bash
# open the url in browser
$ hasura microservice open app

# add /json at the end of the url
```

### Debug

If the push fails with an error `Updating deployment failed`, or the URL is showing `502 Bad Gateway`/`504 Gateway Timeout`,
follow the instruction on the page and checkout the logs to see what is going wrong with the microservice:

```bash
# see status of microservice app
$ hasura microservice list

# get logs for app
$ hasura microservice logs app
```

You can deploy further changes by going through `Edit -> Deploy -> Verify -> Debug` cycle again and again.

*TIP*: If you already have a working flask app and want to deploy it quickly, jump to [Deploy your existing Flask app](#deploy-your-existing-flask-app)

## Use a database

Hasura comes with a pre-configured ready-to-use PostgreSQL database, which can be contacted over HTTP JSON APIs. You can use this database from client side or server side just by making HTTP API calls with JSON data. There are no DB connection strings or ORMs to worry about.

### API Console

The best place to get started with APIs is [Hasura API Console](https://docs.hasura.io/0.15/manual/api-console/index.html).

```bash
$ hasura api-console
```

This command will run a small web server and opens up API Console in a new browser tab.
There are already some tables created along with this boilerplate, like `article` and `author`.
These tables were created using [migrations](https://docs.hasura.io/0.15/manual/data/data-migration.html).
Every change you make on the console is saved as a migration inside `migrations/` directory.

### Using Data APIs

- Create required tables/columns using API Console (Data -> Schema)
- Use Query Builder under API Explorer and create the query
- Click on Generate API Code button and select Python Requests
- Copy and paste the python code into your flask app source code

### Example

This boilerplate defines a `/get_articles` endpoint which fetches a list of articles from the database and return JSON data. The query builder will show similar code when same query is built.

```python
# hasura.py

@hasura_examples.route("/get_articles")
def get_articles():
    query = {
        "type": "select",
        "args": {
            "table": "article",
            "columns": [
                "*"
            ]
        }
    }

    response = requests.post(
        dataUrl, data=json.dumps(query)
    )
    data = response.json()

    return jsonify(data=data)
```

This snippet of code returns a JSON similar to the following format:

```json
{
  "data": [
    {
      "author_id": 12,
      "content": "Vestibulum accumsan neque et nunc. Quisque...",
      "id": 1,
      "rating": 4,
      "title": "sem ut dolor dapibus gravida."
    },
    {
      "author_id": 10,
      "content": "lacus pede sagittis augue, eu tempor erat neque...",
      "id": 2,
      "rating": 4,
      "title": "nonummy. Fusce fermentum fermentum arcu."
    }, 
    ...
  ]
}
```

### Internal & External URLs

If you look closer in `hasura.py`, `dataUrl` is defined in two different ways, internal and external. When your app is running inside the cluster, it can directly contact the Data APIs without any authentication. On the other hand, external URLs always go through the API Gateway, and hence special permissions will have to be applied over table for a non-authenticated user to access data.

- `http://data.hasura` - internal url
- `http://data.[cluster-name].hasura-app.io` - external url

*PS*: [Hasura Data APIs](https://docs.hasura.io/0.15/manual/data/index.html) are really powerful with nifty features like relationships, role based row and column level permissions etc. Using the APIs to their full potential will prevent you from re-inventing the wheel while building your app and can save a lot of time. 

*TIP*: Use `hasura ms list` to get all internal and external URLs available in your current cluster.

## Add authentication

When your app needs authentication, [Hasura Auth APIs](https://docs.hasura.io/0.15/manual/users/index.html) can be used to manage users, login, signup, logout etc. You can think of it like an identity service which takes away all the user management headaches from your app so that you can focus on your app's core functionality.

Just like the Data APIs, you can checkout and experiment with the Auth APIs using [Hasura API Console](https://docs.hasura.io/0.15/manual/api-console/index.html).

Combined with database permission and API gateway session resolution, you can control which user or what roles have access to each row and column in any table.

### API gateway & session middleware

For every request coming through external URL into a cluster, the API gateway tries to resolve a user based on a `Cookie` or an `Authorization` header. If none of them are present or are invalid, the following header is set and then the request is passed on to the upstream service:

- `X-Hasura-Role: anonymous`


But, if the cookie or the authorization header does resolve to a user, gateway gets the user's ID and role from auth microservice and add them as headers before passing to upstream:

- `X-Hasura-User-Id: 3`
- `X-Hasura-Role: user`

Hence, other microservices need not manage sessions and can just rely on `X-Hasura-Role` and `X-Hasura-User-Id` headers.

## Customize

Hasura runs [microservices](https://docs.hasura.io/0.15/manual/custom-microservices/index.html) as Docker containers on a Kubernetes cluster.
You can read about [Hasura architecture](https://docs.hasura.io/0.15/manual/cluster/architecture.html) in case you want to know more.

### Add a python dependency

In order use new python package in your app, you can just add it to `src/requirements.txt` and the git-push or docker build process will
automatically install the package for you. If the `pip install` steps thorw some errors in demand of a system dependency,
you can install those by adding it to the `Dockerfile` at the correct place.

```
# src/requirements.txt:

flask
requests
gunicorn

# add your new packages one per each line
```

### Add a system dependency

The base image used in this boilerplate is [python:3](https://hub.docker.com/_/python/) debian. Hence, all debian packages are available for installation.
You can add a package by mentioning it in the `Dockerfile` among the existing `apt-get install` packages.

```dockerfile
# Dockerfile

FROM python:3

# install required debian packages
# add any package that is required after `python-dev`, end the line with \
RUN apt-get update && apt-get install -y \
    build-essential \
    python-dev \
&& rm -rf /var/lib/apt/lists/*

# install requirements
COPY src/requirements.txt /tmp/requirements.txt
RUN pip3 install -r /tmp/requirements.txt

# set /app as working directory
WORKDIR /app

# copy current directory to /app
COPY . /app

# run gunicorn server
# port is configured through the gunicorn config file
CMD ["gunicorn", "--config", "./conf/gunicorn_config.py", "src:app"]

```

### Deploy your existing Flask app

If you already have a Flask app and want to deploy it onto Hasura, read ahead:

- Replace the contents of `src/` directory with your own app's python files.
- Leave `k8s.yaml`, `Dockerfile` and `conf/` as it is.
- Make sure there is already a `requirements.txt` file present inside the new `src/` indicating all your python dependencies (see [above](#add-a-python-dependency)).
- If there are any system dependencies, add and configure them in `Dockerfile` (see [above](#add-a-system-dependency)).
- If the Flask app is not called `app`, change the last line in `Dockerfile` reflect the same.
  For example, if the app is called `backend`, the `CMD` line in `Dockerfile` will become:
  ```dockerfile
  CMD ["gunicorn", "--config", "./conf/gunicorn_config.py", "src:backend"]
  ```

## Local development

With Hasura's easy and fast git-push-to-deploy feature, you hardly need to run your code locally.
However, you can follow the steps below in case you have to run the code in your local machine.

### Without Docker

It is recommended to use a [Virtual Environment](http://docs.python-guide.org/en/latest/dev/virtualenvs/) for Python when you are running locally.
Don't forget to add these directories to `.gitignore` to avoid committing packages to source code repo.

```bash
# setup pipenv or virtualenv and activate it (see link above)

# go to app directory
$ cd microservices/app

# install dependencies
$ pip install -r src/requirements.txt

# Optional: set an environment variable to run Hasura examples 
# otherwise, remove Hasura examples, 
#   delete lines 5-8 from `src/__init__.py`
#   remove file `src/hasura.py`
$ export CLUSTER_NAME=[your-hasura-cluster-name]

# run the development server (change bind address if it's already used)
$ gunicorn --reload --bind "0.0.0.0:8080" src:app
```

Go to [http://localhost:8080](http://localhost:8080) using your browser to see the development version on the app.
You can keep the gunicorn server running and when you edit source code and save the files, the server will be reload the new code automatically.
Once you have made required changes, you can [deploy them to Hasura cluster](#deploy).

### With Docker

Install [Docker CE](https://docs.docker.com/engine/installation/) and cd to app directory:

```bash
# go to app directory
$ cd microservices/app

# build the docker image
$ docker build -t hello-python-flask-app .

# run the image with port bindings and CLUSTER_NAME environment variable
# as mentioned above, remove hasura.py if you don't want to add CLUSTER_NAME
$ docker run --rm -it -p 8080:8080 -e CLUSTER_NAME=[your-hasura-cluster-name] hello-python-flask-app

# app will be available at `http://localhost:8080`
# press Ctrl+C to stop the running container
```

For any change you make to the source code, you will have to stop the container, build the image again and run a new container.
If you mount the current directory as a volume, you can live-reload your code changes:

```bash
# go to app directory
$ cd microservices/app

# build the docker image
$ docker build -t hello-python-flask-app .

# run the container
$ docker run --rm -it -p 8080:8080 \
             -e CLUSTER_NAME=[your-hasura-cluster-name] \
             -v $(pwd):/app \
             hello-python-flask-app \ 
             gunicorn --reload --bind "0.0.0.0:8080" src:app
             
# app will be available at `http://localhost:8080`
# press Ctrl+C to stop the running container
```

Now, any change you make to your source code will be immediately updated on the running app.


