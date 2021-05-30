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

You can join the community simply by subscribing to our mailing list in the home page! However, before you do, the OSSG community urges you to peruse our :ref:`conduct-label`. Next, for the rest of this tutorial, we are going to teach you how to contribute your own community content.

Introduction to Contributing Community Web Content
--------------------------------------------------

This section is relevant to community **administrators** and **editors** who wish to understand how to actually get web content up on this website. In a nutshell, the Open Space Singapore community webpage is:

* Hosted on `GitHub Pages <https://pages.github.com/>`_ through the main (or master) branch.
* Built using the `Sphinx <https://www.sphinx-doc.org/en/master/>`_ framework and written in `reStructuredText (ReST) <https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html>`_.

**GitHub** is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere. Here is `a guide for GitHub <https://guides.github.com/activities/hello-world/>`_, if you're unfamiliar with Git and version control.

**Sphinx**, is a Python-based library that makes it easy to create intelligent and beautiful documentation, with an emphasis on code handling and clean documentation, using the `reStructuredText (ReST) <https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html>`_ syntax. Here is `a quick start guide for Sphinx <https://www.sphinx-doc.org/en/master/usage/quickstart.html>`_, if you're unfamiliar it.

There are two critical consequences of these two decisions.

|

.. image:: /_static/_banners/openssg_contrib_git1.png
   :align: center

|

First, because the community page is on GitHub, anyone (usually administrators or editors) with collaborator rights granted to their GitHub accounts, or anyone else who doesn't but makes an approved pull request, can change the contents of our community web page.

Yes. Anyone. *Even you*.

Second, because the layout and web contents are built using the Sphinx framework, you don't need to know HTML, CSS, or JavaScript in order to build web content in the Open Space Singapore community. You just need to understand a bit of ReST. The ReST language is not a "programming" or "logic" language, but just a syntactical way of representing better and cleaner documentation. HTML knowledge is only needed if you wish to build features of widgets that are a part of the underlying Sphinx template.

Here's an example to show you just how easy it is! Let's say you're organising some activities, and you want to put up the schedule publicly on the community web. You also want to add a center-aligned image of `Earth Kid` from the local webpage `/_static/` folder. This is the ReST "source code" for generating an example time table.::

	.. image:: /_static/_icons/openssg_favicon.png
	   :align: center
	
	.. table:: 
	   :widths: auto
	   
	   =====  ============================
	   Time   Activity
	   =====  ============================
	   01:00  Building a Flux Capacitor
	   02:00  Studying In-Situ Cold Fusion
	   =====  ============================


... and here is the actual output of that ReST text:

|

.. image:: /_static/_icons/openssg_favicon.png
   :align: center

.. table:: 
   :widths: auto
   
   =====  ============================
   Time   Activity
   =====  ============================
   01:00  Building a Flux Capacitor
   02:00  Studying In-Situ Cold Fusion
   =====  ============================

|

See how easy it is? The ReST framework allows anyone, even students or professionals from non-technical backgrounds, to contribute (moderated) community content.

In the next steps, we will guide you through the installation of Python Sphinx and getting Git on your workstation if you don't have it already. Then, you'll have to clone the repository. If you already have or know how to do both, skip to the actual web content tutorial here.

.. link-button:: https://github.com/sammmlow/OSPACESG
	:text: LINK TO THE OPEN SPACE SINGAPORE WEBPAGE GITHUB
	:classes: btn-success btn-block

.. _contrib-python:

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

.. _contrib-git:

Installing Git and Cloning
--------------------------

Next, we're going to share about how the website is built in general. First, we are going to assume you already have git installed, and that you can run git commands in your terminal. If you can't, especially for Windows users, I suggest getting `Git Bash <https://git-scm.com/downloads>`_.

Once you have Git, navigate to the directory that you want (for example, your `Desktop` using the `cd` commands), and clone a local copy of the Open Space Singapore community website by running in terminal or Git Bash:::

	git clone https://github.com/sammmlow/OSPACESG.git

Now, enter the `OPENSPACESG` folder you just cloned, and list the files (`ls` for Linux or in Git Bash, or `dir` for Windows) and you'll see the source code files:::

	docs/
	source/
	LICENSE
	README.md

If you see them, then congratulations, you've successfully got a local copy of the web on your work station! Now, let's look at how we can add web content.

Adding Your Own Web Content
---------------------------

|

.. image:: /_static/_banners/openssg_contrib_git2.png
   :align: center

|

**In a nutshell:** There are two folders where website content exists. There is the `source` folder and the `docs` folder. The ReST files (.rst) are found in the `source` folder. The `source` is where you do all your building of web content by editting only the ReST files (.rst), and Sphinx converts the ReST files into readable HTML files locally on the source folder through the `make` commands.

When the build is satisfactory, it goes into the `docs` folder, and you can push it to GitHub after committing your local changes. GitHub Pages looks only for the `docs` folder (so don't rename it) and builds the public web content automatically through the GitHub repository. That's it!

Here's the GitHub repository link again.

.. link-button:: https://github.com/sammmlow/OSPACESG
	:text: LINK TO THE OPEN SPACE SINGAPORE WEBPAGE GITHUB
	:classes: btn-success btn-block

Now, let's re-write all of that, but in very specific steps this time.

1. Clone the GitHub repository:::

	git clone https://github.com/sammmlow/OSPACESG.git

2. Enter the source folder to edit the ReST files:::

	cd <repo_directory>/OSPACESG/source

3. Check the contents by listing files (`ls` for Linux, or `dir` for Windows)::

	_build/
	_templates/
	_static/
	about.rst
	conduct.rst
	contrib.rst
	events.rst
	index.rst
	repo.rst
	Makefile
	make.bat
	conf.py

4. Fire up your text editor, add content to the ReST files; save your work.

5. Once you've done with your edits, run this in the `source` folder:::

	make html

6. You can now observe fresh changes to your web content **locally** at `index.html` by going to:

	cd <repo_directory>/OSPACESG/source/_build/html

7. GitHub Pages recognises the name `index.html` as the primary home page. However, it recognises this only in the `docs` directory. Thus, once you are ready to finalise your web content, run this batch file in the `source` folder:::

	make github

8. What this does is it copies over your final build into the `docs` folder, so that GitHub Pages can view it. The ReST files will not be copied over, only the final HTML builds. Fire up `index.html` in the directory:::

	cd <repo_directory>/OSPACESG/docs

9. Once again, check that your changes to the web content is satisfactory, and you can push it to GitHub.

10. Do note that you will need collaborator privileges (which are given to administrators and editors) in order to directly push to the upstream repository. Otherwise, request for admin rights and make a case for it to the admin team, or, make a separate branch for your edits, and then make a pull request and the admins will review your changes.

Finally, once again, click this link if you need a `reference for reStructuredText (ReST) <https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html>`_.

.. note::
   As a general rule of thumb, if you are not confident in web development frameworks, you should change only text contents within the RST files, or add images if you have to! It's as easy as writing plain text files.

.. note::
   Do not change the naming of files within the repository!

.. note::
   Do not delete the `.nojekyll` file in the `docs` folder, as the file tells GitHub Pages not to build the site automatically through the Jekyll framework, which was what GitHub Pages was originally meant for. The `.nojekyll` file overrides the default build options for GitHub Pages so that we can build it through the Sphinx framework in ReST instead!

.. note::
   Do not delete or rename the CNAME file in the `docs` directory as the file is needed to point to the correct DNS of the website. Doing that will take our entire community website offline!

Other Customisable Contents
---------------------------

In this section, we'll briefly touch on some of the more customisable features that you can play around with.

**Web Templating**: If you are familiar with HTML, CSS or JavaScript, the underlying web template is built in the **OSPACESG/source/_templates** directory, in a file called `layout.html`. In this file, you can toy around with the web layout like links, relation bars, side bars, columns, titles and headers et cetera. We will not go into details on that here.

**Sphinx Templating**: If you'd like to experiment with some of the other features on Sphinx, do this in the `conf.py` file in `source`.

.. toctree::
   :maxdepth: 1


