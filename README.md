# Cradle

A Cookiecutter starter for documentation about one technical initiative.

## Create a project

```bash
docker run --rm -it \
  --user "$(id -u):$(id -g)" \
  -e HOME=/tmp \
  -v "$PWD:/work" \
  -w /work \
  ghcr.io/astral-sh/uv:debian \
  uvx cookiecutter \
    --checkout main \
    https://codeberg.org/dominikfalkner/cradle.git
```

## Development container

Open the generated project in VS Code and run **Dev Containers: Reopen in Container**.

The container includes Quarto, TinyTeX, LuaLaTeX, Python, Jupyter, Git, common fonts, and PDF utilities. Run `quarto check` to verify the environment.

Markdown files are rendered individually. The generated repository README contains the rendering commands.
