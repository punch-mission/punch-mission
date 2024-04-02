# Development Guide

PUNCH creates its science processing code primarily in Python. We recommend following Python best practices. 
These can be found in various documents; a good starting point is [the SunPy Developer's Guide](https://docs.sunpy.org/en/latest/dev_guide/index.html). 
You may find [Python Like You Mean It](https://www.pythonlikeyoumeanit.com/index.html) to be helpful if you're newer to Python. 

## General tips

- Follow [PEP8](https://peps.python.org/pep-0008/) when appropriate and always use a linter for style.
- There are many options for linters, but we recommend [ruff](https://github.com/astral-sh/ruff). This should be installed as part of a pre-commit step. Your package maintainer should set pre-commit up. 
- Write tests first. Then, write code to pass the tests. Finally, refactor code for clarity and style.
- Documentation is critical. Do not put it off. Code without documentation is unsusable by the coommunity and by future you when you forget how it works. 
- Class names should be nouns, for example `StarfieldModel`.
- Function names should be verbs, for example `build_starfield_model`. 
- Variable names should be descriptive but still concise. No variables named by just a few letters. So `emission_measure` instead of `em` or `emission_measure_cube_for_reprocessing`. 
- Avoid loops by leveraging `numpy`.
- Functions have clearly defined and restricted purposes. *A function does one thing instead of many.* For example, a function should generally not do calculations **and** handle I/O.
- Don't reinvent the wheel; use existing tools in `astropy`, `sunpy`, and the Python ecosystem. 

## Using virtual environments

It is advised to develop and test in virtual environments. A virtual environment is a non-global Python environment that is dedicated to a specific project. 
By developing in a virtual environment as opposed to a global environmnet, you can avoid package dependency conflicts being a source of your errors. 
You can also experiment with updating to newer versions of packages and see if they are compatible with your code. 

To create and activate a virtual environment run:

```sh
python -m venv my_venv_name
source my_venv_name/bin/activate
```

When you're finished working in this virtual environment, simply run `deactivate`. 

Note that most Python IDEs will manage virtual environments for you, preventing you from having to manually execute these commands. 

## Testing code

We expect nearly all lines of code to have an associated test. Comprehensive testing allows peace of mind when developing new features or modifying existing ones. 
You are alerted by a failed test if something you did breaks the code. We recommend using `pytest` as your testing framework. 
[Read more about testing here](https://docs.sunpy.org/en/latest/dev_guide/contents/tests.html). 

## Documentation

Code without documentation can be as useless as code that doesn't exist and even more frustrating. It is critical to document all code. 
When you write a function, include a docstring in the [numpydoc format](https://numpydoc.readthedocs.io/en/latest/format.html#docstring-standard). 

In addition to documenting directly in code, we recommend developing documentation websites with introductory material and examples as a [Sphinx website](https://www.sphinx-doc.org/en/master/). 

### Type Hints

Type hints serve as one form of documentation. [PEP 484](https://peps.python.org/pep-0484/) and [PEP 526](https://peps.python.org/pep-0526/) describe the standards of type annotations. We use type annotations to make it easier for users and developers to understand what the types of variables are as we move them around. They’re simply a guide and don’t actually impact the code at runtime in our codebase. Some people (such as Prefect) use the type annotations to strictly enforce types, i.e. if a variable’s type differs from the type hint the code will not run. [MyPy](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html) provides a helpful cheatsheet that shows examples of different type hints. 

It’s most important that you annotate the types of functions. Here’s an example of a function annotated:

```py
def streak_correction_matrix(
  n: int, 
  exposure_time: float, 
  readout_line_time: float, 
  reset_line_time: float
) -> np.ndarray:
```

Each function parameter has a type indicated, in this case either integer or float. After the parameter’s closing parenthesis but before the colon, we insert `-> np.ndarray` to indicate that the function returns a numpy array. 


## GitHub practices

We use GitHub to manage our development. This involves sharing code, continuous integration, issue tracking, and more. 

### Creating an issue

When you create a GitHub issue be as specific as possible. More specificity enables a more productive development cycle fixing the issue. 

If you're a package maintainer, it is recommended to 
[set up issue templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository)
to encourage this kind of specificity. 

## NDCube

"[ndcube](https://docs.sunpy.org/projects/ndcube/en/stable/) is a SunPy Project affiliated package designed for handling N-dimensional data cubes described by WCS (World Coordinate System) transformations." 

The PUNCHData object is designed around the NDCube object at its core, with extensions for PUNCH-specific functionality. Each object contains a data array (`np.ndarray` object), a world coordinate system (wcs) (`astropy.wcs` object), an uncertainty / weight array (`np.ndarray` object), an optional mask, meta data, and specified units.

- PUNCHData.data: Primary observation data (2D or multidimensional ndarray)
- PUNCHData.wcs: World coordinate system object describing observation data axes
- PUNCHData.uncertainty: Measure of pixel uncertainty mapping from the primary data array
- PUNCHData.weight: Measure of pixel weighting computed from the inverse of the pixel uncertainty
- PUNCHData.mask: Optional masking array to omit flagged pixels from plotting / visualization
- PUNCHData.meta: Observation metadata, comprised of keywords and values as a modified astropy FITS header object
- PUNCHData.unit: Units for the measurements in the primary data array

The PUNCHData object also contains class methods and properties to facilitate interacting with data, including modules for reading / writing data objects, updating history / meta, and viewing data.

For PUNCH, we have implemented our own metadata class called `NormalizedMetadata`. Learn more about this in the `punchbowl` documentation. 

