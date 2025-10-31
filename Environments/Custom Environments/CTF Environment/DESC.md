# Docker Image: ctf-environment

## Description

This Dockerfile is designed for **Custom Environments** such as Capture The Flag competitions. It allows you to add restrictions on the commands which the players can execute on your CTF level container.

## Getting Started

### Prerequisites

- Ensure you have [Docker](https://docs.docker.com/get-docker/) installed on your machine.

## Building the Image

Before building the image, make sure to specify all your commands in ```blocked_commands.txt```.
<br>
The commands should be seperated using a newline; one command per line.

To build the Docker image, navigate to the directory where your `Dockerfile` is located and run the following command:

```
docker build -t ctf-environment .
```

## Running the Docker Image

To run the Docker image, use the following command:

```
docker run -itd ctf-environment bash
```

## Features

- Uses Ubuntu 24.04 as base image, provides you more control to customize it as compared to Alpine, which has the issue of its ultimate dependency on Busybox utility.
- Removes the command from the directories, where commands are installed according to UNIX conventions.

---

## Exit Status for Docker Build

`0` = Docker image was built successfully without any errors.

`1` = Build failed due to an error in the Dockerfile or build context.