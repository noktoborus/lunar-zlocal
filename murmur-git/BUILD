(
        qmake CONFIG+=no-client $OPTS &&
        make release &&
        prepare_install &&
        install -m755 -D release/murmurd /usr/sbin/murmurd &&
        install -m644 -D man/mur* /usr/share/man/man1 &&
        install -m755 -D scripts/murmur-user-wrapper /usr/sbin/murmur-user-wrapper &&
        install -m644 -D scripts/murmur.ini /etc/murmur.ini &&
        install -m644 -D scripts/murmur.conf /etc/dbus-1/system.d

) > $C_FIFO 2>&1
