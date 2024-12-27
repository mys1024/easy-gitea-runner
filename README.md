# easy-gitea-runner

Easily startup a [**Act Runner**](https://docs.gitea.ac.cn/usage/actions/act-runner) container for [**Gitea**](https://about.gitea.com) with [**Docker Compose**](https://docs.docker.com/compose/).

## Usage

1. Create a `.env` file with your custom configurations:

    ```sh
    GITEA_INSTANCE_URL=YOUR_URL
    GITEA_RUNNER_REGISTRATION_TOKEN=YOUR_TOKEN
    GITEA_RUNNER_CACHE_PORT=32999 # optional, should be the same as the cache port configured in `volumes/config.yaml`
    DOCKER_SOCK_PATH=/var/run/docker.sock  # optional
    ```

2. Generate a configuration file for the runner:

    ```sh
    mkdir -p volumes && docker run --entrypoint="" --rm -it docker.io/gitea/act_runner:latest act_runner generate-config > volumes/config.yaml
    ```

3. Edit the runner configuration file `volumes/config.yaml` to your needs.

4. Startup:

    ```sh
    docker-compose up -d
    ```

## License

[MIT](./LICENSE) License &copy; 2024-PRESENT [mys1024](https://github.com/mys1024)
