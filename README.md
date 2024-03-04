# UoS-RSE FAIR for Research Software lesson setup

Instructions for setting up a lesson repository for the University of
Sheffield FAIR for Research Software training programme.

## Create a new lesson repository from the Carpentries Workbench Template

To create a new lesson repository, make sure you're logged into Github.

Visit https://github.com/carpentries/workbench-template-md/generate
and follow the instructions to generate a repository from the
[Carpentries Workbench
Template](https://github.com/carpentries/workbench-template-md). Checking
the 'Include all branches' option will save some time waiting for the
first website build when your new repository is initialised.

## Clone the lesson repository

```
git clone git@github.com:path/to/my-repo.git
```

## Download and apply the patch file

Download
[fair4rs\_config.patch](https://raw.githubusercontent.com/tdjames1/fair4rs-lesson-setup/main/fair4rs_config.patch?token=GHSAT0AAAAAACKHZVPAZGMVZTGGAUHQOBPSZO4YZ5A).

Apply the patch file:

```
cd my-repo
git apply path/to/fair4rs_config.patch
```

## Edit configuration and citation metadata

### config.yaml

This file contains global parameters for your lesson site. Individual
fields within the file are documented with comments (beginning with
#). At a minimum, you should adjust all the fields marked 'FIXME':

* title
* keywords
* source
* contact
* url

### CITATION.cff

This file contains information about citing this repository. At a
minimum, you should adjust all the fields marked 'FIXME':

* title
* authors (given name, family name, email, affiliation, orcid)
* repository-code
* url
* abstract
* keywords

## Commit configuration and citation

```
git add config.yaml CITATION.cff
git commit -m "Update configuration"
git push
```

## Complete setup

To complete setup of your lesson, follow the instructions given
in [Configure a new lesson](https://github.com/carpentries/workbench-template-md#configure-a-new-lesson).

## Lesson development

Please refer to the [Introduction to The Carpentries
Workbench](https://carpentries.github.io/sandpaper-docs/) for further
documentation.

## Licence

[Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/)

This work is derived from material in the [Carpentries Workbench
Template](https://github.com/carpentries/workbench-template-md), which
is Copyright (c) [The Carpentries](https://carpentries.org/) and is
made available under the [Creative Commons
Attribution](https://creativecommons.org/licenses/by/4.0/) license.
Changes have been made to adapt the instructions for using the
Carpentries Workbench Template in the specific context of the
University of Sheffield's FAIR for Research Software training
programme.
