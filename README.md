# Quantum Toolbox in Julia (QuTiJ) Lecture

This repository contains lecture materials for the package [`QuantumToolbox.jl`](https://github.com/qutip/QuantumToolbox.jl).

All materials are stored in the folder `tutorials/`:

0. [Introduction to Julia](./tutorials/0_introduction_to_julia.ipynb)
1. [Introduction to Quantum Toolbox in Julia (QuantumToolbox.jl)](./tutorials/1_introduction_to_qutij.ipynb)
2. [Larmor Precession](./tutorials/2_Larmor_precession.ipynb)
3. [Vacuum Rabi Oscillation](./tutorials/3_vacuum_Rabi_oscillation.ipynb)

## Run on GitHub Codespace

Click the button below to open the tutorials in a new GitHub Codespace:

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?devcontainer_path=.devcontainer%2Fdevcontainer.json&hide_repo_select=true&ref=main&repo=1350404104&skip_quickstart=true&machine=standardLinux32gb&geo=SoutheastAsia)

A machine type with at least 4 cores is highly recommended. This will consume more of your quota than a 2-core machine; see [Free quota](https://docs.github.com/en/billing/concepts/product-billing/github-codespaces#free-quota) and [Pricing](https://docs.github.com/en/billing/concepts/product-billing/github-codespaces#pricing) for more info.

## Run locally

While GitHub Codespaces are great for learning/experimenting, we advise to set up a local environment on your computer for more in-depth work and better performance.

If you are an advanced user, feel free to clone and setup your environment via the provided project files.

In order to ease the installation of all the dependencies, however, we also provide a *local* VS Code experience similar to GitHub Codespaces, via devcontainers.

The steps are generally as follows.
1. Install VS Code (MacOS users are advised to use [Homebrew](https://formulae.brew.sh/cask/visual-studio-code)).
2. Install Docker and the Dev Containers Extension according to the [documentation](https://code.visualstudio.com/docs/devcontainers/containers#_installation) (on Windows, see notes below).
3. Click on the following button to clone the repo on your computer: [![Clone in VS Code](https://img.shields.io/badge/Clone_in-VS_Code-blue?logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://vscode.git/clone?url=https://github.com/ytdHuang/QuTiJ-Lecture.git)  
4. Once you've chosen a destination folder and you've opened the cloned repo, VS Code will prompt you to ***Reopen in Container***; click that button and you're all set.

## Acknowledgement

Special thanks to [@matteosecli](https://github.com/matteosecli) for the technical support.
