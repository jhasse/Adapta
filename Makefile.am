EXTRA_DIST = \
	COPYING \
	gnome-shell \
	gtk-2.0 \
	gtk-3.20 \
	gtk-3.0 \
	index.theme \
	README.md

GTK_NEXT_DIR = gtk-3.22
CINNAMON_DIR = cinnamon
METACITY_DIR = metacity-1
UNITY_DIR    = unity
XFCE_DIR     = xfwm4 \
               xfce-notify-4.0

themedir = $(datadir)/themes

install-data-hook:
	$(MKDIR_P) $(DESTDIR)$(themedir)/Adapta
	cp -Rv $(EXTRA_DIST) $(DESTDIR)$(themedir)/Adapta

if ENABLE_GTK_NEXT
	cp -Rv $(GTK_NEXT_DIR) $(DESTDIR)$(themedir)/Adapta
endif

if ENABLE_CINNAMON
	cp -Rv $(CINNAMON_DIR) $(DESTDIR)$(themedir)/Adapta
if !ENABLE_FLASHBACK
	cp -Rv $(METACITY_DIR) $(DESTDIR)$(themedir)/Adapta
endif
endif

if ENABLE_FLASHBACK
	cp -Rv $(METACITY_DIR) $(DESTDIR)$(themedir)/Adapta
endif

if ENABLE_UNITY
	cp -Rv $(UNITY_DIR) $(DESTDIR)$(themedir)/Adapta
if !ENABLE_FLASHBACK
	cp -Rv $(METACITY_DIR) $(DESTDIR)$(themedir)/Adapta
endif
endif

if ENABLE_XFCE
	cp -Rv $(XFCE_DIR) $(DESTDIR)$(themedir)/Adapta
endif

uninstall-hook:
	test -e $(DESTDIR)$(themedir)/Adapta && \
	rm -rfv $(DESTDIR)$(themedir)/Adapta
