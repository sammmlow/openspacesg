.. Open Space Research Community of Singapore
   Documentation master file, created by Samuel Y. W. Low
   Using sphinx-quickstart on Tuesday, May 4th
   (May the Fourth be with you...)
   This file should contain the root `toctree` directive.

.. image:: /_static/_headers/openssg_head_bulletin_w.png

.. _webwrite-label:

Guide to Adding Content to Our Community Website
================================================

In this tutorial, we are going to teach you how to write your own content on the community bulletin board. The information learnt in this guide can actually be used to edit any part of this website, and not just the bulletin board really; so you can contribute your own community content in general to the community site.

If you have Python and Sphinx installed, and you're familiar with the web build, skip to the actual web content tutorial at :ref:`webwrite-main`. Else, jump to our install guide to get Python, Sphinx and Git setup on your workstation at :ref:`web-install`.

Else, if you're new, jump to our Python and Sphinx install guide at :ref:`install-python`. Additionally, you would need to clone the website repository, you can find this at :ref:`install-git`. Alternatively, clone it manually from the GitHub link below.

.. link-button:: https://github.com/sammmlow/openspacesg
	:text: Link to the Open Space Singapore GitHub Repo
	:classes: btn-info btn-block

.. _webwrite-intro:

Introduction to the Open Space Singapore Website
------------------------------------------------

In a nutshell, the Open Space Singapore community webpage is:

* Hosted on `GitHub Pages <https://pages.github.com/>`_ through the main (or master) branch.
* Built using the `Sphinx <https://www.sphinx-doc.org/en/master/>`_ framework and written in `reStructuredText (ReST) <https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html>`_.

**GitHub** is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere. Here is `a guide for GitHub <https://guides.github.com/activities/hello-world/>`_, if you're unfamiliar with Git and version control.

**Sphinx**, is a Python-based library that makes it easy to create intelligent and beautiful documentation, with an emphasis on code handling and clean documentation, using the `reStructuredText (ReST) <https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html>`_ syntax. Here is `a quick start guide for Sphinx <https://www.sphinx-doc.org/en/master/usage/quickstart.html>`_, if you're unfamiliar it.

There are two critical consequences of these two decisions.

|

.. image:: /_static/_banners/openssg_contrib_git1.png
   :align: center

|

First, because the community page is on GitHub, anyone with collaborator rights granted to their GitHub accounts, or anyone else who doesn't but makes an approved pull request, can change the contents of our community web page.

Yes. Anyone. *Even you*.

Second, because the layout and web contents are built using the Sphinx framework, you don't need to know HTML, CSS, or JavaScript in order to build web content in the Open Space Singapore community. You just need to understand a bit of ReST. The ReST language is not a "programming" or "logic" language, but just a syntactical way of representing better and cleaner documentation. HTML knowledge is only needed if you wish to build features of widgets that are a part of the underlying Sphinx template.

Click this link if you need a `reference for reStructuredText (ReST) syntax <https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html>`_.

Now, here's an example to show you just how easy it is! Let's say you're organising some activities, and you want to put up the schedule publicly on the community web. You also want to add a center-aligned image of `Earth Kid` from the local webpage `/_static/` folder. This is the ReST "source code" for generating an example time table.::

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

In the next steps, we will need Python Sphinx and Git on your workstation. If you haven't yet gotten Python Sphinx and Git to clone the repository, you can follow :ref:`install-python` and :ref:`install-git`.

.. _webwrite-main:

Write Stuff on the Open Space Singapore Website
-----------------------------------------------

|

.. image:: /_static/_banners/openssg_contrib_git2.png
   :align: center

|

**In a nutshell:** There are two folders where website content exists. There is the `source` folder and the `docs` folder. The ReST files (.rst) are found in the `source` folder. The `source` is where you do all your building of web content by editting only the ReST files (.rst), and Sphinx converts the ReST files into readable HTML files locally on the source folder through the `make` commands.

When the build is satisfactory, it goes into the `docs` folder, and you can push it to GitHub after committing your local changes. GitHub Pages looks only for the `docs` folder (so don't rename it) and builds the public web content automatically through the GitHub repository. That's it!

Now, let us re-write all of the above information, but in very specific steps this time.

1. If you do not have the Open Space Singapore web page on your computer, start by cloning the GitHub repository using your GitHub Desktop, or the clone command below using Git Bash:::

	git clone https://github.com/sammmlow/openspacesg.git

2. Else, if you do have it, you should do a pull from the origin in order to keep your local repository up to date before adding any new content:::

	git pull origin main

3. There would be two main folders in the root OSPACESG directory. First, `docs` is where your final web content is positioned and is the folder which the Open Space Singapore GitHub Page will interface with. Second, `source` is where you do all your webt content editting, and it serves as a staging area for you to add your content before you publish it locally to `docs`, and then to GitHub. Now, let's enter the source folder to edit the ReST files:::

	cd <repo_directory>/OSPACESG/source

4. Check the contents by listing files (`ls` for Linux, or `dir` for Windows)::

	_build/
	_templates/
	_static/
	example_file_01.rst
	example_file_02.rst
	example_file_03.rst
	Makefile
	make.bat
	conf.py

5. Fire up your text editor, add content to and save the RST files of your choice.

6. To build the website in the local source folder, in your command prompt (or in your Anaconda Prompt if you are an Anaconda user) run this in the `source` folder:::

	make html

7. You can now observe fresh changes to your web content **locally only** at `index.html` by going to:::

	cd <repo_directory>/OSPACESG/source/_build/html

8. GitHub Pages recognises the name `index.html` as the primary home page, but only in the `docs` directory and not `source`. What you had done in Step 6 was to build the website locally in the `source` folder, and therefore even if this was pushed to GitHub, the changes would not be reflected in the public web page. Thus, once you are ready to finalise your web content, in your command prompt (or in your Anaconda Prompt if you are an Anaconda user), run this batch file in the `source` folder:::

	make github

9. What `make github` does is: it copies over your final build into the `docs` folder, so that GitHub Pages can view it **once you push your local repository upstream to the origin**. The ReST files will not be copied over, only the final HTML builds. Fire up `index.html` in the directory:::

	cd <repo_directory>/OSPACESG/docs

10. Once again, check that your changes to the web content is satisfactory, and you can push all your changes to GitHub online using the following Git commands. First, you need to add all your changes in the local build (remember to do this only after running *make github*):::

	git add --all

11. Next, you would need to commit these added changes to the **local build** on your own machine. Make sure you add a commit message that describes the changes you made:::

	git commit -m '<commit_message>'

12. Finally, assuming there are no merge conflicts, you can push your committed local changes to the online GitHub repository, and GitHub pages will automatically re-build the website with your added contents in a matter of minutes. Use the following commands to push your changes online:::

	git push -u origin main

13. Note that if the local build of your OPENSPACESG repository is pretty old, chances are, some of the other admins would have made some changes to the web contents already. This would cause a merge conflict when you attempt to push your changes to the online GitHub repository. In this case, you can either do a fresh re-clone, or you can do a pull-and-merge, or a rebase. A tutorial on how to do this can be found `here <https://www.atlassian.com/git/tutorials/syncing/git-pull>`_.

14. Do note that you will need collaborator privileges (which are given to administrators and editors) in order to directly push to the upstream repository. Otherwise, request for admin rights and make a case for it to the admin team, or, make a separate branch for your edits, and then make a pull request and the admins will review your changes.



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

**Web Templating**: If you are familiar with HTML, CSS or JavaScript, the underlying web template is built in the **OSPACESG/source/_templates** directory, in a file called `layout.html`. In this file, you can toy around with the web layout like links, relation bars, side bars, columns, titles and headers et cetera. We will not go into details on that here.

**Sphinx Templating**: For other customisable features on Sphinx, explore the `conf.py` file in `source` A full guide can be found on the Sphinx documentation online if you are interested in this.

.. toctree::
   :maxdepth: 1
   
   webstart.rst

