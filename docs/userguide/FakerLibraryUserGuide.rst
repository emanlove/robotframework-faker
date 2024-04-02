====================================
FakerLibrary Practical User Guide
====================================

.. contents:: Table of contents
    :depth: 3

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
About this Practical User Guide
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: About.rst
.. include:: Feedback.rst

~~~~~~
Topics
~~~~~~

.. contents::
    :depth: 1
    :local:

Using two different locale within the same test
-----------------------------------------------
If your test needs include using two (or more) different "languages" or locales within the
same test case you can do this by importing the library multiple times. Each instance
setting the locale on import to a required language and, this is key, rename that instance
the library. This is done using the ``<import library> AS <another name>`` syntax `as
described <https://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html#setting-custom-name-to-library>`_
in the Robot Framework User Guide.

.. sourcecode:: robotframework

    *** Settings ***
    Library    FakerLibrary    locale=ar_AA  AS   Arabic
    Library    FakerLibrary    locale=fr_FR  AS   French


    *** Test Cases ***
    FakerLibrary Name (Person) Generation
        ${a_name}=    Arabic.Name
        ${f_name}=    French.Name
        Log To Console   \nArabic name: ${a_name}
        Log To Console   \nFrench name: ${f_name}

Then within your test case use the renamed library prefix to the keywords.