# wallabag

This repo helps you create a simple, self-hosted, Docker-based [Wallabag](https://www.wallabag.it/en) instance.

# Instructions

- To start the instance:
  - Docker host: `docker-compose up`. Run `docker-compose up -d` to run the instance in the background.
  - Podman host:
    - Ensure the podman socket has been started: `systemctl --user start podman.socket`
    - Start the instance:
      - Using `docker-compose`:
        - Run the `./start` command. Run `./start -d` if you want to run the instance in the background.
      - Using `podman-compose`:
        - Run `podman-compose up`. Run `podman-compose up -d` to run the instance in the background.

- To enable the instance on boot, use one of the two included helper scripts:
  - `docker-systemd-service-file-generate`
  - `podman-systemd-service-file-generate`
- Either command can be run with the `--help` flag to learn more about automatically starting this service after a reboot.

# Environment

- To edit the environment variables, you should create a `.env` file in the root directory of this repo.
  - You can copy the contents of `.env.example` to `.env` to serve as a reference.
  - You can also edit the `docker-compose.yml` file directly if you want to.
- To bypass email confirmation, change the `SYMFONY__ENV__FOSUSER_CONFIRMATION` parameter to `false`.
- To prevent other users from being able to register, change the `SYMFONY__ENV__FOSUSER_REGISTRATION` parameter to `false` and restart the instance.
- To learn more about configuring the Wallabag Docker image, view their official repo: https://github.com/wallabag/docker 

# Credit

All credit to Wallabag for their amazing software!
