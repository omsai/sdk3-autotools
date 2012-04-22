## Process this file with automake to produce Makefile.in

install-exec-am:
	test -z $(DESTDIR)$(sbindir) || $(mkinstalldirs) $(DESTDIR)$(sbindir)
	$(INSTALL_PROGRAM) update_scmos_firmware.$(VERSION) $(DESTDIR)$(sbindir)

install-data-am:
	test -z $(DESTDIR)$(libdir) || $(mkinstalldirs) $(DESTDIR)$(libdir)
	$(INSTALL_DATA) lib* $(DESTDIR)$(libdir)
