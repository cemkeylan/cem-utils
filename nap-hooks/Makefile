install:
	install -Dm755 user-hooks ${DESTDIR}/etc/zzz.d/resume/99-onresume
	install -Dm755 user-hooks ${DESTDIR}/etc/zzz.d/suspend/99-onsuspend

uninstall:
	rm -f ${DESTDIR}/etc/zzz.d/resume/99-onresume \
	${DESTDIR}/etc/zzz.d/suspend/99-onsuspend 
