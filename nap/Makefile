PREFIX=/usr/local
BINDIR=${PREFIX}/bin
ETCDIR=/etc

install:
	mkdir -p ${DESTDIR}${ETCDIR}/zzz.d/suspend
	mkdir -p ${DESTDIR}${ETCDIR}/zzz.d/resume
	install -Dm755 nap ${DESTDIR}${BINDIR}/nap

uninstall:
	rm -f ${DESTDIR}${BINDIR}/nap
	@echo not removing /etc/zzz.d, you can remove \
		it manually

.PHONY: install uninstall
