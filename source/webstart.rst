.. Open Space Research Community of Singapore
   Documentation master file, created by Samuel Y. W. Low
   Using sphinx-quickstart on Tuesday, May 4th
   (May the Fourth be with you...)
   This file should contain the root `toctree` directive.

.. image:: /_static/_headers/openssg_head_bulletin_w.png

.. _web-install:

Getting Started with Adding Web Content
=======================================

If you would like to manually add your own web content to the Open Space Singapore website, you would need to have Python and the Python Sphinx module installed. You would also need to be able to run Git commands on your work station. This site will run through :ref:`install-python` and :ref:`install-git` if you are new to this.

.. _install-python:

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

.. _install-git:

Cloning the GitHub Website
--------------------------

In this section, we're going to clone the website itself. We are going to assume you already have git installed, and that you can run git commands in your terminal. If you can't, especially for Windows users, I suggest getting `Git Bash <https://git-scm.com/downloads>`_. Alternatively you could also use `GitHub Desktop <https://desktop.github.com/>`_, if you prefer less typing in the terminal.

Once you have Git, navigate to the directory that you want (for example, your `Desktop` using the `cd` commands), and clone a local copy of the Open Space Singapore community website by running in terminal or Git Bash:::

	git clone https://github.com/sammmlow/openspacesg.git

Now, enter the `OSPACESG` folder you just cloned, and list the files (`ls` for Linux or in Git Bash, or `dir` for Windows) and you'll see the source code files:::

	docs/
	source/
	LICENSE
	README.md

If you see them, then congratulations, you've successfully got a local copy of the web on your work station! Now, let's return to the :ref:`webwrite-label` look at how we can add web content.
