# $OpenBSD: Makefile,v 1.6 2021/02/19 23:13:07 sthen Exp $

COMMENT=		simple WSGI-framework for small web-applications

MODPY_EGG_VERSION=	0.12.16
DISTNAME=		bottle-${MODPY_EGG_VERSION}
PKGNAME=		py-bottle-${MODPY_EGG_VERSION}
REVISION=		1

CATEGORIES=		www

HOMEPAGE=		https://bottlepy.org

# MIT
PERMIT_PACKAGE=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes
MODPY_PYTEST=		Yes

FLAVORS=		python3
FLAVOR ?=

post-install:
	mv ${PREFIX}/bin/bottle{,${MODPY_BIN_SUFFIX}}.py

.include <bsd.port.mk>
