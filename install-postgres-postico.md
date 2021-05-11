# Postgres and Postico Install
*Last updated 5/2020*


## Postgres Overview

Postgres is an SQL database. This guide merely shows you how to install the software needed to run Postgres. Actual lectures on using Postgres will follow.

### Prerequisites
You have previously installed Homebrew, the package manager for Mac OS.
To check if you have recently updated Homebrew.

1. Open a terminal
2. Type: `brew update`
3. Press enter key


## Install Brew (if you don’t already have it)

First you need to get brew. You can test if you have brew with this command:

`which brew`

if it logs

`/usr/local/bin/brew`

then you are all set and can go to the next step!

If you don't have it follow the install instructions on http://brew.sh/ . You will need to run a run command in your terminal. Come find an instructor if you have permissions issues. 

## Installing Postgres

1. Open a terminal and run this command: `brew install postgres`

### Starting/Stopping Postgres (Option 1 of 2)

If you have installed Postgres with Homebrew, you can use the built-in Brew Services commands to start/stop the server as below:

- Stop the server: `brew services stop postgresql`
- Start the server: `brew services start postgresql`
- See what is running: `brew services list`

## Postico (Database Client GUI app) Overview

At this point we will have a Postgres server program running on our local computer. We’re now going to install a graphical Client so we can have a fancy way to interact with our new server software. If this doesn’t work, please read to the end of the instructions to try these things before asking questions! We have solutions for several common problems.

### Install Postico

1. Go to: https://eggerapps.at/postico/
2. Download
3. Unzip and move to your Applications folder
4. Open (double-click Postico icon)

First thing we need to do is establish a connection to our server. Postico allows you to save many different connections. For now, we just need one to connect to the database server on our local computer.

### Create New Favorite

1. Click New Favorite

![Favorite Connections](images/postico-favorites.png)

![Add Connection](images/postico-add-connection.png)


2. Fill in this form as follows:

- **Nickname** can be anything. For now use `Localhost` or `Local`
- **Host** Needs to be `localhost` as this runs on our local computer
- **Port** Leave at the default of `5432`
- **User** This needs to be the user account name that installed Postgres. The default should be good.
    - You can find your username in your terminal:
![Add Connection](images/terminal-username.png)
- **Password** If you followed the above installation of Postgres, this can be left blank
- **Database** By default, Postgres creates a database called whatever your username is. Here `lukeschlangen` is Luke Schlangen's username.

## ERRORS? Create a Database

**IMPORTANT: Only complete the following steps if you get an error when you try to connect stating this database does not exist.**

#### To manually create your database

1. In terminal, run `createdb your_username_here`

If yours was `lukeschlangen` you would type: `createdb lukeschlangen`

## Confirm Everything is Working

Now back in Postico you should be able to connect to the host: localhost with a database called your username.

1. Open Postico
2. Connect to the `Local` that you just created (the `connect` button). 
3. You should see something like this:

![Add Connection](images/postico-success.png)

# Postgres and Postico Install
*Last updated 5/2020*


## Postgres Overview

Postgres is an SQL database. This guide merely shows you how to install the software needed to run Postgres. Actual lectures on using Postgres will follow.

### Prerequisites
You have previously installed Homebrew, the package manager for Mac OS.
To check if you have recently updated Homebrew.

1. Open a terminal
2. Type: `brew update`
3. Press enter key


## Install Brew (if you don’t already have it)

First you need to get brew. You can test if you have brew with this command:

`which brew`

if it logs

`/usr/local/bin/brew`

then you are all set and can go to the next step!

If you don't have it follow the install instructions on http://brew.sh/ . You will need to run a run command in your terminal. Come find an instructor if you have permissions issues. 

## Installing Postgres

1. Open a terminal and run this command: `brew install postgres`

### Starting/Stopping Postgres (Option 1 of 2)

If you have installed Postgres with Homebrew, you can use the built-in Brew Services commands to start/stop the server as below:

- Stop the server: `brew services stop postgresql`
- Start the server: `brew services start postgresql`
- See what is running: `brew services list`

## Postico (Database Client GUI app) Overview

At this point we will have a Postgres server program running on our local computer. We’re now going to install a graphical Client so we can have a fancy way to interact with our new server software. If this doesn’t work, please read to the end of the instructions to try these things before asking questions! We have solutions for several common problems.

### Install Postico

1. Go to: https://eggerapps.at/postico/
2. Download
3. Unzip and move to your Applications folder
4. Open (double-click Postico icon)

First thing we need to do is establish a connection to our server. Postico allows you to save many different connections. For now, we just need one to connect to the database server on our local computer.

### Create New Favorite

1. Click New Favorite

![Favorite Connections](images/postico-favorites.png)

![Add Connection](images/postico-add-connection.png)


2. Fill in this form as follows:

- **Nickname** can be anything. For now use `Localhost` or `Local`
- **Host** Needs to be `localhost` as this runs on our local computer
- **Port** Leave at the default of `5432`
- **User** This needs to be the user account name that installed Postgres. The default should be good.
    - You can find your username in your terminal:
![Add Connection](images/terminal-username.png)
- **Password** If you followed the above installation of Postgres, this can be left blank
- **Database** By default, Postgres creates a database called whatever your username is. Here `lukeschlangen` is Luke Schlangen's username.

## ERRORS? Create a Database

**IMPORTANT: Only complete the following steps if you get an error when you try to connect stating this database does not exist.**

#### To manually create your database

1. In terminal, run `createdb your_username_here`

If yours was `lukeschlangen` you would type: `createdb lukeschlangen`

## Confirm Everything is Working

Now back in Postico you should be able to connect to the host: localhost with a database called your username.

1. Open Postico
2. Connect to the `Local` that you just created (the `connect` button). 
3. You should see something like this:

![Add Connection](images/postico-success.png)

## Ubuntu 20.04

If you're using Ubuntu 20.04, you may need an alternate installation of pgadmin (there is no postico). Check here: https://stackoverflow.com/questions/61566325/package-pgadmin4-has-no-installation-candidate-for-ubuntu-20-04/61762947#61762947

You must create the /etc/apt/sources.list.d/pgdg.list file and add the line:

```
deb http://apt.postgresql.org/pub/repos/apt/ focal-pgdg main
```

Then run:
```
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```

Finally run:
```
sudo apt-get update && sudo apt-get install pgadmin4
```

On Linux you may need to set the default postgres user password (or create a new user). 
To set the default postgres password (once postgres is running):
```
sudo -i -u postgres
$ psql
>>> \password
(then type a simple password like 'password', no quotes).
```

Now in pgadmin the username is `postgres` and the password is what you put in. **Recommended**: Use something simple like `password` in case you check in your postgres password to your code, and wont feel bad about it being accidentally exposed in github (we'll use configuration files for this later, but accidents do happen).

You should now be able to open pgadmin from your applications menu in Linux (it will open in a browser tab). Add a new server connection to `localhost` with the username and password you've set up (either postgres or create some other user with your username).

## Postgres.app

If homebrew isn't working you can install the Postgress.app stand-alone postgres tool. This works fine but your command line tools will be missing (`psql` wont work at the terminal), which means heroku push won't work either.

Add the following path to your PATH in `.bashrc` or `.zshrc` (separated by a colon):
`/Applications/Postgres.app/Contents/Versions/latest/bin`
