Creating FakerLibrary releases
=================================

These instructions will cover steps needed to create new releases of FakerLibrary.
For now there are here to remind me (Ed Manlove) how to properly regenerate the
keyword documentation.

Update Keyword Documentation
----------------------------
To list out the Keyword Names (and verify that indeed I have the right library path)
try,::

  libdoc robotframework-faker/FakerLibrary list

To create the actual documentation try::

    libdoc robotframework-faker/FakerLibrary docs/FakerLibrary-${VERSION}.html