(
	[ $NEED_CPP == "y" ] && (cd cpp && make)
	[ $NEED_PHP == "y" ] && (cd php && make)
	prepare_install
	[ $NEED_CPP == "y" ] && (cd cpp && make prefix=/usr install)
	[ $NEED_PHP == "y" ] && (cd php && make prefix=/usr install)
) > $C_FIFO 2>&1 
