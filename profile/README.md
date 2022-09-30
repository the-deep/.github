![deep](https://user-images.githubusercontent.com/6733492/193183087-5eb01f8a-ab47-4ed2-83a2-3ea020c5b902.png)

# What is DEEP?
**DEEP** is an intelligent web-based platform offering a suite of collaborative tools tailored towards humanitarian crisis responses. It includes common analysis workflows and frameworks for thinking using both structured and unstructured, quantitative and qualitative data. By using a customizable analysis frameworks, users can easily catalog information contained in large amounts of documents and export it to a variety of formats. Supporting this, DEEP has a long term vision of using text analysis techniques in order to streamline the process of sourcing information from online sources and semi-automating document information extraction. Although the platform is meant to be a collaborative space, it is open-source and available to be deployed in private server environments. Data in DEEP is visible only to users granted access to a project space and is stored using modern web technology standards.

Development of DEEP began in early 2016 and it is a collaborative project governed by [ACAPS](https://deephelp.zendesk.com/hc/en-us/articles/acaps.org), [IDMC](http://www.internal-displacement.org/), [IFRC](http://ifrc.org/), [JIPS](http://jips.org/), [UNHCR](http://www.unhcr.org/en-us/), [UNICEF](https://www.unicef.org/), [UN OCHA](https://www.unocha.org/), [OHCHR](https://www.ohchr.org/) and [Okular-Analytics](https://www.okular-analytics.com/).

# How to post an issue
Any DEEP user or developer can create an issue and mark it with available labels to prioritize the issue properly. Creating issues helps everyone keep track of bugs, change requests and other on-going development work within DEEP.
For the overall project issue, you can go to [“deeper” repo](https://github.com/the-deep/deeper) and follow the guidelines below. For repository specific issues, please go to the concerned repository and follow the guidelines below:

* Click the **Issues** tab on the top of the repository’s page as seen in the image here:
![issues](https://user-images.githubusercontent.com/6733492/193184461-aa829487-aaff-490e-95a1-6dbb5f74de1a.png)
* Check the issues and see if your issue has already been asked and resolved.
* If not, click on the **New Issue** button on the right side
* Enter the **Title** and write a **Description** of the issue. Please make sure you write a detailed description of the issue and add an example along with the steps to reproduce if possible. If available, we encourage you to attach any images or files that can help us understand and replicate the issue. Here is an example of a good way to [report an issue](https://github.com/the-deep/deeper/issues/297).
* Select a **Label** that properly defines the priority of the issue. Labels help the development team understand the urgency and prioritize the issue accordingly. If it's a critical bug, please assign "High Priority" label to it, if it is non-critical and can wait, assign it "Low Priority". You can also use labels to categorize issues. For example, you can mark an issue as a bug or a feature request by using appropriate labels. Please go through [this link](https://github.com/the-deep/deeper/labels) to know more about the different labels you can use along with their description.
* If you know who should work on the issue, please **assign** the name of the team member. If you are not aware of this, please leave it blank.
* Once you are done, please click on the **Submit new issue** button. 
* You are done! The development team will now take it from here. Please revisit your issue periodically to keep up with the progress, or if you have email alerts setup you will be notified by email when your issue is updated.

# How to Contribute
Thank you for wanting to contribute to this project! We look forward to working with you. Here is a basic set of guidelines for contributing to our project. 
* Please **checkout the issues** in the [deeper repository](https://github.com/the-deep/deeper) or the individual repository you want to contribute to. You can also create a new issue regarding what you want to work on. Please follow the guidelines mentioned above while creating the issue. You will need to include the link to the issue while creating a Pull Request(PR).
* **Fork** the relevant repository.
* **Make necessary changes** to the repository taking into account the **coding guidelines** mentioned in the individual repositories. Some general guidelines include the use of “git rebase” to organize commits and these instructions regarding commit messages:
  * Separate subjects from body with a blank line
  * Limit the subject line to 50 characters
  * Capitalize the subject line
  * Do not end the subject line with a period
  * Use the imperative mood in the subject line
  * Wrap the body at 72 characters
  * Use the body to explain what and why vs. how
* After your work is complete, **make a Pull Request** from your repository to the-deep repository. Describe what you did in as much detail as possible. Furthermore, please link to the issue in the description.
* Our development team will go through the pull request and merge them if they are satisfactory. They can also review the PR and ask for explanations/modifications.

# Repositories
This project contains a number of repositories which work together. Here is a list of the main repositories and their brief descriptions:
* **deeper**: The main repository for the DEEP project with configuration files and scripts for local and cloud deployments
* **server**: Backend server with Django
* **client**: Frontend code with React
* **serverless**: Services for DEEP utilities that run in serverless framework
* **deep-extensions**: Browser extension to add sources to DEEP platform

# Installation Instructions
* Clone deeper repo

`git clone https://github.com/the-deep/deeper.git deep-project-root`
* Go to deeper project root

`cd deep-project-root`
* Clone client, server and other repos

`git clone https://github.com/the-deep/server.git server`

`git clone https://github.com/the-deep/client.git client`

`git clone --branch=feature/only-ary https://github.com/the-deep/client.git ./ary-only-client`

`git clone https://github.com/the-deep/deepl-deep-integration.git deepl-service`

* Comment out pulling of images from docker.io in docker-compose.yml if you want to build from the source

`#image: docker.pkg.github.com/the-deep/client:latest`

`#image: docker.pkg.github.com/the-deep/ary-only-client:latest`

`#image: docker.pkg.github.com/the-deep/client:latest`

`#image: docker.pkg.github.com/the-deep/deepl-service:latest`

* If you have a **Mac with M1 chip**, change the `deepl-service/Dockerfile` to specify amd64 platform in its FROM statement:

`FROM --platform=linux/amd64 python:3.10-slim-buster`

* If you are on a **Mac**, you have to turn off 'Airplay Reciever' from 'System Preferences > Sharing' to make port 5000 available for use.
* Use docker-compose to start the servers (Install latest docker and docker-compose, if they are not installed)

`docker-compose pull`

`docker-compose build`

`docker-compose up`

# Useful Commands
* To migrate, go to the docker container and run migrate command:

`docker-compose exec web bash`

`./manage.py migrate`

* To test, go to the docker container and run the test command:


`docker-compose exec web bash`

`./manage.py test`

# Useful Links:
* [Userguide](https://deephelp.zendesk.com/hc/en-us)
* [DEEP website](https://app.thedeep.io/)







