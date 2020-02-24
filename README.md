# pythondata
1# Python Data

from google.colab import drive
drive.mount("/content/drive")


2# Tools 


## Building the Website

Clone the repository & make sure submodules are included

```
$ git clone https://github.com/jakevdp/PythonDataScienceHandbook.git
$ git checkout origin/website
$ git submodule update --init --recursive
$ cd website
```

Install the required packages:

```
$ conda create -n pelican-blog python=3.5 jupyter notebook
$ source activate pelican-blog
$ pip install pelican Markdown ghp-import
$ mkdir plugins
$ git submodule add git://github.com/danielfrg/pelican-ipynb.git plugins/ipynb
$ git submodule add https://github.com/getpelican/pelican-plugins.git plugins/pelican-plugins
```

Copy the notebook content to the right location (this script also modifies some links for the HTML):
```
$ python copy_notebooks.py
```

Build the html and serve locally:

```
$ make html
$ make serve
$ open http://localhost:8000
```

Deploy to github pages

```
$ make publish-to-github
```

