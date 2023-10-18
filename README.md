# Contributions to the punch-mission

The PUNCH Science Operation Center (SOC) is responsible for the development, maintenance and curation of the PUNCH data reduction pipeline (PUNCH-pipe), user data reduction software (PUNCH-bowl), and several software packages that are required for PUNCH data reduction, but have more general applications (e.g. Solpolpy - the polarization resolver, and RegularizePSF - the point-spread function regularization package). Each of these packages are developed for the user community, and as such the SOC values input from the user community.

The punch-mission is mainly developed in python to ensure it’s open source and available to everyone, and this guide is primarily for python developers. Due to the solar and heliospheric software development heritage, other programing languages are used by the user community (e.g. IDL) and the SOC will do their best to incorporate packages produced in other software development languages.

# Contributing to PUNCH

There are numerous ways to contribute to the punch-mission, including: providing code and documentation, suggesting and discussing ideas, submitting issues and bug reports, providing working examples and engaging with the broader solar physics, heliophysics, and instrument calibration communities. We need you - All code and documentation improvements, suggestions and discussions are valuable to the punch-mission and the wider community, if you have an issue you can be sure others will have similar issues.

Code contributions and pull requests - The SOC has developed the PUNCH software to conform to the latest and greatest development standards, however, new innovations, calibrations and bugs are inevitable, some of which the SOC may not identify. The user community can help the SOC and the user community in general by helping to identify such issues and provide valuable input via the GitHub repository. 

Suggestions to improve existing code and additional packages are both encouraged. The PUNCH-pipe run by the SOC to produce data products is expected to remain largely fixed to provide consistency in the final data product. However, calibration corrections, code improvements are always welcome. 

Additional packages developed by the user community will be reviewed and distributed to the PUNCH-bowl where other users can find them, use them and improve them. When developing code the SOC adhere’s to certain standards (see the Standards & Style Section below) to ensure code is readable, usable, compatible with existing software, and tested for robustness. All contributed code should try and follow similar standards, if this seems daunting do not despair, the SOC is here to help, and will help you develop your code for inclusion.

Documentation contributions - As part of the punch-mission the SOC has developed user guides and development documents to help users navigate data reduction. As with all projects, those that are close to the project (the SOC), and know the intricacies of the code, may not be aware as to what is obvious and what is not to an end user, and may not have expressed themselves effectively. As such, it’s important that the user community helps the SOC develop useful and usable documentation by suggesting improvements to existing documents or helps develop new documents (perhaps in different formats). There are no naive questions or suggestions when it comes to documentation, if it’s not clear to you, it’s not clear to others!

Example contributions - A powerful way that people learn how to use code is by following existing examples. The SOC will provide extensive user examples as part of the development process, but users may use data reduction code and use cases in ways that the SOC cannot envisage. As such, additional examples, suggestions for new examples, or suggestions to clarify existing examples will help the PUNCH user community and are welcomed by the PUNCH team.

# Sharing Ideas & Suggestions

Contributions to the punch-mission can come in many forms, they may be code and other non-code issues (such as suggestions and documentation), pull requests, documentation, etc.

The main method of communication with the SOC and other members of the user community is via the punch-mission GitHub repository/forum: https://github.com/orgs/punch-mission/discussions. Using this discussion board allows others to see your questions and comments, but also for you to see if others have asked or suggested similar questions or comments.

Pull requests can be made via the main punch-mission GitHub code repository: https://github.com/punch-mission. As discussed above, the PUNCH-pipe run by the SOC to produce data products is expected to remain largely fixed to provide consistency in the final data product. However, calibration corrections, code improvements are always welcome. Additional packages developed by the user community will be reviewed and distributed to the PUNCH-bowl where other users can find and review.

As part of the PUNCH software development the SOC will provide: details on how to set up the development virtual environment; resources on how to make a pull requests, and outline our style preferences (see Standards and Style below)

# Standards & Style

PEP (Python Enhancement Proposals) 8 is a Style Guide for Python, and SOC produced code try's to conform to these programming standards. Using PEP 8 helps the software conform to common programming standards as well as avoid mistakes and ensure code readability and internal documentation is sufficient to pass code between programmers working in a multi-developer project. Code and documentation contributors are encouraged to follow the PEP 8 standards, and the PEP 8 style guide for Python is a great place to learn about this: https://www.python.org/dev/peps/pep-0008/.

As the PUNCH data reduction pipeline leverages several sunpy (https://sunpy.org) and astropy (https://www.astropy.org) packages the PUNCH software tools generally follow the sunpy coding standards, with specific deviations only as necessary to accommodate the SOC and data processing requirements. SunPy standards are discussed in the SunPy Developers Guide (https://docs.sunpy.org/en/latest/dev_guide/index.html). 

We encourage contributors to follow and embrace the PEP 8, sunpy, and astropy standards to help produce contributions usable by others, interface seamlessly with existing software, and fit in with the overarching solar and heliospheric python software ecosystem.

If a contribution produces data products we encourage the adoption of industry-standard formats. PUNCH distributes data in industry-standard formats, using established time standards and the World coordinate systems (WCS). Quantitative science data products are delivered in the industry standard FITS format.

As discussed at the top of this document, the punch-mission is mainly developed in python to ensure it’s open source and available to everyone, and this guide is primarily for python developers. Due to the solar and heliospheric software development heritage, other programing languages are used by the user community (e.g. IDL) and the SOC will do their best to incorporate packages produced in other software development languages.


# Code of Conduct

We welcome and encourage contributions to this project in the form of pull requests, submission of issues, and comments on issues.
Contributors are expected
to be respectful and constructive; and
to enforce 1.
This code of conduct applies to all project-related communication that takes place on or at mailing lists, forums, social media, conferences, meetings, and social events.
This code of conduct is adapted from the HAPI-Server project.
