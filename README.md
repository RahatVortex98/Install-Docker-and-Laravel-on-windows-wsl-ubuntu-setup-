# Install-Docker-and-Laravel-on-windows-wsl-ubuntu-setup-


On the Powershell (Run as administrator):

      > wsl --install
Check status:

      >wsl --status

If you see any errors:

      >wsl.exe --install --no-distribution

Your machine looks for a restart, then after the restart, the Ubuntu app pops up:

     ask for->

     username:
     password:

In the terminal, paste this for update and upgrade:

    >sudo apt update && sudo apt upgrade -y

This installs PHP 8.3 + required extensions + dev tools:

    > sudo apt install php8.3-cli php8.3-common php8.3-mbstring php8.3-xml php8.3-bcmath
      php8.3-curl php8.3-mysql php8.3-zip php8.3-readline php8.3-gd php8.3-pgsql unzip curl git composer -y

Next Step is to install Docker:

Link: https://www.docker.com/ (must create an account, and Docker will send you an email verification)

i) And then download the Docker app for desktop!
ii) Again, restart your machine!
iii) Open up your Docker app! (accept those terms)
iv) Log in with your credentials.

And then you see something like this->

<p align='center'><img width="48%"  src="https://github.com/user-attachments/assets/7595ce6f-278a-40b6-afcc-c34f94f76d74" /></p>

v) Go to settings  and then Resources/WSL integration and enable Ubuntu:


<p align='center'>  <img width="48%" src="https://github.com/user-attachments/assets/5a4f9192-5b2d-41c2-8110-ac304b4dadfd" />
  </p>

vi) Apply and restart.

vii)Open up your WSL cmd and write this command:

    >docker --version

and show you this,

    -Docker version 29.1.2, build 890dcca  
    
WSL command to log in to Docker:
      
      docker login -u username
if get error->

     1. Open 👉 https://app.docker.com/settings

     2. Personal access tokens 
      
     3. Click New Access Token
      
     4. Name it: wsl-docker
      
     5. Scope: Read, Write, Delete
      
     6. Create
      
      COPY THE TOKEN (you won’t see it again)

   <p align='center'>  <img width="48%"  src="https://github.com/user-attachments/assets/a4230bb9-fc37-404f-a02c-6cd1fe54a493" />
 </p>


 To check that's works well :
 
       $ docker pull hello-world
<p align='center'>
<img width="48%"  src="https://github.com/user-attachments/assets/378a5c28-769a-485d-8e75-0166e9018471" /> </p>

<h3 align='center'>Laravel Dependencies Inside WSL</h3>

WSL commands:

       :$ cd /mnt/d
       :/mnt/d $ mkdir LaravelProjects
       :/mnt/d $ cd LaravelProjects
       :/mnt/d/LaravelProjects $ composer create-project laravel/laravel myapp
       :/mnt/d/LaravelProjects $ cd myapp
       
<h3 align='center'>Setting up Laravel Sail</h3>

What Laravel Sail actually is
      
      -Laravel Sail is:
      -A Docker Compose wrapper
      -Ships with Laravel
      -Provides ready-to-use containers for:
      #PHP
      #MySQL / PostgreSQL
      #Redis
      #Mailpit
      #Meilisearch
      #Selenium (optional)
      
      You don’t write Dockerfiles manually.
Sail setup command:

      $ composer require laravel/sail --dev
      
      $ php artisan sail:install
      
Then select your DB.

<h3 align='center'>Open The Project In VS code</h3>

command for opening up VS Code ->

      code .

<h3 align='center'>Setting up our DB & .env file</h3>

Sail Commands:

      ./vendor/bin/sail up -d     # start containers
      ./vendor/bin/sail down     # stop containers 
      ./vendor/bin/sail artisan migrate
      ./vendor/bin/sail npm run dev
      ./vendor/bin/sail bash     # enter container shell
      
Note: You still need to run the sail 'down' command, even if you hadn't started sail beforehand.
      Otherwise, your .env changes won't get applied, and you'll get an error when migrating the DB.


### For viewing your database, you can install DBreaver and connect with .env information.


#Viewing Your website in a browser:

Note: Make sure that your sail using-> ./vendor/bin/sail up -d











