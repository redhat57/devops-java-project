# devops-java-project
**Step 1: To generate jar file, Run below command:**

`＄ mvn install`

The jar file can be located in target/ directory.

**Step 2: Building a Docker image**

To build our Docker image using the Dockerfile, run:

`＄ docker build -t my-maven-docker-project.jar .`

The above command Builds our project, naming it my-maven-docker-project.jar
Tags the image via the -t flag
Tells Docker to look for the docker file in the same directory via the .

**Step 3: Running a Docker image**
Finally, we can run our project by starting a Docker container with the previously built image and binding port 8080 on our local machine.

`＄ docker run -p 8080:8080 my-maven-docker-project.jar`

The command above:
Runs the Docker image and -p publishes the container’s port 8080 to the host (your machine) port 8080.
We can now access localhost:8080 with a browser and see the “Hello, World!!! I just Dockerized a Maven Project” message from the webserver.

Dockerfile:
=================================================================
1. FROM keyword tells Docker the base image on which we want our image built. In our case, OpenJDK 8 official docker image.
2. ADD keyword adds the jar we’ve created getting it from the new /target directory.
3. ENTRYPOINT keyword specifies commands to run the jar file.
4. EXPOSE keyword makes port 8080 available outside the Docker container.
=================================================================
