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
	patch -p0 <<EOF
--- kernel/conn.c
+++ kernel/conn.c
@@ -13,6 +13,19 @@
 #include "iscsi_dbg.h"
 #include "digest.h"
 
+#ifndef NIPQUAD
+# define NIPQUAD(addr) \\
+	((unsigned char *)&addr)[0], \\
+	((unsigned char *)&addr)[1], \\
+	((unsigned char *)&addr)[2], \\
+	((unsigned char *)&addr)[3]
+#endif
+#ifndef NIPQUAD_FMT
+# define NIPQUAD_FMT "%u.%u.%u.%u"
+#endif
+
+
+
 static void print_conn_state(char *p, size_t size, unsigned long state)
 {
 	if (test_bit(CONN_ACTIVE, &state))

EOF
	
	make KSRC=/usr/src/linux kernel usr &&
	make KSRC=/usr/src/linux &&
	prepare_install &&
	make KSRC=/usr/src/linux install-kernel &&
	make KSRC=/usr/src/linux install-etc &&
	make KSRC=/usr/src/linux install-usr &&
	make KSRC=/usr/src/linux install-man
) > $C_FIFO 2>&1
