# git Talk. Improve your git skills

To see the slides of the 1st and 2nd part of the git talk,
just open `index.html` file from a browser.

### Requirements
Internet connection to run the slides framework.

#### git-like graphs

The git-like graphs of the q&a section were created with [Graphviz](http://www.graphviz.org)

If you want to modify them or to create new ones, you can do it with:
```
sudo add-apt-repository ppa:gviz-adm/graphviz-dev;
sudo apt-get update;
sudo apt-get install graphviz;
# and then...
dot -Tpng source.txt -o image.png
```

A more complex alternative could be to use [Gitgraph.js](http://gitgraphjs.com)