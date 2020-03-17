PREFIX = /usr/local
BINDIR = ${PREFIX}/bin

install:
	install -Dm755 -t ${DESTDIR}${BINDIR} kf kiss-repooutdated kiss-reporevdepends

uninstall:
	rm -f ${DESTDIR}${BINDIR}/kf
	rm -f ${DESTDIR}${BINDIR}/kiss-repooutdated
	rm -f ${DESTDIR}${BINDIR}/kiss-reporevdepends

.PHONY: install uninstall
