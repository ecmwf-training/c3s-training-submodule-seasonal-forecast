# ECMWF Jupyter based learning resource templates
This repository contains guides to facilitate development and maintenance of ECMWF Jupyter based learning resources. It includes the following templates:

- A template repository, which hosts notebooks, or a collection of similar notebooks
- A template Jupyter notebook based learning resource, such as a tutorial, example workflow, or similar.
- A template Jupyterbook landing page to access and render one or more Jupyter notebooks

## Template repository

This repository is itself a Github template. A new repository can be created from this by simply selecting the green `Use this template` icon on the top right. Create a repository from this template for Jupyter notebooks you plan to develop training purposes at ECMWF.

The default branch for this repository is **develop**, and this branch is used to deploy the review/development version of the JupyterBook. The **main** branch is reserved for published content and will be maintained by ECMWF.

The repository includes github-actions which will automatically build a develop version of the Jupyter Book that can be used for review purposes.

## Template Jupyter notebook

This repository contains a [Jupyter notebook template](https://github.com/ecmwf-training/jupyter-template/blob/develop/jupyter-notebook-template.ipynb), which provides a suggested structure for Jupyter based ECMWF learning resources. It also includes metadata to be applied at the notebook level and at the cell level according to a metadata-schema described here: https://github.com/ecmwf-training/jn-metadata-schema.

### Best practices for Jupyter notebooks

#### Keep notebooks short
Focus on one topic / visualisation / processing routine. Consider separate notebooks if multiple parts or topics are included.

#### Keep headings consistent
- Keep headings in separate cells
- Use # for first level headings, ## for second level, and so on. Do not skip a level (e.g. do not follow a 1st level heading with a third level, without a second level in between).

#### Make use of MyST markdown
Use coloured cells, icons, etc. where needed.

#### Use of images
Any images unique to the Jupyter notebook should be stored in the ./img folder in this repository. Any images needed across multiple notebooks in multiple repositories (such as logolines) should be sourced from an external URL (see for example links to ECMWF and Copernicus logos here https://climate.copernicus.eu/branding-guidelines#Logolines). Images not already online can be uploaded to a dedicated repository for training hosted at https://sites.ecmwf.int/training/ (please contact chris.stewart@ecmwf.int).

### Use of data
Data files should not be stored in the Github repository, but hosted externally and linked to, or downloaded from original source (e.g. CDS/ADS).


## Jupyterbook Build instructions

Notebook providers are responsible for ensuring that the github actions succesfully build and deploy the
JupyterBook. It is advisable to test run the build commands and inspect the output locally before pushing
to the repository as this will save you time and effort.

### Building the JupyterBook locally

The following instructions are for Linux and MacOS users.

It is recommended that you test the build locally prior to creating your pull request to develop,
this will address many of the minor issues you may face and provide you with more readable output.
To ensure that you have the same software installed required to build the JupyterBook,
and that you are not using any unsupported software packages during a local build, it is recommended
that you create an conda-forge environment for building Jupyter Books:

```
conda create -y -n JUPYTER-BUILD -c conda-forge python=3.12
conda activate JUPYTER-BUILD
pip install jupyter-book
```

With your JUPYTER-BUILD environment activated the following line will build the jupyterbook locally:

```
rm -rf _build
jupyter-book build --all .
```

This will create all the html files used to create the JupyterBook in the untracked `_build/` folder.
You can open the homepage of this local build with:

```
open _build/html/index.html
```


### GitHub actions

There are two github actions in place for this repository:

The **`Build`** action builds the JupyterBook using the same proceedure as local build described below.
It is activated when a pull request to the `develop` branch is opened, or when any change is made to the 
develop branch (e.g. after merging a pull request). A pull request can only be merged
into the develop branch if the `Build` action is successful.


The **`Deploy`** action deploys the build JupyterBook to the github pages associated with this repository.
This action is activated when a change is made to the develop branch, after the build action.


## Troubleshooting notes

1. Multiple Level 1 Headers (#) in a notebook seems to break the _toc definition of title. It is also bad practice so discourage.
2. JupyterBooks do not have a running python kernel, threrefore they are not compatible with interactive widgets which require a running kernel, e.g. a number of ipywidgets, as documented here: https://jupyterbook.org/en/stable/interactive/interactive.html?highlight=widgets#ipywidgets
3. Any additional images included in the notebook should be added using markdown hyperlink syntax, html syntax does not work with our jupyter-books. e.g.: `![](.images.png)`
4. Please avoid using placeholder hyperlinks using (the HTML <a> tag without a href provided) and within notebook cross-references (links between sections of the notebook). Due to platform differences they are not rendered correctly on JupyterBook pages and causes many compilation warnings and errors. This means it is much harder for us to identify real issues in the notebook, slowing down the integration process.
5. Please refrain from using HTML tags in general as they often intefere with the HTML config that JupyterBook builds and do not necessarily produce the intended effect when deployed in different environments. Markdown should offer all the text formatting required for the purposes of these traning notebooks.