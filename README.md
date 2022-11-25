### To install NGINX server

`sudo apt install nginx`

### Location of conf file

`/etc/nginx/sites-available`

### To edit the default conf file

`sudo gedit /etc/nginx/sites-available/default`

### Location of htmls

`/var/www/html`

### To start NGINX server

`sudo systemctl start nginx`

### To stop NGINX server

`sudo systemctl stop nginx`

### To check validity of NGINX conf

`sudo nginx -t`

### To reload NGINX server

`sudo systemctl reload nginx`

### To restart NGINX server

`sudo systemctl restart nginx`

### To check NGIINX process status

`sudo systemctl status nginx`

### To install NodeJS

<a name="To_install_NodeJS"></a>

`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash`

> **_NOTE:_** If you dont have `curl` install `sudo apt install curl`

then,

`source ~/.bashrc`

then,

`nvm install v16.18.1`

then check the version (should be v16.18.1)

`node -v`

### To clone a project source code

Make sure you are in the home directory. To change into the home directory

`cd ~`

Then, clone

`git clone <https-url>` , where `<https-url>` can be copied from your bitbucket project repo page.

For example

`git clone https://thuleen@bitbucket.org/thuleen/seafarer.git`

Then, you will need to enter the password. (I usually copy paste from my notepad app because the password is quite long!)

> **_NOTE:_** Remember to setup your bitbucket password. To setup the app password go to bitbucket Personal Settings > App Passwords > (Create app password). Remember to copy and paste to somewhere safe - in a note app or whatever app.

### To transpile the project source code

> **_NOTE:_** You need to Nodejs [installed](#To-install-NodeJS) before transpile.

Change into the project directory, for example

`cd seafarer`

Then transpile the project

`npm run build`

You should check that there is a new directory named `build` is created. To check

`ls -al`

### To copy the `build` directory(and all files in the directory) into NGINX `/var/www/html` directory

`sudo cp -r build/ /var/www/html/`

To check is the directory has been successfully copied

`ls -al /var/www/html`

(There should be the `build` directory in the `html` directory)
