# easy-gitea-runner

Easily startup an [**Act Runner**](https://docs.gitea.ac.cn/usage/actions/act-runner) container for [**Gitea**](https://about.gitea.com) with [**Docker Compose**](https://docs.docker.com/compose/).

## Usage

1. Create a file named `.env` with your custom configurations:

    ```sh
    GITEA_INSTANCE_URL=YOUR_URL # required
    GITEA_RUNNER_REGISTRATION_TOKEN=YOUR_TOKEN # required
    ```

2. Generate a configuration file for the runner:

    ```sh
    mkdir -p volumes && docker run --entrypoint="" --rm -it docker.io/gitea/act_runner:nightly-dind act_runner generate-config > volumes/config.yaml
    ```

3. Start:

    ```sh
    docker-compose up -d
    ```

## License

[MIT](./LICENSE) License &copy; 2024-PRESENT [mys1024](https://github.com/mys1024)
