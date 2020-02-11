PREFIX = /usr/local
BINDIR = ${PREFIX}/bin

install:
	install -Dm755 -t ${DESTDIR}${BINDIR} notify-send kill-notification

uninstall:
	rm -f ${DESTDIR}${BINDIR}/notify-send \
		${DESTDIR}${BINDIR}/kill-notification
