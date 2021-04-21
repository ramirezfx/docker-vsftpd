# Docker-Container With VSFTPD (FTP-Server)

If docker-compose is not installed, installed it (on Debian-based distros)

`sudo apt-get install docker docker-compose`

Get This Repo

`git clone https://github.com/ramirezfx/docker-vsftpd.git`

Navigate To The Working Directory:

`cd docker-vsftpd`

Edit the file .env with your favourite editor and change the variables for FTP_USERNAME, FTP_PASSWORD and MAPPED_FOLDER

Start The Container:

`docker-compose up -d`

Now you can connect with a FTP-Client to the server with the credentials provided in the .env - file

The files are now mapped to the ftp-folder inside the docker-vsftpd - folder

# Add New FTP-Users:

To add new FTP-Users, get the container-name

`docker ps`

On the very right column you will get the container-name (Usually docker-vsftpd_ftp_1)

Then Add The New FTP-User With This Command:

`docker exec -it CONTAINERNAME adduser -h /ftp/USER -s /sbin/nologin USER`

where CONTAINERNAME should be replaced with your container-name and USER should be replaced the name of the ftp-user you want to create.

You will be asked for a password (You must re-type it for security reasons)
