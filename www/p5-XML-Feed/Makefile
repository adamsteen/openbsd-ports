# $OpenBSD: Makefile,v 1.11 2020/07/03 21:46:07 sthen Exp $

COMMENT= 	interface to RSS and Atom feeds

MODULES=	cpan
PKG_ARCH=	*

DISTNAME=	XML-Feed-0.55
CATEGORIES=	www textproc
CONFIGURE_STYLE=modbuild
REVISION=	0

#perl
PERMIT_PACKAGE=	Yes

BUILD_DEPENDS=	www/p5-HTML-Parser \
		www/p5-libwww

RUN_DEPENDS=	devel/p5-Class-ErrorHandler \
		textproc/p5-XML-RSS \
		devel/p5-DateTime \
		devel/p5-DateTime-Format-Mail \
		devel/p5-DateTime-Format-W3CDTF \
		devel/p5-Module-Pluggable \
		www/p5-URI-Fetch \
		www/p5-Feed-Find \
		www/p5-XML-Atom

.include <bsd.port.mk>
