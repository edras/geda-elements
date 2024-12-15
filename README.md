# geda-elements
Geda PCB footprints and Symbols

This is my personal repository of geda-pcb geda-gschem footprints and symbols.

These elements needs to be include in a PCB project made on [eda-lepton](https://github.com/lepton-eda/lepton-eda)

include this repository as a git submodule on your pcb project:

```
git submodule add git@github.com:edras/geda-elements.git
```

It will generate a folder structure like thhis:
```
|your-project-folder
|    | - geda-elements
|    |    - gschem-sym   -> symbols
|    |    - pcb-elements -> footprints
```

# Linking this geda-elements folder to your project

Make a copy of the file **gafrc** to the root of your project.
The file gafrc contains the folder address to where to look for geda-symbol elements.

```
your-project-folder > cp geda-elements/gafrc .
``` 

A geda-lepton project creates a file with extension **.gsch2pcb**
The contents of this file is:
- schematics to be used: *schematics file1.sch file2.sch*
- the output file name: *output-name your_project_name*
- the link to look for additional footprints: *elements-dir ./geda-elements/pcb-elements*

As mentioned above, include on this file the last line:
```
elements-dir ./geda-elements/pcb-elements
```

And your project should find the added extra footprints.
ps: change path accordingly...

I used geda-pcd for several years, but for Ubuntu 24.04 it is not 
supported anymore. A workaround is to use pcb-rnd


## cloning the repo and working submodules

Later to clone a repository containing the submodule:

```
git clone --recurse-submodules your_git_repository_url
```

Or if you forgot to type --recurse-submodule during cloning, cd into the repository folder and initialize the submodule:

```
git submodule init
git submodule update
```




