## dockerized-tooling

My personal collection of tooling that doesn't have official docker image

## golang/mock
How to use
```bash
docker run --rm -v $(PWD):/app -w /app luqmansen/docker-mockgen mockgen -source=pkg/services/services.go -destination=mock/service_mock.go -package=mock
```
   