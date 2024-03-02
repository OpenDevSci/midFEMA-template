https://docs.github.com/en/codespaces/getting-started/quickstart
https://docs.github.com/en/codespaces/getting-started/deep-dive

We recently started using Dev Containers and Codespaces for development on our Jekyll blog here at Earthly. We have a lot of different plugins and dependencies to make things like linting, spell check, and image importing much easier. The problem is, a lot of this was originally set up on an Intel Mac. Now that the team has grown, there are developers using M1s, Linux, and Windows, and so as you can imagine, a lot of our teammates who just want to write a simple blog entry were getting stuck trying to get the blog working locally. Not only did Dev Containers with Codespaces solve this issue for us, it made development in general much easier and more portable

streamlines continuous integration workflows in Codespaces

Dev Containers Vs Codespaces: What’s the Difference?
Dev Containers
You can think of Dev Containers as VS Code running in Docker. They allow you to define a development environment with a Docker or docker-compose.yml file and then run your project in that environment with the click of a button. This can be done locally on your machine, but it can also be done in the cloud using Github Codespaces.

Codespaces
Github Codespaces are containers running in the cloud that you connect to via VS Code. They are often talked about in conjunction with Dev Containers because you use Dev Containers to configure a Codespace. In other words, all Codespaces are Dev Containers running in the cloud.

Working Together
Because VS Code can run in the browser, Dev Containers, along with Github Codespaces, also allow you to develop from almost anywhere. They’re great for standardizing development across a team. They can also make working on several repos at once much easier because each repo can have its own specific environment for development.



## Development Container

This repository includes a Visual Studio Code Dev Containers / GitHub Codespaces development container.

* For [Dev Containers](https://aka.ms/vscode-remote/download/containers), use the **Dev Containers: Clone Repository in Container Volume...** command which creates a Docker volume for better disk I/O on macOS and Windows.
  * If you already have VS Code and Docker installed, you can also click [here](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/microsoft/vscode) to get started. This will cause VS Code to automatically install the Dev Containers extension if needed, clone the source code into a container volume, and spin up a dev container for use.