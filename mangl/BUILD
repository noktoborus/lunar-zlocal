(
	cd xc/doc/man/GL/
	for dir in * ; do cd $dir && xmkmf && make && cd - ; done
	prepare_install &&
	for dir in * ; do cd $dir && make install && cd - ; done
	
) > $C_FIFO 2>&1
