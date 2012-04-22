## Process this file with automake to produce Makefile.in

install-exec-am:
	test -z $(DESTDIR)$(sbindir) || $(mkinstalldirs) $(DESTDIR)$(sbindir)
	cp -p update_scmos_firmware.$(VERSION) $(DESTDIR)$(sbindir)

	test -z $(DESTDIR)$(libdir) || $(mkinstalldirs) $(DESTDIR)$(libdir)
	cp -p lib* $(DESTDIR)$(libdir)
