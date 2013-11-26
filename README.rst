.. image:: https://travis-ci.org/OddBloke/sphinx-git.png?branch=master
    :target: https://travis-ci.org/OddBloke/sphinx-git

sphinx-git allows you to include a git changelog of your Sphinx documentation
within the documentation.

To use it, add 'sphinx_git' to 'extensions' in your Sphinx conf.py, and add::

    .. git_changelog::

where you want the list of commits to appear.  This will display 10 commits by
default; if you want a different number then pass in the ``revisions`` option::

    .. git_changelog::
      :revisions: 5

You can also use a range of commits with the ``rev-list`` option (``man
git-rev-parse`` for details on the syntax)::

    .. git_changelog::
        :rev-list: master..mybranch

You cannot currently apply a ``revisions`` filter to the ``rev-list`` output.

In some repositories, detailed messages (i.e. the bodies of commits) will look
better in a preformatted block (e.g. if they include code samples).  You can
enable preformatted blocks using the ``detailed-message-pre`` option::

    .. git_changelog::
        :detailed-message-pre: True

The ``detailed-message-pre`` option can be combined with all other options.