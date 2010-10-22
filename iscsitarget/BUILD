(
	patch -p0 <<EOF
--- Makefile
+++ Makefile
@@ -238,7 +238,7 @@ install-usr: usr/ietd usr/ietadm
 	@install -vD usr/ietd \$(DESTDIR)/usr/sbin/ietd
 	@install -vD usr/ietadm \$(DESTDIR)/usr/sbin/ietadm
 
-install-etc: install-initd
+install-etc:
 	@if [ ! -e \$(DESTDIR)/etc/ietd.conf ]; then \\
 		if [ ! -e \$(DESTDIR)/etc/iet/ietd.conf ]; then \\
 			install -vD -m 640 etc/ietd.conf \\

EOF
	
	echo "EOF"
	make KSRC=/usr/src/linux kernel usr &&
	make KSRC=/usr/src/linux &&
	echo "PATCH"
	prepare_install &&
	make KSRC=/usr/src/linux install-kernel &&
	make KSRC=/usr/src/linux install-etc &&
	make KSRC=/usr/src/linux install-usr &&
	make KSRC=/usr/src/linux install-man
) > $C_FIFO 2>&1
