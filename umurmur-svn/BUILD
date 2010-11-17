(
	cd src && make EXTRA_LDFLAGS=-lssl &&
	prepare_install
	install -m755 -D umurmurd /usr/sbin/umurmurd
	cd ..
	install -m700 -d /etc/umurmur
	install -m600 -D umurmur.conf.example /etc/umurmur/umurmur.conf

) > $C_FIFO 2>&1
