# Writing Documentation

This page discusses how to contribute documentation for Docuisine. We use [Zensical](https://zensical.org/) to write documentation by using markdown syntax. We use GitHub Pages to host the documentation website. 

## Getting Started

!!! note Requirements

    Installing [git](https://git-scm.com/install/), [uv](https://docs.astral.sh/uv/guides/install-python/) and Python are essential requirements to work with this project.
    If you don't have Python 3.13 on your machine, simply write `uv python install 3.13` on your favourite terminal.

1. Clone the git repository of the project
```bash
git clone https://github.com/docuisine/documentation.git
```

2. Move into the directory
```bash
cd documentation
```

3. Install dependencies
```bash
uv sync
```

4. Start the local documentation server and start writing!
```bash
uv run zensical serve
```

!!! tip Options

    Optionally, add the argument `-a` to specify an address and port for the server to run on.
    Example: `uv run zensical serve -a 0.0.0.0:7000`, this runs on `http://localhost:7000` or `http://0.0.0.0:7000`.

## Formatting

It is imperative to read the [official Zensical documentation](https://zensical.org/docs/authoring/markdown/) if you need to use features such as content tabs, grids, diagrams, advanced formatting, etc. 

## Configuration

If a change in the project configuration file `zensical.toml` is needed, read this [relevant documentation](https://zensical.org/docs/setup/basics/) for a detailed manual.
