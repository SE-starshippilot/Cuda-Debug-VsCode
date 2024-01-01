# Cuda Debugging for VSCode

Debug CUDA programs inside VS Code. Created to assist my [Operating Systems course at CUHK(SZ)](https://github.com/SE-starshippilot/CSC_3150).

****

## Why did I create this repo?

This repo offers an out-of-the-box experience for debugging CUDA programs inside VsCode. As of Nov 2022, the relevant docs are not very helpful, but after tinkering for some time I finally get it up & running.

## How to use this repo?

### Prerequisites

You need to install the following extensions:

- C/C++
- Nsight Visual Studio Code Edition

Find them in the VS Code Extension Marketplace.

### Steps

1. Download the .vscode folder and (re)place your .vscode folder

   ```bash
   git clone https://github.com/SE-starshippilot/CSC3150-Cuda-Debug.git
   ```

2. The following things need to be configured:

   1. In `.vscode/launch.json`

      - Modify the **debuggerPath** to your *cuda-gdb* path

        - You can check yours by running

          ```shell
          which cuda-gdb
          ```

        - As of the time I write this repo, the VSCode CUDA extension has a bug (see [here](https://github.com/NVIDIA/nsight-vscode-edition/issues/2))

        - TLDR, upgrade to the newest version of cuda-gdb. I did so using anaconda

          ```shell
          conda create -n <your_env_name>
          conda activate <your_env_name>
          conda install -c nvidia cuda-gdb
          which cuda-gdb
          ```

   2. In `.vscode/tasks.json`

      - You can modify the **command** option if you don't want to write makefile.

You're all set! Set some breakpoints and enjoy debugging!



## Issues and PRs

Should you have any questions, please open issues.

Help to keep this repo updated by creating PRs.



## Disclaimer 

This repo only contains configuration files for the VS Code.
