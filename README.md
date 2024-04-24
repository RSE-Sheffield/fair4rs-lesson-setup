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
content is written as markdown or [R
Markdown](https://rmarkdown.rstudio.com/) and rendered using [`R`][r]
and [`pandoc`][pandoc].  Lessons can be developed within the
[RStudio IDE][rstudio]) or any other IDE (e.g. [Emacs][emacs]).

We use a [custom fork](https://github.com/RSE-Sheffield/uos-varnish)
of [{varnish}][varnish] from [The Carpentries Workbench][wb] to
apply University of Sheffield branding to the lesson theme and to add
relevant links to training resources to the page footer.

### Setting up your lesson development environment

Required software:

- [git][git] (>= 2.28 recommended)
- [R][r] (>= 3.6)
- [pandoc][pandoc] (>= 2.11) (available through the [RStudio IDE][rstudio])

Please refer to [The Carpentries Workbench installation
instructions](https://carpentries.github.io/sandpaper-docs/#required)
for setting up your lesson development environment.

If you choose to use R Markdown in your lesson then you will need the
[{rmarkdown}][rmarkdown] package, which should be installed as a
dependency of the [{sandpaper}][sandpaper] package by following the
instructions above.

### Applying custom {varnish} locally

To enable the custom theme to be applied when rendering the site
locally, please refer to the following [instructions for installing
`uos-varnish`](https://github.com/RSE-Sheffield/uos-varnish?tab=readme-ov-file#applying-varnish-locally).

## Create a new lesson repository from the Carpentries Workbench Template

To create a new lesson repository, make sure you're logged into GitHub.

The Carpentries Workbench Template is available as a [markdown lesson
template](https://github.com/carpentries/workbench-template-md) or an
[R Markdown lesson
template](https://github.com/carpentries/workbench-template-rmd). In
the R Markdown version the example episode is written in R Markdown
and contains an example of dynamic content generated using R, while
the markdown version contains static content only.

Visit https://github.com/carpentries/workbench-template-md/generate
(markdown) or
https://github.com/carpentries/workbench-template-rmd/generate (R
Markdown) and follow the instructions to generate a lesson repository
from the Carpentries Workbench Template. Checking the 'Include all
branches' option will save some time waiting for the first website
build when your new repository is initialised.

## Clone the lesson repository

Clone the lesson repository to a suitable location on your local computer:

```
cd my-lesson-directory
git clone git@github.com:path/to/my-repo.git
```

## Download and apply the patch file

Download
[fair4rs\_config.patch](https://raw.githubusercontent.com/RSE-Sheffield/fair4rs-lesson-setup/main/fair4rs_config.patch)
by right-clicking and choosing "Save page as...".  Note that on
Windows the file may be saved with the `.txt` file extension, which
means that you'll need to modify the file name in the `git apply`
command below.

Apply the patch file to the lesson repository:

```
cd my-repo
git apply --index path/to/fair4rs_config.patch
```

If the patch does not apply cleanly you may see an error message such as:

```
error: patch failed: config.yaml:17
error: config.yaml: patch does not apply
```

Please let us know by [creating an
issue](https://github.com/RSE-Sheffield/fair4rs-lesson-setup/issues/new)
including details of the error message.

## Rename `.Rproj` file

Rename `FIXME.Rproj` to match your repo name:
```
git mv FIXME.Rproj my-repo.Rproj
```

## Update Metadata

### `config.yaml`

This file contains global parameters for your lesson site. Individual
fields within the file are documented with comments (beginning with
`#`). At a minimum, you should adjust all the fields marked `# FIXME`:

* `title`
* `created`
* `keywords`
* `source`
* `contact`

For the `created` field you can enter the current date but typically you
should adjust this to reflect the date on which you complete preparing
the material.

### `CITATION.cff`

This file contains information about citing this repository. At a
minimum, you should adjust all the fields marked `# FIXME`:

* title
* authors (given name, family name, email, affiliation, orcid)
* repository-code
* url
* abstract
* keywords

### `CONTRIBUTING.md`

Update links to GitHub repository and issues, marked `#FIXME`.

### `LICENSE.md`

Review the licence text and add references/attribution to any derived
material as indicated by the `# FIXME` comment.

### `README.md`

Replace the setup information in your repository's README with
relevant information about your lesson.

## Commit changes to configuration, citation metadata, contributing guide and licence

```
git add -u
git commit -m "Update configuration"
git push
```

## Complete lesson setup

To complete the setup of your lesson, follow the remaining
instructions given in [Configure a new
lesson](https://github.com/carpentries/workbench-template-md#configure-a-new-lesson):

### Activate GitHub Pages for your repository

Navigate to *Settings*, select *Pages* from the left sidebar, and make
sure that the _Source_ is `Deploy from branch` (the default) and
`gh-pages` is selected as the branch to build from. If no
`gh-pages` branch is available, check *Actions* to see if the first
website build workflows are still running. The branch should become
available when those have completed.

Once you've activated GitHub Pages, content pushed to the repository
will be deployed automatically by GitHub Actions. You can view the
lesson website at `https://username.github.io/my-repo/`.

### Add site URL and topic tags to your repository's information

Navigate to the repository landing page and click on the gear
wheel/cog icon at the top-right of the *About* box. Check the "Use
your GitHub Pages website" option, and add some keywords and other
annotations to describe your lesson in the *Topics* field.


## Lesson development

Please refer to the [Introduction to The Carpentries
Workbench](https://carpentries.github.io/sandpaper-docs/) for further
documentation.

## Version information

The lesson setup process has been tested with the following revisions
of the Carpentries Workbench Template:

- [workbench-template-md](https://github.com/carpentries/workbench-template-md): `6c36cf3`
- [workbench-template-rmd](https://github.com/carpentries/workbench-template-rmd): `3f304af`

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

[emacs]: https://www.gnu.org/software/emacs/
[git]: https://git-scm.com
[R]: https://www.r-project.org
[pandoc]: https://pandoc.org
[rmarkdown]: https://pkgs.rstudio.com/rmarkdown/
[rstudio]: https://posit.co/download/rstudio-desktop/#downlod
[sandpaper]: https://github.com/carpentries/sandpaper
[varnish]: https://github.com/carpentries/varnish
[wb]: https://github.com/carpentries/wb
