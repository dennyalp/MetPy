# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line.
SPHINXOPTS    =
SPHINXBUILD   = sphinx-build
SPHINXPROJ    = MetPy
SOURCEDIR     = .
BUILDDIR      = build

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

# Sphinx doesn't know to clean out the debris from sphinx-gallery
cleanall: clean
	rm -rf $(SOURCEDIR)/examples $(SOURCEDIR)/tutorials $(SOURCEDIR)/api/generated

clean:
	rm -rf $(BUILDDIR)/*

# Check that all functions in modules with template overrides are present in the doc file
overridecheck:
	python override_check.py

.PHONY: help Makefile

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
# Manual autogen needed so we can specify the -i option so that imported names
# are included in generation
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
