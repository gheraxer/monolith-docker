Monolith-Docker

Based on https://github.com/Y2Z/monolith
But it works in docker.

To use this project, first install Docker on your computer.


Building the Docker image

To build the Docker image for this project, run the following command:

git clone https://github.com/gheraxer/monolith-docker.git
cd monolith
docker build -t [Image Name] .


Running the container

To run the container with the application, run the following command:

docker run -d --name [Container Name] -v $(pwd):/monolith [Image Name] monolite [target URL] -o [name_witch_you_wont].html

where command is the command to be run inside the container. For example:

docker run -d --name gheraxer -v $(pwd):/monolith gheraxer/monolite:1.0 monolith https://example.com -o output.html

This command runs the monolith command inside the container, which downloads the website at https://example.com and saves it as output.html in 
the /monolith directory of the container. The -v flag mounts the current directory on the host machine to the /monolith directory in the container,
so that the output file can be accessed on the host machine after the container has finished running.
