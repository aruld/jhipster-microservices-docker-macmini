# jhipster-microservices-docker-macmini
Setting up your mac or macmini running OS X El Capitan 10.11.5 to deploy your jhipster microservices infrastructure on docker

## Prepping your Mac

1. Install Java 8 from the [Oracle website](http://www.oracle.com/technetwork/java/javase/downloads/index.html)

    ![Java version](screenshots/java-version.png?raw=true)

2. Install Intellij IDEA from the [Jetbrains website](https://www.jetbrains.com/idea/download/).
   Create a command-line launcher from the Tools menu. It is very handy to launch idea from the project directory.

    ![Idea Tools Menu](screenshots/idea-tools-command-line-launcher.png?raw=true)

3. Install Command Line Tools (OS X 10.11) for Xcode (git & co)

    ![Git version](screenshots/git-version.png?raw=true)

4. Install Homebrew from http://brew.sh

    ![Brew install output](screenshots/brew-install.png?raw=true)

5. Install iTerm2 + zsh (optional) from [iterm2.com website](https://www.iterm2.com).

   Follow these steps to [upgrade](http://stackoverflow.com/a/17649823) your ZSH version from Homebrew. Skip step #5 which changes default shell.

   Set the shell to zsh for iTerm2.

   Set to zsh under iTerm -> Preferences -> Profiles -> General -> Command


   ![iTerm ZSH configuration](screenshots/iterm-zsh-shell.png?raw=true)

   Enhance your zsh experience by installing [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh).
   This install script would automatically change default shell to zsh, you can undo this change by running this command

   ```
    sudo chsh -s /bin/bash
   ```

   I prefer not to change the default Terminal app which uses bash.

## Docker Setup

1. Install Oracle VirtualBox 5.0.20 or later from https://www.virtualbox.org/wiki/Downloads

2. Install Docker Toolbox from [Docker website](https://www.docker.com/products/docker-toolbox)
   Follow these steps from https://docs.docker.com/engine/installation/mac/

3. Run Docker Quickstart Terminal from Launchpad. This should run the default Docker machine and set its IP to 192.168.99.100.

    ![Docker config](screenshots/docker-config.png?raw=true)

    You should see your Docker VM running in VirtualBox

    ![VirtualBox Docker vm](screenshots/virtualbox-docker-vm.png?raw=true)

4. Stop your Docker machine

    ```
    arul@macmini ~: docker-machine ls
    NAME      ACTIVE   DRIVER       STATE     URL                         SWARM   DOCKER    ERRORS
    default   *        virtualbox   Running   tcp://192.168.99.100:2376           v1.11.1

    arul@macmini ~: docker-machine stop
    Stopping "default"...
    Machine "default" was stopped.

    arul@macmini ~: docker-machine ls
    NAME      ACTIVE   DRIVER       STATE     URL   SWARM   DOCKER    ERRORS
    default   -        virtualbox   Stopped                 Unknown
    ```
5. Update default base memory (2 GB) for your default Docker VM in Virtual Box. I set it to 4GB and set Video Memory to 64 MB (was set to 8 MB).

6. Start your Docker machine

    ```
    arul@macmini ~: docker-machine start
    Starting "default"...
    (default) Check network to re-create if needed...
    (default) Waiting for an IP...
    Machine "default" was started.
    Waiting for SSH to be available...
    Detecting the provisioner...
    Started machines may have new IP addresses. You may need to re-run the `docker-machine env` command.
    arul@macmini ~: docker-machine env
    export DOCKER_TLS_VERIFY="1"
    export DOCKER_HOST="tcp://192.168.99.100:2376"
    export DOCKER_CERT_PATH="/Users/arul/.docker/machine/machines/default"
    export DOCKER_MACHINE_NAME="default"
    # Run this command to configure your shell:
    # eval $(docker-machine env)
    arul@macmini ~: docker-machine ls
    NAME      ACTIVE   DRIVER       STATE     URL                         SWARM   DOCKER    ERRORS
    default   *        virtualbox   Running   tcp://192.168.99.100:2376           v1.11.1

    ```


## JHipster Setup

1. Install Node from Homebrew

    ![Node](screenshots/node-version.png?raw=true)

2. Install Yeoman

    ![Yeoman](screenshots/yeoman-install.png?raw=true)

3. Install Bower

    ![Bower](screenshots/bower-install.png?raw=true)

4. Install Gulp

    ![Gulp](screenshots/gulp-install.png?raw=true)

5. Install JHipster

    ![JHipster](screenshots/jhipster-install.png?raw=true)

6. Install JHipster CLI oh-my-zsh Plugin (optional)

    Follow [oh-my-zsh](https://github.com/jhipster/jhipster-oh-my-zsh-plugin) steps to install this plugin.

    ![JHipster oh-my-zsh plugin](screenshots/jhipster-oh-my-zsh-install.png?raw=true)

    Now, you can do tab-completions for jhipster commands

    ![JHipster oh-my-zsh plugin tab completions](screenshots/jhipster-cli-completions.png?raw=true)

##Welcome to the Hipster world!

![JHipster](https://jhipster.github.io/img/logo-jhipster-drink-coffee.png)

Watch this space for more hipversations :-)