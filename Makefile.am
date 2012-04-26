## Process this file with automake to produce Makefile.in

SUBDIRS = $(HOST_ARCH) #bitflow
DIST_SUBDIRS = x86 x86_64 #bitflow

include_HEADERS = inc/atcore.h

sysconf_DATA = etc/andor_sdk.conf

if USB_UDEV
udevrulesdir = $(libdir)/udev/rules.d
udevrules_SCRIPTS = etc/andor.rules
endif

if USB_HOTPLUG
hotplugdir = $(sysconfdir)/hotplug/usb
hotplug_SCRIPTS = etc/andor.usermap etc/andor
endif

ANDOR_DOCFILES=doc/Andor\ Software\ Development\ Kit\ 3.pdf

## Always install documentation
install-data-hook: $(ANDOR_DOCFILES)
	test -z $(DESTDIR)$(docdir) || $(mkinstalldirs) $(DESTDIR)$(docdir)
	$(INSTALL_DATA) $(ANDOR_DOCFILES) $(DESTDIR)$(docdir)/
