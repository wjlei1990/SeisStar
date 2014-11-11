---
layout: docs
title: Contributing 
permalink: /docs/contributing/
---

# Contributing

__Seis*__ will welcome contribution from the outside world once in a decent shape.

For those who are lucky enough to serve as benevolent guinea pigs, this page provides a few instructions.


### Getting the sources

The sources are available from [Seis* GitHub repository](https://github.com/SeisStar/SeisStar).

You will need to fork the main repository, and to clone your fork:

```
$> git clone https://github.com/<username>/SeisStar
```


### Adding and modifiying content

#### Modifying an exisiting page

Under ```_docs/```, open the Markdown (```.md```) file you want to modify.
If you need some insights on the Markdown format, you can take a look at the following resources:

* [Markdown Basics](https://help.github.com/articles/markdown-basics/)
* [GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/)

Think twice before modifying the file header (the first lines of the file between the two ```---``` lines) as it is used by Jekyll to render the Markdown page as an html page.

#### Advanced editing

If you are not satisfied with the feature of Markdown, it is possible to add html code inside the ```.md``` files. You can use [Bootstrap](http://getbootstrap.com/) to style your html code. In particular it provides quite a few [components](http://getbootstrap.com/components/).

#### Adding a new page

You will need to create a new Markdown file under ```_doc/```, call it something like ```<myfile>.md```.

The first lines of ```<myfile>.md``` should looks like:

```yaml
---
layout: docs
title: <My Short Title>
permalink: /docs/<mycontribution>/
---
```

* Opening and closing ```---``` are mandatory, they define where the YAML header starts and ends.
* ```layout: docs``` should usually take this precise form. It specifies how this particular page will be rendered
* ```title: <My Short Title>```, replace ```<My Short Title>``` by a title short enough to look good when displayed in the menu on the right of the screen.
* ```permalink: /docs/<mycontribution>/``` tells you what will be the location of the page you just created. You will need to think of something meaningful to replace ```<mycontribution>```.
* For more header variables, you can read Jekyll doc about the so called [Front Matter](http://jekyllrb.com/docs/frontmatter/).

After creating your new Markdown page, you will need to register it. Open ```_data/docs.yml```. Various sections are defined as ```- title: <Some Title>```.

* If you are happy with the section already present, you will just need to add ```- <mycontribution>``` (from the front matter permalink variable) under (the associative arrays of lists) ```docs:``` from the relevant section.
* If your new page does not fit into the current categories, you can add a new section:

```yaml
- title: <Short Section Title> 
  docs:
  - <mycontribution>
```

### Updating the main repository

#### Testing your changes locally

To make sure your changes are displayed the way you like, you can run Jekyll locally. Instructions are given on [this page](https://help.github.com/articles/using-jekyll-with-pages/), mostly in the `Installing Jekyll` and `Running Jekyll` sections.

#### Sending your change to the main repository

The following lines are extracted from the procedure we described in greater details in [SPECFEM3D wiki](https://github.com/geodynamics/specfem3d/wiki/Advanced-Topics#configure-remotes-connecting-to-the-original-repository), and are only useful if you are new to git.

* Configure remotes connecting to the original repository
    - ```$> git remote add upstream https://github.com/SeisStar/SeisStar```
* Fetch the changes
    - ```$> git fetch upstream```
* See what has changed
    - $ git diff origin 
* Merge the potential changes
    - git merge upstream
* Push your development to your forked GitHub repository
    - git push
* Make a pull request from your forked GitHub repository page
    - Go to your forked repository
    - Click "Pull Request"
    - Follow GitHub instructions and wait...
  
