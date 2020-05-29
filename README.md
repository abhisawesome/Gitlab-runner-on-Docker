# Running Gitlab runner on docker container

1. Run the docker-compose.yml file using the following command

```
docker-compose run --rm gitlab-runner register -n \
  --url https://gitlab.com/ \
  --registration-token <TOKEN> \
  --executor docker \
  --description "YOUR DESCRIPTION" \
  --docker-image "docker:stable" \
  --docker-volumes /var/run/docker.sock:/var/run/docker.sock
``` 
2. You will get the token from the gitlab project: SETTINGS -> CI/CD -> RUNNERS

3. You can add the tags from the gitlab UI 

4. After running the command, config/config.toml will be generated, add the configuration and restart the container.

5. [Official Documentation](https://docs.gitlab.com/runner/register/index.html)