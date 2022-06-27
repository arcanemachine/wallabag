# wallabag

This repo helps you easily create a self-hosted, Docker-based [Wallabag](https://www.wallabag.it/en) instance.


# Read this First!

To make things easy to set up, the default config allows users to register without needing to confirm their email address.

#### If you plan on hosting this instance publicly over the Internet, you should probably disable user registration after creating your account. See the [Environment](#environment) section for instructions.


# Instructions

- Install `[Docker](https://docs.docker.com/engine/install/)` or `podman`

- Install `[docker-compose](https://docs.docker.com/compose/install/)`

- To start the instance:
  - Docker host: Run the `./start-docker` command. Run `./start-docker -d` if you want to run the instance in the background.
  - Podman host:
    - Ensure the podman socket has been started: `systemctl --user start podman.socket`
    - Run the `./start` command. Run `./start -d` if you want to run the instance in the background.

- To start the instance automatically on boot:
  - Use one of the two included helper scripts to generate a `systemd` service file:
    - `docker-systemd-service-file-generate`
    - `podman-systemd-service-file-generate`
  - Either script can be run with the `--help` flag to learn more about their use.


# Environment

- To edit the environment variables, you should create a `.env` file in the root directory of this repo.
  - You can copy the contents of `.env.example` to `.env` to serve as a reference.
  - You can also edit the `docker-compose.yml` file directly if you want to.

- To prevent other users from being able to register, change the `SYMFONY__ENV__FOSUSER_REGISTRATION` parameter to `false` and restart the instance.

- To require email confirmation, change the `SYMFONY__ENV__FOSUSER_CONFIRMATION` parameter to `true`.

- To learn more about configuring the Wallabag Docker image, view their official repo: https://github.com/wallabag/docker 


# Credit

All credit to Wallabag for their amazing software!
