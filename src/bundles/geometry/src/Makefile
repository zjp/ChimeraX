# === UCSF ChimeraX Copyright ===
# Copyright 2016 Regents of the University of California.
# All rights reserved.  This software provided pursuant to a
# license agreement containing restrictions on its disclosure,
# duplication and use.  For details see:
# https://www.rbvi.ucsf.edu/chimerax/docs/licensing.html
# This notice must be embedded in or attached to all copies,
# including partial copies, of the software or any revisions
# or derivations thereof.
# === UCSF ChimeraX Copyright ===

TOP = ../../..
include $(TOP)/mk/config.make

PKG_DIR = $(PYSITEDIR)/chimerax/geometry
APP_PKG_DIR = $(APP_PYSITEDIR)/chimerax/geometry

SUBDIRS	= _geometry

PYSRCS = __init__.py adaptive_tree.py align.py \
	bins.py bounds.py icosahedron.py \
	matrix.py place.py plane.py psession.py \
	sphere.py spline.py symmetry.py vector.py

# All needed subdirectories must be set by now.
include $(TOP)/mk/subdir.make

all: $(PYOBJS)

install: all dir
	$(RSYNC) $(PYSRCS) $(PKG_DIR)
	#if [ -d "$(APP_PKG_DIR)" ]; then $(RSYNC) $(PYSRCS) $(APP_PKG_DIR); fi

dir:
	if [ ! -d "$(PKG_DIR)" ]; then mkdir $(PKG_DIR); fi
	#if [ -d "$(app_prefix)" ]; then mkdir -p $(APP_PKG_DIR); fi

clean:
	rm -rf __pycache__

pylint:
	$(PYLINT) $(PYSRCS)
