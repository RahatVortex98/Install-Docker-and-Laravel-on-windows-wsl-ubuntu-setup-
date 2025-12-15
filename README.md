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









    
