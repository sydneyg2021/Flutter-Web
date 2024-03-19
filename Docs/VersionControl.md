# Source Code Version Control Tools
## Introduction
Version control is essential for maintaining the project's integrity by tracking changes made to code and ensuring that changes are transparent and reversible if necessary. They keep an extensive history of changes, allowing developers to understand how the source code has evolved. This record of changes facilitates troubleshooting, rollback to previous working versions, and analysis of past code. Moreover, version control maintains collaboration by providing a centralized platform for sharing and managing code. 

## Version Control System Used
For this project, I used Git instead of other methods like Bazaar or Concurrent Versions System, as I was the most familiar with that system. Its seamless integration with Flutter development tools and workflow makes it easy to implement and use. Additionally, its distributed nature makes it well-suited for distributed development environments, typical in Flutter projects where developers may work remotely or across different time zones. Its branching and merging capabilities, essential for managing the complexity of Flutter projects, were also majorly attractive for this project. 

## Repository Setup
**Structure of the Repository**
* The branching strategy for this project included a Git Flow branching model with main, develop, feature, release, and hotfix branches.
* The directory contains a Docs folder with relevant documentation for the project, as well as devcontainer and GitHub folders for development in the main branch.  

**Integration with DevContainer and CI/CD Pipeline**
* DevContainer Integration: Utilized a DevContainer configuration for consistent development environments across systems. This configuration includes a Dockerfile, Docker Compose file, and necessary dependencies for the Flutter project.

* CI/CD Pipeline Integration: Integration with a CI/CD service using GitHub Actions to automate build, test, and deployment processes. The pipeline triggers commits to specific branches (e.g., main, develop) and executes defined workflows (e.g., build, test, deploy).

**Standards and Conventions Adopted**
* Branch Naming Conventions: Using descriptive branch names, such as feature/<feature-name>, release/<version>, or hotfix/<issue-number>, to provide clarity and context.

* Documentation Standards: Maintain documentation in Markdown format (README.md, docs/) following best practices for readability, completeness, and accuracy.

## Common Commands and Usage
_Common version control commands used:_
* `git clone <repository-url>`: Clones a repository onto the local machine.
* `git commit -m "Add new feature"`: Commits changes to the repository with a message.
* `git pull origin <branch-name>`: Push changes from the local repository to a remote repository.
* `git push origin <branch-name>`: Pushes changes from the local repository and merges them into the current branch.


## Collaboration Features
As explained earlier above in the **Introduction** section, Version control tools like Git foster collaboration in Flutter projects through tracking changes using branching, pull requests, and code reviews. 
* Branching allows developers to work independently on features, preventing conflicts.
* Pull requests enable code review, ensuring quality and adherence to standards before merging changes.
* Code reviews leverage team expertise for continuous improvement. Conflict resolution tools help reconcile conflicting changes efficiently. 

## Challenges and Solutions
Due to my previous use of Git version control, I did not encounter any current issues deploying push and pull requests and could accurately use version control for its intended functionalities. But, if issues occur in the future, refer to the [Issues](https://github.com/sydneyg2021/Flutter-Web/issues) section for this repository.

## Conclusion
In conclusion, utilizing Git for our Flutter project allows for concurrent development, preventing conflicts, and facilitating efficient collaboration among team members. Pull requests and code reviews ensure code quality and adherence to standards before merging changes. Git's conflict resolution tools aid in reconciling conflicting changes seamlessly. Integrating version control into our development workflow has provided insights into structured collaboration, streamlined code management, and enhanced project transparency. Overall, Git enhances productivity, code quality, and team coordination, fostering a cohesive and efficient development environment for our Flutter project.
