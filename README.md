# UoS-RSE FAIR for Research Software lesson setup

Instructions for setting up a lesson repository for the University of
Sheffield FAIR for Research Software training programme.

These instructions assume that you are familiar with following command
line instructions.  Please contact
[RSE-Sheffield](https://github.com/RSE-Sheffield) if you require any
support with lesson setup.

## Introduction to The Carpentries Workbench

[The Carpentries
Workbench](https://carpentries.github.io/sandpaper-docs/) provides a
standardised lesson format which we are using for the University of
Sheffield FAIR for Research Software training programme.  The lesson
content is written as markdown or RMarkdown and rendered using `R` and
`pandoc`.  Lessons can be developed within the [RStudio
IDE](https://posit.co/download/rstudio-desktop/#download).

### Setting up your lesson development environment

Required software:

- git (>= 2.28 recommended)
- R (>= 3.6)
- pandoc (>= 2.11) (available through the [RStudio
  IDE](https://posit.co/download/rstudio-desktop/#download))

Please refer to [The Carpentries installation instructions]
(https://carpentries.github.io/sandpaper-docs/#required) for setting
up your lesson development environment.

## Create a new lesson repository from the Carpentries Workbench Template

To create a new lesson repository, make sure you're logged into GitHub.

Visit https://github.com/carpentries/workbench-template-md/generate
and follow the instructions to generate a repository from the
[Carpentries Workbench
Template](https://github.com/carpentries/workbench-template-md). Checking
the 'Include all branches' option will save some time waiting for the
first website build when your new repository is initialised.

## Clone the lesson repository

Clone the lesson repository to a suitable location on your local computer:

```
cd my-lesson-directory
git clone git@github.com:path/to/my-repo.git
```

## Download and apply the patch file

Download [fair4rs\_config.patch](https://raw.githubusercontent.com/tdjames1/fair4rs-lesson-setup/main/fair4rs_config.patch).

Apply the patch file to the lesson repository:

```
cd my-repo
git apply path/to/fair4rs_config.patch
```

### Rename `.Rproj` file

Rename `FIXME.Rproj` to match your repo name:
```
git mv FIXME.Rproj my-repo.Rproj
```

## Edit configuration, citation metadata, contributing guide and licence

### `config.yaml`

This file contains global parameters for your lesson site. Individual
fields within the file are documented with comments (beginning with
#). At a minimum, you should adjust all the fields marked 'FIXME':

* title
* keywords
* source
* contact
* url

### `CITATION.cff`

This file contains information about citing this repository. At a
minimum, you should adjust all the fields marked 'FIXME':

* title
* authors (given name, family name, email, affiliation, orcid)
* repository-code
* url
* abstract
* keywords

### `CONTRIBUTING.md`

Update links to GitHub repository and issues, marked 'FIXME'.

### `LICENSE.md`

Review the licence text and add references/attribution to any derived
material as indicated by the `#FIXME` comment.

## Commit changes to configuration, citation metadata, contributing guide and licence

```
git add config.yaml CITATION.cff CONTRIBUTING.md LICENSE.md
git commit -m "Update configuration"
git push
```

## Complete setup

To complete the setup of your lesson, follow the instructions given
in [Configure a new lesson](https://github.com/carpentries/workbench-template-md#configure-a-new-lesson) to:

- Make sure GitHub Pages is activated
- Annotate the repository
- Update your repository's README with relevant information about your lesson.

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
Attribution](https://creativecommons.org/licenses/by/4.0/) licence.
Changes have been made to adapt the instructions for using the
Carpentries Workbench Template in the specific context of the
University of Sheffield's FAIR for Research Software training
programme.
