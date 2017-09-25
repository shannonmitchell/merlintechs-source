# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line.
SPHINXOPTS    =
SPHINXBUILD   = python -msphinx
SPHINXPROJ    = MerlinTechs
SOURCEDIR     = .
BUILDDIR      = _build
PUBLISH_REPO  = ../../shannonmitchell.github.io

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

allthethings: html
	rm -rf $(PUBLISH_REPO)/*; mv $(BUILDDIR)/html/* $(PUBLISH_REPO)/; cd $(PUBLISH_REPO); touch $(PUBLISH_REPO)/.nojekyll; touch $(PUBLISH_REPO)/_static/.nojekyll; git add .; git commit -a -m "rebuild docs"; git push --force origin master
