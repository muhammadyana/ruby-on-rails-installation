### Ruby is Fun 🎉🎊


----------
## Install RVM to manage our Rubies:

    gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

    curl -sSL https://get.rvm.io | bash -s stable
    
    or if you want include with stable ruby try this one, and u can skip for Install ruby version section
    \curl -sSL https://get.rvm.io | bash -s stable --ruby


----------
### Install ZSH (This is recommended) 

    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

### Install ZSH Plugin syntax highlighting (optional)

    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
    echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc

### Install ZSH Plugin syntax highlighting (optional)

    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    nano ~/.zshrc
    # Add plugin to 
    plugins=(git zsh-autosuggestions rails rvm ruby)
    

### inisialisasi rvm 

    source ~/.rvm/scripts/rvm
    rvm requirements

### Check if RVM was installed

    rvm -v
    rvm 1.29.3 (latest) by Michal Papis, Piotr Kuczynski, Wayne E. Seguin [https://rvm.io]
    

### Install ruby version

    rvm install 2.4.1 # if u want install specific ruby version use `rvm install x.x.x`
    rvm use 2.4.1 --default
    

### cek if ruby was installed

    ruby -v
    ruby 2.4.1p111 (2017-03-22 revision 58053) [x86_64-darwin17]
    
### Install Bundler

    gem install bundler -V --no-ri --no-rdoc

### Setting up SSH Keys

    ssh -T git@github.com
    Permission denied (publickey)
    
### setting SSH 

    ssh-keygen -t rsa
    cat ~/.ssh/id_rsa.pub
Copy and add to github account

### Install Node JS
rails require node js

    sudo apt-get install nodejs
    sudo apt-get install npm

### Install Yarn
    curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
    sudo apt update && sudo apt install yarn

### Install Mimemagick (Optional)
    sudo apt-get update -y
    sudo apt-get install -y ruby-mini-magick

### Install Nginx
    sudo apt update && sudo apt install nginx
    sudo ufw app list
    sudo ufw allow 'Nginx HTTP'
    sudo ufw status


### Install Redis
    sudo apt update && sudo apt install redis-server

Edit ```redis.conf```

    sudo nano /etc/redis/redis.conf
change to ```supervised systemd```
Restart redis

    sudo systemctl restart redis.service



### Install Postgresql

    sudo apt-get update
    sudo apt-get install postgresql postgresql-contrib
    sudo apt-get install postgresql postgresql-contrib libpq-dev
### Configure PostgreSQL to start up upon server boot.

    update-rc.d postgresql enable

### Run Postgres Server

    service postgresql start

### Enter postgres console
change user to postgres

    sudo -i -u postgres
    psql

### Create new user

    createuser --interactive
    or if you not logged ass postgres user
    sudo -u postgres createuser --interactive

### Create DB 
create db must be same with your user pc, if your user **yana@ubuntu** make user yana

    createdb user_name
    sudo -i -u user_name
    psql

If you want your user to connect to a different database, you can do so by specifying the database like this:

    psql -d postgres
Check if connected

    \conninfo
    You are connected to database "postgres" as user "postgres" via socket in "/var/run/postgresql" at port "5432".
