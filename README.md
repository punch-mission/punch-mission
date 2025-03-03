# Welcome to PUNCH

PUNCH, the Polarimeter to UNify the Corona and Heliosphere, is a NASA Small Explorer (SMEX) mission to better understand how the mass and energy of the Sun’s corona become the solar wind that fills the solar system.
Four suitcase-sized satellites will work together to produce images of the entire inner solar system around the clock. [Learn more here](https://punch.space.swri.edu/).

## What's in this repository?

This repository contains the top-level documents for the PUNCH mission's work on GitHub:

- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Contribution Guide](contributing.md)
- [Development Guide](development.md)
- [Advice on how to get help](getting_help.md)
- [Repository Index](repository_index.md)
- [Contributed Tools](contributed_tools.md)
- [A project wide requirements.txt that pins dependencies](requirements.txt) (This is what we run when producing data.)
- [Current versions of PUNCH-authored packages used in data production.](requirements_PUNCH.txt)
- [Compatibility among PUNCH packages](compatibility.md)


## Where can I ask questions?

You can access our [top-level discussions](https://github.com/orgs/punch-mission/discussions) to ask general questions about PUNCH.
If you have a question or issue specific to a certain repository, please ask in that repository's discussion.


## Setting up the PUNCH environment

1. Download the [requirements.txt](requirements.txt).
2. Download the [PUNCH package list](requirements_PUNCH.txt). 
3. Create a virtual environment in Python using `venv` with `python -m venv .venv`
4. Activate the virtual environment with `source .venv/bin/activate`.
5. Install the dependencies with `pip install -r requirements.txt`
6. Install the appropriate SOC-developed packages either manually from source or with `pip install -r requirements_PUNCH.txt`.
7. Explore some data!
