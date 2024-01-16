See https://github.com/renovatebot/renovate/discussions/26645#discussioncomment-8137039 for issue description

Run using Docker

```
docker run --rm -it -v "./config.js:/usr/src/app/config.js" --env GITHUB_COM_TOKEN=<token> --env RENOVATE_TOKEN=<token> renovate/renovate:37.133.0-full
```

You will get a warning:

```
 WARN: Package lookup failures (repository=AndreasPetersen/renovate-26645)
       "warnings": ["Failed to look up helm package my-host/artifactory//"],
       "files": ["Jenkinsfile"]
```

It is to be expected that Renovate cannot look up `my-host`, but as can also be seen, the Handlebars are not compiled. The `depName` should be `my-host/artifactory/helm-remotes/redis`.