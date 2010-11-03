(
	default_configure --disable-avahi --disable-lirc
	cat > $SOURCE_DIRECTORY/gmpc-avahi/Makefile <<EOF
all:
	echo OK

install:
	echo OK

EOF
	default_build &&
	prepare_install &&
	make install
) > $C_FIFO 2>&1
