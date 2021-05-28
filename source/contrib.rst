.. Open Space Research Community of Singapore
   Documentation master file, created by Samuel Y. W. Low
   Using sphinx-quickstart on Tuesday, May 4th
   (May the Fourth be with you...)
   This file should contain the root `toctree` directive.

.. image:: /_static/_headers/openssg_head_contrib.png

.. _contrib-label:

Contributing to Open Space Singapore
====================================

The Open Space Singapore project is purely community-driven research interest group, and as such, this project is open-sourced and thus contributable in all ways imaginable.

Contributing Roles and Responsibilities
---------------------------------------

* **Participants:** Just join and be there for our activities!
* **Presenters:** Share your research in our rolling workshops!
* **Editors:** Write our quarterly newsletters and web content!
* **Administrators:** Organise meaningful activities for the community!

You can join the community simply by subscribing to our mailing list in the home page! However, before you do, the OSSG community urges you to peruse our :ref:`conduct-label`.

Introduction to Contributing Community Web Content
--------------------------------------------------

This section is relevant to community **administrators** and **editors** who wish to understand how to actually get web content up on this website. In a nutshell, the Open Space Singapore community webpage is:

* Hosted on `GitHub Pages <https://pages.github.com/>`_ through the main (or master) branch.
* Built using the `Sphinx <https://www.sphinx-doc.org/en/master/>`_ framework and written in `reStructuredText (ReST) <https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html>`_.

.. link-button:: https://github.com/sammmlow/OPENSPACESG
	:text: OPEN SPACE SINGAPORE COMMUNITY WEBPAGE GITHUB
	:classes: btn-success btn-block

GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere. Here is `a guide for GitHub <https://guides.github.com/activities/hello-world/>`_, if you're unfamiliar with Git and version control.

Sphinx, is a Python-based library that makes it easy to create intelligent and beautiful documentation, with an emphasis on code handling and clean documentation, using the `reStructuredText (ReST) <https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html>`_ syntax. Here is `a quick start guide for Sphinx <https://www.sphinx-doc.org/en/master/usage/quickstart.html>`_, if you're unfamiliar it.

There are two critical consequences of these two decisions.

First, because the community page is on GitHub, anyone (usually administrators or editors) with collaborator rights granted to their GitHub accounts, or anyone else who doesn't but makes a pull request that gets approved by the administration team, can change the contents of our community web page.

Yes. Anyone. Even you.

Second, because the layout and web contents are built using the Sphinx framework, you do not need to know HTML, CSS, or JavaScript in order to build web content in the Open Space Singapore community. You just need to understand a bit of ReST. The ReST language is not a "programming" or "logic" language, but just a syntactical way of representing better and cleaner documentation. HTML knowledge is only needed if you wish to build features of widgets that are a part of the underlying Sphinx template.

Installing Python and Sphinx
----------------------------

To begin working on adding web content, you need to have Python installed. We suggest either using Python through `Anaconda <https://www.anaconda.com/products/individual>`_ which comes with the Spyder IDE, the Conda environment, and a pretty neat package manager, or you can try others like the `PyCharm IDE  <https://www.jetbrains.com/pycharm/>`_ too.

Make sure you have Python installed. If you're using Anaconda, open up your Anaconda Prompt (so you know you're in your Conda environment). Else, if you've Python installed in a separate environment, flip up your terminal and crunch:::

	python --version

You should see something like `Python 3.X.X`. You should be using Python 3, and not 2 (don't be a dinosaur)! Next, you'll need to install Sphinx and an extension called Sphinx Panels, using `pip`, which is basically a Python package installer. So, first, check if you have `pip` by typing in your same terminal:::

	pip --version

You should see your `pip` version pop out like this for Anaconda users:::

	pip 20.2.4 from C:\Users\sammm\anaconda3\lib\site-packages\pip (python 3.8)

Now, run the following command (which should work regardless of whether you're a Linux, Mac or Windows user):::

	pip install -U sphinx

After installation, verify it by typing on your terminal or command prompt:::

	sphinx-build --version

If everything worked fine, you will see the version number for the Sphinx package you just installed. For further help in installing Sphinx, checkout the `Sphinx installation guide <https://www.sphinx-doc.org/en/master/usage/installation.html>`_ here. Next, we need to get Sphinx Panels. Currently, several widgets and buttons on the Open Space Singapore website make use of Sphinx panels. To install it, simply crunch:::

	pip install sphinx-panels

Installing Git and Cloning This Website
---------------------------------------

Next, we're going to share about how the website is built in general. First, we are going to assume you already have git installed, and that you can run git commands in your terminal. If you can't, especially for Windows users, I suggest getting `Git Bash <https://git-scm.com/downloads>`_.

Once you have Git, navigate to the directory that you want (using the `cd` commands), and clone a local copy of the Open Space Singapore community website by running in terminal or Git Bash:::

	git clone https://github.com/sammmlow/OPENSPACESG.git

Now, list the files (`ls` for Linux or in Git Bash, or `dir` for Windows) and you'll see the source code files:::

	docs/
	source/
	LICENSE
	README.md  

.. note::
   Hello world!

If you haven't already, get either GitHub desktop or Git Bash installed too.




|



|



.. toctree::
   :maxdepth: 1

..
	`Link text <link URL>`_


