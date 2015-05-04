# Project Overview #

The neo-web2py2eclipse project is primarily a Python script called "create\_eclipse\_project" that you can add to your path. It is used to automatically create an Eclipse project by executing the script from the target Web2py applications directory. In addition to transforming the target application into an Eclipse IDE project the script also adds some files to the .hgignore file.

The project also contains an external Eclipse tool to start the generation of Epydoc documentation.

# Requirements #

Requirements: The target platform should have the following items installed and configured before running the script: Python 2.5 or more (not Python 3), Apache Maven and Java, the JVM, because Maven runs on Java.

The web sites also gives information about how to configure an Eclipse environment with different plug-ins to work with Python, Web2py, Eclipse, GoogleCode and the Mercurial versionning system. More specifically, these are the Eclipse IDE, the Eclipse Mylyn Plug-in, the Google Code Mylyn Connector Plugin, the Mercurial Eclipse Plugin, Mercurial itself and the Pydev plugin. Pryor to installing Eclipse and the related plugins you will also need to install and properly configure the Mercurial versioning system and Apache Maven and the Java Development Kit (JDK).
Time

**IMPORTANT:** Before you can use the script. You need to install Maven and Java if they are not already installed. Since this is about web2py development, we suppose Python and Web2py are already installed. This may of course take some time so avoiding using the script if you don't create a lot of web2py applications and do things manually instead may be a better idea. Personally, I believe this script is very pleasant to use and it also saves time.
Limitations

In the previous versions of the script, the script was creating Eclipse projects with two Pydev external libraries (web2py, web2py/site-packages) and other internal source folders (models, modules, controllers). But to the point of view of web2py, these last tree folders are not in the Python path. For example, you cannot import a model module in a controller module. So I removed them in a later version. But, if there not listed as source folders for Pydev, Pydev won't use Pylint to scan them and we will not see our TODOs. So I added them back. So there is a the trade off here but I choose to add all Python folders so Pylint will scan all of them. But with this configuration Pydev may suggest imports that do not make sense. Be aware.
Instructions

Usage Example

Once Everything is installed and configured you can turn your target application into a nicely configured Eclipse project ready to be imported. Note: The request for "Name of Pydev Python interpreter to use" refers to what you called your target Python version when configuring the interpreter for Pydev in Eclipse. By default this can be called "python" on some systems. If you have more than one version of python running you may want to use the same naming scheme such as the one shown below to help you easily choose between versions for each project.

```
cjs@flow:~/Desktop/web2py/applications$ cd uc_voa_theme
cjs@flow:~/Desktop/web2py/applications/uc_voa_theme$ create_eclipse_project
Name of Pydev Python interpreter to use (empty string to cancel)? python2.6
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------------
[INFO] Building uc_voa_theme
[INFO]    task-segment: [eclipse:eclipse]
[INFO] ------------------------------------------------------------------------
[INFO] Preparing eclipse:eclipse
[INFO] No goals needed for project - skipping
[INFO] [eclipse:eclipse {execution: default-cli}]
[INFO] Using Eclipse Workspace: null
[INFO] Adding default classpath container: org.eclipse.jdt.launching.JRE_CONTAINER
[INFO] Not writing settings - defaults suffice
[INFO] Wrote Eclipse project for "uc_voa_theme" to /home/cjs/Desktop/web2py/applications/uc_voa_theme.
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESSFUL
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 1 second
[INFO] Finished at: Thu Aug 19 11:33:14 EDT 2010
[INFO] Final Memory: 16M/168M
[INFO] ------------------------------------------------------------------------
```
Now you can import the project into Eclipse and "everything" should be working.

Happy Development

# Project home page:

[neo-web2py2eclipse](https://github.com/Pierre-Thibault/neo-web2py2eclipse/)
