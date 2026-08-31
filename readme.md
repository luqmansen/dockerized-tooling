## dockerized-tooling

My personal collection of tooling that doesn't have official docker image

## golang/mock
How to use
```bash
docker run --rm -v $(PWD):/app -w /app luqmansen/docker-mockgen mockgen -source=pkg/services/services.go -destination=mock/service_mock.go -package=mock
```

## LaTeX
Full TeX Live (`texlive-full`, `latexmk`, `biber`) on Debian bookworm. Run any tool with the current directory mounted at `/tmp`.
```bash
docker run --rm -v $(PWD):/tmp luqmansen/docker-latex pdflatex sample.tex
```
