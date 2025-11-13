BUILT_SOURCES = do_subst

RMS_SYSCONFDIR = $(sysconfdir)/@PACKAGE@

crondir = $(sysconfdir)/cron.d
cron_SCRIPTS = \
	rmsgw

#This will replace variables in the .in files when make processes them
edit = sed \
	-e 's|@bindir[@]|$(bindir)|g' \
	-e 's|@rmssysconfdir[@]|$(RMS_SYSCONFDIR)|g'

do_subst:
	@list='$(cron_SCRIPTS)'; for p in $$list; do \
	$(edit) $(srcdir)/$$p.in >$$p; \
	done

CLEANFILES = $(cron_SCRIPTS)

EXTRA_DIST = \
	rmsgw.in

