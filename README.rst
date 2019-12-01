TEI OpenEdition - localized documentation
#########################################################

This repository contains localized documentation for OpenEdition TEI documentation. It
is based on master document placed in phpmyadmin repository.

How to update translations after source update
=========================================================

1. Update main documentation, pot and po

.. code-block:: sh

   # Update the submodule (main documentation repo)
   git submodule update --recursive --remote
   # Followwing commands are executed from 'docs' directory
   cd docs
   # Build html
   # make html
   # Build gettext (create .pot)
   sphinx-build -b gettext en _build/gettext
   # Build po english files
   sphinx-intl update -p _build/gettext -l en_US

2. Edit and update .po files (poedit)

3. Build html with english translation (for local preview)

.. code-block:: sh

   sphinx-build -b html -D language=en_US -v en _build/html

4. git add commit and push to update the remote repo and the readthedocs documentation

