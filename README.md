# Errbit Docker image

Dockerfile and repository for running [errbit] in a docker container.

The short version of how to get it running:
```bash
docker run -d --name mongodb mongodb
docker run -d \
  --name errbit 
  --link mongodb:mongodb 
  -p 3000:80
  -e "MONGO_URL=mongodb://mongodb/errbit"
  simonoff/errbit
docker run \
  --rm \
  --link mongodb:mongodb
  -e "MONGO_URL=mongodb://mongodb/errbit"
  simonoff/errbit
  bundle exec rake errbit:bootstrap
```

And then point your browser at ```http://localhost:3000```

## Configuration

The image supports configuration using environment variables.
See the errbit documentation for list of [available variables].

[errbit]: https://github.com/errbit/errbit
[available variables]: https://github.com/errbit/errbit/blob/master/docs/ENV-VARIABLES.md
