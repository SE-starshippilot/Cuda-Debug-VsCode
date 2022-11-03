# CSC3150-Cuda-Debug

Debug CUDA programs inside VS Code

****

## Why did I create this repo?

Because configuring VS code for CUDA debug is such a 菊中之痛. The relevant docs are not very helpful (as of Nov 3, 2022), but after tinkering for some time I finally get it up & running.

## How to use this repo?

### Prerequisites

You need to install the following extensions

- C/C++
- Nsight Visual Studio Code Edition

Find them in the VS Code Extension Marketplace

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

Should you have any questions please open issues.

Help to keep this repo updated by creating PRs.



## Disclaimer 

This repo only contains config files for VS Code. No code of the actual assignment code will be uploaded before DDL of assignment.
