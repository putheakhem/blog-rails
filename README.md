# README (Ubuntu 18.04 LTS)

This README would normally document whatever steps are necessary to get the
application up and running.

## Setup Development Enviroment

### Installing Ruby

* Install some dependencies 
```bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev nodejs yarn

```

* Install Ruby using rvm 
```bash
sudo apt-get install libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
curl -sSL https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm install 2.6.1
rvm use 2.6.1 --default
ruby -v

```

* Install Bundler 

```bash
    gem install bundler
```

## Install Rails

* Install NodeJs
```bash
    curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
    sudo apt-get install -y nodejs

```

* Install Rails 
```bash
    gem install rails -v 5.2.2
```

* Install Postgres
```bash 
    sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ xenial-pgdg main' > /etc/apt/sources.list.d/pgdg.list"
    wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | sudo apt-key add -
    sudo apt-get update
    sudo apt-get install postgresql-common
    sudo apt-get install postgresql-9.5 libpq-dev
```

* Create user in postgres
```bash
    sudo -u postgres createuser <user>  -s
```
* If you want to set a password to user 

```bash
sudo -u postgres psql
postgres=# \password <user>
```
:notebook: change <user> to your postgres user name 



:soon: To be written 

* Deployment Instruction 
## Deployment on heroku 

* Installing heroku 
```bash 
    sudo snap install --classic heroku
```

* Login to heroku 



# Solutions: 

* if you got an error message while run `rake db:create` as the following
`You must use Bundler 2 or greater with this lockfile.`
    * Plese run the following command 
        ```bash 
            gem update --system
            gem install bundler
        ```
* You still can't create database check [Here](https://stackoverflow.com/questions/18664074/getting-error-peer-authentication-failed-for-user-postgres-when-trying-to-ge)