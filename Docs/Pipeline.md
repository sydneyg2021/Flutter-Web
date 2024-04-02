# Continuous Integration and Continous Development Pipeline
## Introduction
Continuous Integration and Continuous Deployment (CI/CD) is a set of practices, frameworks, and tools to automate and streamline the software delivery process. This process is represented in the CI/CD pipeline, where code changes are recorded as they are automatically built, tested, and deployed to various environments. This document outlines the CI/CD pipeline for this project.

## CI/CD Pipeline Environment
This project's CI/CD pipeline environment is the GitHub suite, where GitHub Actions are used for automation, and Github pages are used for publishing static websites from the repository. Additionally, Developers work in a local development environment using Visual Studio Code (VSCode) with Docker and Devcontainer extensions, creating an Ubuntu containerized environment for development. Git is utilized for version control, allowing for efficient collaboration and code management from local repositories to the remote repository hosted on GitHub.

## CI/CD Pipeline Tools
### [GitHub Actions:](https://github.com/features/actions)
The GitHub Actions tool is the primary source for this project's CI/CD pipeline, as it allows for easy automation and seamless integration with the GitHub repository. By providing a platform for automation that creates a workflow directly in the repository, the need for an external CI/CD server is eliminated. Using GitHub Actions, developers can define custom workflows using YAML, automating the build, test, and deploy phases. Due to the smaller nature of this project, GitHub actions works great. However, it does have limits on concurrency, execution time, and resource usage for workflows, which can constrain large-scale or resource-intensive builds.

### [Docker:](https://www.docker.com/)
For this CI/CD pipeline, Docker containerizes our web application, ensuring consistent deployment across different environments. By packaging the application and its dependencies into a Docker image, we can isolate the environment into a Docker container, allowing for streamlined deployment. A strength of Docker containers is that they provide a lightweight and portable solution to simplify deployment and reduce configuration errors between different environments. A limitation of using Docker is that  improperly configured Docker containers can pose security risks, such as vulnerabilities in base images or insecure container configurations, so being mindful of known exploits is necessary. 

### [GitHub Pages:](https://pages.github.com/)
For this CI/CD pipeline, GitHub Pages hosts and publishes static websites directly from our GitHub repository. This allows developers to create and host a website without using external hosting services like Amazon Web Services (AWS). Due to being a part of the GitHub suite, GitHub pages integrates easily with the CI/CD pipeline, allowing for automatic deployment of changes to the live website whenever new commits are pushed to the GitHub Repository. While great for this project, GitHub Pages is designed for hosting static websites and does not support server-side scripting or dynamic content generation, so it would not work for more complex web applications. 

## Automation Process
### Build Phase:

1. **Code Compilation**: Upon a new code push to the repository, the workflow begins by checking out the code repository using the GitHub Actions checkout action. Next, the Flutter SDK is set up using the subosito/flutter-action action, specifying the stable channel. Dependencies for the Flutter application located in the './app' directory are installed using the 'flutter pub get' command.

2. **Unit Testing**: Automated tests for the Flutter application are executed using the 'flutter test' command to ensure code quality and functionality. This step verifies the correctness of individual components of the application.

3. **Integration Testing**: Integration testing ensures compatibility and interaction between different application components. This is executed by:
- Setting up the Testing Environment
- Running Integration Tests by using [Flutter's integration testing](https://docs.flutter.dev/testing/integration-tests) framework to simulate user interactions and validate UI behavior.
- Collecting and Analyzing the Test Results
- Generating the Test Reports

### Deployment Phase:

1. **Deployment to GitHub Pages**: Once the build and testing phases are successful, the built web assets of the Flutter application located in the './app/build/web' directory are deployed to GitHub Pages. This deployment is facilitated using the peaceiris/actions-gh-pages action. The action publishes the contents of the specified directory to the 'gh-pages' branch of the repository, making the application accessible as a static website.

# Conclusion
To conclude, to create the CI/CD Pipeline for this project, allowing for automated building, testing, and deployment of a Flutter Web application, a GitHub Enivonment was used, utilizing GitHub Actions, Github Pages, and Docker. 
