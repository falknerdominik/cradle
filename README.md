# Cradle

A Cookiecutter starter for documentation about one technical initiative.

## Create a project

```bash
cookiecutter /path/to/cradle
```

Cookiecutter prompts only for `repository_name` and creates the complete documentation structure in a folder with that name.

For non-interactive use:

```bash
cookiecutter /path/to/cradle \
  --no-input repository_name=my-initiative
```

## Development container

Open the generated project in VS Code and run **Dev Containers: Reopen in Container**.

The container includes Quarto, TinyTeX, LuaLaTeX, Python, Jupyter, Git, common fonts, and PDF utilities. Run `quarto check` to verify the environment.

Markdown files are rendered individually. The generated repository README contains the rendering commands.
