# PyMatterChat
PyMatterChat will be a containerized bot written in Python for Mattermost Bot Hackfest Jan '20. The development of the bot is divided into three phases:
- **Phase 0:** Develop a general framework to integrate different types of actions and responses.
- **Phase 1:** Execute CLI commands remotely in a **secure** environment.
**Theme: ChatOps**
- **Phase 2:** Develop an intelligent Chatbot to answer frequently asked questions about tools and services used by developers.
**Theme: Machine Learning (ML) and/or Artificial Intelligence (AI)**
## Sending us your suggestions:
Make a pull request [here](https://github.com/KMK-Git/mattermost-hackathon-idea-phase).
## Project Focus Areas:
- Security
- Extensibility
- Testing
- CI/CD
## Phase 0:
The first phase will build a general framework which will act as the skeleton for all types of integrations possible with the bot. This includes building the general architecture of the bot (listening to posts via webhooks and responding via the REST API), defining the attributes which will be required for all types of integrations and the manner in which these attributes will be used.
## Phase 1:
Executing CLI commands remotely gives the ability for developers to perform certain tasks remotely, with the output visible to everyone in the team. The main aim of this phase is to build a general framework for integrations of any type of CLI commands, while providing restrictions on the type and scope of CLI commands which can be executed. The framework will also define ways to authenticate and authorize execution of such commands, and will also provide means to enable separate authorization levels for every user. The other aim is to build one or two examples of such an integration, while keeping the ability to extend the framework to other types of CLI integrations.

**Example:** AWS CLI integration with Mattermost. Authorization can either be same for all users, or the AWS AssumeRole API can be used to generate temporary credentials for all users depending on the IAM role assigned to them.
## Phase 2:
Instead of having to Google the answer to a commonly asked question, you can simply ask the question to the bot and the bot can send a response if it knows the answer. The main aim is to build a prototype which will accept a knowledge base in the form of a list of questions and answers, and then answer questions similar to the questions in the knowledge base.
## General architecture
![architecture](https://raw.githubusercontent.com/KMK-Git/mattermost-hackathon-idea-phase/master/architecture.png)

The bot will run inside a Docker container. It will listen to new posts via a websocket connection with the Mattermost server. It will send a response back via the REST API. For any persistent data which needs to be stored, it will communicate with a Database via an ORM.
## Activity Diagram for bot actions
![activity](https://raw.githubusercontent.com/KMK-Git/mattermost-hackathon-idea-phase/master/activity.png)

Once a post notification is received, the bot will figure out which type of response needs to be triggered. For CLI response type, the command will be executed and stdout + stderr will be sent as response. For Knowledge Bot, a specific intent will be triggered based on the post sent, and then the response generated will be sent back as the answer. Other types of custom response types can also be added.
## Technologies/Frameworks/Tools
- [Python](https://www.python.org/)
- [GitHub](https://github.com)
- [Docker](https://www.docker.com/)
- [Python Mattermost Driver for APIv4](https://github.com/Vaelor/python-mattermost-driver)
- [SQLAlchemy](https://www.sqlalchemy.org/)
- [Rasa](https://rasa.com/)
- [Travis CI](https://travis-ci.org/)
