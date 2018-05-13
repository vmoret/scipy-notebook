# vimo76/scipy-notebook

Slightly modified version of the [jupyter/scipy-notebook](https://github.com/jupyter/docker-stacks/tree/master/scipy-notebook) docker image.

Basically the `pandas` version is too old in the standard docker image and we're using `/home/jovyan/work` as WORKDIR instead of `/home/jovyan`.

## Usage

Create a `docker-compose.yml` file

```yaml
version: '3'
services:
    notebook:
        image: "vimo76/scipy-notebook"
        ports:
        - "8888:8888"
        volumes:
        - D:\Work:/home/jovyan/work
        - D:\Data:/home/jovyan/data
        environment:
            JIRA_USER: user
            JIRA_PASS: password

```

and run it with `docker-compose`.

```bash
docker-compose up
```