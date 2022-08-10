# res_comp_leeds_2022

Talk for the [Research Computing Leeds Conference](https://rescompleedscon.github.io/conference2022/schedule/): Save your tears for the data - A touch of Docker in a Data Scientist's workflow.

Slides: [PDF](https://github.com/R-icntay/res_comp_leeds_2022/blob/main/Eric_rs_comp_leeds.pdf)


### Abstract

Many data science teams have become multilingual, leveraging R, Python, Julia and friends in their work. Into the bargain, different data scientists have different preferences in their coding environments and operating systems. While this diversity allows data scientists to work with the tools they are most comfortable with, it can become a pain to share the same projects on different machines with different configurations. This talk illustrates how data scientists can leverage **Dev Containers** to create portable, reproducible and tailored development environments, which can be instantiated reliably in different environments, operating systems and hardware. Data scientists can therefore focus on what they love and do best (i.e data science) without having to worry about the hassle required to reproduce their work, deploy their analysis dashboards or even deploy their models.

### Setting up the development container

A **development container** is a running [Docker](https://www.docker.com) container with a well-defined tool/runtime stack and its prerequisites. You can try out development containers with **[GitHub Codespaces](https://github.com/features/codespaces)** on the cloud or **[Visual Studio Code Remote - Containers](https://aka.ms/vscode-remote/containers)** on a machine that has Docker installed as per the instructions below:

#### GitHub Codespaces
Follow these steps to open this workshop in a Codespace:
1. Click the Code drop-down menu on the repo and select the **Open with Codespaces** option.
2. Select **+ New codespace** at the bottom on the pane.

For more info, check out the [GitHub documentation](https://docs.github.com/en/free-pro-team@latest/github/developing-online-with-codespaces/creating-a-codespace#creating-a-codespace).

#### VS Code Remote - Containers
Follow these steps to open this workshop in a container using the VS Code Remote - Containers extension:

1. If this is your first time using a development container, please ensure your system meets the pre-reqs (i.e. have Docker installed) in the [getting started steps](https://aka.ms/vscode-remote/containers/getting-started).

2. Press <kbd>F1</kbd> select and **Add Development Container Configuration Files...** command for **Remote-Containers** or **Codespaces**.

   > **Note:** If needed, you can drag-and-drop the `.devcontainer` folder from this sub-folder in a locally cloned copy of this repository into the VS Code file explorer instead of using the command.

3. Select this definition. You may also need to select **Show All Definitions...** for it to appear.

4. Finally, press <kbd>F1</kbd> and run **Remote-Containers: Reopen Folder in Container** to start using the definition.

At some point, you may want to make changes to your container, such as installing a new package. You'll need to rebuild your container for your changes to take effect. 


### Demo

We create a dev container that can support data science tasks in **R**, **Python**, **VS Code** and **RStudio**.

#### Spinning up RStudio server

Toggle terminal: `ctrl` + `

Navigate to `PORTS` tab, then click on the 🌐 icon:

<p align = "center">
    <img src = images\rsport.png>
</p>

The default username and password is **rstudio** (as it should? 🤭)

### Resources

- [The Rocker Project](https://rocker-project.org/): Docker Containers for the R Environment
- [A repository of development container definitions](https://github.com/microsoft/vscode-dev-containers)
- [Introduction to dev containers](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/introduction-to-dev-containers)
- [Saturn Cloud Webinar: Docker for Data Scientists by Jacqueline Nolis](https://www.youtube.com/watch?v=2YMu9bzDJbY)
- [Valohai: Docker for Data Science: What every data scientist should know about Docker](https://valohai.com/blog/docker-for-data-science/)

### Thanks to

Thank you to the following folks for providing helpful info on how to set up RStudio server on a dev container:
- David Smith: [Zero-setup R workshops with GitHub Codespaces](https://github.com/revodavid/devcontainers-rstudio)
- えいつぴ (@[eitsupi](https://twitter.com/eitsupi)): For [helpful info on using RStudio in a Rocker container](https://www.rocker-project.org/images/versioned/rstudio)
- Eric Nantz ([R-Podcast](https://r-podcast.org/)): For the episode "[Fully containerized R dev environment with Docker, RStudio, and VS-Code](https://www.youtube.com/watch?v=4wRiPG9LM3o)"
