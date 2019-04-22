# Simple Anaconda / Python Developer Environment

I needed an Anaconda environment for a training class, but did not want to install the tools locally. After not finding a simply, complete and working Docker example I put this project together. I am sure it is missing some things and I will be updating stuff for as long as my training goes or based on how much I use Python. Hopefully this will help others starting out that just want a simple, run-it-and-forget-it example to hit the floor running. 

**Note:** This application has not been hardened or vulnerability tested and is not intended for production use.

## Basic Notes 
- This uses continuumio/anaconda3 which I assume is latest. If things break for you then it might be that anaconda was updated. I was using Anaconda 2019.03 when I created this project. 
- jupyter_notebook_config.json and requirements.txt are used in the gitignore to avoid them being uploaded for my projects. Simply rename the existing files in /srv/anaconda/conf to remove _EXAMPLE and the project should function as a basic level.
- Password for Notebook is "password" if you use the examples included. If you want to change this:
  - Blank out local file /srv/anaconda/conf/jupyter_notebook_config.json
  - Compose Up and visit http://localhost
  - Shell into Container and run "/opt/conda/bin/jupyter notebook list"
  - This will output a URL with the login Token.
  - Use this Token to set a password and login.
  - In your Container Shell, cp /root/.jupyter/jupyter_notebook_config.json /opt/notebooks/jupyter_notebook_config.json
  - This will place the config file in the notebooks folder in your local project.
  - Move this file to overwrite the local file /srv/anaconda/conf/jupyter_notebook_config.json
  - Compose Down and Compose Up and Notebooks should use your new password.
- /srv/anaconda/conf/requirements.txt should list out any required packaged you need for PIP to install.


### Folder Structure

**/srv**
- Custom configs for Anaconda
- Contains Dockerfile for Anaconda build.

**/notebooks**
- Source Files for Notebooks

