# $OpenBSD: Makefile,v 1.7 2021/02/28 13:46:59 sthen Exp $

COMMENT=	inline and side-by-side colored and incremental diff

# was renamed cdiff->ydiff
MODPY_EGG_VERSION=	1.2
DISTNAME=	ydiff-${MODPY_EGG_VERSION}

CATEGORIES=	textproc

HOMEPAGE=	https://github.com/ymattw/ydiff

# BSD
PERMIT_PACKAGE=	Yes

MODULES=	lang/python

MODPY_PI=	Yes

TEST_DEPENDS=	devel/git \
		devel/py-codestyle${MODPY_FLAVOR} \
		devel/py-coverage${MODPY_FLAVOR} \
		shells/bash \
		textproc/py-docutils${MODPY_FLAVOR}

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/ydiff
	${INSTALL_DATA} ${WRKSRC}/README.rst ${PREFIX}/share/doc/ydiff/

pre-test:
	ln -sf ${MODPY_BIN} ${WRKDIR}/bin/python
	ln -sf ${LOCALBASE}/bin/rst2html ${WRKDIR}/bin/rst2html.py
	ln -sf ${LOCALBASE}/bin/pycodestyle ${WRKDIR}/bin/pep8
	ln -sf ${LOCALBASE}/bin/coverage-${MODPY_VERSION} ${WRKDIR}/bin/coverage

.include <bsd.port.mk>
