(
	patch -p0 <<EOF
--- usr/iscsi_sysfs.c
+++ usr/iscsi_sysfs.c
@@ -1176,6 +1176,7 @@ char *iscsi_sysfs_get_iscsi_kernel_version(void)
 
 int iscsi_sysfs_check_class_version(void)
 {
+#if 0
 	char *version;
 	int i;
 
@@ -1209,4 +1210,6 @@ fail:
 		"date version of iscsid is running. Exiting...",
 		ISCSI_VERSION_FILE);
 	return -1;
+#endif
+	return 0;
 }
EOF

	make KSRC=/usr/src/linux user &&
	prepare_install       &&
	make install_user
) > $C_FIFO 2>&1

