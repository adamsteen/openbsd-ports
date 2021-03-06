# $OpenBSD: Makefile,v 1.130 2021/01/11 00:49:44 kmos Exp $

COMMENT=		Unicode character map for the GNOME project

GNOME_PROJECT=		gucharmap
GNOME_VERSION=		13.0.4
REVISION=		0

SHARED_LIBS +=  gucharmap_2_90            7.0 # 7.0

# GPLv3+
PERMIT_PACKAGE=		Yes

WANTLIB += atk-1.0 c cairo gdk-3 gio-2.0 glib-2.0 gobject-2.0
WANTLIB += gtk-3 intl pango-1.0 pangocairo-1.0

MASTER_SITES =		https://gitlab.gnome.org/GNOME/gucharmap/-/archive/${GNOME_VERSION}/
EXTRACT_SUFX =		.tar.bz2

# C11
COMPILER=		base-clang ports-gcc
COMPILER_LANGS=		c

MODULES=		devel/dconf \
			devel/meson \
			x11/gnome

MODGNOME_TOOLS=		desktop-file-utils gobject-introspection vala yelp

BUILD_DEPENDS=		archivers/unzip \
			devel/gsettings-desktop-schemas \
			textproc/gtk-doc \
			textproc/unicode-ucd>=9.0.0

RUN_DEPENDS =		devel/gsettings-desktop-schemas

LIB_DEPENDS=		x11/gtk+3,-main

CONFIGURE_ARGS +=	-Ducd_path=${LOCALBASE}/share/unicode/ucd/

.include <bsd.port.arch.mk>
.if !${PROPERTIES:Mlld}
# ERROR: Assert failed: -Wl,-Bsymbolic-functions is required but not supported
CONFIGURE_ARGS +=	-Dsymbolic_functions=false
.endif

.include <bsd.port.mk>
