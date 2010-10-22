(
	patch -p0 <<EOF
--- tsocks
+++ tsocks
@@ -46,14 +46,14 @@ case "\$1" in
 	on)
 		if [ -z "\$LD_PRELOAD" ]
 			then
-				export LD_PRELOAD="/usr/lib/libtsocks.so"
+				export LD_PRELOAD="/lib/libtsocks.so"
 			else
-				echo \$LD_PRELOAD | grep -q "/usr/lib/libtsocks\.so" || \\
-				export LD_PRELOAD="/usr/lib/libtsocks.so \$LD_PRELOAD"
+				echo \$LD_PRELOAD | grep -q "/lib/libtsocks\.so" || \\
+				export LD_PRELOAD="/lib/libtsocks.so \$LD_PRELOAD"
 		fi
 	;;
 	off)
-		export LD_PRELOAD=\`echo -n \$LD_PRELOAD | sed 's/\/usr\/lib\/libtsocks.so \?//'\`
+		export LD_PRELOAD=\`echo -n \$LD_PRELOAD | sed 's/\/lib\/libtsocks.so \?//'\`
 		if [ -z "\$LD_PRELOAD" ]
 			then
 				unset LD_PRELOAD
@@ -68,10 +68,10 @@ case "\$1" in
 	*)
 		if [ -z "\$LD_PRELOAD" ]
 		then
-			export LD_PRELOAD="/usr/lib/libtsocks.so"
+			export LD_PRELOAD="/lib/libtsocks.so"
 		else
-			echo \$LD_PRELOAD | grep -q "/usr/lib/libtsocks\.so" || \\
-			export LD_PRELOAD="/usr/lib/libtsocks.so \$LD_PRELOAD"
+			echo \$LD_PRELOAD | grep -q "/lib/libtsocks\.so" || \\
+			export LD_PRELOAD="/lib/libtsocks.so \$LD_PRELOAD"
 		fi
 
 		if [ \$# = 0 ]

EOF

	default_build
) > $C_FIFO 2>&1
