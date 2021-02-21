# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.154.0/containers/python-3/.devcontainer/base.Dockerfile

# Set Docker arguments
ARG VARIANT
ARG GPU_SUPPORT
ARG WSL_GYM_SUPPORT

# [Choice] Python version: 3, 3.9, 3.8, 3.7, 3.6
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

# Global git ignore (temp files & OS X shit)
RUN echo '*~' >> ~/.gitignore_global && echo .DS_Store >> ~/.gitignore_global && git config --global core.excludesfile ~/.gitignore_global

# Upgrade pip and setuptools
RUN pip install --upgrade pip setuptools

# [Optional] If your pip requirements rarely change, uncomment this section to add them to the image.
COPY requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
   && rm -rf /tmp/pip-tmp

# Install pycodestyle
RUN pip3 --disable-pip-version-check --no-cache-dir install pycodestyle

# [Optional] Uncomment this section to install additional OS packages.
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - \
&& apt-get update -y \
&& apt-get -y install --no-install-recommends x11-apps python-opengl libgl1-mesa-glx libosmesa6

# Set X11 server endpoint.
ENV DISPLAY=host.docker.internal:0.0
ENV LIBGL_ALWAYS_INDIRECT=1

# Install GPU support if GPU_SUPPORT is set to true.

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1