PREFIX = /usr/local
BINDIR = ${PREFIX}/bin

install:
	install -Dm755 -t ${DESTDIR}${BINDIR} kf kiss-repooutdated

uninstall:
	rm -f ${DESTDIR}${BINDIR}/kf
	rm -f ${DESTDIR}${BINDIR}/kiss-repooutdated

.PHONY: install uninstall
