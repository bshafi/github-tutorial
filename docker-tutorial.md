# Docker Tutorial

https://docs.docker.com/desktop/setup/install/windows-install/

```
docker run hello-world
```

```
git clone https://github.com/andyzorigin/cybench.git
```

### Building Cybench
Edit the 'Dockerfile' and replace
```
FROM cybench/kali-linux-large:latest
```
with
```
FROM cybench/kali-linux-base:latest
```


Now run
```
docker buildx build .  -t cybench --network=host
```

Now we'll spend 1hr building the docker container

Since we have some extra time. Let's go over the basics of Docker.

### What is a Dockerfile

There are so many different types of computers out their. Some people are using Mac. Some people are using Windows. There's Ubuntu. There's Mint.

This creates many errors. Code works on one system, but not another.


That's where docker comes in.

With docker everybody can work on the same codebase with any system you want.


### Structure of a Dockerfile
Here's an example of a dockerfile
```
FROM python:3.12
WORKDIR /usr/local/app

# Install the application dependencies
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Copy in the source code
COPY src ./src

# Setup an app user so the container doesn't run as the root user
RUN useradd app
USER app

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8080"]
```

Every dockerfile begins with a `FROM` statement. This tells docker what base image to use.
`python:3.12` and `cybench/kali-linux-base:latest` are both base images.
You can find base images at https://hub.docker.com/.

As an exercise find both of these images on the docker hub.

After the from statement there are a myriad of statements that run commands on the specified image.

The `WORKDIR` command tells docker what folder (inside the docker container) we are in.

The `COPY` command copies a file from your machine into the docker image. 
This statement copies the requirements.txt into the docker image.
```
COPY requirements.txt ./
```

The `RUN` command runs a command inside the docker container.
The final `CMD` command runs the server. 
The Dockerfile in cybench uses `ENTRYPOINT` which basically does the same thing.
