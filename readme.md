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

### `latex-docker` wrapper (use the tools like native binaries)
[`latex/latex-docker`](latex/latex-docker) runs a tool inside the image with the current
directory mounted at the **same path** in the container, so absolute paths and SyncTeX
resolve natively. Install it on your PATH under the real tool names:
```bash
install -m 0755 latex/latex-docker ~/.local/bin/latex-docker
for c in pdflatex latex xelatex lualatex latexmk biber bibtex makeindex dvips tex; do
  ln -sf ~/.local/bin/latex-docker ~/.local/bin/"$c"
done
# then, from any directory:
pdflatex sample.tex
```
The image defaults to a locally built `latex`; set `LATEX_IMAGE=luqmansen/docker-latex:latest`
to use the published image instead.

### VS Code / LaTeX Workshop
[`latex/vscode-settings.json`](latex/vscode-settings.json) is a LaTeX Workshop recipe that
builds through the wrapper (no path rewriting, SyncTeX works). Merge its keys into your VS
Code user settings or a workspace `.vscode/settings.json`.
