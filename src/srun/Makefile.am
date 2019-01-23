#

SUBDIRS = libsrun

AUTOMAKE_OPTIONS = foreign
CLEANFILES = core.*

AM_CPPFLAGS = -I$(top_srcdir) -I$(top_srcdir)/src/srun/libsrun

bin_PROGRAMS = srun

depend_libs = $(top_builddir)/src/srun/libsrun/libsrun.la \
	$(top_builddir)/src/bcast/libfile_bcast.la


srun_SOURCES = \
	srun.c \
	srun_pty.c srun_pty.h \
	srun.wrapper.c
srun_LDADD = $(depend_libs) $(DL_LIBS) $(LIB_SLURM)

srun_DEPENDENCIES = $(depend_libs) $(LIB_SLURM_BUILD)

srun_LDFLAGS = -export-dynamic $(CMD_LDFLAGS)

force:
$(srun_DEPENDENCIES) : force
	@cd `dirname $@` && $(MAKE) `basename $@`
