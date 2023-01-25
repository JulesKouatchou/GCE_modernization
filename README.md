# GCE Code Modernization

## 2023 Goals

### Initial Tasks
- Create a private Gitlab repository at mysmce and transfer the source code there
- Modernize the Makefile files to streamline the compilation process.
- Write a Python tool that will automatically get the code (from the Git repository), compile it, run it and compare the outputs against a baseline.

### Implmentation Steps

* Create a Gitlab repository
* Reorganize the compilation proccess so that commands such as `make all`, `make debug` and `make clean` can be issued without copying Makefile files.
* Write a envionment variable setting script that can be used to load all the necessary modules needed at both compilation and run time
* Refactor the script that creates the experiment directory. May need to be driven by a YAML-like file.
* Reorganize the experiment directory so that the input files and the output files have their own subdirectories
* Create a Python regression testing tool to automatically obtain, compile, and run the code. The tool will have the ability to compare outputs from different verstions of the code. The tool will electronically send a report to the user.

## Long-Term Goals
We want to avoid editing source code files before compiling the code.

- Modify the code so that the problem size is determined at run time. The main arrays will be dynamically allocated.
- Modify the code so that the total number of processors to use is set at run time. There will be an option to set (at run time) the number of processors in the x-direction and y-direction. This decomposition can also be do internally by the code.
- Modify the compilation process to include directives (such as `-DMPE`) to facilate pre-processing. We may need to create a `configure` file to select the necessary options.
