# Docker JFrog Alpine
Docker image for the JFrog CLI based upon the lightweight Alpine docker image

Available on docker hub at https://hub.docker.com/r/jamesseymour0/jfrog-alpine

Example usage in a docker file:
```
FROM jamesseymour0/jfrog-alpine

RUN jfrog rt config --url=<Repository URL> --user=<Repository User>  --password=<Repository Password>
RUN jfrog rt ping
```

This is also been useful in GitLab builds for running basic tasks. For example:

```
My-Build-Job:
  stage: my-build-stage
  image: jamesseymour0/jfrog-alpine
  script:
    - jfrog rt config --url=$ARTIFACTORY_URL --user=$ARTIFACTORY_USER --password=$ARTIFACTORY_PASSWORD
    - jfrog rt ping
```
