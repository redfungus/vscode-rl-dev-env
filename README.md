# VSCode Reinforcement Learning Dev Container

This repo contains simple .devcontainer configuration files to easily start playing around with [OpenAI Gym](https://gym.openai.com/).
It's been tested using [Docker](https://www.docker.com/) on [WLS2](https://docs.microsoft.com/en-us/windows/wsl/install-win10). 

Run `python examples/open_ai_gym.py` in the dev container to test if everything is setup correctly

### Requirements
* VSCode
* Docker
* VSCode plugins needed for remote development. For more information visit [here](https://code.visualstudio.com/blogs/2020/07/01/containers-wsl).
* Xserver installed on host machine. (e.g [VcXsrv](https://sourceforge.net/projects/vcxsrv/)) This is needed to forward the graphical applications from the Docker container to the host machine. Check out the following tutorials for more information: [[1](https://marinerobotics.gtorg.gatech.edu/running-ros-with-gui-in-docker-using-windows-subsystem-for-linux-2-wsl2/)][[2](https://dev.to/darksmile92/run-gui-app-in-linux-docker-container-on-windows-host-4kde)]

### TODO
* Add GPU support
* Test support on Mac and Ubuntu
* Add simple algorithm implementations
* Fix DeepMind acme dependenies
