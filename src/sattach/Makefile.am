#

AUTOMAKE_OPTIONS = foreign

AM_CPPFLAGS = -I$(top_srcdir)

bin_PROGRAMS = sattach

sattach_SOURCES = \
	attach.c attach.h \
	opt.c opt.h \
	sattach.c \
	sattach.wrapper.c

convenience_libs = $(LIB_SLURM) $(DL_LIBS)
sattach_DEPENDENCIES = $(LIB_SLURM_BUILD)

sattach_LDADD = \
	$(convenience_libs)

sattach_LDFLAGS = -export-dynamic $(CMD_LDFLAGS)

force:
$(convenience_libs) : force
	@cd `dirname $@` && $(MAKE) `basename $@`
