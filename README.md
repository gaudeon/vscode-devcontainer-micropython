# vscode-devcontainer-micropython
Container configuration to develop in micropython in VS Code

# installing packages
For some reason I failed to get the dockerfile to run upip install commands during builds. After a devcontainer exists I could add them in just fine either explicitly or via requirements.txt. 

So for now I recommend you add do something similar. After you build your devcontainer from a folder containing this configuration and are running within; then do something like pip install from requirements.txt for the packages you need in the container. Example:

    > micropython -m upip install -r requirements.txt

# Thanks to...
Mitchell Currie (mitchins) for (docker-micropython-linux)[https://github.com/mitchins/docker-micropython-linux]
