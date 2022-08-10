# R version: 4, 4.1, 4.0
ARG VARIANT="4.2"
FROM rocker/tidyverse:${VARIANT}
# Includes packages: devtools tidyverse tidymodels glmnet randomForest xgboost 

# Use the [Option] comment to specify true/false arguments that should appear in VS Code UX
#
# [Option] Install zsh
ARG INSTALL_ZSH="true"
# [Option] Upgrade OS packages to their latest versions
ARG UPGRADE_PACKAGES="false"

# Install needed packages and setup non-root user. Use a separate RUN statement to add your own dependencies.
ARG USERNAME=vscode
ARG USER_UID=1001
ARG USER_GID=$USER_UID
COPY library-scripts/*.sh /tmp/library-scripts/
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && /bin/bash /tmp/library-scripts/common-debian.sh "${INSTALL_ZSH}" "${USERNAME}" "${USER_UID}" "${USER_GID}" "${UPGRADE_PACKAGES}" "true" "true" \
    && usermod -a -G staff ${USERNAME} \
    && apt-get -y install \
        python3.9 \
        #python3-pip \
        libgit2-dev \
        libcurl4-openssl-dev \
        libssl-dev \
        libxml2-dev \
        libxt-dev \
    && apt-get autoremove -y && apt-get clean -y && rm -rf /var/lib/apt/lists/* /tmp/library-scripts \
    # Installing pip for python 3.9: https://askubuntu.com/questions/1331391/how-do-you-install-pip-for-python3-9-4
    && curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py \
    && python3.9 get-pip.py \ 
    && pip3 --no-cache-dir install radian \
    && pip3 --disable-pip-version-check --no-cache-dir install pandas \
    && pip3 --disable-pip-version-check --no-cache-dir install seaborn \
    && install2.r --error --skipinstalled --ncpus -1 \
        palmerpenguins \
        languageserver \
        httpgd \
    && rm -rf /tmp/downloaded_packages




# VSCode R Debugger dependency. Install the latest release version from GitHub without using GitHub API.
# See https://github.com/microsoft/vscode-dev-containers/issues/1032
RUN export TAG=$(git ls-remote --tags --refs --sort='version:refname' https://github.com/ManuelHentschel/vscDebugger v\* | tail -n 1 | cut --delimiter='/' --fields=3) \
    && Rscript -e "remotes::install_git('https://github.com/ManuelHentschel/vscDebugger.git', ref = '"${TAG}"', dependencies = FALSE)"

# R Session watcher settings.
# See more details: https://github.com/REditorSupport/vscode-R/wiki/R-Session-watcher
RUN echo 'source(file.path(Sys.getenv("HOME"), ".vscode-R", "init.R"))' >> ${HOME}/.Rprofile

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update \
#     && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment this section to install additional R packages.
# RUN install2.r --error --skipinstalled --ncpus -1 <your-package-list-here>


# [Optional] Uncomment this section to install vscode-jupyter dependencies.
RUN apt-get update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libzmq3-dev \
    && install2.r --error --skipinstalled --ncpus -1 IRkernel \
    && pip3 --no-cache-dir install jupyter \
    && R --vanilla -s -e 'IRkernel::installspec(user = FALSE)'

# [Optional] Uncomment this section to install Quarto
# Find download link at: https://quarto.org/docs/get-started/
RUN wget https://github.com/quarto-dev/quarto-cli/releases/download/v1.0.38/quarto-1.0.38-linux-amd64.deb \
    && sudo dpkg -i quarto-1.0.38-linux-amd64.deb \
    && rm quarto-1.0.38-linux-amd64.deb

# Expose Rstudio port. Log in with rstudio/rstudio as username and password
EXPOSE 8787

# Expose Jupyter port
EXPOSE 8888

CMD ["/init"]