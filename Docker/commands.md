
# 

Build & Run
`docker-compose up --build -d`
Looks for the file 'docker-compose.yml', downloads & build the images and runs respective containers.
'-d' for detached mode, so you're free to keep using your terminal window.

List containers
`docker ps`

Stop (Pause)
`docker-compose down`
Stop running the container

Clean Up
`docker-compose rm`
Delete the container

ssh into a container
`docker exec -it <container name> /bin/bash`
Use 'docker ps' first to get the container name.
