# res_comp_leeds_2022

Talk for the [Research Computing Leeds Conference](https://rescompleedscon.github.io/conference2022/schedule/): Save your tears for the data - A touch of Docker in a Data Scientist's workflow.

Slides:


### Abstract

Many data science teams have become multilingual, leveraging R, Python, Julia and friends in their work. Into the bargain, different data scientists have different preferences in their coding environments and operating systems. While this diversity allows data scientists to work with the tools they are most comfortable with, it can become a pain to share the same projects on different machines with different configurations. This talk illustrates how data scientists can leverage **Dev Containers** to create portable, reproducible and tailored development environments, which can be instantiated reliably in different environments, operating systems and hardware. Data scientists can therefore focus on what they love and do best (i.e data science) without having to worry about the hassle required to reproduce their work, deploy their analysis dashboards or even deploy their models.

### Demo

We create a dev container that can support data science tasks in **R**, **Python**, **VS Code** and **RStudio**.



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
