# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line, and also
# from the environment for the first two.
SPHINXOPTS    ?=
SPHINXBUILD   ?= sphinx-build
SOURCEDIR     = source
BUILDDIR      = build

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile

# 原有
html:
	@$(SPHINXBUILD) -b html $(SOURCEDIR) $(BUILDDIR)/html

# 生成pot翻译模板
gettext:
	$(SPHINXBUILD) -b gettext $(SOURCEDIR) $(BUILDDIR)/locale

# 更新中文po文件
update-po: gettext
	sphinx-intl update -p $(BUILDDIR)/locale -l zh‑cn

# 本地编译中文版本
html-zhcn:
	$(SPHINXBUILD) -D language=zh‑cn $(SOURCEDIR) $(BUILDDIR)/html_zhcn

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
