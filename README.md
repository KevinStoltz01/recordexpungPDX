# recordexpungPDX
A project to automate expunging qualifying criminal records.  This project is done in conjunction with the Multnomah County Public Defender's Office. [Learn more in the wiki](https://github.com/CodeForPortland/recordexpungPDX/wiki).

[![Waffle.io - Columns and their card count](https://badge.waffle.io/CodeForPortland/recordexpungPDX.svg?columns=all)](https://waffle.io/CodeForPortland/recordexpungPDX)

[![Build Status](https://travis-ci.com/CodeForPortland/recordexpungPDX.svg?branch=master)](https://travis-ci.com/CodeForPortland/recordexpungPDX)


## Table of Contents

- [Installation](#installation)
- [Running Components](#running-components)
- [Testing](#testing)
- [Project Layout](#project-layout)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. **[Fork](https://help.github.com/articles/fork-a-repo/#fork-an-example-repository)**, 
	and **[clone](https://help.github.com/articles/fork-a-repo/#step-2-create-a-local-clone-of-your-fork)** the repo.

2. Install Python:

    * **Mac** 
    
      To install the latest version of Python on Mac run:
		
          $ brew install python3

      <!-- -->
		note: This will pull the latest version of Python, so when Python 3.8 or 
		greater is released it will install that version.

    * **Linux**

        - Ubuntu 18.04

			To install Python 3.7 on Ubuntu 18.04 run the command:
			```
			$ sudo apt-get install python3.7 -y 
			```

        - Ubuntu 16.04
	
			To install Python 3.7 on Ubuntu 16.04 follow the instructions 
			[here](https://github.com/CodeForPortland/recordexpungPDX/wiki/Installing-python3.7-on-ubuntu-16.04).

    * **Windows**

      To install Python 3.7 on Windows, follow the instructions [in this guide.](https://wiki.python.org/moin/BeginnersGuide/Download).

3. Install Pipenv

	Install the [pipenv](https://pipenv.readthedocs.io/en/latest/install) 
	package manager which also automatically creates and manages virtual 
	environments.

5. Install NPM if you don't already have it installed. [This link provides 
	instructions on how to install Node.js and NPM](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)

4. Install backend dependencies:

	A [Makefile](https://www.gnu.org/software/make/) controls installing 
  dependencies, running the Flask app, and removing build artifacts.
	While in the directory of your local `recordexpungePDX` repo, install the 
  backend dependencies by running:
	
	```
	$ make install
	```
	
	Make will read `Pipfile` and install listed Python packages into a `Pipenv` 
  virtualenv.

3. Install frontend dependencies

	While in the directory of your local `recordexpungePDX` repo, enter into your
  command line and run:

  ```
	$ cd src/frontend

	$ npm install
  ```

## Running Components

### Backend

#### Running Backend Development Server

While in the directory of your local repo, run:
	
```
$ make run
```
	
Doing so runs the `Flask` app inside a `Pipenv` virtualenv (the `Flask` app will 
also install dependencies as part of this process). On success, a
development server for the backend should be started on `http://localhost:5000`.
To check this, navigate to `http://localhost:5000/hello`. If everything worked
correctly, your browser should display the text `Hello, world!`.

##### Cleaning

While in the directory of your local repo, run:
	
```
$ make clean
```
in order to remove build artifacts.

### Frontend

#### Running Frontend Development Server


While in your `recordexpungePDX`, directory, enter into your command line and
run:

  ```
	$ cd /src/frontend

	$ npm start
  ```

If successful, the above should start a development server that can be viewed at
`http://localhost:3000/`.

## Testing

Currently using [pytest](https://docs.pytest.org) for testing.   
Run all tests with the following command:

```bash
$ make test
```


## Project Layout

`.flaskenv`: Environment variables read by `flask` command-line interface via [python-dotenv](https://github.com/theskumar/python-dotenv)

`Makefile`: GNU Makefile controlling installing dependencies and running the application

`Pipfile`: `Pipenv` file listing project dependencies

`config`: Project configuration files

`doc`: Developer-generated documentation

`settings.py`: `python-dotenv` configuration file

`src`: Source dir

`src/backend/expungeservice/app.py`: Flask application
`

## <a name="contributing"></a>Contributing

 1. **[Fork](https://help.github.com/articles/fork-a-repo/#fork-an-example-repository)** the repo on GitHub
 2. **[Clone](https://help.github.com/articles/fork-a-repo/#step-2-create-a-local-clone-of-your-fork)** the project to your own machine. Replacing YOUR-USERNAME with your github username.
   ```bash
    $ git clone https://github.com/YOUR-USERNAME/recordexpungPDX.git
   ```
 3. cd into recordexpungPDX
   ```bash
    $ cd recordexpungPDX
   ```
 4. Configure upstream to sync with your fork
   ```bash
    $ git remote add upstream https://github.com/CodeForPortland/recordexpungPDX.git
   ```
 5. Create a branch to work on. Replacing BRANCH_NAME with a descriptive name of the work planned such as `update_contributing_doc`
   ```bash
     $ git checkout -b BRANCH_NAME
   ```
 6. **Commit** changes to your branch (never to master)
 7. **Push** your work back up to your fork
   ```bash
     $ git push
   ```
   - NOTE: The first time you do `git push` on your branch it will error with:
   ```bash
    fatal: The current branch BRANCH_NAME has no upstream branch.
    To push the current branch and set the remote as upstream, use

        git push --set-upstream origin BRANCH_NAME
   ```
   - Copy the output and run it. Then afterwords simply push more commits by running `git push`.
 8. Submit a **Pull request**

- NOTE: For future contributions be sure to sync master with upstream
```bash
  $ git checkout master
  $ git pull upstream master
  $ git checkout -b BRANCH_NAME
```


## License

TODO: Add license
