# $OpenBSD: Makefile,v 1.8 2021/02/16 23:02:07 sthen Exp $

COMMENT =		versioning library for Python projects

MODPY_EGG_VERSION =	17.5.0

DISTNAME =		incremental-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
REVISION =		2

CATEGORIES =		devel

# MIT
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes
MODPY_PYTEST =		Yes
MODPY_PYTEST_ARGS =	src/incremental

TEST_DEPENDS =		devel/py-click${MODPY_FLAVOR} \
			devel/py-twisted${MODPY_FLAVOR}

FLAVORS =		python3
FLAVOR =		python3

.include <bsd.port.mk>
