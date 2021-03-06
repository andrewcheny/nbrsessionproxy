# nbrsessionproxy

**nbrsessionproxy** provides Jupyter server and notebook extensions to proxy RStudio.

![Screenshot](screenshot.png)

If you have a JupyterHub deployment, nbrsessionproxy can take advantage of JupyterHub's existing authenticator and spawner to launch RStudio in users' Jupyter environments. You can also run this from within Jupyter.
Note that [RStudio Server Pro](https://www.rstudio.com/products/rstudio-server-pro/architecture) has more featureful authentication and spawning than the standard version, in the event that you do not want to use Jupyter's.

## Installation

### Pre-reqs

#### Install rstudio
Use conda `conda install rstudio` or [download](https://www.rstudio.com/products/rstudio/download-server/) the corresponding package for your platform 

Note that rstudio server is needed to work with this extension.

### Install nbrsessionproxy 
Install the library:
```
pip install nbrsessionproxy
```
or
```
conda install -c conda-forge nbrsessionproxy
```

If installing via pip, you need to enable the extension.

```
jupyter serverextension enable  --py --sys-prefix nbrsessionproxy
jupyter nbextension     install --py --sys-prefix nbrsessionproxy
jupyter nbextension     enable  --py --sys-prefix nbrsessionproxy
```

For JupyterLab first clone this repository to a known location and
install from the directory.
```
git clone https://github.com/jupyterhub/nbrsessionproxy /opt/nbrsessionproxy
pip install -e /opt/nbrsessionproxy
jupyter serverextension enable --py nbrsessionproxy
jupyter labextension link /opt/nbrsessionproxy/jupyterlab-rsessionproxy
```

The Dockerfile contains an example installation on top of [jupyter/r-notebook](https://github.com/jupyter/docker-stacks/tree/master/r-notebook).
