# Welcome to PUNCH

PUNCH, the Polarimeter to UNify the Corona and Heliosphere, is a NASA Small Explorer (SMEX) mission to better understand how the mass and energy of the Sun’s corona become the solar wind that fills the solar system.
Four suitcase-sized satellites work together to produce images of the entire inner solar system around the clock. [Learn more here](https://punch.space.swri.edu/).

## What's in this repository?

This repository contains the top-level documents for the PUNCH mission's work on GitHub:

- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Contribution Guide](contributing.md)
- [Development Guide](development.md)
- [Advice on how to get help](getting_help.md)
- [Repository Index](repository_index.md)
- [Contributed Tools](contributed_tools.md)
- [A project wide requirements.txt that pins dependencies](requirements.txt) (This is what we run when producing data.)
- [Current versions of PUNCH-authored packages used in data production.](requirements_punch.txt)
- [Compatibility among PUNCH packages](compatibility.md)

> [!TIP]
> [punchbowl](https://github.com/punch-mission/punchbowl) is the main calibration code for PUNCH. It's a good starting point for understanding PUNCH data.

## Where can I ask questions?

You can access our [top-level discussions](https://github.com/orgs/punch-mission/discussions) to ask general questions about PUNCH.
If you have a question or issue specific to a certain repository, please ask in that repository's discussion.


## Where can I learn how the PUNCH data reduction works? 

The main documentation is on [ReadTheDocs for punchbowl](https://punchbowl.readthedocs.io/en/latest/index.html). 

## Setting up the PUNCH environment

1. Clone this repository on your local machine.
2. TODO; The behavior we want from uv to allow complementary installs (based on if you are a developer or a user) is currently not implemented... (https://github.com/astral-sh/uv/pull/18272)
3. Create a virtual environment in Python using `uv` with `uv sync --no-editable`.
4. Activate the virtual environment with `source .venv/bin/activate` on Mac/Linux or `.venv\Scripts\activate` on Windows.
5. Explore some data!
