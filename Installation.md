

## Required Files ##

The Maude Formal Environment can be used both on the official distribution of [Maude](http://maude.cs.uiuc.edu/) (Maude 2.6.1) or on the Maude++ extended version available from this site. The termination tool and sufficient completion tool require internal hooks not available in the official distribution, and therefore these tools will not be available inside the MFE if the official version of Maude is used. The rest of the tools will work normally on both versions of Maude.

The following files, available from the _Downloads_ section, are required to install the MFE:

  * `mfe.zip`
  * `maude++.tar.gz` (only if the MTT and SCC tools are to be used)

The Maude Termination Tool requires the installation of external backend termination tools that follow the rules of the termination competition (the AProVE tool, in its 1.2 pre-release version is available in the Downloads section.

## Installation ##

Uncompress the required files to the directories of choice.

## Termination Back-ends ##

Automatic termination checks by the MTT will require back-end tools, like `CiME`, `AProVE`, `MuTerm`, etc. If there are not back-end tools configured properly, then a advisory message will be displayed by the MFE whenever a check of termination is requested. In principle, any tool that adheres to the [specification for participants into the annual termination competition](http://termcomp.uibk.ac.at/2011/rules.html).

The interaction with the different termination tools is carried out following ideas already in the `MTT` (see [more details](http://www.lcc.uma.es/%7Eduran/MTT/)).

### Configuration of Back-end Tools ###

The information of the available back-end tools is read from the file

`mfe.config`

The MFE searches for this file in maude++'s executable directory and then in the directory referenced by the shell variable `MAUDE_LIB`. Such a configuration file must contain one text line per tool, and with the following syntax:

```
< name with which you will refer to the tool inside MFE > < path of the batch of the tool > < extension of the files to load >
```

For instance, the `mfe.config' file could look like this:
```
aprove /usr/local/share/runme .trs
ttc /usr/local/share/runmepar
```

The third parameter in each text line is optional. See the `mfe.config` file included in `maude++.tar.gz` for more details.

### Some Back-end Tools ###

Termination tools should provide a script which gets as only arguments the name of the TRS-file and the timeout in seconds.

  * `AProVE` is a termination tool with webpage at [http://aprove.informatik.rwth-aachen.de](http://aprove.informatik.rwth-aachen.de). The MFE uses the 2006 Termination Competition version of `AProVE`, available in the Downloads section. The zip file in the Downloads section includes both the java jar file of AProVE and an script to execute it. Make sure you edit it and provide the right location of the jar file.