# repo-mainfest

## Install 

```
$ git clone https://gerrit.googlesource.com/git-repo
$ PATH="${HOME}/git-repo/:${PATH}"
$ chmod a+rx ~/git-repo/repo
```
For repo to persist in your path you should add the second line to your .bash_profile or .bashrc file prior to the `export PATH` statement. 

## Initialise

Navigate to your existing MATLAB project directory, or create a new project using:
```
$ mkdir new_project
$ cd new_project
```
This manifest file specifies which repositories to pull in to the project. We need to initialise it in the following way:
```
~/new project $ repo init -u https://github.com/leonidlambroglou/repo-mainfest.git -b main
```
The -u flag allows you to specify the URL of the location of the manifest file. 
The -b flag incidates the branch is main. 
The default name for a manifest file is default.xml 

This will create a `.repo` directory within `new_project` with the relevant data as specified by the manifest file.  

Finally, to download the code as specified by the manifest, run: 
```
~/new project $ repo sync
```
This will create a directory called `lib` within `new_project` containing the code for the specified packages. 
