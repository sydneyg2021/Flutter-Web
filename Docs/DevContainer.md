# DevContainer Environment
## Introduction
A DevContainer is a pre-configured development environment packaged within a Docker container. It bundles all the necessary tools, libraries, and dependencies a project needs to run smoothly.  A DevContainer is especially beneficial for Flutter development due to its consistency, reduced setup time, isolation, and portability. DevContainers offers a streamlined and consistent development experience for Flutter projects, saving time on setup, minimizing compatibility issues, and ensuring everyone works with the same tools and libraries. 

## Configuration steps 
To configure my DevContainer, I:

1. Created a Dockerfile Image with a pre-configured base image specifically designed for development containers by Microsoft. It provides a base Ubuntu environment with some basic tools pre-installed.
2. I also installed additional tools to the image:
      - wget: Used for downloading files from the internet.
      - xz-utils: Provides tools for working with xz-compressed files.
      - git: Used for version control with Git repositories.
      - curl: Used for making HTTP requests.
      - file: Used to determine the type of a file.
      - unzip: Used for extracting ZIP archives.

3. To make sure the Flutter was available for my DevContainer, I cloned the Flutter SDK and also changed the DevContainer path to include the SDK so Flutter applications could be run directly from the container.

## Integration with VS Code
In my DevContainer, I also installed specific Dart and Flutter extensions for Visual Studio Code (VS Code) to provide the necessary tools for working on my Flutter project.

## Usage
**Using a DevContainer for Flutter Development Workflow**
### Prerequisites
Make sure [Docker](https://www.docker.com/get-started/) is installed on your system before continuing.

### Getting Started

1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/sydneyg2021/Flutter-Web.git
   cd Flutter-Web
2. Build the Docker image:
    ```bash
    docker build -t Flutter-Web:latest
3. Run the container:
    ```bash
    docker run -it --rm -v $(pwd):/app Flutter-Web:latest

This command mounts your project directory into the container and starts an interactive session. You can also edit the code to your specifications if needed on your local copy.

### Running a web application
1. Create a directory for your application in the dart terminal (i.e, app):
   ```bash
   Flutter create app
2. Change into that directory:
    ```bash
    cd app
3. Run the app (in this case the default Flutter application):
    ```bash
    flutter run -d web-server

## Challenges and Solutions
I did run into some issues getting my Flutter app to work on Chrome, and I ran into issues with Flutter recognizing my app directory and the path to get to it. I found out that when setting up Flutter in my Dockerfile Image, I was not using the correct permissions (i.e., chmod -R 777). Once I changed those permissions, I could access my web app. 

## Conclusion
Once again, using a DevContainer for this project has allowed me to keep a pre-configured environment, allowing me to develop easily without worry that if I moved to a different device, I would still be able to develop my Flutter application with ease. 
