# $OpenBSD: Makefile,v 1.12 2020/07/26 16:22:06 sthen Exp $

PKG_ARCH=	*

COMMENT=	tool to check the quality of a DNS zone

MODULES=	cpan
CPAN_AUTHOR=	ZNMSTR
V=		2.0.4
DISTNAME=	Zonemaster-CLI-v$V
PKGNAME=	zonemaster-$V
CATEGORIES=	net

MAINTAINER=	Stuart Henderson <stu.ports@spacehopper.org>

# BSD
PERMIT_PACKAGE=	Yes

WANTLIB=	perl

CONFIGURE_STYLE= modinst

BUILD_DEPENDS=	${RUN_DEPENDS}

RUN_DEPENDS=	devel/p5-MooseX-Getopt \
		devel/p5-namespace-autoclean \
		net/p5-Zonemaster/engine>=2.0.0 \
		textproc/p5-Text-Reflow

.include <bsd.port.mk>
