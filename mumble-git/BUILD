(
	qmake CONFIG+=no-server CONFIG+=no-update CONFIG+=no-oss CONFIG+=no-embed-qt-translations\
   		CONFIG+=no-g15 $OPTS\
	   	DEFINES+="PLUGIN_PATH=/usr/lib/mumble/plugins" &&
	make release &&
	prepare_install &&

	install -m644 -d /usr/lib/mumble/plugins &&
	install -m644 -d /usr/share/man/man1 &&
	cd ./release &&
	install -m755 -D mumble /usr/bin/mumble &&
	install -m755 -D mumble11x /usr/bin/mumble11x &&
	install -m755 -D libmumble.* /usr/lib/mumble/ &&
	install -m755 -D plugins/* /usr/lib/mumble/plugins/ &&
	cd ../scripts &&
	install -m755 -D mumble-overlay /usr/bin/mumble-overlay &&
	cd ../man &&
	install -m644 -D mum* /usr/share/man/man1/ &&
	cd ../icons &&
	install -m644 -D mumble.svg /usr/share/icons/hicolor/scalable/apps/mumble.svg &&
	install -m644 -D mumble.xpm /usr/share/pixmaps/mumble.xpm

) > $C_FIFO 2>&1
